---
title: <commonParameters>
ms.date: 03/30/2017
ms.assetid: ffc20832-34d6-4622-8174-81924fd53514
ms.openlocfilehash: d4b912d003af201b19697854a67943e3d87e3734
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90558488"
---
# \<commonParameters>
<span data-ttu-id="c020d-101">Reprezentuje kolekcję parametrów, które są globalnie używane w wielu usługach.</span><span class="sxs-lookup"><span data-stu-id="c020d-101">Represents a collection of parameters that are used globally across multiple services.</span></span> <span data-ttu-id="c020d-102">Ta kolekcja zazwyczaj obejmuje parametry połączenia z bazą danych, które mogą być współużytkowane przez trwałe usługi.</span><span class="sxs-lookup"><span data-stu-id="c020d-102">This collection will typically include the database connection string that might be shared by durable services.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowRuntime>**](workflowruntime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<commonParameters>**  
  
## <a name="syntax"></a><span data-ttu-id="c020d-103">Składnia</span><span class="sxs-lookup"><span data-stu-id="c020d-103">Syntax</span></span>  
  
```xml  
<workflowRuntime>
  <commonParameters>
    <add name="String"
         value="String" />
  </commonParameters>
</workflowRuntime>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c020d-104">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="c020d-104">Attributes and Elements</span></span>  
 <span data-ttu-id="c020d-105">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="c020d-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c020d-106">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="c020d-106">Attributes</span></span>  
 <span data-ttu-id="c020d-107">Brak.</span><span class="sxs-lookup"><span data-stu-id="c020d-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c020d-108">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="c020d-108">Child Elements</span></span>  
  
|<span data-ttu-id="c020d-109">Element</span><span class="sxs-lookup"><span data-stu-id="c020d-109">Element</span></span>|<span data-ttu-id="c020d-110">Opis</span><span class="sxs-lookup"><span data-stu-id="c020d-110">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-of-commonparameters.md)|<span data-ttu-id="c020d-111">Dodaje parę nazwa-wartość wspólnych parametrów używanych przez usługi do kolekcji.</span><span class="sxs-lookup"><span data-stu-id="c020d-111">Adds a name-value pair of common parameters used by services to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c020d-112">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="c020d-112">Parent Elements</span></span>  
  
|<span data-ttu-id="c020d-113">Element</span><span class="sxs-lookup"><span data-stu-id="c020d-113">Element</span></span>|<span data-ttu-id="c020d-114">Opis</span><span class="sxs-lookup"><span data-stu-id="c020d-114">Description</span></span>|  
|-------------|-----------------|  
|[\<workflowRuntime>](workflowruntime.md)|<span data-ttu-id="c020d-115">Określa ustawienia dla wystąpienia programu <xref:System.Workflow.Runtime.WorkflowRuntime> do hostowania usług Windows Communication Foundation opartych na przepływie pracy (WCF).</span><span class="sxs-lookup"><span data-stu-id="c020d-115">Specifies settings for an instance of <xref:System.Workflow.Runtime.WorkflowRuntime> for hosting workflow-based Windows Communication Foundation (WCF) services.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c020d-116">Uwagi</span><span class="sxs-lookup"><span data-stu-id="c020d-116">Remarks</span></span>  
 <span data-ttu-id="c020d-117">`<commonParameters>`Element definiuje wszystkie parametry, które są używane globalnie w wielu usługach, na przykład `ConnectionString` podczas korzystania z <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService> .</span><span class="sxs-lookup"><span data-stu-id="c020d-117">The `<commonParameters>` element defines any parameters that are used globally across multiple services, for example `ConnectionString` when using the <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c020d-118">Usługa śledzenia SQL nie będzie w sposób ciągły używać `ConnectionString` wartości, jeśli została określona w `<commonParameters>` sekcji.</span><span class="sxs-lookup"><span data-stu-id="c020d-118">SQL Tracking service does not consistently use the `ConnectionString` value if it is specified in the `<commonParameters>` section.</span></span> <span data-ttu-id="c020d-119">Niektóre jego operacje, takie jak pobieranie `StateMachineWorkflowInstance.StateHistory` właściwości, mogą zakończyć się niepowodzeniem.</span><span class="sxs-lookup"><span data-stu-id="c020d-119">Some of its operations such as retrieving the `StateMachineWorkflowInstance.StateHistory` property may fail.</span></span> <span data-ttu-id="c020d-120">Aby to obejść, określ `ConnectionString` atrybut w sekcji konfiguracji dla dostawcy śledzenia, jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="c020d-120">To workaround this, specify the `ConnectionString` attribute in the configuration section for tracking provider, as indicated in the following example.</span></span>  

```xml  
<add
type="System.Workflow.Runtime.Tracking.SqlTrackingService, System.Workflow.Runtime, Version=3.0.00000.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"
ConnectionString="Data Source=localhost;Initial Catalog=Partner20WFTP;Integrated Security=True;" />
```  
  
 <span data-ttu-id="c020d-121">W przypadku usług, które zatwierdzają partie pracy do magazynów trwałości, takich jak <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> i <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService> , można umożliwić im ponawianie transakcji przy użyciu `EnableRetries` parametru, jak pokazano w następującym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="c020d-121">For services that commit work batches to persistence stores, such as <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> and <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, you can enable them to retry their transaction by using the `EnableRetries` parameter as shown in the following example:</span></span>  
  
```xml  
<workflowRuntime name="SampleApplication"
                 unloadOnIdle="false">
  <commonParameters>
    <add name="ConnectionString"
         value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />
    <add name="EnableRetries"
         value="True" />
  </commonParameters>
  <services>
    <add type="System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService, System.Workflow.Runtime,
               Version=3.0.00000.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"
         enableRetries="False" />
  </services>
</workflowRuntime>
```  
  
 <span data-ttu-id="c020d-122">Należy zauważyć, że `EnableRetries` parametr można ustawić na poziomie globalnym (jak pokazano w sekcji *Parametry* ) lub dla poszczególnych usług, które obsługują `EnableRetries` (jak pokazano w sekcji *usługi* ).</span><span class="sxs-lookup"><span data-stu-id="c020d-122">Notice that the `EnableRetries` parameter can be set either at a global level (as shown in the *CommonParameters* section) or for individual services that support `EnableRetries` (as shown in the *Services* section).</span></span>  
  
 <span data-ttu-id="c020d-123">Poniższy przykładowy kod pokazuje, jak zmienić wspólne parametry programowo:</span><span class="sxs-lookup"><span data-stu-id="c020d-123">The following sample code shows how to change the common parameters programmatically:</span></span>
  
```csharp  
Configuration config = WebConfigurationManager.OpenWebConfiguration("/Workflow", "Default Web Site", null, "localhost");
var wfruntime = config.GetSection("WorkflowRuntime") as WorkflowRuntimeSection;  
NameValueConfigurationCollection commonParameters = wfruntime.CommonParameters;
commonParameters["ConnectionString"].Value="another connection string";  
config.Save();  
```  
  
 <span data-ttu-id="c020d-124">Aby uzyskać więcej informacji o korzystaniu z pliku konfiguracji w celu sterowania zachowaniem <xref:System.Workflow.Runtime.WorkflowRuntime> obiektu Windows Workflow Foundation aplikacji hosta, zobacz [pliki konfiguracji przepływu pracy](/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="c020d-124">For more information about using a configuration file to control the behavior of a <xref:System.Workflow.Runtime.WorkflowRuntime> object of a Windows Workflow Foundation host application, see [Workflow Configuration Files](/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c020d-125">Przykład</span><span class="sxs-lookup"><span data-stu-id="c020d-125">Example</span></span>  
  
```xml  
<commonParameters>
   <add name="ConnectionString"
        value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />
   <add name="EnableRetries"
        value="true" />
</commonParameters>
```  
  
## <a name="see-also"></a><span data-ttu-id="c020d-126">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="c020d-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>
- <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>
- <xref:System.Workflow.Runtime.WorkflowRuntime>
- <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService>
- <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>
- <span data-ttu-id="c020d-127">[Pliki konfiguracji przepływu pracy](/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="c020d-127">[Workflow Configuration Files](/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>
- [\<add>](add-of-commonparameters.md)
