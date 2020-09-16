---
title: <add> dla <services>
ms.date: 03/30/2017
ms.assetid: 6bdc4590-aa9c-4ec8-9345-879d780cd141
ms.openlocfilehash: 26d43460f225cb57946aca80e3d1e3fde2ea1100
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557713"
---
# <a name="add-of-services"></a><span data-ttu-id="b3156-102">\<add> dla \<services></span><span class="sxs-lookup"><span data-stu-id="b3156-102">\<add> of \<services></span></span>
<span data-ttu-id="b3156-103">Określa ustawienia dla wystąpienia programu <xref:System.Workflow.Runtime.WorkflowRuntime> do hostowania usług Windows Communication Foundation opartych na przepływie pracy (WCF).</span><span class="sxs-lookup"><span data-stu-id="b3156-103">Specifies settings for an instance of <xref:System.Workflow.Runtime.WorkflowRuntime> for hosting workflow-based Windows Communication Foundation (WCF) services.</span></span> <span data-ttu-id="b3156-104">Ten element jest typu <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> .</span><span class="sxs-lookup"><span data-stu-id="b3156-104">This element is of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowRuntime>**](workflowruntime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services-of-workflowruntime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="b3156-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="b3156-105">Syntax</span></span>  
  
```xml  
<workflowRuntime>
  <services>
    <add type="String" />
  </services>
</workflowRuntime>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b3156-106">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="b3156-106">Attributes and Elements</span></span>  
 <span data-ttu-id="b3156-107">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="b3156-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b3156-108">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="b3156-108">Attributes</span></span>  
  
|<span data-ttu-id="b3156-109">Atrybut</span><span class="sxs-lookup"><span data-stu-id="b3156-109">Attribute</span></span>|<span data-ttu-id="b3156-110">Opis</span><span class="sxs-lookup"><span data-stu-id="b3156-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b3156-111">typ</span><span class="sxs-lookup"><span data-stu-id="b3156-111">type</span></span>|<span data-ttu-id="b3156-112">Ciąg określający nazwę typu kwalifikowanego zestawu usługi do zainicjowania.</span><span class="sxs-lookup"><span data-stu-id="b3156-112">A string that specifies the assembly-qualified type name of the service to be initialized.</span></span> <span data-ttu-id="b3156-113">Określona usługa musi być zgodna z określonymi regułami dotyczącymi podpisów ich konstruktorów.</span><span class="sxs-lookup"><span data-stu-id="b3156-113">The service specified must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="b3156-114">Aby uzyskać więcej informacji, zobacz <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="b3156-114">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b3156-115">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="b3156-115">Child Elements</span></span>  
 <span data-ttu-id="b3156-116">Brak.</span><span class="sxs-lookup"><span data-stu-id="b3156-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b3156-117">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="b3156-117">Parent Elements</span></span>  
  
|<span data-ttu-id="b3156-118">Element</span><span class="sxs-lookup"><span data-stu-id="b3156-118">Element</span></span>|<span data-ttu-id="b3156-119">Opis</span><span class="sxs-lookup"><span data-stu-id="b3156-119">Description</span></span>|  
|-------------|-----------------|  
|[\<services>](services-of-workflowruntime.md)|<span data-ttu-id="b3156-120">Kolekcja usług, które zostaną dodane do <xref:System.Workflow.Runtime.WorkflowRuntime> aparatu.</span><span class="sxs-lookup"><span data-stu-id="b3156-120">A collection of services that will be added to the <xref:System.Workflow.Runtime.WorkflowRuntime> engine.</span></span> <span data-ttu-id="b3156-121">Elementy są typu <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> .</span><span class="sxs-lookup"><span data-stu-id="b3156-121">The elements are of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  <span data-ttu-id="b3156-122">Usługi określone w kolekcji zostaną zainicjowane przez aparat środowiska uruchomieniowego przepływu pracy i dodawane do swoich usług, gdy <xref:System.Workflow.Runtime.WorkflowRuntime> zostanie wywołany odpowiedni Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="b3156-122">The services specified in the collection will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="b3156-123">W związku z tym usługi określone w kolekcji muszą przestrzegać pewnych zasad dotyczących podpisów ich konstruktorów.</span><span class="sxs-lookup"><span data-stu-id="b3156-123">Therefore, the services specified in the collection must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="b3156-124">Aby uzyskać więcej informacji, zobacz <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="b3156-124">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b3156-125">Uwagi</span><span class="sxs-lookup"><span data-stu-id="b3156-125">Remarks</span></span>  
 <span data-ttu-id="b3156-126">Usługa określona w tym elemencie zostanie zainicjowana przez aparat środowiska uruchomieniowego przepływu pracy i dodana do jej usług, gdy <xref:System.Workflow.Runtime.WorkflowRuntime> zostanie wywołany odpowiedni Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="b3156-126">The service specified in this element will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="b3156-127">W związku z tym określona usługa musi być zgodna z określonymi regułami dotyczącymi podpisów ich konstruktorów.</span><span class="sxs-lookup"><span data-stu-id="b3156-127">Therefore, the service specified must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="b3156-128">Aby uzyskać więcej informacji, zobacz <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="b3156-128">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b3156-129">Przykład</span><span class="sxs-lookup"><span data-stu-id="b3156-129">Example</span></span>  
  
```xml  
<serviceBehaviors>
  <behavior name="ServiceBehavior">
    <workflowRuntime name="WorkflowServiceHostRuntime"
                     validateOnCreate="true"
                     enablePerformanceCounters="true">
      <services>
        <add type="NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common.TestPersistenceService.FilePersistenceService, NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common" />
      </services>
    </workflowRuntime>
  </behavior>
</serviceBehaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="b3156-130">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="b3156-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>
- <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>
- <xref:System.Workflow.Runtime.WorkflowRuntime>
- <span data-ttu-id="b3156-131">[Pliki konfiguracji przepływu pracy](/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="b3156-131">[Workflow Configuration Files](/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>
