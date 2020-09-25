---
title: <customTrackingQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e9e732d-911d-45a3-a569-4b5e9cd1ffbe
ms.openlocfilehash: 3a666b7c7affda06fbf03515b045eddf2a1f6af5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91175892"
---
# \<customTrackingQueries>

<span data-ttu-id="d7a97-101">Reprezentuje kolekcję zapytań, które są używane do śledzenia zdarzeń zdefiniowanych przez użytkownika w działaniach kodu.</span><span class="sxs-lookup"><span data-stu-id="d7a97-101">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="d7a97-102">Zapytanie jest niezbędne do śledzenia uczestnika do subskrybowania śledzenia niestandardowe rekordów.</span><span class="sxs-lookup"><span data-stu-id="d7a97-102">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="d7a97-103">Aby uzyskać więcej informacji o śledzeniu zapytań profilowych, zobacz [śledzenie profilów](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="d7a97-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="d7a97-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="d7a97-104">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <customTrackingQueries>
        <customTrackingQuery activityName="String"
                             name="String" />
      </customTrackingQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d7a97-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="d7a97-105">Attributes and Elements</span></span>  

 <span data-ttu-id="d7a97-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="d7a97-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d7a97-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="d7a97-107">Attributes</span></span>  

 <span data-ttu-id="d7a97-108">Brak.</span><span class="sxs-lookup"><span data-stu-id="d7a97-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d7a97-109">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="d7a97-109">Child Elements</span></span>  
  
|<span data-ttu-id="d7a97-110">Element</span><span class="sxs-lookup"><span data-stu-id="d7a97-110">Element</span></span>|<span data-ttu-id="d7a97-111">Opis</span><span class="sxs-lookup"><span data-stu-id="d7a97-111">Description</span></span>|  
|-------------|-----------------|  
|[\<customTrackingQuery>](customtrackingquery.md)|<span data-ttu-id="d7a97-112">Zapytanie, które jest używane do śledzenia zdarzeń zdefiniowanych przez użytkownika w działaniach kodu.</span><span class="sxs-lookup"><span data-stu-id="d7a97-112">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d7a97-113">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="d7a97-113">Parent Elements</span></span>  
  
|<span data-ttu-id="d7a97-114">Element</span><span class="sxs-lookup"><span data-stu-id="d7a97-114">Element</span></span>|<span data-ttu-id="d7a97-115">Opis</span><span class="sxs-lookup"><span data-stu-id="d7a97-115">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](workflow.md)|<span data-ttu-id="d7a97-116">Element konfiguracji, który zawiera wszystkie zapytania dla określonego przepływu pracy identyfikowanego przez właściwość **activityDefinitionId** .</span><span class="sxs-lookup"><span data-stu-id="d7a97-116">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d7a97-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="d7a97-117">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="d7a97-118">Kontrola i śledzenie przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="d7a97-118">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="d7a97-119">Profile śledzenia</span><span class="sxs-lookup"><span data-stu-id="d7a97-119">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
