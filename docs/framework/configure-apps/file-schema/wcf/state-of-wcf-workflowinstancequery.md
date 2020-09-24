---
title: <state> programu WCF, <workflowInstanceQuery>
ms.date: 03/30/2017
ms.assetid: 40f21055-766c-4be9-86c4-d1d899007098
ms.openlocfilehash: c323f7dba265e7fbcb09482115694088e761af0e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148896"
---
# <a name="state-of-wcf-workflowinstancequery"></a><span data-ttu-id="a9993-102">\<state> programu WCF, \<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="a9993-102">\<state> of WCF, \<workflowInstanceQuery></span></span>

<span data-ttu-id="a9993-103">Reprezentuje kolekcję subskrybowanego stanów z wystąpienia śledzonych przepływu pracy podczas tworzenia rekordów śledzenia.</span><span class="sxs-lookup"><span data-stu-id="a9993-103">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="a9993-104">Aby uzyskać więcej informacji o śledzeniu zapytań profilowych, zobacz [śledzenie profilów](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="a9993-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQueries>**](workflowinstancequeries-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQuery>**](workflowinstancequery-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<states>**](states-of-wcf-workflowinstancequery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<state>**  
  
## <a name="syntax"></a><span data-ttu-id="a9993-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="a9993-105">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <workflowInstanceQueries>
          <workflowInstanceQuery>
            <states>
              <state name="Name" />
            </states>
          </workflowInstanceQuery>
        </workflowInstanceQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a9993-106">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="a9993-106">Attributes and elements</span></span>

<span data-ttu-id="a9993-107">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="a9993-107">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="a9993-108">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="a9993-108">Attributes</span></span>

|<span data-ttu-id="a9993-109">Atrybut</span><span class="sxs-lookup"><span data-stu-id="a9993-109">Attribute</span></span>|<span data-ttu-id="a9993-110">Opis</span><span class="sxs-lookup"><span data-stu-id="a9993-110">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="a9993-111">Ciąg, który określa subskrybowanego stanu z wystąpienia śledzonych przepływu pracy podczas rekordem śledzenia.</span><span class="sxs-lookup"><span data-stu-id="a9993-111">A string that specifies a subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a9993-112">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="a9993-112">Child elements</span></span>

<span data-ttu-id="a9993-113">Brak.</span><span class="sxs-lookup"><span data-stu-id="a9993-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="a9993-114">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="a9993-114">Parent elements</span></span>

|<span data-ttu-id="a9993-115">Element</span><span class="sxs-lookup"><span data-stu-id="a9993-115">Element</span></span>|<span data-ttu-id="a9993-116">Opis</span><span class="sxs-lookup"><span data-stu-id="a9993-116">Description</span></span>|  
|-------------|-----------------|  
|[\<states>](states-of-wcf-workflowinstancequery.md)|<span data-ttu-id="a9993-117">Kolekcja subskrybowanego stanów z wystąpienia elementu śledzonych przepływu pracy podczas tworzenia rekordów śledzenia.</span><span class="sxs-lookup"><span data-stu-id="a9993-117">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a9993-118">Uwagi</span><span class="sxs-lookup"><span data-stu-id="a9993-118">Remarks</span></span>  

<span data-ttu-id="a9993-119">Zwracane rekordy są filtrowane według stanów w tej kolekcji.</span><span class="sxs-lookup"><span data-stu-id="a9993-119">The returned records are filtered by the states in this collection.</span></span>  
  
<span data-ttu-id="a9993-120">Możliwe wartości stanu są opisane w poniższej tabeli:</span><span class="sxs-lookup"><span data-stu-id="a9993-120">Possible state values are described in the following table:</span></span>
  
|<span data-ttu-id="a9993-121">Stan</span><span class="sxs-lookup"><span data-stu-id="a9993-121">State</span></span>|<span data-ttu-id="a9993-122">Opis</span><span class="sxs-lookup"><span data-stu-id="a9993-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a9993-123">Zostało przerwane</span><span class="sxs-lookup"><span data-stu-id="a9993-123">Aborted</span></span>|<span data-ttu-id="a9993-124">Wystąpienie przepływu pracy zostało przerwane.</span><span class="sxs-lookup"><span data-stu-id="a9993-124">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="a9993-125">Ukończone</span><span class="sxs-lookup"><span data-stu-id="a9993-125">Completed</span></span>|<span data-ttu-id="a9993-126">Wystąpienie przepływu pracy zostało zakończone.</span><span class="sxs-lookup"><span data-stu-id="a9993-126">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="a9993-127">Usunięte</span><span class="sxs-lookup"><span data-stu-id="a9993-127">Deleted</span></span>|<span data-ttu-id="a9993-128">Wystąpienie przepływu pracy, został usunięty.</span><span class="sxs-lookup"><span data-stu-id="a9993-128">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="a9993-129">Okresy</span><span class="sxs-lookup"><span data-stu-id="a9993-129">Idle</span></span>|<span data-ttu-id="a9993-130">Wystąpienie przepływu pracy jest bezczynny.</span><span class="sxs-lookup"><span data-stu-id="a9993-130">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="a9993-131">Trwały</span><span class="sxs-lookup"><span data-stu-id="a9993-131">Persisted</span></span>|<span data-ttu-id="a9993-132">Wystąpienie przepływu pracy jest trwały.</span><span class="sxs-lookup"><span data-stu-id="a9993-132">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="a9993-133">Wznowione</span><span class="sxs-lookup"><span data-stu-id="a9993-133">Resumed</span></span>|<span data-ttu-id="a9993-134">Wystąpienie przepływu pracy zostanie wznowione.</span><span class="sxs-lookup"><span data-stu-id="a9993-134">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="a9993-135">Rozpoczęto</span><span class="sxs-lookup"><span data-stu-id="a9993-135">Started</span></span>|<span data-ttu-id="a9993-136">Wystąpienie przepływu pracy zostało rozpoczęte.</span><span class="sxs-lookup"><span data-stu-id="a9993-136">The workflow instance is started.</span></span>|  
|<span data-ttu-id="a9993-137">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="a9993-137">UnhandledException</span></span>|<span data-ttu-id="a9993-138">Wystąpienie przepływu pracy napotkał nieobsługiwany wyjątek.</span><span class="sxs-lookup"><span data-stu-id="a9993-138">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="a9993-139">Zwolniono</span><span class="sxs-lookup"><span data-stu-id="a9993-139">Unloaded</span></span>|<span data-ttu-id="a9993-140">Wystąpienie przepływu pracy nie jest załadowany.</span><span class="sxs-lookup"><span data-stu-id="a9993-140">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="a9993-141">Anulowane</span><span class="sxs-lookup"><span data-stu-id="a9993-141">Canceled</span></span>|<span data-ttu-id="a9993-142">Wystąpienie przepływu pracy zostało anulowane.</span><span class="sxs-lookup"><span data-stu-id="a9993-142">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="a9993-143">Suspended</span><span class="sxs-lookup"><span data-stu-id="a9993-143">Suspended</span></span>|<span data-ttu-id="a9993-144">Wystąpienie przepływu pracy jest zawieszone.</span><span class="sxs-lookup"><span data-stu-id="a9993-144">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="a9993-145">Zakończony</span><span class="sxs-lookup"><span data-stu-id="a9993-145">Terminated</span></span>|<span data-ttu-id="a9993-146">Wystąpienie przepływu pracy jest zakończone.</span><span class="sxs-lookup"><span data-stu-id="a9993-146">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="a9993-147">Anulowano</span><span class="sxs-lookup"><span data-stu-id="a9993-147">Unsuspended</span></span>|<span data-ttu-id="a9993-148">Anulowano to wystąpienie przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="a9993-148">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a9993-149">Przykład</span><span class="sxs-lookup"><span data-stu-id="a9993-149">Example</span></span>

<span data-ttu-id="a9993-150">Następująca konfiguracja subskrybuje przepływu rekordów dla śledzenia na poziomie wystąpienia `Started` stan wystąpienia przy użyciu tego zapytania.</span><span class="sxs-lookup"><span data-stu-id="a9993-150">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="a9993-151">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="a9993-151">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="a9993-152">Kontrola i śledzenie przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="a9993-152">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="a9993-153">Profile śledzenia</span><span class="sxs-lookup"><span data-stu-id="a9993-153">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
