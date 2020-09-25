---
title: <add> dla <services>
ms.date: 03/30/2017
ms.assetid: 6bdc4590-aa9c-4ec8-9345-879d780cd141
ms.openlocfilehash: 31a4d2a5a3baf3d53cf18ab6e37edfaf7acb8540
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204986"
---
# <a name="add-of-services"></a>\<add> dla \<services>

Określa ustawienia dla wystąpienia programu <xref:System.Workflow.Runtime.WorkflowRuntime> do hostowania usług Windows Communication Foundation opartych na przepływie pracy (WCF). Ten element jest typu <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> .  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowRuntime>**](workflowruntime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services-of-workflowruntime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a>Składnia  
  
```xml  
<workflowRuntime>
  <services>
    <add type="String" />
  </services>
</workflowRuntime>
```  
  
## <a name="attributes-and-elements"></a>Atrybuty i elementy  

 W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.  
  
### <a name="attributes"></a>Atrybuty  
  
|Atrybut|Opis|  
|---------------|-----------------|  
|typ|Ciąg określający nazwę typu kwalifikowanego zestawu usługi do zainicjowania. Określona usługa musi być zgodna z określonymi regułami dotyczącymi podpisów ich konstruktorów. Aby uzyskać więcej informacji, zobacz <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.|  
  
### <a name="child-elements"></a>Elementy podrzędne  

 Brak.  
  
### <a name="parent-elements"></a>Elementy nadrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|[\<services>](services-of-workflowruntime.md)|Kolekcja usług, które zostaną dodane do <xref:System.Workflow.Runtime.WorkflowRuntime> aparatu. Elementy są typu <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> .  Usługi określone w kolekcji zostaną zainicjowane przez aparat środowiska uruchomieniowego przepływu pracy i dodawane do swoich usług, gdy <xref:System.Workflow.Runtime.WorkflowRuntime> zostanie wywołany odpowiedni Konstruktor. W związku z tym usługi określone w kolekcji muszą przestrzegać pewnych zasad dotyczących podpisów ich konstruktorów. Aby uzyskać więcej informacji, zobacz <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.|  
  
## <a name="remarks"></a>Uwagi  

 Usługa określona w tym elemencie zostanie zainicjowana przez aparat środowiska uruchomieniowego przepływu pracy i dodana do jej usług, gdy <xref:System.Workflow.Runtime.WorkflowRuntime> zostanie wywołany odpowiedni Konstruktor. W związku z tym określona usługa musi być zgodna z określonymi regułami dotyczącymi podpisów ich konstruktorów. Aby uzyskać więcej informacji, zobacz <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.  
  
## <a name="example"></a>Przykład  
  
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
  
## <a name="see-also"></a>Zobacz też

- <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>
- <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>
- <xref:System.Workflow.Runtime.WorkflowRuntime>
- [Pliki konfiguracji przepływu pracy](/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))
