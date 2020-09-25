---
title: <bookmarkResumptionQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8ed61a7f-4254-439c-bdd8-b474971533f7
ms.openlocfilehash: 047d13bc8477214fa1e3c9ffdbed6785b29da637
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189582"
---
# \<bookmarkResumptionQueries>

<span data-ttu-id="c6604-101">Reprezentuje kolekcję zapytań, które są używane do śledzenia wznowienie zakładki w ramach wystąpienie przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="c6604-101">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="c6604-102">Zapytanie jest niezbędne do śledzenia uczestnika do subskrybowania zakładki wznowienie rekordów.</span><span class="sxs-lookup"><span data-stu-id="c6604-102">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="c6604-103">Aby uzyskać więcej informacji o śledzeniu zapytań profilowych, zobacz [śledzenie profilów](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="c6604-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bookmarkResumptionQueries>**  

## <a name="syntax"></a><span data-ttu-id="c6604-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="c6604-104">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <bookmarkResumptionQueries>
        <bookmarkResumptionQuery name="String" />
      </bookmarkResumptionQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c6604-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="c6604-105">Attributes and Elements</span></span>  

 <span data-ttu-id="c6604-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="c6604-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c6604-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="c6604-107">Attributes</span></span>  

 <span data-ttu-id="c6604-108">Brak.</span><span class="sxs-lookup"><span data-stu-id="c6604-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c6604-109">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="c6604-109">Child Elements</span></span>  
  
|<span data-ttu-id="c6604-110">Element</span><span class="sxs-lookup"><span data-stu-id="c6604-110">Element</span></span>|<span data-ttu-id="c6604-111">Opis</span><span class="sxs-lookup"><span data-stu-id="c6604-111">Description</span></span>|  
|-------------|-----------------|  
|[\<bookmarkResumptionQuery>](bookmarkresumptionquery.md)|<span data-ttu-id="c6604-112">Zapytanie, które jest używane do śledzenia wznowienie zakładki w ramach wystąpienie przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="c6604-112">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="c6604-113">Zapytanie jest niezbędne do śledzenia uczestnika do subskrybowania zakładki wznowienie rekordów.</span><span class="sxs-lookup"><span data-stu-id="c6604-113">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c6604-114">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="c6604-114">Parent Elements</span></span>  
  
|<span data-ttu-id="c6604-115">Element</span><span class="sxs-lookup"><span data-stu-id="c6604-115">Element</span></span>|<span data-ttu-id="c6604-116">Opis</span><span class="sxs-lookup"><span data-stu-id="c6604-116">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](workflow.md)|<span data-ttu-id="c6604-117">Element konfiguracji, który zawiera wszystkie zapytania dla określonego przepływu pracy identyfikowanego przez właściwość **activityDefinitionId** .</span><span class="sxs-lookup"><span data-stu-id="c6604-117">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c6604-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="c6604-118">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="c6604-119">Kontrola i śledzenie przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="c6604-119">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="c6604-120">Profile śledzenia</span><span class="sxs-lookup"><span data-stu-id="c6604-120">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
