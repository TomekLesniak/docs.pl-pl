---
title: <activityStateQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 9f8c3e4f-e2e3-4402-9760-03bf918ece7b
ms.openlocfilehash: fdb173f6d16087e921fc7f2edbb30fa901545eac
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177764"
---
# \<activityStateQuery>

<span data-ttu-id="8e9f1-101">Reprezentuje zapytanie, które jest używane do śledzenia zmian cyklem życia działań, które tworzą wystąpienie przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="8e9f1-101">Represents a query that is used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="8e9f1-102">Na przykład możesz chcieć śledzić każde działanie "Wyślij wiadomość E-Mail" w ramach wystąpienia przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="8e9f1-102">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="8e9f1-103">To zapytanie jest niezbędne do śledzenia uczestnika do subskrybowania obiektów rekordu stanu działania.</span><span class="sxs-lookup"><span data-stu-id="8e9f1-103">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="8e9f1-104">Stany do subskrybowania są wyszczególnione w ActivityStates.</span><span class="sxs-lookup"><span data-stu-id="8e9f1-104">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
 <span data-ttu-id="8e9f1-105">Aby uzyskać więcej informacji na temat śledzenia kwerend profilu, zobacz [śledzenie profilów](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="8e9f1-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQueries>**](activitystatequeries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityStateQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="8e9f1-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="8e9f1-106">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <arguments>
          <argument name="String"/>
        </arguments>
        <states>
          <state name="String"/>
        </states>
        <variables>
          <variable name="String"/>
        </variables>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8e9f1-107">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="8e9f1-107">Attributes and Elements</span></span>  

 <span data-ttu-id="8e9f1-108">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="8e9f1-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8e9f1-109">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="8e9f1-109">Attributes</span></span>  
  
|<span data-ttu-id="8e9f1-110">Atrybut</span><span class="sxs-lookup"><span data-stu-id="8e9f1-110">Attribute</span></span>|<span data-ttu-id="8e9f1-111">Opis</span><span class="sxs-lookup"><span data-stu-id="8e9f1-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8e9f1-112">activityName</span><span class="sxs-lookup"><span data-stu-id="8e9f1-112">activityName</span></span>|<span data-ttu-id="8e9f1-113">Ciąg określający nazwę czynności, aby filtrować <xref:System.Activities.Tracking.ActivityStateRecord> wystąpień.</span><span class="sxs-lookup"><span data-stu-id="8e9f1-113">A string that specifies the name of the activity to filter <xref:System.Activities.Tracking.ActivityStateRecord> instances on.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8e9f1-114">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="8e9f1-114">Child Elements</span></span>  
  
|<span data-ttu-id="8e9f1-115">Element</span><span class="sxs-lookup"><span data-stu-id="8e9f1-115">Element</span></span>|<span data-ttu-id="8e9f1-116">Opis</span><span class="sxs-lookup"><span data-stu-id="8e9f1-116">Description</span></span>|  
|-------------|-----------------|  
|[\<arguments>](arguments.md)|<span data-ttu-id="8e9f1-117">Kolekcja argumenty skojarzone z tej kwerendy działania.</span><span class="sxs-lookup"><span data-stu-id="8e9f1-117">A collection of arguments associated with this activity query.</span></span>|  
|[\<states>](states.md)|<span data-ttu-id="8e9f1-118">Kolekcja elementów konfiguracji, które zawierają stany subskrybowanego działania, dla którego należy obliczanie rekord śledzenia.</span><span class="sxs-lookup"><span data-stu-id="8e9f1-118">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
|[\<states>](states.md)|<span data-ttu-id="8e9f1-119">Kolekcja zmiennych skojarzoną z tym zapytaniem działania.</span><span class="sxs-lookup"><span data-stu-id="8e9f1-119">A collection of variables associated with this activity query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8e9f1-120">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="8e9f1-120">Parent Elements</span></span>  
  
|<span data-ttu-id="8e9f1-121">Element</span><span class="sxs-lookup"><span data-stu-id="8e9f1-121">Element</span></span>|<span data-ttu-id="8e9f1-122">Opis</span><span class="sxs-lookup"><span data-stu-id="8e9f1-122">Description</span></span>|  
|-------------|-----------------|  
|[\<faultPropagationQuery>](faultpropagationquery.md)|<span data-ttu-id="8e9f1-123">Reprezentuje listę elementów konfiguracji, które są używane do śledzenia żądań, aby anulować działanie podrzędne przez działanie nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="8e9f1-123">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="8e9f1-124">Zapytanie jest niezbędne do uczestnika śledzenia do subskrybowania Anuluj żądanie rekordu obiektów.</span><span class="sxs-lookup"><span data-stu-id="8e9f1-124">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8e9f1-125">Uwagi</span><span class="sxs-lookup"><span data-stu-id="8e9f1-125">Remarks</span></span>  

 <span data-ttu-id="8e9f1-126">Jedno rozwiązanie ActivityStateQuery jest możliwość wyodrębniania danych podczas śledzenia wykonywania przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="8e9f1-126">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="8e9f1-127">Umożliwia to dodatkowy kontekst podczas uzyskiwania dostępu do śledzenia rekordów post wykonywania.</span><span class="sxs-lookup"><span data-stu-id="8e9f1-127">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="8e9f1-128">Można użyć [\<arguments>](arguments.md) [\<states>](states.md) elementów i, [\<states>](states.md) Aby wyodrębnić dowolną zmienną lub argument z dowolnego działania w przepływie pracy.</span><span class="sxs-lookup"><span data-stu-id="8e9f1-128">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="8e9f1-129">W poniższym przykładzie przedstawiono zapytanie o stan działania, które wyodrębnia zmienne i argumenty podczas `Closed` emitowania rekordu śledzenia działania.</span><span class="sxs-lookup"><span data-stu-id="8e9f1-129">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="8e9f1-130">Zmienne i argumenty mogą być wyodrębniane tylko za pomocą ActivityStateRecord i w ten sposób są subskrybowane w ramach profilu śledzenia przy użyciu [\<activityStateQuery>](activitystatequery.md) .</span><span class="sxs-lookup"><span data-stu-id="8e9f1-130">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8e9f1-131">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="8e9f1-131">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="8e9f1-132">Kontrola i śledzenie przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="8e9f1-132">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="8e9f1-133">Profile śledzenia</span><span class="sxs-lookup"><span data-stu-id="8e9f1-133">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
