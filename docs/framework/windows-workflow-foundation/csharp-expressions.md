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
# <a name="c-expressions"></a><span data-ttu-id="3cce7-102">Wyrażenia języka C#</span><span class="sxs-lookup"><span data-stu-id="3cce7-102">C# Expressions</span></span>

<span data-ttu-id="3cce7-103">Począwszy od .NET Framework 4,5, wyrażenia języka C# są obsługiwane w Windows Workflow Foundation (WF).</span><span class="sxs-lookup"><span data-stu-id="3cce7-103">Starting with .NET Framework 4.5, C# expressions are supported in Windows Workflow Foundation (WF).</span></span> <span data-ttu-id="3cce7-104">Nowe projekty przepływu pracy w języku C# utworzone w programie Visual Studio 2012, które są przeznaczone dla .NET Framework 4,5 używają wyrażeń języka C# i Visual Basic projekty przepływu pracy używają wyrażeń Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="3cce7-104">New C# workflow projects created in Visual Studio 2012 that target .NET Framework 4.5 use C# expressions, and Visual Basic workflow projects use Visual Basic expressions.</span></span> <span data-ttu-id="3cce7-105">Istniejące projekty przepływu pracy w .NET Framework 4, które używają wyrażeń Visual Basic, można migrować [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] niezależnie od języka projektu i są obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="3cce7-105">Existing .NET Framework 4 workflow projects that use Visual Basic expressions can be migrated to [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] regardless of the project language and are supported.</span></span> <span data-ttu-id="3cce7-106">Ten temat zawiera omówienie wyrażeń języka C# w programie [!INCLUDE[wf1](../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3cce7-106">This topic provides an overview of C# expressions in [!INCLUDE[wf1](../../../includes/wf1-md.md)].</span></span>

## <a name="using-c-expressions-in-workflows"></a><span data-ttu-id="3cce7-107">Używanie wyrażeń języka C# w przepływach pracy</span><span class="sxs-lookup"><span data-stu-id="3cce7-107">Using C# expressions in workflows</span></span>

