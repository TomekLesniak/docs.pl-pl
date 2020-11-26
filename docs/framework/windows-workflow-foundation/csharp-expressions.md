---
title: Wyrażenia języka C#
ms.date: 03/30/2017
ms.assetid: 29110be7-f4e3-407e-8dbe-78102eb21115
ms.openlocfilehash: b0e5d7f2fbb1f7b84c6d8f0110bd111165f0ea52
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239630"
---
# <a name="c-expressions"></a>Wyrażenia języka C#

Począwszy od .NET Framework 4,5, wyrażenia języka C# są obsługiwane w Windows Workflow Foundation (WF). Nowe projekty przepływu pracy w języku C# utworzone w programie Visual Studio 2012, które są przeznaczone dla .NET Framework 4,5 używają wyrażeń języka C# i Visual Basic projekty przepływu pracy używają wyrażeń Visual Basic. Istniejące projekty przepływu pracy w .NET Framework 4, które używają wyrażeń Visual Basic, można migrować [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] niezależnie od języka projektu i są obsługiwane. Ten temat zawiera omówienie wyrażeń języka C# w programie [!INCLUDE[wf1](../../../includes/wf1-md.md)] .

## <a name="using-c-expressions-in-workflows"></a>Używanie wyrażeń języka C# w przepływach pracy

