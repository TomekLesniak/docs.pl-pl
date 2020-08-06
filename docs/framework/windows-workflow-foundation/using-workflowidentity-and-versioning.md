---
title: Używanie obiektu WorkflowIdentity i wersjonowanie
ms.date: 03/30/2017
ms.assetid: b8451735-8046-478f-912b-40870a6c0c3a
ms.openlocfilehash: 1d31739c135dbb518f05c40ba802c782b6817bff
ms.sourcegitcommit: c37e8d4642fef647ebab0e1c618ecc29ddfe2a0f
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/06/2020
ms.locfileid: "87855637"
---
# <a name="using-workflowidentity-and-versioning"></a><span data-ttu-id="910a3-102">Używanie obiektu WorkflowIdentity i wersjonowanie</span><span class="sxs-lookup"><span data-stu-id="910a3-102">Using WorkflowIdentity and Versioning</span></span>

<span data-ttu-id="910a3-103"><xref:System.Activities.WorkflowIdentity>umożliwia deweloperom aplikacji przepływu pracy kojarzenie nazw i <xref:System.Version> z definicją przepływu pracy oraz dla tych informacji, które mają być skojarzone z utrwalonym wystąpieniem przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="910a3-103"><xref:System.Activities.WorkflowIdentity> provides a way for workflow application developers to associate a name and a <xref:System.Version> with a workflow definition, and for this information to be associated with a persisted workflow instance.</span></span> <span data-ttu-id="910a3-104">Te informacje o tożsamości mogą być używane przez deweloperów aplikacji przepływu pracy do włączania scenariuszy, takich jak wykonywanie równoczesne wielu wersji definicji przepływu pracy i udostępniają one podstawę do innych funkcji, takich jak aktualizacja dynamiczna.</span><span class="sxs-lookup"><span data-stu-id="910a3-104">This identity information can be used by workflow application developers to enable scenarios such as side-by-side execution of multiple versions of a workflow definition, and provides the cornerstone for other functionality such as dynamic update.</span></span> <span data-ttu-id="910a3-105">Ten temat zawiera omówienie korzystania z programu <xref:System.Activities.WorkflowIdentity> z <xref:System.Activities.WorkflowApplication> obsługą programu.</span><span class="sxs-lookup"><span data-stu-id="910a3-105">This topic provides as overview of using <xref:System.Activities.WorkflowIdentity> with <xref:System.Activities.WorkflowApplication> hosting.</span></span> <span data-ttu-id="910a3-106">Aby uzyskać informacje na temat wykonywania operacji równoległych w definicjach przepływu pracy w usłudze przepływu pracy, zobacz [obok siebie przechowywanie wersji obok siebie w obszarze WorkflowServiceHost](../wcf/feature-details/side-by-side-versioning-in-workflowservicehost.md).</span><span class="sxs-lookup"><span data-stu-id="910a3-106">For information on side-by-side execution of workflow definitions in a workflow service, see [Side by Side Versioning in WorkflowServiceHost](../wcf/feature-details/side-by-side-versioning-in-workflowservicehost.md).</span></span> <span data-ttu-id="910a3-107">Aby uzyskać informacje na temat aktualizacji dynamicznej, zobacz [Aktualizacja dynamiczna](dynamic-update.md).</span><span class="sxs-lookup"><span data-stu-id="910a3-107">For information on dynamic update, see [Dynamic Update](dynamic-update.md).</span></span>

## <a name="in-this-topic"></a><span data-ttu-id="910a3-108">W tym temacie:</span><span class="sxs-lookup"><span data-stu-id="910a3-108">In this topic</span></span>

