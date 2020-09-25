---
title: <behavior><serviceBehaviors>przepływu pracy
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 6a4b718a-1b40-4957-935a-f6122819ab3c
ms.openlocfilehash: 14c528746963a3078e0ab377d095414d2fca0dbe
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189620"
---
# <a name="behavior-of-servicebehaviors-of-workflow"></a><span data-ttu-id="45702-102">\<behavior>\<serviceBehaviors>przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="45702-102">\<behavior> of \<serviceBehaviors> of workflow</span></span>

<span data-ttu-id="45702-103">Element **Behavior** zawiera kolekcję ustawień zachowania usługi.</span><span class="sxs-lookup"><span data-stu-id="45702-103">The **behavior** element contains a collection of settings for the behavior of a service.</span></span> <span data-ttu-id="45702-104">Każde zachowanie jest indeksowane według jego **nazwy**.</span><span class="sxs-lookup"><span data-stu-id="45702-104">Each behavior is indexed by its **name**.</span></span> <span data-ttu-id="45702-105">Usługi mogą łączyć się z każdym zachowaniem za pomocą tej nazwy przy użyciu atrybutu **behaviorConfiguration** [\<endpoint>](../wcf/endpoint-element.md) elementu.</span><span class="sxs-lookup"><span data-stu-id="45702-105">Services can link to each behavior through this name using the **behaviorConfiguration** attribute of the [\<endpoint>](../wcf/endpoint-element.md) element.</span></span> <span data-ttu-id="45702-106">Dzięki temu punktów końcowych udostępnić typowych konfiguracji zachowanie bez ponownego definiowania ustawień.</span><span class="sxs-lookup"><span data-stu-id="45702-106">This allows endpoints to share common behavior configurations without redefining the settings.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<behavior>**  
  
## <a name="syntax"></a><span data-ttu-id="45702-107">Składnia</span><span class="sxs-lookup"><span data-stu-id="45702-107">Syntax</span></span>  
  
