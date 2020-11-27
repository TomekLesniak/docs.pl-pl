---
title: Projektowanie i implementowanie niestandardowych działań
description: Ten artykuł zawiera zasoby służące do tworzenia niestandardowych działań w programie Workflow Foundation przez tworzenie działań złożonych lub tworzenie nowych typów działań.
ms.date: 03/30/2017
ms.assetid: 4e30e63d-6e33-4842-a7a4-ce807cef1fad
ms.openlocfilehash: cb6e189cf5f59630ce8d89610eb0c2fc2acc92a7
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96280393"
---
# <a name="designing-and-implementing-custom-activities"></a><span data-ttu-id="ec38b-103">Projektowanie i implementowanie niestandardowych działań</span><span class="sxs-lookup"><span data-stu-id="ec38b-103">Designing and Implementing Custom Activities</span></span>

<span data-ttu-id="ec38b-104">Działania niestandardowe w programie [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] są tworzone przez umieszczenie działań dostarczonych przez system w działaniach złożonych lub przez utworzenie nowych typów, które pochodzą z <xref:System.Activities.CodeActivity> , <xref:System.Activities.AsyncCodeActivity> lub <xref:System.Activities.NativeActivity> .</span><span class="sxs-lookup"><span data-stu-id="ec38b-104">Custom activities in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] are created by either assembling system-provided activities into composite activities or by creating new types that derive from <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity>, or <xref:System.Activities.NativeActivity>.</span></span> <span data-ttu-id="ec38b-105">W tej sekcji opisano sposób tworzenia działań niestandardowych przy użyciu dowolnej metody.</span><span class="sxs-lookup"><span data-stu-id="ec38b-105">This section describes how to create custom activities with either method.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="ec38b-106">Działania niestandardowe domyślnie są wyświetlane w Projektancie przepływu pracy jako prosty prostokąt z nazwą działania.</span><span class="sxs-lookup"><span data-stu-id="ec38b-106">Custom activities by default display within the workflow designer as a simple rectangle with the activity’s name.</span></span> <span data-ttu-id="ec38b-107">Aby zapewnić niestandardową reprezentację działania w Projektancie przepływów pracy, należy również utworzyć projektanta niestandardowego.</span><span class="sxs-lookup"><span data-stu-id="ec38b-107">To provide a custom visual representation of your activity in the workflow designer you must also create a custom designer.</span></span> <span data-ttu-id="ec38b-108">Aby uzyskać więcej informacji, zobacz [Używanie niestandardowych projektantów i szablonów działań](using-custom-activity-designers-and-templates.md).</span><span class="sxs-lookup"><span data-stu-id="ec38b-108">For more information, see [Using Custom Activity Designers and Templates](using-custom-activity-designers-and-templates.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ec38b-109">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="ec38b-109">In This Section</span></span>  

 [<span data-ttu-id="ec38b-110">Opcje tworzenia działań</span><span class="sxs-lookup"><span data-stu-id="ec38b-110">Activity Authoring Options</span></span>](activity-authoring-options-in-wf.md)  
 <span data-ttu-id="ec38b-111">Omówienie stylów tworzenia dostępnych w programie [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ec38b-111">Discusses the authoring styles available in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)].</span></span>  
  
 [<span data-ttu-id="ec38b-112">Używanie niestandardowego działania</span><span class="sxs-lookup"><span data-stu-id="ec38b-112">Using a custom activity</span></span>](using-a-custom-activity.md)  
 <span data-ttu-id="ec38b-113">Opisuje sposób dodawania niestandardowego działania do projektu przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="ec38b-113">Describes how to add a custom activity to a workflow project.</span></span>  
  
  [<span data-ttu-id="ec38b-114">Tworzenie działań asynchronicznych</span><span class="sxs-lookup"><span data-stu-id="ec38b-114">Creating Asynchronous Activities</span></span>](creating-asynchronous-activities-in-wf.md)  
 <span data-ttu-id="ec38b-115">Opisuje sposób tworzenia działań asynchronicznych.</span><span class="sxs-lookup"><span data-stu-id="ec38b-115">Describes how to create asynchronous activities.</span></span>  
  
 [<span data-ttu-id="ec38b-116">Konfigurowanie walidacji działania</span><span class="sxs-lookup"><span data-stu-id="ec38b-116">Configuring Activity Validation</span></span>](configuring-activity-validation.md)  
 <span data-ttu-id="ec38b-117">Opisuje, w jaki sposób Walidacja działania może służyć do identyfikowania i zgłaszania błędów w konfiguracji działania przed jej wykonaniem.</span><span class="sxs-lookup"><span data-stu-id="ec38b-117">Describes how activity validation can be used to identify and report errors in an activity’s configuration prior to its execution.</span></span>  
  
 [<span data-ttu-id="ec38b-118">Tworzenie działania w środowisku uruchomieniowym</span><span class="sxs-lookup"><span data-stu-id="ec38b-118">Creating an Activity at Runtime</span></span>](creating-an-activity-at-runtime-with-dynamicactivity.md)  
 <span data-ttu-id="ec38b-119">W tym artykule omówiono sposób tworzenia działań w czasie wykonywania przy użyciu programu <xref:System.Activities.DynamicActivity> .</span><span class="sxs-lookup"><span data-stu-id="ec38b-119">Discusses how to create activities at runtime using <xref:System.Activities.DynamicActivity>.</span></span>  
  
 [<span data-ttu-id="ec38b-120">Właściwości wykonania przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="ec38b-120">Workflow Execution Properties</span></span>](workflow-execution-properties.md)  
 <span data-ttu-id="ec38b-121">Opisuje sposób używania właściwości wykonywania przepływu pracy w celu dodawania właściwości specyficznych dla kontekstu do środowiska działania</span><span class="sxs-lookup"><span data-stu-id="ec38b-121">Describes how to use workflow execution properties to add context specific properties to an activity’s environment</span></span>  
  
 [<span data-ttu-id="ec38b-122">Używanie delegatów działania</span><span class="sxs-lookup"><span data-stu-id="ec38b-122">Using Activity Delegates</span></span>](using-activity-delegates.md)  
 <span data-ttu-id="ec38b-123">W tym artykule omówiono sposób tworzenia i używania działań zawierających delegatów działań.</span><span class="sxs-lookup"><span data-stu-id="ec38b-123">Discusses how to author and use activities that contain activity delegates.</span></span>
  
 [<span data-ttu-id="ec38b-124">Używanie rozszerzeń działania</span><span class="sxs-lookup"><span data-stu-id="ec38b-124">Using Activity Extensions</span></span>](using-activity-extensions.md)  
 <span data-ttu-id="ec38b-125">Opisuje sposób tworzenia i używania rozszerzeń działań.</span><span class="sxs-lookup"><span data-stu-id="ec38b-125">Describes how to author and use activity extensions.</span></span>  
  
 [<span data-ttu-id="ec38b-126">Wykorzystywanie źródeł strumieniowych danych OData z przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="ec38b-126">Consuming OData Feeds from a Workflow</span></span>](consuming-odata-feeds-from-a-workflow.md)  
 <span data-ttu-id="ec38b-127">Opisuje kilka metod wywoływania usługi danych programu WCF z przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="ec38b-127">Describes several methods for calling a WCF Data Service from a workflow.</span></span>  
  
 [<span data-ttu-id="ec38b-128">Wyznaczanie zakresu i widoczność definicji działania</span><span class="sxs-lookup"><span data-stu-id="ec38b-128">Activity Definition Scoping and Visibility</span></span>](activity-definition-scoping-and-visibility.md)  
 <span data-ttu-id="ec38b-129">Opisuje opcje i reguły definiowania określania zakresu danych i widoczności elementów członkowskich dla działań.</span><span class="sxs-lookup"><span data-stu-id="ec38b-129">Describes the options and rules for defining data scoping and member visibility for activities.</span></span>
