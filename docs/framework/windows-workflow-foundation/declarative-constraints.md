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
# <a name="declarative-constraints"></a><span data-ttu-id="93ec8-102">Ograniczenia deklaratywne</span><span class="sxs-lookup"><span data-stu-id="93ec8-102">Declarative Constraints</span></span>

<span data-ttu-id="93ec8-103">Ograniczenia deklaracyjne zapewniają zaawansowaną metodę weryfikacji dla działania i jego relacji z innymi działaniami.</span><span class="sxs-lookup"><span data-stu-id="93ec8-103">Declarative constraints provide a powerful method of validation for an activity and its relationships with other activities.</span></span> <span data-ttu-id="93ec8-104">Ograniczenia są konfigurowane dla działania podczas procesu tworzenia, ale można także określić dodatkowe ograniczenia przez hosta przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="93ec8-104">Constraints are configured for an activity during the authoring process, but additional constraints can also be specified by the workflow host.</span></span> <span data-ttu-id="93ec8-105">Ten temat zawiera omówienie użycia ograniczeń deklaratywnych w celu zapewnienia weryfikacji aktywności.</span><span class="sxs-lookup"><span data-stu-id="93ec8-105">This topic provides an overview of using declarative constraints to provide activity validation.</span></span>  
  
## <a name="using-declarative-constraints"></a><span data-ttu-id="93ec8-106">Używanie ograniczeń deklaratywnych</span><span class="sxs-lookup"><span data-stu-id="93ec8-106">Using Declarative Constraints</span></span>  

 <span data-ttu-id="93ec8-107">Ograniczenie to działanie, które zawiera logikę walidacji.</span><span class="sxs-lookup"><span data-stu-id="93ec8-107">A constraint is an activity that contains validation logic.</span></span> <span data-ttu-id="93ec8-108">To działanie ograniczenia można utworzyć w kodzie lub w języku XAML.</span><span class="sxs-lookup"><span data-stu-id="93ec8-108">This constraint activity can be authored in code or in XAML.</span></span> <span data-ttu-id="93ec8-109">Po utworzeniu działania ograniczenia autorzy działań dodają to ograniczenie do <xref:System.Activities.Activity.Constraints%2A> właściwości działania do zweryfikowania, lub używają ograniczenia, aby zapewnić dodatkową weryfikację przy użyciu <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> właściwości <xref:System.Activities.Validation.ValidationSettings> wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="93ec8-109">After a constraint activity is created, activity authors add this constraint to the <xref:System.Activities.Activity.Constraints%2A> property of the activity to validate, or they use the constraint to provide additional validation by using the <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> property of a <xref:System.Activities.Validation.ValidationSettings> instance.</span></span> <span data-ttu-id="93ec8-110">Logika walidacji może składać się z prostych poprawń, takich jak Walidacja metadanych działania, ale może również przeprowadzać walidację, która uwzględnia relacje bieżącego działania ze swoimi działaniami nadrzędnymi, podrzędnymi i równorzędnymi.</span><span class="sxs-lookup"><span data-stu-id="93ec8-110">The validation logic can consist of simple validations such as validating an activity’s metadata, but it can also perform validation that takes into account the relationship of the current activity to its parent, children, and sibling activities.</span></span> <span data-ttu-id="93ec8-111">Ograniczenia są tworzone przy użyciu <xref:System.Activities.Validation.Constraint%601> działania oraz kilka dodatkowych działań weryfikacyjnych, które ułatwiają tworzenie błędów i ostrzeżeń walidacji oraz dostarczanie informacji o działaniach związanych z przepływem pracy.</span><span class="sxs-lookup"><span data-stu-id="93ec8-111">Constraints are authored by using the <xref:System.Activities.Validation.Constraint%601> activity, and several additional validation activities are provided to assist with the creation of validation errors and warnings and to provide information about related activities in the workflow.</span></span>  
  