```xml  
<system.ServiceModel>  
  <behaviors>  
    <serviceBehaviors>  
      <behavior name="String">
        <bufferReceive maxPendingMessagesPerChannel="Integer" />
        <etwTracking profileName="String" />
        <sendMessageChannelCache allowUnsafeCaching="Boolean">
          <channelSettings idleTimeout="TimeSpan"
                           leaseTimeout="TimeSpan"
                           maxItemsInCache="Integer" />
          <factorySettings idleTimeout="TimeSpan"
                           leaseTimeout="TimeSpan"
                           maxItemsInCache="Integer" />
        </sendMessageChannelCache>
        <sqlWorkflowInstanceStore connectionStringName="String"
                                  hostLockRenewalPeriod="TimeSpan"
                                  instanceCompletionAction="DeleteNothing/DeleteAll"
                                  instanceEncodingAction="None/GZip"
                                  instanceLockedExceptionAction="NoRetry/BasicRetry/AggressiveRetry"
                                  runnableInstancesDetectionPeriod="TimeSpan" />
        <workflowIdle timeToPersist="TimeSpan"
                      timeToUnload="TimeSpan" />
        <workflowUnhandledException action="Abandon/AbandonAndSuspend/Cancel/Terminate" />
      </behavior>
    </serviceBehaviors>  
  </behaviors>  
</system.ServiceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="45702-108">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="45702-108">Attributes and Elements</span></span>  

 <span data-ttu-id="45702-109">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="45702-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="45702-110">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="45702-110">Attributes</span></span>  
  
|<span data-ttu-id="45702-111">Atrybut</span><span class="sxs-lookup"><span data-stu-id="45702-111">Attribute</span></span>|<span data-ttu-id="45702-112">Opis</span><span class="sxs-lookup"><span data-stu-id="45702-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="45702-113">name</span><span class="sxs-lookup"><span data-stu-id="45702-113">name</span></span>|<span data-ttu-id="45702-114">Unikatowy ciąg, który zawiera nazwę konfiguracji zachowanie.</span><span class="sxs-lookup"><span data-stu-id="45702-114">A unique string that contains the configuration name of the behavior.</span></span> <span data-ttu-id="45702-115">Ta wartość jest ciągiem zdefiniowanej przez użytkownika, który musi być unikatowy, ponieważ działa jako ciąg identyfikacyjny dla elementu.</span><span class="sxs-lookup"><span data-stu-id="45702-115">This value is a user-defined string that must be unique, since it acts as the identification string for the element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="45702-116">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="45702-116">Child Elements</span></span>  
  
|<span data-ttu-id="45702-117">Element</span><span class="sxs-lookup"><span data-stu-id="45702-117">Element</span></span>|<span data-ttu-id="45702-118">Opis</span><span class="sxs-lookup"><span data-stu-id="45702-118">Description</span></span>|  
|-------------|-----------------|  
|[\<bufferReceive>](bufferreceive.md)|<span data-ttu-id="45702-119">Zachowanie usługi, które umożliwia usługa do użycia buforowanego odbierać przetwarzania, co umożliwia usługi przepływu pracy w celu przetwarzania komunikatów poza kolejnością.</span><span class="sxs-lookup"><span data-stu-id="45702-119">A service behavior that enables a service to use buffered receive processing, which enables a workflow service to process out-of-order messages.</span></span>|  
|[\<routing>](../wcf/routing-of-servicebehavior.md)|<span data-ttu-id="45702-120">Zachowanie usługi, które umożliwia usłudze korzystanie z funkcji śledzenia ETW przy użyciu programu <xref:System.Activities.Tracking.EtwTrackingParticipant> .</span><span class="sxs-lookup"><span data-stu-id="45702-120">A service behavior that allows a service to utilize ETW tracking using an <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span></span>|  
|[\<sendMessageChannelCache>](sendmessagechannelcache.md)|<span data-ttu-id="45702-121">Zachowanie usługi, które umożliwia dostosowanie poziomów udostępniania pamięci podręcznej, ustawień pamięci podręcznej fabryki kanałów oraz ustawień pamięci podręcznej kanału dla przepływów pracy, które wysyłają komunikaty do punktów końcowych usługi przy użyciu działań wysyłania komunikatów.</span><span class="sxs-lookup"><span data-stu-id="45702-121">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>|  
|[\<sqlWorkflowInstanceStore>](sqlworkflowinstancestore.md)|<span data-ttu-id="45702-122">Zachowanie usługi, które umożliwia skonfigurowanie <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> funkcji, która obsługuje utrwalanie informacji o stanie dla wystąpień usługi przepływu pracy w bazie danych SQL Server 2005 lub SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="45702-122">A service behavior that allows you to configure the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> feature, which supports persisting state information for workflow service instances into an SQL Server 2005 or SQL Server 2008 database.</span></span>|  
|[\<workflowIdle>](workflowidle.md)|<span data-ttu-id="45702-123">Zachowanie usługi sterująca po zwolnione wystąpienia bezczynności przepływu pracy i utrwalone.</span><span class="sxs-lookup"><span data-stu-id="45702-123">A service behavior that controls when idle workflow instances are unloaded and persisted.</span></span>|  
|[\<workflowInstanceManagement>](workflowinstancemanagement.md)|<span data-ttu-id="45702-124">Zachowanie usługi, które umożliwia określenie ustawień, które kontrolują, jak są uruchamiane wystąpienia przepływu pracy, łącznie z trwałości, nieobsługiwanych wyjątków zachowanie i zachowanie bezczynności.</span><span class="sxs-lookup"><span data-stu-id="45702-124">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>|  
|[\<workflowUnhandledException>](workflowunhandledexception.md)|<span data-ttu-id="45702-125">Zachowanie usługi, który umożliwia określenie Akcja podejmowana po wystąpieniu nieobsługiwanego wyjątku w ramach usługi przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="45702-125">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="45702-126">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="45702-126">Parent Elements</span></span>  
  
|<span data-ttu-id="45702-127">Element</span><span class="sxs-lookup"><span data-stu-id="45702-127">Element</span></span>|<span data-ttu-id="45702-128">Opis</span><span class="sxs-lookup"><span data-stu-id="45702-128">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceBehaviors>](servicebehaviors-of-workflow.md)|<span data-ttu-id="45702-129">Kolekcja elementów zachowanie usługi.</span><span class="sxs-lookup"><span data-stu-id="45702-129">A collection of service behavior elements.</span></span>|
