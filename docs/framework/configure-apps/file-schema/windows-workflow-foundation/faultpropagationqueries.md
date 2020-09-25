---
title: <faultPropagationQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 00ff90ae-ebe0-4c85-a93f-61557288d0a3
ms.openlocfilehash: 24e9136729df1352ebb1e665d1ebaf0ce9dc28a5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91175840"
---
# \<faultPropagationQueries>

<span data-ttu-id="7ad07-101">Reprezentuje kolekcję zapytań, które są używane do śledzenia obsługi błędów występujących w ramach działania.</span><span class="sxs-lookup"><span data-stu-id="7ad07-101">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="7ad07-102">To zdarzenie jest wykonywane za każdym razem, gdy FaultHandler przetwarza błąd.</span><span class="sxs-lookup"><span data-stu-id="7ad07-102">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="7ad07-103">Należy użyć takiej kwerendy do śledzenia obsługi błędów występujących w ramach działania.</span><span class="sxs-lookup"><span data-stu-id="7ad07-103">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="7ad07-104">Zapytanie jest niezbędne do śledzenia uczestnika do subskrybowania błędów propagacji rekordów.</span><span class="sxs-lookup"><span data-stu-id="7ad07-104">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="7ad07-105">Aby uzyskać więcej informacji na temat śledzenia kwerend profilu, zobacz [śledzenie profilów](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="7ad07-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<faultPropagationQueries>**
  
## <a name="syntax"></a><span data-ttu-id="7ad07-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="7ad07-106">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <faultPropagationQueries>
        <faultPropagationQuery activityName="String"
                               faultHandlerActivityName="String" />
      </faultPropagationQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7ad07-107">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="7ad07-107">Attributes and Elements</span></span>  

 <span data-ttu-id="7ad07-108">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="7ad07-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7ad07-109">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="7ad07-109">Attributes</span></span>  

 <span data-ttu-id="7ad07-110">Brak.</span><span class="sxs-lookup"><span data-stu-id="7ad07-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7ad07-111">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="7ad07-111">Child Elements</span></span>  
  
|<span data-ttu-id="7ad07-112">Element</span><span class="sxs-lookup"><span data-stu-id="7ad07-112">Element</span></span>|<span data-ttu-id="7ad07-113">Opis</span><span class="sxs-lookup"><span data-stu-id="7ad07-113">Description</span></span>|  
|-------------|-----------------|  
|[\<faultPropagationQuery>](faultpropagationquery.md)|<span data-ttu-id="7ad07-114">Zapytanie, które jest używane do śledzenia obsługi błędów występujących w ramach działania.</span><span class="sxs-lookup"><span data-stu-id="7ad07-114">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="7ad07-115">To zdarzenie jest wykonywane za każdym razem, gdy FaultHandler przetwarza błąd.</span><span class="sxs-lookup"><span data-stu-id="7ad07-115">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7ad07-116">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="7ad07-116">Parent Elements</span></span>  
  
|<span data-ttu-id="7ad07-117">Element</span><span class="sxs-lookup"><span data-stu-id="7ad07-117">Element</span></span>|<span data-ttu-id="7ad07-118">Opis</span><span class="sxs-lookup"><span data-stu-id="7ad07-118">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](workflow.md)|<span data-ttu-id="7ad07-119">Element konfiguracji, który zawiera wszystkie zapytania dla określonego przepływu pracy identyfikowanego przez właściwość **activityDefinitionId** .</span><span class="sxs-lookup"><span data-stu-id="7ad07-119">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7ad07-120">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="7ad07-120">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="7ad07-121">Kontrola i śledzenie przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="7ad07-121">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="7ad07-122">Profile śledzenia</span><span class="sxs-lookup"><span data-stu-id="7ad07-122">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