- [<span data-ttu-id="3cce7-108">Używanie wyrażeń języka C# w Projektant przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="3cce7-108">Using C# expressions in the Workflow Designer</span></span>](csharp-expressions.md#WFDesigner)

  - [<span data-ttu-id="3cce7-109">Zgodność z poprzednimi wersjami</span><span class="sxs-lookup"><span data-stu-id="3cce7-109">Backwards compatibility</span></span>](csharp-expressions.md#BackwardCompat)

- [<span data-ttu-id="3cce7-110">Używanie wyrażeń języka C# w przepływach pracy kodu</span><span class="sxs-lookup"><span data-stu-id="3cce7-110">Using C# expressions in code workflows</span></span>](csharp-expressions.md#CodeWorkflows)

- [<span data-ttu-id="3cce7-111">Używanie wyrażeń języka C# w przepływach pracy XAML</span><span class="sxs-lookup"><span data-stu-id="3cce7-111">Using C# expressions in XAML workflows</span></span>](csharp-expressions.md#XamlWorkflows)

  - [<span data-ttu-id="3cce7-112">Skompilowany kod XAML</span><span class="sxs-lookup"><span data-stu-id="3cce7-112">Compiled Xaml</span></span>](csharp-expressions.md#CompiledXaml)

  - [<span data-ttu-id="3cce7-113">Luźny kod XAML</span><span class="sxs-lookup"><span data-stu-id="3cce7-113">Loose Xaml</span></span>](csharp-expressions.md#LooseXaml)

- [<span data-ttu-id="3cce7-114">Używanie wyrażeń języka C# w usługach XAMLX Workflow Services</span><span class="sxs-lookup"><span data-stu-id="3cce7-114">Using C# expressions in XAMLX workflow services</span></span>](csharp-expressions.md#WFServices)

### <a name="using-c-expressions-in-the-workflow-designer"></a><a name="WFDesigner"></a> <span data-ttu-id="3cce7-115">Używanie wyrażeń języka C# w Projektant przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="3cce7-115">Using C# expressions in the Workflow Designer</span></span>

<span data-ttu-id="3cce7-116">Począwszy od .NET Framework 4,5, wyrażenia języka C# są obsługiwane w Windows Workflow Foundation (WF).</span><span class="sxs-lookup"><span data-stu-id="3cce7-116">Starting with .NET Framework 4.5, C# expressions are supported in Windows Workflow Foundation (WF).</span></span> <span data-ttu-id="3cce7-117">Projekty przepływu pracy w języku c# utworzone w programie Visual Studio 2012, które są przeznaczone dla .NET Framework 4,5 używać wyrażeń języka C#, podczas gdy Visual Basic projekty przepływu pracy używają wyrażeń Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="3cce7-117">C# workflow projects created in Visual Studio 2012 that target .NET Framework 4.5 use C# expressions, while Visual Basic workflow projects use Visual Basic expressions.</span></span> <span data-ttu-id="3cce7-118">Aby określić żądane wyrażenie języka C#, wpisz je w polu Etykieta **wprowadź wyrażenie języka c#**.</span><span class="sxs-lookup"><span data-stu-id="3cce7-118">To specify the desired C# expression, type it into the box labeled **Enter a C# expression**.</span></span> <span data-ttu-id="3cce7-119">Etykieta jest wyświetlana w oknie właściwości, gdy działanie jest wybrane w projektancie, lub na działaniu w Projektancie przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="3cce7-119">This label is displayed in the properties window when the activity is selected in the designer, or on the activity in the workflow designer.</span></span> <span data-ttu-id="3cce7-120">W poniższym przykładzie dwa `WriteLine` działania są zawarte w obrębie `Sequence` wewnątrz `NoPersistScope` .</span><span class="sxs-lookup"><span data-stu-id="3cce7-120">In the following example, two `WriteLine` activities are contained within a `Sequence` inside a `NoPersistScope`.</span></span>

![Zrzut ekranu pokazujący automatycznie utworzone działanie sekwencji.](./media/csharp-expressions/auto-surround-sequence-activity.png)

> [!NOTE]
> <span data-ttu-id="3cce7-122">Wyrażenia języka C# są obsługiwane tylko w programie Visual Studio i nie są obsługiwane w przypadku ponownego hostowanego projektanta przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="3cce7-122">C# expressions are supported only in Visual Studio, and are not supported in the re-hosted workflow designer.</span></span> <span data-ttu-id="3cce7-123">Aby uzyskać więcej informacji na temat nowych funkcji WF45 obsługiwanych w projektancie w dalszym zakresie, zobacz temat [Obsługa nowych funkcji programu Workflow Foundation 4,5 w Projektant przepływu pracy](wf-features-in-the-rehosted-workflow-designer.md)przeprowadzonej przez Ciebie.</span><span class="sxs-lookup"><span data-stu-id="3cce7-123">For more information about new WF45 features supported in the re-hosted designer, see [Support for New Workflow Foundation 4.5 Features in the Rehosted Workflow Designer](wf-features-in-the-rehosted-workflow-designer.md).</span></span>

#### <a name="backwards-compatibility"></a><a name="BackwardCompat"></a> <span data-ttu-id="3cce7-124">Zgodność z poprzednimi wersjami</span><span class="sxs-lookup"><span data-stu-id="3cce7-124">Backwards compatibility</span></span>

<span data-ttu-id="3cce7-125">Obsługiwane są wyrażenia Visual Basic w istniejących projektach przepływu pracy .NET Framework 4 w języku C#, które zostały poddane migracji do programu [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3cce7-125">Visual Basic expressions in existing .NET Framework 4 C# workflow projects that have been migrated to [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] are supported.</span></span> <span data-ttu-id="3cce7-126">Gdy wyrażenia Visual Basic są wyświetlane w Projektancie przepływu pracy, tekst istniejącego wyrażenia Visual Basic zostanie zastąpiony **wartością wartość została ustawiona w języku XAML**, chyba że wyrażenie Visual Basic jest prawidłową składnią języka C#.</span><span class="sxs-lookup"><span data-stu-id="3cce7-126">When the Visual Basic expressions are viewed in the workflow designer, the text of the existing Visual Basic expression is replaced with **Value was set in XAML**, unless the Visual Basic expression is valid C# syntax.</span></span> <span data-ttu-id="3cce7-127">Jeśli wyrażenie Visual Basic jest prawidłową składnią języka C#, wyświetlane jest wyrażenie.</span><span class="sxs-lookup"><span data-stu-id="3cce7-127">If the Visual Basic expression is valid C# syntax, then the expression is displayed.</span></span> <span data-ttu-id="3cce7-128">Aby zaktualizować wyrażenia Visual Basic do języka C#, można je edytować w Projektancie przepływu pracy i określić równoważne wyrażenie języka C#.</span><span class="sxs-lookup"><span data-stu-id="3cce7-128">To update the Visual Basic expressions to C#, you can edit them in the workflow designer and specify the equivalent C# expression.</span></span> <span data-ttu-id="3cce7-129">Nie jest wymagane aktualizowanie wyrażeń Visual Basic do języka C#, ale po zaktualizowaniu wyrażeń w Projektancie przepływu pracy są one konwertowane do języka C# i nie można ich przywrócić do Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="3cce7-129">It is not required to update the Visual Basic expressions to C#, but once the expressions are updated in the workflow designer they are converted to C# and may not be reverted to Visual Basic.</span></span>

### <a name="using-c-expressions-in-code-workflows"></a><a name="CodeWorkflows"></a> <span data-ttu-id="3cce7-130">Używanie wyrażeń języka C# w przepływach pracy kodu</span><span class="sxs-lookup"><span data-stu-id="3cce7-130">Using C# expressions in code workflows</span></span>

<span data-ttu-id="3cce7-131">Wyrażenia języka c# są obsługiwane w [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] przepływach pracy opartych na kodzie, ale zanim przepływ pracy może być wywoływany, wyrażenia języka c# muszą być kompilowane przy użyciu <xref:System.Activities.XamlIntegration.TextExpressionCompiler.Compile%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="3cce7-131">C# expressions are supported in [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] code based workflows, but before the workflow can be invoked the C# expressions must be compiled using <xref:System.Activities.XamlIntegration.TextExpressionCompiler.Compile%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="3cce7-132">Autorzy przepływu pracy mogą używać `CSharpValue` do reprezentowania wartości r wyrażenia i `CSharpReference` reprezentowania wartości l wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="3cce7-132">Workflow authors can use `CSharpValue` to represent the r-value of an expression, and `CSharpReference` to represent the l-value of an expression.</span></span> <span data-ttu-id="3cce7-133">W poniższym przykładzie przepływ pracy jest tworzony przy użyciu `Assign` działania i `WriteLine` działania zawartego w `Sequence` działaniu.</span><span class="sxs-lookup"><span data-stu-id="3cce7-133">In the following example, a workflow is created with an `Assign` activity and a `WriteLine` activity contained in a `Sequence` activity.</span></span> <span data-ttu-id="3cce7-134">Element `CSharpReference` jest określony dla `To` argumentu `Assign` i reprezentuje l-wartość wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="3cce7-134">A `CSharpReference` is specified for the `To` argument of the `Assign`, and represents the l-value of the expression.</span></span> <span data-ttu-id="3cce7-135">`CSharpValue`Jest określony dla `Value` argumentu `Assign` , i dla `Text` argumentu `WriteLine` i reprezentuje wartość r dla tych dwóch wyrażeń.</span><span class="sxs-lookup"><span data-stu-id="3cce7-135">A `CSharpValue` is specified for the `Value` argument of the `Assign`, and for the `Text` argument of the `WriteLine`, and represents the r-value for those two expressions.</span></span>

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

<span data-ttu-id="3cce7-136">Po skonstruowaniu przepływu pracy wyrażenia języka C# są kompilowane przez wywołanie `CompileExpressions` metody pomocnika, a następnie wywołanie przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="3cce7-136">After the workflow is constructed, the C# expressions are compiled by calling the `CompileExpressions` helper method and then the workflow is invoked.</span></span> <span data-ttu-id="3cce7-137">Poniższy przykład jest `CompileExpressions` metodą.</span><span class="sxs-lookup"><span data-stu-id="3cce7-137">The following example is the `CompileExpressions` method.</span></span>

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
> <span data-ttu-id="3cce7-138">Jeśli wyrażenia języka C# nie są kompilowane, <xref:System.NotSupportedException> jest zgłaszany, gdy przepływ pracy jest wywoływany z komunikatem podobnym do następującego: `Expression Activity type 'CSharpValue` 1 "wymaga kompilacji, aby można było uruchomić.</span><span class="sxs-lookup"><span data-stu-id="3cce7-138">If the C# expressions are not compiled, a <xref:System.NotSupportedException> is thrown when the workflow is invoked with a message similar to the following: `Expression Activity type 'CSharpValue`1' requires compilation in order to run.</span></span>  <span data-ttu-id="3cce7-139">Upewnij się, że przepływ pracy został skompilowany.</span><span class="sxs-lookup"><span data-stu-id="3cce7-139">Please ensure that the workflow has been compiled.\`</span></span>

<span data-ttu-id="3cce7-140">Jeśli niestandardowy przepływ pracy oparty na kodzie `DynamicActivity` jest używany, niektóre zmiany `CompileExpressions` metody są wymagane, jak pokazano w poniższym przykładzie kodu.</span><span class="sxs-lookup"><span data-stu-id="3cce7-140">If your custom code based workflow uses `DynamicActivity`, then some changes to the `CompileExpressions` method are required, as demonstrated in the following code example.</span></span>

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

<span data-ttu-id="3cce7-141">Istnieje kilka różnic w `CompileExpressions` przeciążeniu, które kompiluje wyrażenia języka C# w działaniu dynamicznym.</span><span class="sxs-lookup"><span data-stu-id="3cce7-141">There are several differences in the `CompileExpressions` overload that compiles the C# expressions in a dynamic activity.</span></span>

- <span data-ttu-id="3cce7-142">Parametr ma wartość `CompileExpressions` `DynamicActivity` .</span><span class="sxs-lookup"><span data-stu-id="3cce7-142">The parameter to `CompileExpressions` is a `DynamicActivity`.</span></span>

- <span data-ttu-id="3cce7-143">Nazwa typu i przestrzeń nazw są pobierane przy użyciu `DynamicActivity.Name` właściwości.</span><span class="sxs-lookup"><span data-stu-id="3cce7-143">The type name and namespace are retrieved using the `DynamicActivity.Name` property.</span></span>

- <span data-ttu-id="3cce7-144">`TextExpressionCompilerSettings.ForImplementation` jest ustawiony na `true` .</span><span class="sxs-lookup"><span data-stu-id="3cce7-144">`TextExpressionCompilerSettings.ForImplementation` is set to `true`.</span></span>

- <span data-ttu-id="3cce7-145">`CompiledExpressionInvoker.SetCompiledExpressionRootForImplementation` jest wywoływana zamiast `CompiledExpressionInvoker.SetCompiledExpressionRoot` .</span><span class="sxs-lookup"><span data-stu-id="3cce7-145">`CompiledExpressionInvoker.SetCompiledExpressionRootForImplementation` is called instead of `CompiledExpressionInvoker.SetCompiledExpressionRoot`.</span></span>

<span data-ttu-id="3cce7-146">Aby uzyskać więcej informacji na temat pracy z wyrażeniami w kodzie, zobacz [Tworzenie przepływów pracy, działań i wyrażeń przy użyciu własnego kodu](authoring-workflows-activities-and-expressions-using-imperative-code.md).</span><span class="sxs-lookup"><span data-stu-id="3cce7-146">For more information about working with expressions in code, see [Authoring Workflows, Activities, and Expressions Using Imperative Code](authoring-workflows-activities-and-expressions-using-imperative-code.md).</span></span>

### <a name="using-c-expressions-in-xaml-workflows"></a><a name="XamlWorkflows"></a> <span data-ttu-id="3cce7-147">Używanie wyrażeń języka C# w przepływach pracy XAML</span><span class="sxs-lookup"><span data-stu-id="3cce7-147">Using C# expressions in XAML workflows</span></span>

<span data-ttu-id="3cce7-148">Wyrażenia języka C# są obsługiwane w przepływach pracy XAML.</span><span class="sxs-lookup"><span data-stu-id="3cce7-148">C# expressions are supported in XAML workflows.</span></span> <span data-ttu-id="3cce7-149">Skompilowane przepływy pracy XAML są kompilowane w typie i luźne przepływy pracy XAML są ładowane przez środowisko uruchomieniowe i kompilowane w drzewie aktywności podczas wykonywania przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="3cce7-149">Compiled XAML workflows are compiled into a type, and loose XAML workflows are loaded by the runtime and compiled into an activity tree when the workflow is executed.</span></span>

- [<span data-ttu-id="3cce7-150">Skompilowany kod XAML</span><span class="sxs-lookup"><span data-stu-id="3cce7-150">Compiled Xaml</span></span>](csharp-expressions.md#CompiledXaml)

- [<span data-ttu-id="3cce7-151">Luźny kod XAML</span><span class="sxs-lookup"><span data-stu-id="3cce7-151">Loose Xaml</span></span>](csharp-expressions.md#LooseXaml)

#### <a name="compiled-xaml"></a><a name="CompiledXaml"></a> <span data-ttu-id="3cce7-152">Skompilowany kod XAML</span><span class="sxs-lookup"><span data-stu-id="3cce7-152">Compiled Xaml</span></span>

<span data-ttu-id="3cce7-153">Wyrażenia języka C# są obsługiwane w skompilowanych przepływach pracy XAML, które są kompilowane do typu w ramach projektu przepływu pracy C#, który jest przeznaczony dla elementu docelowego [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3cce7-153">C# expressions are supported in compiled XAML workflows that are compiled to a type as part of a C# workflow project that targets [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)].</span></span> <span data-ttu-id="3cce7-154">Skompilowany kod XAML to domyślny typ tworzenia przepływu pracy w programie Visual Studio i projekty przepływu pracy w języku C# utworzone w programie Visual Studio, które są [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] przeznaczone dla wyrażeń języka c#.</span><span class="sxs-lookup"><span data-stu-id="3cce7-154">Compiled XAML is the default type of workflow authoring in Visual Studio, and C# workflow projects created in Visual Studio that target [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] use C# expressions.</span></span>

#### <a name="loose-xaml"></a><a name="LooseXaml"></a> <span data-ttu-id="3cce7-155">Luźny kod XAML</span><span class="sxs-lookup"><span data-stu-id="3cce7-155">Loose Xaml</span></span>

<span data-ttu-id="3cce7-156">Wyrażenia języka C# są obsługiwane w luźnych przepływach pracy XAML.</span><span class="sxs-lookup"><span data-stu-id="3cce7-156">C# expressions are supported in loose XAML workflows.</span></span> <span data-ttu-id="3cce7-157">Program hosta przepływu pracy, który ładuje i wywołuje luźny przepływ pracy XAML, musi być obiektem docelowym [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] i <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> musi być ustawiony na `true` (wartość domyślna to `false` ).</span><span class="sxs-lookup"><span data-stu-id="3cce7-157">The workflow host program that loads and invokes the loose XAML workflow must target [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)], and <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> must be set to `true` (the default is `false`).</span></span> <span data-ttu-id="3cce7-158">Aby ustawić <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> na `true` , Utwórz <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings> wystąpienie z jego <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> właściwością ustawioną na `true` i przekaż je jako parametr do <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="3cce7-158">To set <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> to `true`, create an <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings> instance with its <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> property set to `true`, and pass it as a parameter to <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="3cce7-159">Jeśli `CompileExpressions` nie jest ustawiona na `true` , <xref:System.NotSupportedException> zostanie zgłoszony komunikat podobny do następującego: `Expression Activity type 'CSharpValue` 1 "wymaga kompilacji do uruchomienia.</span><span class="sxs-lookup"><span data-stu-id="3cce7-159">If `CompileExpressions` Is not set to `true`, a <xref:System.NotSupportedException> will be thrown with a message similar to the following: `Expression Activity type 'CSharpValue`1' requires compilation in order to run.</span></span>  <span data-ttu-id="3cce7-160">Upewnij się, że przepływ pracy został skompilowany.</span><span class="sxs-lookup"><span data-stu-id="3cce7-160">Please ensure that the workflow has been compiled.\`</span></span>

```csharp
ActivityXamlServicesSettings settings = new ActivityXamlServicesSettings
{
    CompileExpressions = true
};

DynamicActivity<int> wf = ActivityXamlServices.Load(new StringReader(serializedAB), settings) as DynamicActivity<int>;
```

<span data-ttu-id="3cce7-161">Aby uzyskać więcej informacji na temat pracy z przepływami pracy XAML, zobacz [Serializowanie przepływów pracy i działań do i z języka XAML](serializing-workflows-and-activities-to-and-from-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="3cce7-161">For more information about working with XAML workflows, see [Serializing Workflows and Activities to and from XAML](serializing-workflows-and-activities-to-and-from-xaml.md).</span></span>

### <a name="using-c-expressions-in-xamlx-workflow-services"></a><a name="WFServices"></a> <span data-ttu-id="3cce7-162">Używanie wyrażeń języka C# w usługach XAMLX Workflow Services</span><span class="sxs-lookup"><span data-stu-id="3cce7-162">Using C# expressions in XAMLX workflow services</span></span>

<span data-ttu-id="3cce7-163">Wyrażenia języka C# są obsługiwane w usługach XAMLX Workflow Services.</span><span class="sxs-lookup"><span data-stu-id="3cce7-163">C# expressions are supported in XAMLX workflow services.</span></span> <span data-ttu-id="3cce7-164">Gdy usługa przepływu pracy jest hostowana w usługach IIS lub nie jest wymagana żadna dodatkowa procedura, ale jeśli usługa przepływu pracy XAML jest samodzielna, należy skompilować wyrażenia języka C#.</span><span class="sxs-lookup"><span data-stu-id="3cce7-164">When a workflow service is hosted in IIS or WAS then no additional steps are required, but if the XAML workflow service is self-hosted, then the C# expressions must be compiled.</span></span> <span data-ttu-id="3cce7-165">Aby skompilować wyrażenia C# w usłudze samoobsługowego przepływu pracy XAMLX, najpierw Załaduj plik XAMLX do `WorkflowService` , a następnie Przekaż `Body` `WorkflowService` `CompileExpressions` metodę do metody opisanej w poprzednich [wyrażeniach języka C# using w sekcji przepływy kodu](csharp-expressions.md#CodeWorkflows) .</span><span class="sxs-lookup"><span data-stu-id="3cce7-165">To compile the C# expressions in a self-hosted XAMLX workflow service, first load the XAMLX file into a `WorkflowService`, and then pass the `Body` of the `WorkflowService` to the `CompileExpressions` method described in the previous [Using C# expressions in code workflows](csharp-expressions.md#CodeWorkflows) section.</span></span> <span data-ttu-id="3cce7-166">W poniższym przykładzie zostaje załadowana usługa przepływu pracy XAMLX, wyrażenia języka C# są kompilowane, a następnie usługa przepływu pracy jest otwarta i oczekuje na żądania.</span><span class="sxs-lookup"><span data-stu-id="3cce7-166">In the following example, a XAMLX workflow service is loaded, the C# expressions are compiled, and then the workflow service is opened and waits for requests.</span></span>

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

<span data-ttu-id="3cce7-167">Jeśli wyrażenia języka C# nie są kompilowane, `Open` operacja zakończy się powodzeniem, ale przepływ pracy zakończy się niepowodzeniem, gdy zostanie wywołany.</span><span class="sxs-lookup"><span data-stu-id="3cce7-167">If the C# expressions are not compiled, the `Open` operation succeeds but the workflow will fail when it is invoked.</span></span> <span data-ttu-id="3cce7-168">Następująca `CompileExpressions` Metoda jest taka sama jak metoda z poprzedniego [wyrażenia C# using w sekcji przepływy pracy kodu](csharp-expressions.md#CodeWorkflows) .</span><span class="sxs-lookup"><span data-stu-id="3cce7-168">The following `CompileExpressions` method is the same as the method from the previous [Using C# expressions in code workflows](csharp-expressions.md#CodeWorkflows) section.</span></span>

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
