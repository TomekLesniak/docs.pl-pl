---
title: <customTrackingQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e108e89-1132-46b7-868a-c7f5c69dc89f
ms.openlocfilehash: 59a76ea772dc8d06c390e3bca9d531df5f11e5f0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148727"
---
# \<customTrackingQuery>

<span data-ttu-id="d837a-101">Reprezentuje kolekcję zapytań, które są używane do śledzenia zdarzeń zdefiniowanych przez użytkownika w działaniach kodu.</span><span class="sxs-lookup"><span data-stu-id="d837a-101">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="d837a-102">Zapytanie jest niezbędne do śledzenia uczestnika do subskrybowania śledzenia niestandardowe rekordów.</span><span class="sxs-lookup"><span data-stu-id="d837a-102">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="d837a-103">Aby uzyskać więcej informacji o śledzeniu zapytań profilowych, zobacz [śledzenie profilów](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="d837a-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customTrackingQueries>**](customtrackingqueries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="d837a-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="d837a-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d837a-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="d837a-105">Attributes and Elements</span></span>  

 <span data-ttu-id="d837a-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="d837a-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d837a-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="d837a-107">Attributes</span></span>  
  
|<span data-ttu-id="d837a-108">Atrybut</span><span class="sxs-lookup"><span data-stu-id="d837a-108">Attribute</span></span>|<span data-ttu-id="d837a-109">Opis</span><span class="sxs-lookup"><span data-stu-id="d837a-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d837a-110">activityName</span><span class="sxs-lookup"><span data-stu-id="d837a-110">activityName</span></span>|<span data-ttu-id="d837a-111">Ciąg określający nazwę działania, który wygenerował rekord śledzenia.</span><span class="sxs-lookup"><span data-stu-id="d837a-111">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|<span data-ttu-id="d837a-112">name</span><span class="sxs-lookup"><span data-stu-id="d837a-112">name</span></span>|<span data-ttu-id="d837a-113">Ciąg, który określa nazwę rekord śledzenia niestandardowego, który jest emitowane.</span><span class="sxs-lookup"><span data-stu-id="d837a-113">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d837a-114">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="d837a-114">Child Elements</span></span>  

 <span data-ttu-id="d837a-115">Brak.</span><span class="sxs-lookup"><span data-stu-id="d837a-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d837a-116">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="d837a-116">Parent Elements</span></span>  
  
|<span data-ttu-id="d837a-117">Element</span><span class="sxs-lookup"><span data-stu-id="d837a-117">Element</span></span>|<span data-ttu-id="d837a-118">Opis</span><span class="sxs-lookup"><span data-stu-id="d837a-118">Description</span></span>|  
|-------------|-----------------|  
|[\<customTrackingQuery>](customtrackingquery.md)|<span data-ttu-id="d837a-119">Zapytanie, które jest używane do śledzenia zdarzeń zdefiniowanych przez użytkownika w działaniach kodu.</span><span class="sxs-lookup"><span data-stu-id="d837a-119">A query that is used to track events that you define in your code activities.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d837a-120">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="d837a-120">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="d837a-121">Kontrola i śledzenie przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="d837a-121">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="d837a-122">Profile śledzenia</span><span class="sxs-lookup"><span data-stu-id="d837a-122">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
