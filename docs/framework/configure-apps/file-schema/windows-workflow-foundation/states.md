---
title: <states>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ebea5e7c-ad58-43c5-8f2d-cca25ae1b721
ms.openlocfilehash: e759f86e7746eaf3fdd72ed923612b24ef9b0c23
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91150820"
---
# \<states>

<span data-ttu-id="2cd02-101">Reprezentuje kolekcję subskrybowanego stanów z wystąpienia śledzonych przepływu pracy podczas tworzenia rekordów śledzenia.</span><span class="sxs-lookup"><span data-stu-id="2cd02-101">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="2cd02-102">Aby uzyskać więcej informacji o śledzeniu zapytań profilowych, zobacz [śledzenie profilów](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="2cd02-102">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQueries>**](workflowinstancequeries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQuery>**](workflowinstancequery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<states>**  
  
## <a name="syntax"></a><span data-ttu-id="2cd02-103">Składnia</span><span class="sxs-lookup"><span data-stu-id="2cd02-103">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <workflowInstanceQueries>
        <workflowInstanceQuery>
          <states>
            <state name="Name"/>
          </states>
        </workflowInstanceQuery>
      </workflowInstanceQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2cd02-104">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="2cd02-104">Attributes and Elements</span></span>  

 <span data-ttu-id="2cd02-105">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="2cd02-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2cd02-106">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="2cd02-106">Attributes</span></span>  

 <span data-ttu-id="2cd02-107">Brak.</span><span class="sxs-lookup"><span data-stu-id="2cd02-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2cd02-108">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="2cd02-108">Child Elements</span></span>  
  
|<span data-ttu-id="2cd02-109">Element</span><span class="sxs-lookup"><span data-stu-id="2cd02-109">Element</span></span>|<span data-ttu-id="2cd02-110">Opis</span><span class="sxs-lookup"><span data-stu-id="2cd02-110">Description</span></span>|  
|-------------|-----------------|  
|[\<state>](states.md)|<span data-ttu-id="2cd02-111">Stan subskrybowanego z wystąpienia elementu śledzonych przepływu pracy podczas rekordem śledzenia.</span><span class="sxs-lookup"><span data-stu-id="2cd02-111">A subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2cd02-112">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="2cd02-112">Parent Elements</span></span>  
  
|<span data-ttu-id="2cd02-113">Element</span><span class="sxs-lookup"><span data-stu-id="2cd02-113">Element</span></span>|<span data-ttu-id="2cd02-114">Opis</span><span class="sxs-lookup"><span data-stu-id="2cd02-114">Description</span></span>|  
|-------------|-----------------|  
|[\<workflowInstanceQuery>](workflowinstancequery.md)|<span data-ttu-id="2cd02-115">Zapytanie, które śledzi zmiany cyklu życia wystąpienia przepływu pracy, takie jak zdarzenie uruchomione lub ukończone.</span><span class="sxs-lookup"><span data-stu-id="2cd02-115">A query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2cd02-116">Uwagi</span><span class="sxs-lookup"><span data-stu-id="2cd02-116">Remarks</span></span>  

 <span data-ttu-id="2cd02-117">Zwracane rekordy są filtrowane według stanów w tej kolekcji.</span><span class="sxs-lookup"><span data-stu-id="2cd02-117">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="2cd02-118">Stan możliwe wartości są opisane w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="2cd02-118">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="2cd02-119">Stan</span><span class="sxs-lookup"><span data-stu-id="2cd02-119">State</span></span>|<span data-ttu-id="2cd02-120">Opis</span><span class="sxs-lookup"><span data-stu-id="2cd02-120">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2cd02-121">Zostało przerwane</span><span class="sxs-lookup"><span data-stu-id="2cd02-121">Aborted</span></span>|<span data-ttu-id="2cd02-122">Wystąpienie przepływu pracy zostało przerwane.</span><span class="sxs-lookup"><span data-stu-id="2cd02-122">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="2cd02-123">Ukończone</span><span class="sxs-lookup"><span data-stu-id="2cd02-123">Completed</span></span>|<span data-ttu-id="2cd02-124">Wystąpienie przepływu pracy zostało zakończone.</span><span class="sxs-lookup"><span data-stu-id="2cd02-124">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="2cd02-125">Usunięte</span><span class="sxs-lookup"><span data-stu-id="2cd02-125">Deleted</span></span>|<span data-ttu-id="2cd02-126">Wystąpienie przepływu pracy, został usunięty.</span><span class="sxs-lookup"><span data-stu-id="2cd02-126">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="2cd02-127">Okresy</span><span class="sxs-lookup"><span data-stu-id="2cd02-127">Idle</span></span>|<span data-ttu-id="2cd02-128">Wystąpienie przepływu pracy jest bezczynny.</span><span class="sxs-lookup"><span data-stu-id="2cd02-128">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="2cd02-129">Trwały</span><span class="sxs-lookup"><span data-stu-id="2cd02-129">Persisted</span></span>|<span data-ttu-id="2cd02-130">Wystąpienie przepływu pracy jest trwały.</span><span class="sxs-lookup"><span data-stu-id="2cd02-130">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="2cd02-131">Wznowione</span><span class="sxs-lookup"><span data-stu-id="2cd02-131">Resumed</span></span>|<span data-ttu-id="2cd02-132">Wystąpienie przepływu pracy zostanie wznowione.</span><span class="sxs-lookup"><span data-stu-id="2cd02-132">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="2cd02-133">Rozpoczęto</span><span class="sxs-lookup"><span data-stu-id="2cd02-133">Started</span></span>|<span data-ttu-id="2cd02-134">Wystąpienie przepływu pracy zostało rozpoczęte.</span><span class="sxs-lookup"><span data-stu-id="2cd02-134">The workflow instance is started.</span></span>|  
|<span data-ttu-id="2cd02-135">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="2cd02-135">UnhandledException</span></span>|<span data-ttu-id="2cd02-136">Wystąpienie przepływu pracy napotkał nieobsługiwany wyjątek.</span><span class="sxs-lookup"><span data-stu-id="2cd02-136">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="2cd02-137">Zwolniono</span><span class="sxs-lookup"><span data-stu-id="2cd02-137">Unloaded</span></span>|<span data-ttu-id="2cd02-138">Wystąpienie przepływu pracy nie jest załadowany.</span><span class="sxs-lookup"><span data-stu-id="2cd02-138">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="2cd02-139">Anulowane</span><span class="sxs-lookup"><span data-stu-id="2cd02-139">Canceled</span></span>|<span data-ttu-id="2cd02-140">Wystąpienie przepływu pracy zostało anulowane.</span><span class="sxs-lookup"><span data-stu-id="2cd02-140">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="2cd02-141">Suspended</span><span class="sxs-lookup"><span data-stu-id="2cd02-141">Suspended</span></span>|<span data-ttu-id="2cd02-142">Wystąpienie przepływu pracy jest zawieszone.</span><span class="sxs-lookup"><span data-stu-id="2cd02-142">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="2cd02-143">Zakończony</span><span class="sxs-lookup"><span data-stu-id="2cd02-143">Terminated</span></span>|<span data-ttu-id="2cd02-144">Wystąpienie przepływu pracy jest zakończone.</span><span class="sxs-lookup"><span data-stu-id="2cd02-144">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="2cd02-145">Anulowano</span><span class="sxs-lookup"><span data-stu-id="2cd02-145">Unsuspended</span></span>|<span data-ttu-id="2cd02-146">Anulowano to wystąpienie przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="2cd02-146">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2cd02-147">Przykład</span><span class="sxs-lookup"><span data-stu-id="2cd02-147">Example</span></span>  

 <span data-ttu-id="2cd02-148">Następująca konfiguracja subskrybuje przepływu rekordów dla śledzenia na poziomie wystąpienia `Started` stan wystąpienia przy użyciu tego zapytania.</span><span class="sxs-lookup"><span data-stu-id="2cd02-148">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2cd02-149">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="2cd02-149">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="2cd02-150">Kontrola i śledzenie przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="2cd02-150">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="2cd02-151">Profile śledzenia</span><span class="sxs-lookup"><span data-stu-id="2cd02-151">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
