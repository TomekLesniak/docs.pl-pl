---
title: Ograniczenia deklaratywne
ms.date: 03/30/2017
ms.assetid: 67001ed1-7f4d-4ada-ae57-a31176901a53
ms.openlocfilehash: 9098a3d79337689fef6d37e4cccf3633d8128a10
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236458"
---
# <a name="declarative-constraints"></a>Ograniczenia deklaratywne

Ograniczenia deklaracyjne zapewniają zaawansowaną metodę weryfikacji dla działania i jego relacji z innymi działaniami. Ograniczenia są konfigurowane dla działania podczas procesu tworzenia, ale można także określić dodatkowe ograniczenia przez hosta przepływu pracy. Ten temat zawiera omówienie użycia ograniczeń deklaratywnych w celu zapewnienia weryfikacji aktywności.  
  
## <a name="using-declarative-constraints"></a>Używanie ograniczeń deklaratywnych  

 Ograniczenie to działanie, które zawiera logikę walidacji. To działanie ograniczenia można utworzyć w kodzie lub w języku XAML. Po utworzeniu działania ograniczenia autorzy działań dodają to ograniczenie do <xref:System.Activities.Activity.Constraints%2A> właściwości działania do zweryfikowania, lub używają ograniczenia, aby zapewnić dodatkową weryfikację przy użyciu <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> właściwości <xref:System.Activities.Validation.ValidationSettings> wystąpienia. Logika walidacji może składać się z prostych poprawń, takich jak Walidacja metadanych działania, ale może również przeprowadzać walidację, która uwzględnia relacje bieżącego działania ze swoimi działaniami nadrzędnymi, podrzędnymi i równorzędnymi. Ograniczenia są tworzone przy użyciu <xref:System.Activities.Validation.Constraint%601> działania oraz kilka dodatkowych działań weryfikacyjnych, które ułatwiają tworzenie błędów i ostrzeżeń walidacji oraz dostarczanie informacji o działaniach związanych z przepływem pracy.  
  
### <a name="assertvalidation-and-addvalidationerror"></a>AssertValidation i AddValidationError  

 <xref:System.Activities.Validation.AssertValidation>Działanie oblicza wyrażenie odwołujące się do jego <xref:System.Activities.Validation.AssertValidation.Assertion%2A> właściwości, a jeśli wyrażenie zwróci wartość, do `false` elementu zostanie dodany błąd walidacji lub ostrzeżenie <xref:System.Activities.Validation.ValidationResults> . <xref:System.Activities.Validation.AssertValidation.Message%2A>Właściwość opisuje błąd walidacji, a <xref:System.Activities.Validation.AssertValidation.IsWarning%2A> Właściwość wskazuje, czy błąd walidacji jest błąd lub ostrzeżenie. Wartość domyślna <xref:System.Activities.Validation.AssertValidation.IsWarning%2A> to `false` .  
  
 W poniższym przykładzie jest zadeklarowane ograniczenie, które zwraca ostrzeżenie o walidacji, jeśli <xref:System.Activities.Activity.DisplayName%2A> zweryfikowane działanie ma dwa znaki lub mniej. Parametr typu ogólnego używany do <xref:System.Activities.Validation.Constraint%601> określania typu działania, które jest sprawdzane przez ograniczenie. To ograniczenie służy <xref:System.Activities.Activity> jako typ ogólny i może służyć do walidacji wszystkich typów działań.  
  
```csharp  
public static Constraint ActivityDisplayNameIsNotSetWarning()  
{  
    DelegateInArgument<Activity> element = new DelegateInArgument<Activity>();  
  
    return new Constraint<Activity>  
    {  
        Body = new ActivityAction<Activity, ValidationContext>  
        {  
            Argument1 = element,  
            Handler = new AssertValidation  
            {  
                IsWarning = true,  
                Assertion = new InArgument<bool>(env => (element.Get(env).DisplayName.Length > 2)),  
                Message = new InArgument<string>("It is a best practice to have a DisplayName of more than 2 characters."),  
            }  
        }  
    };  
}  
```  
  
 Aby określić to ograniczenie dla działania, jest ono dodawane do <xref:System.Activities.Activity.Constraints%2A> działania, jak pokazano w poniższym przykładowym kodzie.  
  
```csharp  
public sealed class SampleActivity : CodeActivity  
{  
    public SampleActivity()  
    {  
        base.Constraints.Add(ActivityDisplayNameIsNotSetWarning());  
    }  
  
    // Activity implementation omitted.  
}  
```  
  
 Host może także określić to ograniczenie dla działań w przepływie pracy przy użyciu <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> , który jest objęty w następnej sekcji.  
  
 To <xref:System.Activities.Validation.AddValidationError> działanie służy do generowania błędu lub ostrzeżenia walidacji, bez konieczności obliczania wyrażenia. Jego właściwości są podobne do <xref:System.Activities.Validation.AssertValidation> i mogą być używane w połączeniu z działaniami sterowania przepływem ograniczenia, takiego jak <xref:System.Activities.Statements.If> działanie.
  
### <a name="workflow-relationship-activities"></a>Działania relacji przepływu pracy