### <a name="assertvalidation-and-addvalidationerror"></a><span data-ttu-id="93ec8-112">AssertValidation i AddValidationError</span><span class="sxs-lookup"><span data-stu-id="93ec8-112">AssertValidation and AddValidationError</span></span>  

 <span data-ttu-id="93ec8-113"><xref:System.Activities.Validation.AssertValidation>Działanie oblicza wyrażenie odwołujące się do jego <xref:System.Activities.Validation.AssertValidation.Assertion%2A> właściwości, a jeśli wyrażenie zwróci wartość, do `false` elementu zostanie dodany błąd walidacji lub ostrzeżenie <xref:System.Activities.Validation.ValidationResults> .</span><span class="sxs-lookup"><span data-stu-id="93ec8-113">The <xref:System.Activities.Validation.AssertValidation> activity evaluates the expression referenced by its <xref:System.Activities.Validation.AssertValidation.Assertion%2A> property, and if the expression evaluates to `false`, a validation error or warning is added to the <xref:System.Activities.Validation.ValidationResults>.</span></span> <span data-ttu-id="93ec8-114"><xref:System.Activities.Validation.AssertValidation.Message%2A>Właściwość opisuje błąd walidacji, a <xref:System.Activities.Validation.AssertValidation.IsWarning%2A> Właściwość wskazuje, czy błąd walidacji jest błąd lub ostrzeżenie.</span><span class="sxs-lookup"><span data-stu-id="93ec8-114">The <xref:System.Activities.Validation.AssertValidation.Message%2A> property describes the validation error and the <xref:System.Activities.Validation.AssertValidation.IsWarning%2A> property indicates whether the validation failure is an error or a warning.</span></span> <span data-ttu-id="93ec8-115">Wartość domyślna <xref:System.Activities.Validation.AssertValidation.IsWarning%2A> to `false` .</span><span class="sxs-lookup"><span data-stu-id="93ec8-115">The default value for <xref:System.Activities.Validation.AssertValidation.IsWarning%2A> is `false`.</span></span>  
  
 <span data-ttu-id="93ec8-116">W poniższym przykładzie jest zadeklarowane ograniczenie, które zwraca ostrzeżenie o walidacji, jeśli <xref:System.Activities.Activity.DisplayName%2A> zweryfikowane działanie ma dwa znaki lub mniej.</span><span class="sxs-lookup"><span data-stu-id="93ec8-116">In the following example, a constraint is declared that returns a validation warning if the <xref:System.Activities.Activity.DisplayName%2A> of the activity being validated is two characters or less in length.</span></span> <span data-ttu-id="93ec8-117">Parametr typu ogólnego używany do <xref:System.Activities.Validation.Constraint%601> określania typu działania, które jest sprawdzane przez ograniczenie.</span><span class="sxs-lookup"><span data-stu-id="93ec8-117">The generic type parameter used for <xref:System.Activities.Validation.Constraint%601> specifies the type of activity that is validated by the constraint.</span></span> <span data-ttu-id="93ec8-118">To ograniczenie służy <xref:System.Activities.Activity> jako typ ogólny i może służyć do walidacji wszystkich typów działań.</span><span class="sxs-lookup"><span data-stu-id="93ec8-118">This constraint uses <xref:System.Activities.Activity> as the generic type and can be used to validate all types of activities.</span></span>  
  
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
  
 <span data-ttu-id="93ec8-119">Aby określić to ograniczenie dla działania, jest ono dodawane do <xref:System.Activities.Activity.Constraints%2A> działania, jak pokazano w poniższym przykładowym kodzie.</span><span class="sxs-lookup"><span data-stu-id="93ec8-119">To specify this constraint for an activity, it is added to the <xref:System.Activities.Activity.Constraints%2A> of the activity, as shown in the following example code.</span></span>  
  
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
  
 <span data-ttu-id="93ec8-120">Host może także określić to ograniczenie dla działań w przepływie pracy przy użyciu <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> , który jest objęty w następnej sekcji.</span><span class="sxs-lookup"><span data-stu-id="93ec8-120">The host could also specify this constraint for activities in a workflow by using <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A>, which is covered in the next section.</span></span>  
  
 <span data-ttu-id="93ec8-121">To <xref:System.Activities.Validation.AddValidationError> działanie służy do generowania błędu lub ostrzeżenia walidacji, bez konieczności obliczania wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="93ec8-121">The <xref:System.Activities.Validation.AddValidationError> activity is used to generate a validation error or warning without requiring the evaluation of an expression.</span></span> <span data-ttu-id="93ec8-122">Jego właściwości są podobne do <xref:System.Activities.Validation.AssertValidation> i mogą być używane w połączeniu z działaniami sterowania przepływem ograniczenia, takiego jak <xref:System.Activities.Statements.If> działanie.</span><span class="sxs-lookup"><span data-stu-id="93ec8-122">Its properties are similar to <xref:System.Activities.Validation.AssertValidation> and it can be used in conjunction with flow control activities of a constraint such as the <xref:System.Activities.Statements.If> activity.</span></span>
  
