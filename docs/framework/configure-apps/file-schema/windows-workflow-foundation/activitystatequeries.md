---
title: <activityStateQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: bdd3c8ae-a13f-4df1-9b3c-a9d6c4bb1b5f
ms.openlocfilehash: 4663ccedcafb6b151de75568afd3743c83c75224
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189828"
---
# \<activityStateQueries>

<span data-ttu-id="15e23-101">Reprezentuje kolekcję zapytań, które są używane do śledzenia zmian cyklem życia działań, które tworzą wystąpienie przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="15e23-101">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="15e23-102">Na przykład możesz chcieć śledzić każde działanie "Wyślij wiadomość E-Mail" w ramach wystąpienia przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="15e23-102">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="15e23-103">To zapytanie jest niezbędne do śledzenia uczestnika do subskrybowania obiektów rekordu stanu działania.</span><span class="sxs-lookup"><span data-stu-id="15e23-103">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="15e23-104">Stany do subskrybowania są wyszczególnione w ActivityStates.</span><span class="sxs-lookup"><span data-stu-id="15e23-104">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
 <span data-ttu-id="15e23-105">Aby uzyskać więcej informacji na temat śledzenia kwerend profilu, zobacz [śledzenie profilów](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="15e23-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityStateQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="15e23-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="15e23-106">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <arguments>
          <argument name="String" />
        </arguments>
        <states>
          <state name="String" />
        </states>
        <variables>
         <variable name="String" />
        </variables>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="15e23-107">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="15e23-107">Attributes and Elements</span></span>  

 <span data-ttu-id="15e23-108">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="15e23-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="15e23-109">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="15e23-109">Attributes</span></span>  

 <span data-ttu-id="15e23-110">Brak.</span><span class="sxs-lookup"><span data-stu-id="15e23-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="15e23-111">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="15e23-111">Child Elements</span></span>  
  
|<span data-ttu-id="15e23-112">Element</span><span class="sxs-lookup"><span data-stu-id="15e23-112">Element</span></span>|<span data-ttu-id="15e23-113">Opis</span><span class="sxs-lookup"><span data-stu-id="15e23-113">Description</span></span>|  
|-------------|-----------------|  
|[\<activityStateQuery>](activitystatequery.md)|<span data-ttu-id="15e23-114">Zapytanie, które jest używane do śledzenia obsługi błędów występujących w ramach działania.</span><span class="sxs-lookup"><span data-stu-id="15e23-114">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="15e23-115">To zdarzenie jest wykonywane za każdym razem, gdy FaultHandler przetwarza błąd.</span><span class="sxs-lookup"><span data-stu-id="15e23-115">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="15e23-116">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="15e23-116">Parent Elements</span></span>  
  
|<span data-ttu-id="15e23-117">Element</span><span class="sxs-lookup"><span data-stu-id="15e23-117">Element</span></span>|<span data-ttu-id="15e23-118">Opis</span><span class="sxs-lookup"><span data-stu-id="15e23-118">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](workflow.md)|<span data-ttu-id="15e23-119">Element konfiguracji, który zawiera wszystkie zapytania dla określonego przepływu pracy identyfikowanego przez właściwość **activityDefinitionId** .</span><span class="sxs-lookup"><span data-stu-id="15e23-119">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="15e23-120">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="15e23-120">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="15e23-121">Kontrola i śledzenie przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="15e23-121">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="15e23-122">Profile śledzenia</span><span class="sxs-lookup"><span data-stu-id="15e23-122">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
