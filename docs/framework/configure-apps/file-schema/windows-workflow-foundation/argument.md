---
title: <argument>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a7144d53-8023-4e90-971f-895e016fd58a
ms.openlocfilehash: 72a2d6f8439e720bb7bf236bd942552224e85501
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189730"
---
# \<argument>

<span data-ttu-id="5ecee-101">Element konfiguracji, który reprezentuje argumentu skojarzonych z kwerendą stanu działania.</span><span class="sxs-lookup"><span data-stu-id="5ecee-101">A configuration element that represents an argument associated with an activity state query.</span></span>  
  
 <span data-ttu-id="5ecee-102">Aby uzyskać więcej informacji na temat śledzenia kwerend profilu, zobacz [śledzenie profilów](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="5ecee-102">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQueries>**](activitystatequeries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQuery>**](activitystatequery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<arguments>**](arguments.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<argument>**  
  
## <a name="syntax"></a><span data-ttu-id="5ecee-103">Składnia</span><span class="sxs-lookup"><span data-stu-id="5ecee-103">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <arguments>
          <argument name="String"/>
        </arguments>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5ecee-104">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="5ecee-104">Attributes and Elements</span></span>  

 <span data-ttu-id="5ecee-105">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="5ecee-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5ecee-106">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="5ecee-106">Attributes</span></span>  
  
|<span data-ttu-id="5ecee-107">Atrybut</span><span class="sxs-lookup"><span data-stu-id="5ecee-107">Attribute</span></span>|<span data-ttu-id="5ecee-108">Opis</span><span class="sxs-lookup"><span data-stu-id="5ecee-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5ecee-109">name</span><span class="sxs-lookup"><span data-stu-id="5ecee-109">name</span></span>|<span data-ttu-id="5ecee-110">Ciąg określający nazwę argumentu.</span><span class="sxs-lookup"><span data-stu-id="5ecee-110">A string that specifies the name of the argument.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5ecee-111">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="5ecee-111">Child Elements</span></span>  

 <span data-ttu-id="5ecee-112">Brak.</span><span class="sxs-lookup"><span data-stu-id="5ecee-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5ecee-113">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="5ecee-113">Parent Elements</span></span>  
  
|<span data-ttu-id="5ecee-114">Element</span><span class="sxs-lookup"><span data-stu-id="5ecee-114">Element</span></span>|<span data-ttu-id="5ecee-115">Opis</span><span class="sxs-lookup"><span data-stu-id="5ecee-115">Description</span></span>|  
|-------------|-----------------|  
|[\<arguments>](arguments.md)|<span data-ttu-id="5ecee-116">Kolekcja argumenty skojarzone z tej kwerendy działania.</span><span class="sxs-lookup"><span data-stu-id="5ecee-116">A collection of arguments associated with this activity query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5ecee-117">Uwagi</span><span class="sxs-lookup"><span data-stu-id="5ecee-117">Remarks</span></span>  

 <span data-ttu-id="5ecee-118">Jedno rozwiązanie ActivityStateQuery jest możliwość wyodrębniania danych podczas śledzenia wykonywania przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="5ecee-118">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="5ecee-119">Umożliwia to dodatkowy kontekst podczas uzyskiwania dostępu do śledzenia rekordów post wykonywania.</span><span class="sxs-lookup"><span data-stu-id="5ecee-119">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="5ecee-120">Można użyć [\<arguments>](arguments.md) [\<states>](states.md) elementów i, [\<states>](states.md) Aby wyodrębnić dowolną zmienną lub argument z dowolnego działania w przepływie pracy.</span><span class="sxs-lookup"><span data-stu-id="5ecee-120">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="5ecee-121">W poniższym przykładzie przedstawiono zapytanie o stan działania, które wyodrębnia zmienne i argumenty podczas `Closed` emitowania rekordu śledzenia działania.</span><span class="sxs-lookup"><span data-stu-id="5ecee-121">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="5ecee-122">Zmienne i argumenty mogą być wyodrębniane tylko za pomocą ActivityStateRecord i w ten sposób są subskrybowane w ramach profilu śledzenia przy użyciu [\<activityStateQuery>](activitystatequery.md) .</span><span class="sxs-lookup"><span data-stu-id="5ecee-122">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
```xml  
<activityStateQuery activityName="SendEmailActivity">  
  <states>  
    <state name="Closed"/>  
  </states>  
  <variables>  
    <variable name="FromAddress"/>  
  </variables>  
  <arguments>  
    <argument name="Result"/>  
  </arguments>  
</activityStateQuery>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5ecee-123">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="5ecee-123">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ArgumentElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="5ecee-124">Kontrola i śledzenie przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="5ecee-124">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="5ecee-125">Profile śledzenia</span><span class="sxs-lookup"><span data-stu-id="5ecee-125">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