### <a name="workflow-relationship-activities"></a><span data-ttu-id="93ec8-123">Działania relacji przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="93ec8-123">Workflow Relationship Activities</span></span>

<span data-ttu-id="93ec8-124">Dostępne są kilka działań weryfikacji, które zapewniają informacje o innych działaniach w przepływie pracy w odniesieniu do zweryfikowanego działania.</span><span class="sxs-lookup"><span data-stu-id="93ec8-124">Several validation activities are available that provide information about the other activities in the workflow in relation to the activity being validated.</span></span> <span data-ttu-id="93ec8-125"><xref:System.Activities.Validation.GetParentChain> Zwraca kolekcję działań, które zawierają wszystkie działania między bieżącym działaniem a głównym działaniem.</span><span class="sxs-lookup"><span data-stu-id="93ec8-125"><xref:System.Activities.Validation.GetParentChain> returns a collection of activities that contains all of the activities between the current activity and the root activity.</span></span> <span data-ttu-id="93ec8-126"><xref:System.Activities.Validation.GetChildSubtree> zawiera kolekcję działań, które zawierają działania podrzędne w cyklicznym wzorcu i <xref:System.Activities.Validation.GetWorkflowTree> Pobiera wszystkie działania w przepływie pracy.</span><span class="sxs-lookup"><span data-stu-id="93ec8-126"><xref:System.Activities.Validation.GetChildSubtree> provides a collection of activities that contains the child activities in a recursive pattern, and <xref:System.Activities.Validation.GetWorkflowTree> gets all the activities in the workflow.</span></span>  
  
<span data-ttu-id="93ec8-127">W poniższym przykładzie `CreateState` zdefiniowano działanie.</span><span class="sxs-lookup"><span data-stu-id="93ec8-127">In the following example, a `CreateState` activity is defined.</span></span> <span data-ttu-id="93ec8-128">`CreateState`Działanie musi być zawarte w `CreateCountry` działaniu, a `GetParent` Metoda zwraca ograniczenie, które wymusza to wymaganie.</span><span class="sxs-lookup"><span data-stu-id="93ec8-128">The `CreateState` activity must be contained within a `CreateCountry` activity, and the `GetParent` method returns a constraint that enforces this requirement.</span></span> <span data-ttu-id="93ec8-129">`GetParent` używa <xref:System.Activities.Validation.GetParentChain> działania w połączeniu z <xref:System.Activities.Statements.ForEach%601> działaniem, aby zbadać działania nadrzędne działania w `CreateState` celu ustalenia, czy wymaganie jest spełnione.</span><span class="sxs-lookup"><span data-stu-id="93ec8-129">`GetParent` uses the <xref:System.Activities.Validation.GetParentChain> activity in conjunction with a <xref:System.Activities.Statements.ForEach%601> activity to inspect the parent activities of the `CreateState` activity to determine if the requirement is met.</span></span>  
  
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
  
