---
title: <tracking> programu WCF
ms.date: 03/30/2017
ms.assetid: 70cfaf24-a91c-4e56-ac47-d2ed87a963b3
ms.openlocfilehash: 223a30cd79d346d6ae36ca64fa887a683e6bfc8d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201437"
---
# <a name="tracking-of-wcf"></a><span data-ttu-id="bc710-102">\<tracking> programu WCF</span><span class="sxs-lookup"><span data-stu-id="bc710-102">\<tracking> of WCF</span></span>

<span data-ttu-id="bc710-103">Reprezentuje sekcję konfiguracji do definiowania ustawień śledzenia dla usługi przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="bc710-103">Represents a configuration section for defining tracking settings for a workflow service.</span></span>  
  
 <span data-ttu-id="bc710-104">Aby uzyskać więcej informacji na temat śledzenia przepływu pracy i jego konfiguracji, zobacz [śledzenie i śledzenie przepływów pracy](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) oraz [Konfigurowanie śledzenia dla przepływu pracy](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="bc710-104">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Configuring Tracking for a Workflow](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<tracking>**  
  
## <a name="syntax"></a><span data-ttu-id="bc710-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="bc710-105">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <tracking>
    <participants>
      <add name="String"
           profileName="String"
           type="String" />
    </participants>
    <profiles>
      <trackingProfile name="String">
        <workflow activityDefinitionId="String">
          <activityScheduledQueries>
            <activityScheduledQuery activityName="String"
                                    childActivityName="String"/>
          </activityScheduledQueries>
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
          <bookmarkResumptionQueries>
            <bookmarkResumptionQuery name="String" />
          </bookmarkResumptionQueries>
          <cancelRequestQueries>
            <cancelRequestQuery activityName="String"
                                childActivityName="String"/>
          </cancelRequestQueries>
          <customTrackingQueries>
            <customTrackingQuery activityName="String"
                                 name="String"/>
          </customTrackingQueries>
          <faultPropagationQueries>
            <faultPropagationQuery activityName="String"
                                   faultHandlerActivityName="String"/>
          </faultPropagationQueries>
          <workflowInstanceQueries>
            <workflowInstanceQuery>
              <states>
                <state name="String"/>
              </states>
            </workflowInstanceQuery>
          </workflowInstanceQueries>
        </workflow>
      </trackingProfile>
    </profiles>
  </tracking>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bc710-106">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="bc710-106">Attributes and Elements</span></span>  

 <span data-ttu-id="bc710-107">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="bc710-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bc710-108">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="bc710-108">Attributes</span></span>  

 <span data-ttu-id="bc710-109">Brak.</span><span class="sxs-lookup"><span data-stu-id="bc710-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="bc710-110">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="bc710-110">Child Elements</span></span>  
  
|<span data-ttu-id="bc710-111">Element</span><span class="sxs-lookup"><span data-stu-id="bc710-111">Element</span></span>|<span data-ttu-id="bc710-112">Opis</span><span class="sxs-lookup"><span data-stu-id="bc710-112">Description</span></span>|  
|-------------|-----------------|  
|[\<participants>](../windows-workflow-foundation/participants.md)|<span data-ttu-id="bc710-113">Kolekcja elementów konfiguracji definiujących uczestników, którzy subskrybują śledzenie rekordów.</span><span class="sxs-lookup"><span data-stu-id="bc710-113">A collection of configuration elements defining participants that subscribe to tracking records.</span></span> <span data-ttu-id="bc710-114">Uczestnicy śledzenia zawierają logikę do przetwarzania ładunku z rekordów śledzenia (na przykład mogą wybrać zapis w pliku).</span><span class="sxs-lookup"><span data-stu-id="bc710-114">The tracking participants contain the logic to process the payload from the tracking records (for example, they could choose to write to a file).</span></span>|  
|[\<trackingProfile>](../windows-workflow-foundation/trackingprofile.md)|<span data-ttu-id="bc710-115">Profil śledzenia do filtrowania rekordów śledzenia emitowane z wystąpienia przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="bc710-115">A tracking profile to filter tracking records emitted from a workflow instance.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bc710-116">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="bc710-116">Parent Elements</span></span>  
  
|<span data-ttu-id="bc710-117">Element</span><span class="sxs-lookup"><span data-stu-id="bc710-117">Element</span></span>|<span data-ttu-id="bc710-118">Opis</span><span class="sxs-lookup"><span data-stu-id="bc710-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bc710-119">System.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="bc710-119">system.ServiceModel</span></span>|<span data-ttu-id="bc710-120">Element główny wszystkich elementów konfiguracji przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="bc710-120">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bc710-121">Uwagi</span><span class="sxs-lookup"><span data-stu-id="bc710-121">Remarks</span></span>  

 <span data-ttu-id="bc710-122">Śledzenie umożliwia należy sprawdzić, czy wykonywania przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="bc710-122">Tracking provides you with the ability to examine the execution of a workflow.</span></span> <span data-ttu-id="bc710-123">Infrastruktura śledzenia przepływu pracy instruments przepływu pracy, aby emitować rekordów odzwierciedlający kluczy zdarzeń podczas wykonywania.</span><span class="sxs-lookup"><span data-stu-id="bc710-123">The workflow tracking infrastructure instruments a workflow to emit records reflecting key events during the execution.</span></span> <span data-ttu-id="bc710-124">Na przykład po uruchomieniu wystąpienia przepływu pracy lub zakończeniu śledzenia rekordy są emitowane.</span><span class="sxs-lookup"><span data-stu-id="bc710-124">For example, when a workflow instance starts or completes tracking records are emitted.</span></span> <span data-ttu-id="bc710-125">Śledzenie również można wyodrębnić business odpowiednie dane skojarzone z zmienne przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="bc710-125">Tracking can also extract business relevant data associated with the workflow variables.</span></span> <span data-ttu-id="bc710-126">Na przykład, jeśli przepływ pracy reprezentuje system przetwarzania zamówień, można wyodrębnić identyfikator zamówienia wraz z rekordem śledzenia.</span><span class="sxs-lookup"><span data-stu-id="bc710-126">For example, if the workflow represents an order processing system the order id can be extracted along with the tracking record.</span></span> <span data-ttu-id="bc710-127">Ogólnie rzecz biorąc włączania WF śledzenia umożliwia wykonywanie operacji diagnostyki lub analiz biznesowych za wykonywanie przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="bc710-127">In general, enabling WF tracking facilitates diagnostics or business analytics over a workflow execution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc710-128">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="bc710-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection?displayProperty=nameWithType>
- [<span data-ttu-id="bc710-129">Kontrola i śledzenie przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="bc710-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
