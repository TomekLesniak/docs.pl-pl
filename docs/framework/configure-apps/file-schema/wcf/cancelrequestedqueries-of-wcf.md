---
title: <cancelRequestedQueries> programu WCF
ms.date: 03/30/2017
ms.assetid: a7cc7125-9ea3-4d3f-99c0-878cdeb1258a
ms.openlocfilehash: 205399330c1aa69b332c2149ee32d9b6098ccdbe
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91151171"
---
# <a name="cancelrequestedqueries-of-wcf"></a><span data-ttu-id="da5b3-102">\<cancelRequestedQueries> programu WCF</span><span class="sxs-lookup"><span data-stu-id="da5b3-102">\<cancelRequestedQueries> of WCF</span></span>

<span data-ttu-id="da5b3-103">Reprezentuje kolekcję zapytań, które są używane do śledzenia żądań, aby anulować działanie podrzędne przez działanie nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="da5b3-103">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="da5b3-104">Zapytanie jest niezbędne do uczestnika śledzenia do subskrybowania Anuluj żądanie rekordu obiektów.</span><span class="sxs-lookup"><span data-stu-id="da5b3-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
<span data-ttu-id="da5b3-105">Aby uzyskać więcej informacji o śledzeniu zapytań profilowych, zobacz [śledzenie profilów](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="da5b3-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cancelRequestedQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="da5b3-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="da5b3-106">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <cancelRequestQueries>
          <cancelRequestQuery activityName="String"
                              childActivityName="String" />
        </cancelRequestQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="da5b3-107">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="da5b3-107">Attributes and elements</span></span>  

<span data-ttu-id="da5b3-108">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="da5b3-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="da5b3-109">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="da5b3-109">Attributes</span></span>

<span data-ttu-id="da5b3-110">Brak.</span><span class="sxs-lookup"><span data-stu-id="da5b3-110">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="da5b3-111">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="da5b3-111">Child elements</span></span>
  
|<span data-ttu-id="da5b3-112">Element</span><span class="sxs-lookup"><span data-stu-id="da5b3-112">Element</span></span>|<span data-ttu-id="da5b3-113">Opis</span><span class="sxs-lookup"><span data-stu-id="da5b3-113">Description</span></span>|  
|-------------|-----------------|  
|[\<cancelRequestedQuery>](cancelrequestedquery-of-wcf.md)|<span data-ttu-id="da5b3-114">Zapytanie, które jest używane do śledzenia żądań, aby anulować działanie podrzędne przez działanie nadrzędne</span><span class="sxs-lookup"><span data-stu-id="da5b3-114">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="da5b3-115">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="da5b3-115">Parent elements</span></span>  
  
|<span data-ttu-id="da5b3-116">Element</span><span class="sxs-lookup"><span data-stu-id="da5b3-116">Element</span></span>|<span data-ttu-id="da5b3-117">Opis</span><span class="sxs-lookup"><span data-stu-id="da5b3-117">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="da5b3-118">Element konfiguracji, który zawiera wszystkie zapytania dla określonego przepływu pracy identyfikowane przez <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId> właściwości.</span><span class="sxs-lookup"><span data-stu-id="da5b3-118">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId> property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="da5b3-119">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="da5b3-119">See also</span></span>

- <xref:System.Activities.Tracking.CancelRequestedQuery>
- [<span data-ttu-id="da5b3-120">Kontrola i śledzenie przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="da5b3-120">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="da5b3-121">Profile śledzenia</span><span class="sxs-lookup"><span data-stu-id="da5b3-121">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