- [Używanie wyrażeń języka C# w Projektant przepływu pracy](csharp-expressions.md#WFDesigner)

  - [Zgodność z poprzednimi wersjami](csharp-expressions.md#BackwardCompat)

- [Używanie wyrażeń języka C# w przepływach pracy kodu](csharp-expressions.md#CodeWorkflows)

- [Używanie wyrażeń języka C# w przepływach pracy XAML](csharp-expressions.md#XamlWorkflows)

  - [Skompilowany kod XAML](csharp-expressions.md#CompiledXaml)

  - [Luźny kod XAML](csharp-expressions.md#LooseXaml)

- [Używanie wyrażeń języka C# w usługach XAMLX Workflow Services](csharp-expressions.md#WFServices)

### <a name="using-c-expressions-in-the-workflow-designer"></a><a name="WFDesigner"></a> Używanie wyrażeń języka C# w Projektant przepływu pracy

Począwszy od .NET Framework 4,5, wyrażenia języka C# są obsługiwane w Windows Workflow Foundation (WF). Projekty przepływu pracy w języku c# utworzone w programie Visual Studio 2012, które są przeznaczone dla .NET Framework 4,5 używać wyrażeń języka C#, podczas gdy Visual Basic projekty przepływu pracy używają wyrażeń Visual Basic. Aby określić żądane wyrażenie języka C#, wpisz je w polu Etykieta **wprowadź wyrażenie języka c#**. Etykieta jest wyświetlana w oknie właściwości, gdy działanie jest wybrane w projektancie, lub na działaniu w Projektancie przepływu pracy. W poniższym przykładzie dwa `WriteLine` działania są zawarte w obrębie `Sequence` wewnątrz `NoPersistScope` .

![Zrzut ekranu pokazujący automatycznie utworzone działanie sekwencji.](./media/csharp-expressions/auto-surround-sequence-activity.png)

> [!NOTE]
> Wyrażenia języka C# są obsługiwane tylko w programie Visual Studio i nie są obsługiwane w przypadku ponownego hostowanego projektanta przepływu pracy. Aby uzyskać więcej informacji na temat nowych funkcji WF45 obsługiwanych w projektancie w dalszym zakresie, zobacz temat [Obsługa nowych funkcji programu Workflow Foundation 4,5 w Projektant przepływu pracy](wf-features-in-the-rehosted-workflow-designer.md)przeprowadzonej przez Ciebie.

#### <a name="backwards-compatibility"></a><a name="BackwardCompat"></a> Zgodność z poprzednimi wersjami

Obsługiwane są wyrażenia Visual Basic w istniejących projektach przepływu pracy .NET Framework 4 w języku C#, które zostały poddane migracji do programu [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] . Gdy wyrażenia Visual Basic są wyświetlane w Projektancie przepływu pracy, tekst istniejącego wyrażenia Visual Basic zostanie zastąpiony **wartością wartość została ustawiona w języku XAML**, chyba że wyrażenie Visual Basic jest prawidłową składnią języka C#. Jeśli wyrażenie Visual Basic jest prawidłową składnią języka C#, wyświetlane jest wyrażenie. Aby zaktualizować wyrażenia Visual Basic do języka C#, można je edytować w Projektancie przepływu pracy i określić równoważne wyrażenie języka C#. Nie jest wymagane aktualizowanie wyrażeń Visual Basic do języka C#, ale po zaktualizowaniu wyrażeń w Projektancie przepływu pracy są one konwertowane do języka C# i nie można ich przywrócić do Visual Basic.

### <a name="using-c-expressions-in-code-workflows"></a><a name="CodeWorkflows"></a> Używanie wyrażeń języka C# w przepływach pracy kodu

Wyrażenia języka c# są obsługiwane w [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] przepływach pracy opartych na kodzie, ale zanim przepływ pracy może być wywoływany, wyrażenia języka c# muszą być kompilowane przy użyciu <xref:System.Activities.XamlIntegration.TextExpressionCompiler.Compile%2A?displayProperty=nameWithType> . Autorzy przepływu pracy mogą używać `CSharpValue` do reprezentowania wartości r wyrażenia i `CSharpReference` reprezentowania wartości l wyrażenia. W poniższym przykładzie przepływ pracy jest tworzony przy użyciu `Assign` działania i `WriteLine` działania zawartego w `Sequence` działaniu. Element `CSharpReference` jest określony dla `To` argumentu `Assign` i reprezentuje l-wartość wyrażenia. `CSharpValue`Jest określony dla `Value` argumentu `Assign` , i dla `Text` argumentu `WriteLine` i reprezentuje wartość r dla tych dwóch wyrażeń.

```csharp
Variable<int> n = new Variable<int>
{
    Name = "n"
};

Activity wf = new Sequence
{
    Variables = { n },
    Activities =
    {
        new Assign<int>
        {
            To = new CSharpReference<int>("n"),
            Value = new CSharpValue<int>("new Random().Next(1, 101)")
        },
        new WriteLine
        {
            Text = new CSharpValue<string>("\"The number is \" + n")
        }
    }
};

CompileExpressions(wf);

WorkflowInvoker.Invoke(wf);
```

Po skonstruowaniu przepływu pracy wyrażenia języka C# są kompilowane przez wywołanie `CompileExpressions` metody pomocnika, a następnie wywołanie przepływu pracy. Poniższy przykład jest `CompileExpressions` metodą.

```csharp
static void CompileExpressions(Activity activity)
{
    // activityName is the Namespace.Type of the activity that contains the
    // C# expressions.
    string activityName = activity.GetType().ToString();

    // Split activityName into Namespace and Type.Append _CompiledExpressionRoot to the type name
    // to represent the new type that represents the compiled expressions.
    // Take everything after the last . for the type name.
    string activityType = activityName.Split('.').Last() + "_CompiledExpressionRoot";
    // Take everything before the last . for the namespace.
    string activityNamespace = string.Join(".", activityName.Split('.').Reverse().Skip(1).Reverse());

    // Create a TextExpressionCompilerSettings.
    TextExpressionCompilerSettings settings = new TextExpressionCompilerSettings
    {
        Activity = activity,
        Language = "C#",
        ActivityName = activityType,
        ActivityNamespace = activityNamespace,
        RootNamespace = null,
        GenerateAsPartialClass = false,
        AlwaysGenerateSource = true,
        ForImplementation = false
    };

    // Compile the C# expression.
    TextExpressionCompilerResults results =
        new TextExpressionCompiler(settings).Compile();

    // Any compilation errors are contained in the CompilerMessages.
    if (results.HasErrors)
    {
        throw new Exception("Compilation failed.");
    }

    // Create an instance of the new compiled expression type.
    ICompiledExpressionRoot compiledExpressionRoot =
        Activator.CreateInstance(results.ResultType,
            new object[] { activity }) as ICompiledExpressionRoot;

    // Attach it to the activity.
    CompiledExpressionInvoker.SetCompiledExpressionRoot(
        activity, compiledExpressionRoot);
}
```

> [!NOTE]
> Jeśli wyrażenia języka C# nie są kompilowane, <xref:System.NotSupportedException> jest zgłaszany, gdy przepływ pracy jest wywoływany z komunikatem podobnym do następującego: `Expression Activity type 'CSharpValue` 1 "wymaga kompilacji, aby można było uruchomić.  Upewnij się, że przepływ pracy został skompilowany.

Jeśli niestandardowy przepływ pracy oparty na kodzie `DynamicActivity` jest używany, niektóre zmiany `CompileExpressions` metody są wymagane, jak pokazano w poniższym przykładzie kodu.

```csharp
static void CompileExpressions(DynamicActivity dynamicActivity)
{
    // activityName is the Namespace.Type of the activity that contains the
    // C# expressions. For Dynamic Activities this can be retrieved using the
    // name property , which must be in the form Namespace.Type.
    string activityName = dynamicActivity.Name;

    // Split activityName into Namespace and Type.Append _CompiledExpressionRoot to the type name
    // to represent the new type that represents the compiled expressions.
    // Take everything after the last . for the type name.
    string activityType = activityName.Split('.').Last() + "_CompiledExpressionRoot";
    // Take everything before the last . for the namespace.
    string activityNamespace = string.Join(".", activityName.Split('.').Reverse().Skip(1).Reverse());

    // Create a TextExpressionCompilerSettings.
    TextExpressionCompilerSettings settings = new TextExpressionCompilerSettings
    {
        Activity = dynamicActivity,
        Language = "C#",
        ActivityName = activityType,
        ActivityNamespace = activityNamespace,
        RootNamespace = null,
        GenerateAsPartialClass = false,
        AlwaysGenerateSource = true,
        ForImplementation = true
    };

    // Compile the C# expression.
    TextExpressionCompilerResults results =
        new TextExpressionCompiler(settings).Compile();

    // Any compilation errors are contained in the CompilerMessages.
    if (results.HasErrors)
    {
        throw new Exception("Compilation failed.");
    }

    // Create an instance of the new compiled expression type.
    ICompiledExpressionRoot compiledExpressionRoot =
        Activator.CreateInstance(results.ResultType,
            new object[] { dynamicActivity }) as ICompiledExpressionRoot;

    // Attach it to the activity.
    CompiledExpressionInvoker.SetCompiledExpressionRootForImplementation(
        dynamicActivity, compiledExpressionRoot);
}
```

Istnieje kilka różnic w `CompileExpressions` przeciążeniu, które kompiluje wyrażenia języka C# w działaniu dynamicznym.

- Parametr ma wartość `CompileExpressions` `DynamicActivity` .

- Nazwa typu i przestrzeń nazw są pobierane przy użyciu `DynamicActivity.Name` właściwości.

- `TextExpressionCompilerSettings.ForImplementation` jest ustawiony na `true` .

- `CompiledExpressionInvoker.SetCompiledExpressionRootForImplementation` jest wywoływana zamiast `CompiledExpressionInvoker.SetCompiledExpressionRoot` .

Aby uzyskać więcej informacji na temat pracy z wyrażeniami w kodzie, zobacz [Tworzenie przepływów pracy, działań i wyrażeń przy użyciu własnego kodu](authoring-workflows-activities-and-expressions-using-imperative-code.md).

### <a name="using-c-expressions-in-xaml-workflows"></a><a name="XamlWorkflows"></a> Używanie wyrażeń języka C# w przepływach pracy XAML

Wyrażenia języka C# są obsługiwane w przepływach pracy XAML. Skompilowane przepływy pracy XAML są kompilowane w typie i luźne przepływy pracy XAML są ładowane przez środowisko uruchomieniowe i kompilowane w drzewie aktywności podczas wykonywania przepływu pracy.

- [Skompilowany kod XAML](csharp-expressions.md#CompiledXaml)

- [Luźny kod XAML](csharp-expressions.md#LooseXaml)

#### <a name="compiled-xaml"></a><a name="CompiledXaml"></a> Skompilowany kod XAML

Wyrażenia języka C# są obsługiwane w skompilowanych przepływach pracy XAML, które są kompilowane do typu w ramach projektu przepływu pracy C#, który jest przeznaczony dla elementu docelowego [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] . Skompilowany kod XAML to domyślny typ tworzenia przepływu pracy w programie Visual Studio i projekty przepływu pracy w języku C# utworzone w programie Visual Studio, które są [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] przeznaczone dla wyrażeń języka c#.

#### <a name="loose-xaml"></a><a name="LooseXaml"></a> Luźny kod XAML

Wyrażenia języka C# są obsługiwane w luźnych przepływach pracy XAML. Program hosta przepływu pracy, który ładuje i wywołuje luźny przepływ pracy XAML, musi być obiektem docelowym [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] i <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> musi być ustawiony na `true` (wartość domyślna to `false` ). Aby ustawić <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> na `true` , Utwórz <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings> wystąpienie z jego <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> właściwością ustawioną na `true` i przekaż je jako parametr do <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A?displayProperty=nameWithType> . Jeśli `CompileExpressions` nie jest ustawiona na `true` , <xref:System.NotSupportedException> zostanie zgłoszony komunikat podobny do następującego: `Expression Activity type 'CSharpValue` 1 "wymaga kompilacji do uruchomienia.  Upewnij się, że przepływ pracy został skompilowany.

```csharp
ActivityXamlServicesSettings settings = new ActivityXamlServicesSettings
{
    CompileExpressions = true
};

DynamicActivity<int> wf = ActivityXamlServices.Load(new StringReader(serializedAB), settings) as DynamicActivity<int>;
```

Aby uzyskać więcej informacji na temat pracy z przepływami pracy XAML, zobacz [Serializowanie przepływów pracy i działań do i z języka XAML](serializing-workflows-and-activities-to-and-from-xaml.md).

### <a name="using-c-expressions-in-xamlx-workflow-services"></a><a name="WFServices"></a> Używanie wyrażeń języka C# w usługach XAMLX Workflow Services

Wyrażenia języka C# są obsługiwane w usługach XAMLX Workflow Services. Gdy usługa przepływu pracy jest hostowana w usługach IIS lub nie jest wymagana żadna dodatkowa procedura, ale jeśli usługa przepływu pracy XAML jest samodzielna, należy skompilować wyrażenia języka C#. Aby skompilować wyrażenia C# w usłudze samoobsługowego przepływu pracy XAMLX, najpierw Załaduj plik XAMLX do `WorkflowService` , a następnie Przekaż `Body` `WorkflowService` `CompileExpressions` metodę do metody opisanej w poprzednich [wyrażeniach języka C# using w sekcji przepływy kodu](csharp-expressions.md#CodeWorkflows) . W poniższym przykładzie zostaje załadowana usługa przepływu pracy XAMLX, wyrażenia języka C# są kompilowane, a następnie usługa przepływu pracy jest otwarta i oczekuje na żądania.

```csharp
// Load the XAMLX workflow service.
WorkflowService workflow1 =
    (WorkflowService)XamlServices.Load(xamlxPath);

// Compile the C# expressions in the workflow by passing the Body to CompileExpressions.
CompileExpressions(workflow1.Body);

// Initialize the WorkflowServiceHost.
var host = new WorkflowServiceHost(workflow1, new Uri("http://localhost:8293/Service1.xamlx"));

// Enable Metadata publishing/
ServiceMetadataBehavior smb = new ServiceMetadataBehavior();
smb.HttpGetEnabled = true;
smb.MetadataExporter.PolicyVersion = PolicyVersion.Policy15;
host.Description.Behaviors.Add(smb);

// Open the WorkflowServiceHost and wait for requests.
host.Open();
Console.WriteLine("Press enter to quit");
Console.ReadLine();
```

Jeśli wyrażenia języka C# nie są kompilowane, `Open` operacja zakończy się powodzeniem, ale przepływ pracy zakończy się niepowodzeniem, gdy zostanie wywołany. Następująca `CompileExpressions` Metoda jest taka sama jak metoda z poprzedniego [wyrażenia C# using w sekcji przepływy pracy kodu](csharp-expressions.md#CodeWorkflows) .

```csharp
static void CompileExpressions(Activity activity)
{
    // activityName is the Namespace.Type of the activity that contains the
    // C# expressions.
    string activityName = activity.GetType().ToString();

    // Split activityName into Namespace and Type.Append _CompiledExpressionRoot to the type name
    // to represent the new type that represents the compiled expressions.
    // Take everything after the last . for the type name.
    string activityType = activityName.Split('.').Last() + "_CompiledExpressionRoot";
    // Take everything before the last . for the namespace.
    string activityNamespace = string.Join(".", activityName.Split('.').Reverse().Skip(1).Reverse());

    // Create a TextExpressionCompilerSettings.
    TextExpressionCompilerSettings settings = new TextExpressionCompilerSettings
    {
        Activity = activity,
        Language = "C#",
        ActivityName = activityType,
        ActivityNamespace = activityNamespace,
        RootNamespace = null,
        GenerateAsPartialClass = false,
        AlwaysGenerateSource = true,
        ForImplementation = false
    };

    // Compile the C# expression.
    TextExpressionCompilerResults results =
        new TextExpressionCompiler(settings).Compile();

    // Any compilation errors are contained in the CompilerMessages.
    if (results.HasErrors)
    {
        throw new Exception("Compilation failed.");
    }

    // Create an instance of the new compiled expression type.
    ICompiledExpressionRoot compiledExpressionRoot =
        Activator.CreateInstance(results.ResultType,
            new object[] { activity }) as ICompiledExpressionRoot;

    // Attach it to the activity.
    CompiledExpressionInvoker.SetCompiledExpressionRoot(
        activity, compiledExpressionRoot);
}
```
