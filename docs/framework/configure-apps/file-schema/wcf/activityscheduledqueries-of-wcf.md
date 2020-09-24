---
title: <activityScheduledQueries> programu WCF
ms.date: 03/30/2017
ms.assetid: e351329f-9676-4f11-9b19-f4bac82f36fc
ms.openlocfilehash: 86f196437b2230d6541570aa8994d99e7b340f66
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91151197"
---
# <a name="activityscheduledqueries-of-wcf"></a><span data-ttu-id="592ce-102">\<activityScheduledQueries> programu WCF</span><span class="sxs-lookup"><span data-stu-id="592ce-102">\<activityScheduledQueries> of WCF</span></span>

<span data-ttu-id="592ce-103">Reprezentuje kolekcję zapytań, które są używane do śledzenia działania zaPLanowane do wykonania przez działanie nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="592ce-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="592ce-104">Zapytanie jest niezbędne do śledzenia uczestnika do subskrybowania zaPLanowane rekordów.</span><span class="sxs-lookup"><span data-stu-id="592ce-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
<span data-ttu-id="592ce-105">Aby uzyskać więcej informacji o śledzeniu zapytań profilowych, zobacz [śledzenie profilów](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="592ce-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="592ce-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="592ce-106">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <activityScheduledQueries>
          <activityScheduledQuery activityName="String"
                                  childActivityName="String" />
        </activityScheduledQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="592ce-107">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="592ce-107">Attributes and elements</span></span>  

<span data-ttu-id="592ce-108">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="592ce-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="592ce-109">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="592ce-109">Attributes</span></span>  

<span data-ttu-id="592ce-110">Brak.</span><span class="sxs-lookup"><span data-stu-id="592ce-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="592ce-111">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="592ce-111">Child elements</span></span>  
  
|<span data-ttu-id="592ce-112">Element</span><span class="sxs-lookup"><span data-stu-id="592ce-112">Element</span></span>|<span data-ttu-id="592ce-113">Opis</span><span class="sxs-lookup"><span data-stu-id="592ce-113">Description</span></span>|  
|-------------|-----------------|  
|[\<activityScheduledQuery>](activityscheduledquery-of-wcf.md)|<span data-ttu-id="592ce-114">Zapytanie, które jest używane do śledzenia działania zaPLanowane do wykonania przez działanie nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="592ce-114">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="592ce-115">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="592ce-115">Parent elements</span></span>  
  
|<span data-ttu-id="592ce-116">Element</span><span class="sxs-lookup"><span data-stu-id="592ce-116">Element</span></span>|<span data-ttu-id="592ce-117">Opis</span><span class="sxs-lookup"><span data-stu-id="592ce-117">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="592ce-118">Element konfiguracji, który zawiera wszystkie zapytania dla określonego przepływu pracy identyfikowane przez `activityDefinitionId` właściwości.</span><span class="sxs-lookup"><span data-stu-id="592ce-118">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="592ce-119">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="592ce-119">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection>
- <xref:System.Activities.Tracking.ActivityScheduledQuery>
- [<span data-ttu-id="592ce-120">Kontrola i śledzenie przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="592ce-120">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="592ce-121">Profile śledzenia</span><span class="sxs-lookup"><span data-stu-id="592ce-121">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