## <a name="additional-constraints"></a><span data-ttu-id="93ec8-130">Dodatkowe ograniczenia</span><span class="sxs-lookup"><span data-stu-id="93ec8-130">Additional Constraints</span></span>  

 <span data-ttu-id="93ec8-131">Autorzy hosta przepływu pracy mogą określić dodatkowe ograniczenia sprawdzania poprawności działań w przepływie pracy, tworząc ograniczenia i dodając je do <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> słownika <xref:System.Activities.Validation.ValidationSettings> wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="93ec8-131">Workflow host authors can specify additional validation constraints for activities in a workflow by creating constraints and adding them to the <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> dictionary of a <xref:System.Activities.Validation.ValidationSettings> instance.</span></span> <span data-ttu-id="93ec8-132">Każdy element w <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> zawiera typ działania, dla którego stosowane są ograniczenia oraz listę dodatkowych ograniczeń dla tego typu działania.</span><span class="sxs-lookup"><span data-stu-id="93ec8-132">Each item in <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> contains the type of activity for which the constraints apply and a list of the additional constraints for that type of activity.</span></span> <span data-ttu-id="93ec8-133">Po wywołaniu walidacji dla przepływu pracy każde działanie określonego typu, w tym klasy pochodne, szacuje ograniczenia.</span><span class="sxs-lookup"><span data-stu-id="93ec8-133">When validation is invoked for the workflow, each activity of the specified type, including derived classes, evaluates the constraints.</span></span> <span data-ttu-id="93ec8-134">W tym przykładzie `ActivityDisplayNameIsNotSetWarning` ograniczenie z poprzedniej sekcji jest stosowane do wszystkich działań w przepływie pracy.</span><span class="sxs-lookup"><span data-stu-id="93ec8-134">In this example, the `ActivityDisplayNameIsNotSetWarning` constraint from the previous section is applied to all activities in a workflow.</span></span>  
  
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
  
 <span data-ttu-id="93ec8-135">Jeśli <xref:System.Activities.Validation.ValidationSettings.OnlyUseAdditionalConstraints%2A> Właściwość <xref:System.Activities.Validation.ValidationSettings> ma wartość `true` , tylko określone dodatkowe ograniczenia są oceniane, gdy Walidacja jest wywoływana przez wywołanie <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> .</span><span class="sxs-lookup"><span data-stu-id="93ec8-135">If the <xref:System.Activities.Validation.ValidationSettings.OnlyUseAdditionalConstraints%2A> property of <xref:System.Activities.Validation.ValidationSettings> is `true`, then only the specified additional constraints are evaluated when validation is invoked by calling <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>.</span></span> <span data-ttu-id="93ec8-136">Może to być przydatne do sprawdzania przepływów pracy pod kątem określonych konfiguracji sprawdzania poprawności.</span><span class="sxs-lookup"><span data-stu-id="93ec8-136">This can be useful for inspecting workflows for specific validation configurations.</span></span> <span data-ttu-id="93ec8-137">Należy jednak pamiętać, że gdy przepływ pracy zostanie wywołany, logika walidacji skonfigurowana w przepływie pracy jest szacowana i musi zostać pomyślnie zakończona, aby można było rozpocząć przepływ pracy.</span><span class="sxs-lookup"><span data-stu-id="93ec8-137">Note however that when the workflow is invoked, the validation logic configured in the workflow is evaluated and must pass for the workflow to successfully begin.</span></span> <span data-ttu-id="93ec8-138">Aby uzyskać więcej informacji na temat wywoływania walidacji, zobacz [wywoływanie walidacji działania](invoking-activity-validation.md).</span><span class="sxs-lookup"><span data-stu-id="93ec8-138">For more information about invoking validation, see [Invoking Activity Validation](invoking-activity-validation.md).</span></span>
