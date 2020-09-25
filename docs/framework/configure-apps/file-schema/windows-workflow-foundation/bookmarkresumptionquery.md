---
title: <bookmarkResumptionQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 226de75d-d25c-48d5-b069-4b7d80a6852b
ms.openlocfilehash: efd1e4e54223ff9f5d60b4087fbe5b6bebf1af2f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189593"
---
# \<bookmarkResumptionQuery>

<span data-ttu-id="de217-101">Reprezentuje zapytanie, które jest używane do śledzenia wznowienie zakładki w ramach wystąpienie przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="de217-101">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="de217-102">Zapytanie jest niezbędne do śledzenia uczestnika do subskrybowania zakładki wznowienie rekordów.</span><span class="sxs-lookup"><span data-stu-id="de217-102">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="de217-103">Aby uzyskać więcej informacji o śledzeniu zapytań profilowych, zobacz [śledzenie profilów](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="de217-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bookmarkResumptionQueries>**](bookmarkresumptionqueries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bookmarkResumptionQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="de217-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="de217-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="de217-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="de217-105">Attributes and Elements</span></span>  

 <span data-ttu-id="de217-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="de217-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="de217-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="de217-107">Attributes</span></span>  
  
|<span data-ttu-id="de217-108">Atrybut</span><span class="sxs-lookup"><span data-stu-id="de217-108">Attribute</span></span>|<span data-ttu-id="de217-109">Opis</span><span class="sxs-lookup"><span data-stu-id="de217-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="de217-110">name</span><span class="sxs-lookup"><span data-stu-id="de217-110">name</span></span>|<span data-ttu-id="de217-111">Ciąg określający nazwę rekordu zakładki do subskrybowania.</span><span class="sxs-lookup"><span data-stu-id="de217-111">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="de217-112">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="de217-112">Child Elements</span></span>  

 <span data-ttu-id="de217-113">Brak.</span><span class="sxs-lookup"><span data-stu-id="de217-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="de217-114">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="de217-114">Parent Elements</span></span>  
  
|<span data-ttu-id="de217-115">Element</span><span class="sxs-lookup"><span data-stu-id="de217-115">Element</span></span>|<span data-ttu-id="de217-116">Opis</span><span class="sxs-lookup"><span data-stu-id="de217-116">Description</span></span>|  
|-------------|-----------------|  
|[\<bookmarkResumptionQueries>](bookmarkresumptionqueries.md)|<span data-ttu-id="de217-117">Reprezentuje kolekcję zapytań, które są używane do śledzenia wznowienie zakładki w ramach wystąpienie przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="de217-117">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="de217-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="de217-118">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="de217-119">Kontrola i śledzenie przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="de217-119">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="de217-120">Profile śledzenia</span><span class="sxs-lookup"><span data-stu-id="de217-120">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