Dostępne są kilka działań weryfikacji, które zapewniają informacje o innych działaniach w przepływie pracy w odniesieniu do zweryfikowanego działania. <xref:System.Activities.Validation.GetParentChain> Zwraca kolekcję działań, które zawierają wszystkie działania między bieżącym działaniem a głównym działaniem. <xref:System.Activities.Validation.GetChildSubtree> zawiera kolekcję działań, które zawierają działania podrzędne w cyklicznym wzorcu i <xref:System.Activities.Validation.GetWorkflowTree> Pobiera wszystkie działania w przepływie pracy.  
  
W poniższym przykładzie `CreateState` zdefiniowano działanie. `CreateState`Działanie musi być zawarte w `CreateCountry` działaniu, a `GetParent` Metoda zwraca ograniczenie, które wymusza to wymaganie. `GetParent` używa <xref:System.Activities.Validation.GetParentChain> działania w połączeniu z <xref:System.Activities.Statements.ForEach%601> działaniem, aby zbadać działania nadrzędne działania w `CreateState` celu ustalenia, czy wymaganie jest spełnione.  
  
```csharp  
public sealed class CreateState : CodeActivity  
{  
    public CreateState()  
    {  
        base.Constraints.Add(CheckParent());  
        this.Cities = new List<Activity>();
    }  
  
    public List<Activity> Cities { get; set; }  
  
    public string Name { get; set; }
  
    static Constraint CheckParent()  
    {  
        DelegateInArgument<CreateState> element = new DelegateInArgument<CreateState>();  
        DelegateInArgument<ValidationContext> context = new DelegateInArgument<ValidationContext>();
        Variable<bool> result = new Variable<bool>();  
        DelegateInArgument<Activity> parent = new DelegateInArgument<Activity>();  
  
        return new Constraint<CreateState>  
        {
            Body = new ActivityAction<CreateState,ValidationContext>  
            {
                Argument1 = element,  
                Argument2 = context,  
                Handler = new Sequence  
                {  
                    Variables =  
                    {  
                        result
                    },  
                    Activities =  
                    {  
                        new ForEach<Activity>  
                        {
                            Values = new GetParentChain  
                            {  
                                ValidationContext = context
                            },  
                            Body = new ActivityAction<Activity>  
                            {
                                Argument = parent,
                                Handler = new If()  
                                {
                                    Condition = new InArgument<bool>((env) => object.Equals(parent.Get(env).GetType(),typeof(CreateCountry))),
                                    Then = new Assign<bool>  
                                    {  
                                        Value = true,  
                                        To = result  
                                    }  
                                }  
                            }
                        },  
                        new AssertValidation  
                        {  
                            Assertion = new InArgument<bool>(result),  
                            Message = new InArgument<string> ("CreateState has to be inside a CreateCountry activity"),
                        }  
                    }  
                }  
            }  
        };  
    }  
  
    protected override void Execute(CodeActivityContext context)  
    {  
        // not needed for the sample  
    }  
}  
```
  
## <a name="additional-constraints"></a>Dodatkowe ograniczenia  

 Autorzy hosta przepływu pracy mogą określić dodatkowe ograniczenia sprawdzania poprawności działań w przepływie pracy, tworząc ograniczenia i dodając je do <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> słownika <xref:System.Activities.Validation.ValidationSettings> wystąpienia. Każdy element w <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> zawiera typ działania, dla którego stosowane są ograniczenia oraz listę dodatkowych ograniczeń dla tego typu działania. Po wywołaniu walidacji dla przepływu pracy każde działanie określonego typu, w tym klasy pochodne, szacuje ograniczenia. W tym przykładzie `ActivityDisplayNameIsNotSetWarning` ograniczenie z poprzedniej sekcji jest stosowane do wszystkich działań w przepływie pracy.  
  
```csharp  
Activity wf = new Sequence  
{  
    // Workflow Details Omitted.  
};  
  
ValidationSettings settings = new ValidationSettings()  
{  
  
    AdditionalConstraints =  
    {  
        {typeof(Activity), new List<Constraint> {ActivityDisplayNameIsNotSetWarning()}},
    }  
};  
  
// Validate the workflow.  
ValidationResults results = ActivityValidationServices.Validate(wf, settings);  
  
// Evaluate the results.  
if (results.Errors.Count == 0 && results.Warnings.Count == 0)  
{  
    Console.WriteLine("No warnings or errors");  
}  
else  
{  
    foreach (ValidationError error in results.Errors)  
    {  
        Console.WriteLine("Error in " + error.Source.DisplayName + ": " + error.Message);  
    }  
    foreach (ValidationError warning in results.Warnings)  
    {  
        Console.WriteLine("Warning in " + warning.Source.DisplayName + ": " + warning.Message);  
    }  
}  
```  
  
 Jeśli <xref:System.Activities.Validation.ValidationSettings.OnlyUseAdditionalConstraints%2A> Właściwość <xref:System.Activities.Validation.ValidationSettings> ma wartość `true` , tylko określone dodatkowe ograniczenia są oceniane, gdy Walidacja jest wywoływana przez wywołanie <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> . Może to być przydatne do sprawdzania przepływów pracy pod kątem określonych konfiguracji sprawdzania poprawności. Należy jednak pamiętać, że gdy przepływ pracy zostanie wywołany, logika walidacji skonfigurowana w przepływie pracy jest szacowana i musi zostać pomyślnie zakończona, aby można było rozpocząć przepływ pracy. Aby uzyskać więcej informacji na temat wywoływania walidacji, zobacz [wywoływanie walidacji działania](invoking-activity-validation.md).
