---
title: <activityScheduledQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a8bcd6d4-b389-4daf-86bf-1ade85fec114
ms.openlocfilehash: 207931f68303883c29161cc28a5fc1974d01b6b8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148740"
---
# \<activityScheduledQuery>

<span data-ttu-id="1933e-101">Reprezentuje kolekcję zapytań, które są używane do śledzenia działania zaPLanowane do wykonania przez działanie nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="1933e-101">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="1933e-102">Zapytanie jest niezbędne do śledzenia uczestnika do subskrybowania zaPLanowane rekordów.</span><span class="sxs-lookup"><span data-stu-id="1933e-102">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="1933e-103">Aby uzyskać więcej informacji o śledzeniu zapytań profilowych, zobacz [śledzenie profilów](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="1933e-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityScheduledQueries>**](activityscheduledqueries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="1933e-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="1933e-104">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityScheduledQueries>
        <activityScheduledQuery activityName="String"
                                childActivityName="String"/>
      </activityScheduledQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1933e-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="1933e-105">Attributes and Elements</span></span>  

 <span data-ttu-id="1933e-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="1933e-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1933e-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="1933e-107">Attributes</span></span>  
  
|<span data-ttu-id="1933e-108">Atrybut</span><span class="sxs-lookup"><span data-stu-id="1933e-108">Attribute</span></span>|<span data-ttu-id="1933e-109">Opis</span><span class="sxs-lookup"><span data-stu-id="1933e-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1933e-110">activityName</span><span class="sxs-lookup"><span data-stu-id="1933e-110">activityName</span></span>|<span data-ttu-id="1933e-111">Ciąg określający nazwę działania, który żąda anulowania.</span><span class="sxs-lookup"><span data-stu-id="1933e-111">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="1933e-112">childActivityName</span><span class="sxs-lookup"><span data-stu-id="1933e-112">childActivityName</span></span>|<span data-ttu-id="1933e-113">Ciąg, który określa nazwę działania podrzędnego, dla której zażądano anulowania.</span><span class="sxs-lookup"><span data-stu-id="1933e-113">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1933e-114">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="1933e-114">Child Elements</span></span>  

 <span data-ttu-id="1933e-115">Brak.</span><span class="sxs-lookup"><span data-stu-id="1933e-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1933e-116">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="1933e-116">Parent Elements</span></span>  
  
|<span data-ttu-id="1933e-117">Element</span><span class="sxs-lookup"><span data-stu-id="1933e-117">Element</span></span>|<span data-ttu-id="1933e-118">Opis</span><span class="sxs-lookup"><span data-stu-id="1933e-118">Description</span></span>|  
|-------------|-----------------|  
|[\<activityScheduledQuery>](activityscheduledquery.md)|<span data-ttu-id="1933e-119">Zapytanie, które jest używane do śledzenia działania zaPLanowane do wykonania przez działanie nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="1933e-119">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1933e-120">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="1933e-120">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="1933e-121">Kontrola i śledzenie przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="1933e-121">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="1933e-122">Profile śledzenia</span><span class="sxs-lookup"><span data-stu-id="1933e-122">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