- [<span data-ttu-id="910a3-109">Korzystanie z właściwości WorkflowIdentity</span><span class="sxs-lookup"><span data-stu-id="910a3-109">Using WorkflowIdentity</span></span>](using-workflowidentity-and-versioning.md#UsingWorkflowIdentity)

  - [<span data-ttu-id="910a3-110">Wykonywanie równoczesne przy użyciu właściwości WorkflowIdentity</span><span class="sxs-lookup"><span data-stu-id="910a3-110">Side-by-side Execution using WorkflowIdentity</span></span>](using-workflowidentity-and-versioning.md#SxS)

- [<span data-ttu-id="910a3-111">Uaktualnianie baz danych trwałości .NET Framework 4 w celu obsługi wersji przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="910a3-111">Upgrading .NET Framework 4 Persistence Databases to Support Workflow Versioning</span></span>](using-workflowidentity-and-versioning.md#UpdatingWF4PersistenceDatabases)

  - [<span data-ttu-id="910a3-112">Aby uaktualnić schemat bazy danych</span><span class="sxs-lookup"><span data-stu-id="910a3-112">To upgrade the database schema</span></span>](using-workflowidentity-and-versioning.md#ToUpgrade)

## <a name="using-workflowidentity"></a><a name="UsingWorkflowIdentity"></a><span data-ttu-id="910a3-113">Korzystanie z właściwości WorkflowIdentity</span><span class="sxs-lookup"><span data-stu-id="910a3-113">Using WorkflowIdentity</span></span>

<span data-ttu-id="910a3-114">Aby użyć <xref:System.Activities.WorkflowIdentity> , Utwórz wystąpienie, skonfiguruj je i skojarz z <xref:System.Activities.WorkflowApplication> wystąpieniem.</span><span class="sxs-lookup"><span data-stu-id="910a3-114">To use <xref:System.Activities.WorkflowIdentity>, create an instance, configure it, and associate it with a <xref:System.Activities.WorkflowApplication> instance.</span></span> <span data-ttu-id="910a3-115"><xref:System.Activities.WorkflowIdentity>Wystąpienie zawiera trzy tożsamości informacji.</span><span class="sxs-lookup"><span data-stu-id="910a3-115">A <xref:System.Activities.WorkflowIdentity> instance contains three identifying pieces of information.</span></span> <span data-ttu-id="910a3-116"><xref:System.Activities.WorkflowIdentity.Name%2A>i <xref:System.Activities.WorkflowIdentity.Version%2A> zawiera nazwę i <xref:System.Version> i są wymagane i <xref:System.Activities.WorkflowIdentity.Package%2A> jest opcjonalne i może służyć do określenia dodatkowego ciągu zawierającego informacje takie jak nazwa zestawu lub inne żądane informacje.</span><span class="sxs-lookup"><span data-stu-id="910a3-116"><xref:System.Activities.WorkflowIdentity.Name%2A> and <xref:System.Activities.WorkflowIdentity.Version%2A> contain a name and a <xref:System.Version> and are required, and <xref:System.Activities.WorkflowIdentity.Package%2A> is optional and can be used to specify an additional string containing information such as assembly name or other desired information.</span></span> <span data-ttu-id="910a3-117"><xref:System.Activities.WorkflowIdentity>Jest unikatowa, jeśli którykolwiek z jego trzech właściwości różni się od innego <xref:System.Activities.WorkflowIdentity> .</span><span class="sxs-lookup"><span data-stu-id="910a3-117">A <xref:System.Activities.WorkflowIdentity> is unique if any of its three properties are different from another <xref:System.Activities.WorkflowIdentity>.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="910a3-118">A <xref:System.Activities.WorkflowIdentity> nie powinna zawierać żadnych informacji umożliwiających identyfikację użytkownika.</span><span class="sxs-lookup"><span data-stu-id="910a3-118">A <xref:System.Activities.WorkflowIdentity> should not contain any personally identifiable information (PII).</span></span> <span data-ttu-id="910a3-119">Informacje o <xref:System.Activities.WorkflowIdentity> użytym do utworzenia wystąpienia są emitowane do wszelkich skonfigurowanych usług śledzenia w kilku różnych punktach cyklu życia działania przez środowisko uruchomieniowe.</span><span class="sxs-lookup"><span data-stu-id="910a3-119">Information about the <xref:System.Activities.WorkflowIdentity> used to create an instance is emitted to any configured tracking services at several different points of the activity life-cycle by the runtime.</span></span> <span data-ttu-id="910a3-120">Śledzenie WF nie ma żadnego mechanizmu ukrywania danych osobowych (poufne dane użytkownika).</span><span class="sxs-lookup"><span data-stu-id="910a3-120">WF Tracking does not have any mechanism to hide PII (sensitive user data).</span></span> <span data-ttu-id="910a3-121">W związku z tym <xref:System.Activities.WorkflowIdentity> wystąpienie nie powinno zawierać żadnych danych osobowych, ponieważ będzie emitowane przez środowisko uruchomieniowe w celu śledzenia rekordów i może być widoczne dla każdego, kto ma dostęp do wyświetlania rekordów śledzenia.</span><span class="sxs-lookup"><span data-stu-id="910a3-121">Therefore, a <xref:System.Activities.WorkflowIdentity> instance should not contain any PII data as it will be emitted by the runtime in tracking records and may be visible to anyone with access to view the tracking records.</span></span>

<span data-ttu-id="910a3-122">W poniższym przykładzie <xref:System.Activities.WorkflowIdentity> jest tworzona i skojarzona z wystąpieniem przepływu pracy utworzonego przy użyciu `MortgageWorkflow` definicji przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="910a3-122">In the following example, a <xref:System.Activities.WorkflowIdentity> is created and associated with an instance of a workflow created using a `MortgageWorkflow` workflow definition.</span></span>

```csharp
WorkflowIdentity identityV1 = new WorkflowIdentity
{
    Name = "MortgageWorkflow v1",
    Version = new Version(1, 0, 0, 0)
};

WorkflowApplication wfApp = new WorkflowApplication(new MortgageWorkflow(), identity);

// Configure the WorkflowApplication with persistence and desired workflow event handlers.
ConfigureWorkflowApplication(wfApp);

// Run the workflow.
wfApp.Run();
```

<span data-ttu-id="910a3-123">Po ponownym załadowaniu i wznowieniu przepływu pracy, <xref:System.Activities.WorkflowIdentity> który jest skonfigurowany do dopasowania do <xref:System.Activities.WorkflowIdentity> wystąpienia utrwalonego przepływu pracy, musi być używany.</span><span class="sxs-lookup"><span data-stu-id="910a3-123">When reloading and resuming a workflow, a <xref:System.Activities.WorkflowIdentity> that is configured to match the <xref:System.Activities.WorkflowIdentity> of the persisted workflow instance must be used.</span></span>

```csharp
WorkflowApplication wfApp = new WorkflowApplication(new MortgageWorkflow(), identityV1);

// Configure the WorkflowApplication with persistence and desired workflow event handlers.
ConfigureWorkflowApplication(wfApp);

// Load the workflow.
wfApp.Load(instanceId);

// Resume the workflow...
```

<span data-ttu-id="910a3-124">Jeśli <xref:System.Activities.WorkflowIdentity> używany podczas ponownego ładowania wystąpienia przepływu pracy nie jest zgodny z utrwalonym <xref:System.Activities.WorkflowIdentity> , <xref:System.Activities.VersionMismatchException> zostanie zgłoszony.</span><span class="sxs-lookup"><span data-stu-id="910a3-124">If the <xref:System.Activities.WorkflowIdentity> used when reloading the workflow instance does not match the persisted <xref:System.Activities.WorkflowIdentity>, a <xref:System.Activities.VersionMismatchException> is thrown.</span></span> <span data-ttu-id="910a3-125">W poniższym przykładzie podjęto próbę załadowania `MortgageWorkflow` wystąpienia, które było utrwalone w poprzednim przykładzie.</span><span class="sxs-lookup"><span data-stu-id="910a3-125">In the following example a load attempt is made on the `MortgageWorkflow` instance that was persisted in the previous example.</span></span> <span data-ttu-id="910a3-126">Ta próba załadowania została wykonana przy użyciu <xref:System.Activities.WorkflowIdentity> skonfigurowanej dla nowszej wersji przepływu pracy hipotecznej, która nie jest zgodna z utrwalonym wystąpieniem.</span><span class="sxs-lookup"><span data-stu-id="910a3-126">This load attempt is made using a <xref:System.Activities.WorkflowIdentity> configured for a newer version of the mortgage workflow that does not match the persisted instance.</span></span>

```csharp
WorkflowApplication wfApp = new WorkflowApplication(new MortgageWorkflow_v2(), identityV2);

// Configure the WorkflowApplication with persistence and desired workflow event handlers.
ConfigureWorkflowApplication(wfApp);

// Attempt to load the workflow instance.
wfApp.Load(instanceId);

// Resume the workflow...
```

<span data-ttu-id="910a3-127">Gdy poprzedni kod jest wykonywany, <xref:System.Activities.VersionMismatchException> zgłaszane są następujące elementy.</span><span class="sxs-lookup"><span data-stu-id="910a3-127">When the previous code is executed, the following <xref:System.Activities.VersionMismatchException> is thrown.</span></span>

```output
The WorkflowIdentity ('MortgageWorkflow v1; Version=1.0.0.0') of the loaded instance does not match the WorkflowIdentity ('MortgageWorkflow v2; Version=2.0.0.0') of the provided workflow definition. The instance can be loaded using a different definition, or updated using Dynamic Update.
```

### <a name="side-by-side-execution-using-workflowidentity"></a><a name="SxS"></a><span data-ttu-id="910a3-128">Wykonywanie równoczesne przy użyciu właściwości WorkflowIdentity</span><span class="sxs-lookup"><span data-stu-id="910a3-128">Side-by-side Execution using WorkflowIdentity</span></span>

<span data-ttu-id="910a3-129"><xref:System.Activities.WorkflowIdentity>może służyć do ułatwienia wykonywania wielu wersji przepływu pracy obok siebie.</span><span class="sxs-lookup"><span data-stu-id="910a3-129"><xref:System.Activities.WorkflowIdentity> can be used to facilitate the execution of multiple versions of a workflow side-by-side.</span></span> <span data-ttu-id="910a3-130">Jednym z typowych scenariuszy jest zmiana wymagań firmy na długotrwały przepływ pracy.</span><span class="sxs-lookup"><span data-stu-id="910a3-130">One common scenario is changing business requirements on a long-running workflow.</span></span> <span data-ttu-id="910a3-131">Podczas wdrażania zaktualizowanej wersji można uruchomić wiele wystąpień przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="910a3-131">Many instances of a workflow could be running when an updated version is deployed.</span></span> <span data-ttu-id="910a3-132">Aplikacja hosta może być skonfigurowana do używania zaktualizowanej definicji przepływu pracy podczas uruchamiania nowych wystąpień i jest odpowiedzialna za aplikację hosta, aby zapewnić prawidłową definicję przepływu pracy podczas wznawiania wystąpień.</span><span class="sxs-lookup"><span data-stu-id="910a3-132">The host application can be configured to use the updated workflow definition when starting new instances, and it is the responsibility of the host application to provide the correct workflow definition when resuming instances.</span></span> <span data-ttu-id="910a3-133"><xref:System.Activities.WorkflowIdentity>może służyć do identyfikowania i dostarczania pasującej definicji przepływu pracy podczas wznawiania wystąpień przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="910a3-133"><xref:System.Activities.WorkflowIdentity> can be used to identify and supply the matching workflow definition when resuming workflow instances.</span></span>

<span data-ttu-id="910a3-134">Aby można było pobrać <xref:System.Activities.WorkflowIdentity> wystąpienie utrwalonego przepływu pracy, <xref:System.Activities.WorkflowApplication.GetInstance%2A> Metoda jest używana.</span><span class="sxs-lookup"><span data-stu-id="910a3-134">To retrieve the <xref:System.Activities.WorkflowIdentity> of a persisted workflow instance, the <xref:System.Activities.WorkflowApplication.GetInstance%2A> method is used.</span></span> <span data-ttu-id="910a3-135"><xref:System.Activities.WorkflowApplication.GetInstance%2A>Metoda przyjmuje <xref:System.Activities.WorkflowApplication.Id%2A> wystąpienie utrwalonego przepływu pracy i <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> zawiera wystąpienie utrwalane i zwraca wartość <xref:System.Activities.WorkflowApplicationInstance> .</span><span class="sxs-lookup"><span data-stu-id="910a3-135">The <xref:System.Activities.WorkflowApplication.GetInstance%2A> method takes the <xref:System.Activities.WorkflowApplication.Id%2A> of the persisted workflow instance and the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> that contains the persisted instance and returns a <xref:System.Activities.WorkflowApplicationInstance>.</span></span> <span data-ttu-id="910a3-136">A <xref:System.Activities.WorkflowApplicationInstance> zawiera informacje o utrwalonym wystąpieniu przepływu pracy, w tym jego skojarzone <xref:System.Activities.WorkflowIdentity> .</span><span class="sxs-lookup"><span data-stu-id="910a3-136">A <xref:System.Activities.WorkflowApplicationInstance> contains information about a persisted workflow instance, including its associated <xref:System.Activities.WorkflowIdentity>.</span></span> <span data-ttu-id="910a3-137">Ta skojarzona <xref:System.Activities.WorkflowIdentity> może być używana przez hosta w celu dostarczenia prawidłowej definicji przepływu pracy podczas ładowania i wznawiania wystąpienia przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="910a3-137">This associated <xref:System.Activities.WorkflowIdentity> can be used by the host to supply the correct workflow definition when loading and resuming the workflow instance.</span></span>

> [!NOTE]
> <span data-ttu-id="910a3-138">Wartość null <xref:System.Activities.WorkflowIdentity> jest prawidłowa i może być używana przez hosta w celu mapowania wystąpień, które zostały utrwalone bez skojarzonych z <xref:System.Activities.WorkflowIdentity> prawidłową definicją przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="910a3-138">A null <xref:System.Activities.WorkflowIdentity> is valid, and can be used by the host to map instances that were persisted with no associated <xref:System.Activities.WorkflowIdentity> to the proper workflow definition.</span></span> <span data-ttu-id="910a3-139">Ten scenariusz może wystąpić, gdy aplikacja przepływu pracy nie została początkowo zapisywana przy użyciu wersji przepływu pracy lub gdy aplikacja jest uaktualniana z .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="910a3-139">This scenario can occur when a workflow application was not initially written with workflow versioning, or when an application is upgraded from .NET Framework 4.</span></span> <span data-ttu-id="910a3-140">Aby uzyskać więcej informacji, zobacz [uaktualnianie baz danych trwałości .NET Framework 4 w celu zapewnienia obsługi wersji przepływu pracy](using-workflowidentity-and-versioning.md#UpdatingWF4PersistenceDatabases).</span><span class="sxs-lookup"><span data-stu-id="910a3-140">For more information, see [Upgrading .NET Framework 4 Persistence Databases to Support Workflow Versioning](using-workflowidentity-and-versioning.md#UpdatingWF4PersistenceDatabases).</span></span>

<span data-ttu-id="910a3-141">W poniższym przykładzie `Dictionary<WorkflowIdentity, Activity>` jest używany do kojarzenia <xref:System.Activities.WorkflowIdentity> wystąpień z pasującymi definicjami przepływów pracy, a przepływ pracy jest uruchamiany przy użyciu `MortgageWorkflow` definicji przepływu pracy, która jest skojarzona z `identityV1` <xref:System.Activities.WorkflowIdentity> .</span><span class="sxs-lookup"><span data-stu-id="910a3-141">In the following example a `Dictionary<WorkflowIdentity, Activity>` is used to associate <xref:System.Activities.WorkflowIdentity> instances with their matching workflow definitions, and a workflow is started using the `MortgageWorkflow` workflow definition, which is associated with the `identityV1` <xref:System.Activities.WorkflowIdentity>.</span></span>

```csharp
WorkflowIdentity identityV1 = new WorkflowIdentity
{
    Name = "MortgageWorkflow v1",
    Version = new Version(1, 0, 0, 0)
};

WorkflowIdentity identityV2 = new WorkflowIdentity
{
    Name = "MortgageWorkflow v2",
    Version = new Version(2, 0, 0, 0)
};

Dictionary<WorkflowIdentity, Activity> WorkflowVersionMap = new Dictionary<WorkflowIdentity, Activity>();
WorkflowVersionMap.Add(identityV1, new MortgageWorkflow());
WorkflowVersionMap.Add(identityV2, new MortgageWorkflow_v2());

WorkflowApplication wfApp = new WorkflowApplication(new MortgageWorkflow(), identityV1);

// Configure the WorkflowApplication with persistence and desired workflow event handlers.
ConfigureWorkflowApplication(wfApp);

// Run the workflow.
wfApp.Run();
```

<span data-ttu-id="910a3-142">W poniższym przykładzie informacje o utrwalonym wystąpieniu przepływu pracy z poprzedniego przykładu są pobierane przez wywołanie <xref:System.Activities.WorkflowApplication.GetInstance%2A> , a utrwalone <xref:System.Activities.WorkflowIdentity> informacje są używane do pobierania pasującej definicji przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="910a3-142">In the following example, information about the persisted workflow instance from the previous example is retrieved by calling <xref:System.Activities.WorkflowApplication.GetInstance%2A>, and the persisted <xref:System.Activities.WorkflowIdentity> information is used to retrieve the matching workflow definition.</span></span> <span data-ttu-id="910a3-143">Te informacje służą do konfigurowania <xref:System.Activities.WorkflowApplication> , a następnie ładowania przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="910a3-143">This information is used to configure the <xref:System.Activities.WorkflowApplication>, and then the workflow is loaded.</span></span> <span data-ttu-id="910a3-144">Należy zauważyć, że ponieważ <xref:System.Activities.WorkflowApplication.Load%2A> Przeciążenie, które pobiera <xref:System.Activities.WorkflowApplicationInstance> , jest używane, <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> który został skonfigurowany na, <xref:System.Activities.WorkflowApplicationInstance> jest używany przez <xref:System.Activities.WorkflowApplication> i dlatego jego <xref:System.Activities.WorkflowApplication.InstanceStore%2A> właściwości nie trzeba konfigurować.</span><span class="sxs-lookup"><span data-stu-id="910a3-144">Note that because the <xref:System.Activities.WorkflowApplication.Load%2A> overload that takes the <xref:System.Activities.WorkflowApplicationInstance> is used, the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> that was configured on the <xref:System.Activities.WorkflowApplicationInstance> is used by the <xref:System.Activities.WorkflowApplication> and therefore its <xref:System.Activities.WorkflowApplication.InstanceStore%2A> property does not need to be configured.</span></span>

> [!NOTE]
> <span data-ttu-id="910a3-145">Jeśli <xref:System.Activities.WorkflowApplication.InstanceStore%2A> Właściwość jest ustawiona, musi być ustawiona z tym samym wystąpieniem, które jest <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> używane przez <xref:System.Activities.WorkflowApplicationInstance> lub w przeciwnym razie <xref:System.ArgumentException> zostanie wygenerowany z następującym komunikatem: `The instance is configured with a different InstanceStore than this WorkflowApplication.` .</span><span class="sxs-lookup"><span data-stu-id="910a3-145">If the <xref:System.Activities.WorkflowApplication.InstanceStore%2A> property is set, it must be set with the same <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> instance used by the <xref:System.Activities.WorkflowApplicationInstance> or else an <xref:System.ArgumentException> will be thrown with the following message: `The instance is configured with a different InstanceStore than this WorkflowApplication.`.</span></span>

```csharp
// Get the WorkflowApplicationInstance of the desired workflow from the specified
// SqlWorkflowInstanceStore.
WorkflowApplicationInstance instance = WorkflowApplication.GetInstance(instanceId, store);

// Use the persisted WorkflowIdentity to retrieve the correct workflow
// definition from the dictionary.
Activity definition = WorkflowVersionMap[instance.DefinitionIdentity];

WorkflowApplication wfApp = new WorkflowApplication(definition, instance.DefinitionIdentity);

// Configure the WorkflowApplication with persistence and desired workflow event handlers.
ConfigureWorkflowApplication(wfApp);

// Load the persisted workflow instance.
wfApp.Load(instance);

// Resume the workflow...
```

## <a name="upgrading-net-framework-4-persistence-databases-to-support-workflow-versioning"></a><a name="UpdatingWF4PersistenceDatabases"></a><span data-ttu-id="910a3-146">Uaktualnianie baz danych trwałości .NET Framework 4 w celu obsługi wersji przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="910a3-146">Upgrading .NET Framework 4 Persistence Databases to Support Workflow Versioning</span></span>

<span data-ttu-id="910a3-147">Skrypt bazy danych SqlWorkflowInstanceStoreSchemaUpgrade. SQL jest dostarczany w celu uaktualnienia baz danych trwałości utworzonych przy użyciu skryptów bazy danych .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="910a3-147">A SqlWorkflowInstanceStoreSchemaUpgrade.sql database script is provided to upgrade persistence databases created using the .NET Framework 4 database scripts.</span></span> <span data-ttu-id="910a3-148">Ten skrypt aktualizuje bazy danych programu w celu obsługi nowych możliwości przechowywania wersji wprowadzonych w .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="910a3-148">This script updates the databases to support the new versioning capabilities introduced in .NET Framework 4.5.</span></span> <span data-ttu-id="910a3-149">Wszystkie wystąpienia utrwalonych przepływów pracy w bazach danych otrzymują domyślne wartości wersji, a następnie mogą uczestniczyć w wykonywaniu równoczesnym i aktualizacji dynamicznej.</span><span class="sxs-lookup"><span data-stu-id="910a3-149">Any persisted workflow instances in the databases are given default versioning values, and can then participate in side-by-side execution and dynamic update.</span></span>

<span data-ttu-id="910a3-150">Jeśli aplikacja przepływu pracy .NET Framework 4,5 próbuje wykonać wszystkie operacje trwałości korzystające z nowych funkcji przechowywania wersji w bazie danych trwałości, która nie została uaktualniona przy użyciu dostarczonego skryptu, <xref:System.Runtime.DurableInstancing.InstancePersistenceCommandException> zgłaszany jest komunikat podobny do następującego.</span><span class="sxs-lookup"><span data-stu-id="910a3-150">If a .NET Framework 4.5 workflow application attempts any persistence operations that use the new versioning features on a persistence database which has not been upgraded using the provided script, an <xref:System.Runtime.DurableInstancing.InstancePersistenceCommandException> is thrown with a message similar to the following message.</span></span>

```output
The SqlWorkflowInstanceStore has a database version of '4.0.0.0'. InstancePersistenceCommand 'System.Activities.DurableInstancing.CreateWorkflowOwnerWithIdentityCommand' cannot be run against this database version.  Please upgrade the database to '4.5.0.0'.
```

### <a name="to-upgrade-the-database-schema"></a><a name="ToUpgrade"></a><span data-ttu-id="910a3-151">Aby uaktualnić schemat bazy danych</span><span class="sxs-lookup"><span data-stu-id="910a3-151">To upgrade the database schema</span></span>

1. <span data-ttu-id="910a3-152">Otwórz SQL Server Management Studio i nawiąż połączenie z serwerem bazy danych trwałości, na przykład **.\SQLEXPRESS**.</span><span class="sxs-lookup"><span data-stu-id="910a3-152">Open SQL Server Management Studio and connect to the persistence database server, for example **.\SQLEXPRESS**.</span></span>

2. <span data-ttu-id="910a3-153">Wybierz polecenie **Otwórz**, **plik** z menu **plik** .</span><span class="sxs-lookup"><span data-stu-id="910a3-153">Choose **Open**, **File** from the **File** menu.</span></span> <span data-ttu-id="910a3-154">Przejdź do następującego folderu:`C:\Windows\Microsoft.NET\Framework\v4.0.30319\sql\en`</span><span class="sxs-lookup"><span data-stu-id="910a3-154">Browse to the following folder: `C:\Windows\Microsoft.NET\Framework\v4.0.30319\sql\en`</span></span>

3. <span data-ttu-id="910a3-155">Wybierz **SqlWorkflowInstanceStoreSchemaUpgrade. SQL** , a następnie kliknij przycisk **Otwórz**.</span><span class="sxs-lookup"><span data-stu-id="910a3-155">Select **SqlWorkflowInstanceStoreSchemaUpgrade.sql** and click **Open**.</span></span>

4. <span data-ttu-id="910a3-156">Wybierz nazwę bazy danych trwałości z listy rozwijanej **dostępne bazy danych** .</span><span class="sxs-lookup"><span data-stu-id="910a3-156">Select the name of the persistence database in the **Available Databases** drop-down.</span></span>

5. <span data-ttu-id="910a3-157">Wybierz polecenie **Execute** z menu **zapytanie** .</span><span class="sxs-lookup"><span data-stu-id="910a3-157">Choose **Execute** from the **Query** menu.</span></span>

<span data-ttu-id="910a3-158">Po zakończeniu wykonywania zapytania schemat bazy danych zostanie uaktualniony i w razie potrzeby można wyświetlić domyślną tożsamość przepływu pracy przypisaną do wystąpień utrwalonych przepływów pracy.</span><span class="sxs-lookup"><span data-stu-id="910a3-158">When the query completes, the database schema is upgraded, and if desired, you can view the default workflow identity that was assigned to the persisted workflow instances.</span></span> <span data-ttu-id="910a3-159">Rozwiń swoją bazę danych trwałości w węźle **bazy danych** **Eksplorator obiektów**, a następnie rozwiń węzeł **widoki** .</span><span class="sxs-lookup"><span data-stu-id="910a3-159">Expand your persistence database in the **Databases** node of the **Object Explorer**, and then expand the **Views** node.</span></span> <span data-ttu-id="910a3-160">Kliknij prawym przyciskiem myszy pozycję **System. Activities. DurableInstancing. instances** i wybierz **pozycję Wybierz pierwsze 1000 wierszy**.</span><span class="sxs-lookup"><span data-stu-id="910a3-160">Right-click **System.Activities.DurableInstancing.Instances** and choose **Select Top 1000 Rows**.</span></span> <span data-ttu-id="910a3-161">Przewiń do końca kolumn i zwróć uwagę, że do widoku dodano sześć dodatkowych kolumn: **IdentityName**, **IdentityPackage**, **Build**, **główna**, **pomocnicza**i **poprawka**.</span><span class="sxs-lookup"><span data-stu-id="910a3-161">Scroll to end of the columns and note that there are six additional columns added to the view: **IdentityName**, **IdentityPackage**, **Build**, **Major**, **Minor**, and **Revision**.</span></span> <span data-ttu-id="910a3-162">Wszystkie utrwalone przepływy pracy będą mieć wartość **null** dla tych pól reprezentujących pustą tożsamość przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="910a3-162">Any persisted workflows will have a value of **NULL** for these fields, representing a null workflow identity.</span></span>
