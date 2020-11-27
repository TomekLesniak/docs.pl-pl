---
title: Wprowadzenie Tutorial2
description: Ten artykuł rozpoczyna sekwencję samouczków, które zawierają wprowadzenie do programowania aplikacji Windows Workflow Foundation.
ms.date: 03/30/2017
helpviewer_keywords:
- WF [WF], getting started
- Windows Workflow Foundation [WF], getting started
ms.assetid: c2d3585f-6b1a-4d4f-9865-bd7cd31c5d42
ms.openlocfilehash: e9856320faa82becf12dda04d02f6f1c08081feb
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293601"
---
# <a name="getting-started-tutorial"></a><span data-ttu-id="53383-103">Wprowadzenie — samouczek</span><span class="sxs-lookup"><span data-stu-id="53383-103">Getting Started Tutorial</span></span>

<span data-ttu-id="53383-104">Ta sekcja zawiera zestaw przewodników, które umożliwiają Programowanie aplikacji Windows Workflow Foundation (WF).</span><span class="sxs-lookup"><span data-stu-id="53383-104">This section contains a set of walkthrough topics that introduce you to programming Windows Workflow Foundation (WF) applications.</span></span> <span data-ttu-id="53383-105">Postępując zgodnie z procedurami opisanymi w tych tematach, utworzysz aplikację, która jest grą o większej liczbie.</span><span class="sxs-lookup"><span data-stu-id="53383-105">By following the procedures in these topics, you will build an application that is a number guessing game.</span></span> <span data-ttu-id="53383-106">Pierwszy temat w samouczku prowadzi użytkownika przez procedurę tworzenia niestandardowych działań wymaganych dla przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="53383-106">The first topic in the tutorial leads you through the steps to create the custom activities required for the workflow.</span></span> <span data-ttu-id="53383-107">W drugim temacie te działania są składane wraz z wbudowanymi działaniami przepływu pracy do przepływu pracy schematu blokowego.</span><span class="sxs-lookup"><span data-stu-id="53383-107">In the second topic, these activities are assembled along with built-in workflow activities into a flowchart workflow.</span></span> <span data-ttu-id="53383-108">W trzecim temacie aplikacja hosta jest skonfigurowana do uruchamiania przepływu pracy i zostaje wprowadzona Ostatnia trwałość tematu.</span><span class="sxs-lookup"><span data-stu-id="53383-108">In the third topic, the host application is configured to run the workflow, and in the final topic persistence is introduced.</span></span> <span data-ttu-id="53383-109">Każdy krok w tym procesie zależy od poprzednich kroków, dlatego zalecamy ich zakończenie w kolejności.</span><span class="sxs-lookup"><span data-stu-id="53383-109">Each step in this process depends on the previous steps, so we recommend that you complete them in order.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="53383-110">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="53383-110">In This Section</span></span>  

 [<span data-ttu-id="53383-111">Instrukcje: Tworzenie działania</span><span class="sxs-lookup"><span data-stu-id="53383-111">How to: Create an Activity</span></span>](how-to-create-an-activity.md)  
 <span data-ttu-id="53383-112">Opisuje sposób tworzenia niestandardowych działań, które pochodzą z <xref:System.Activities.NativeActivity%601> i jak tworzyć to działanie wraz z wbudowaną aktywnością w ramach działania złożonego za pomocą projektanta działań.</span><span class="sxs-lookup"><span data-stu-id="53383-112">Describes how to create a custom activity that derives from <xref:System.Activities.NativeActivity%601>, and how to compose this activity along with a built-in activity into a composite activity using the activity designer.</span></span>  
  
 [<span data-ttu-id="53383-113">Instrukcje: Tworzenie przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="53383-113">How to: Create a Workflow</span></span>](how-to-create-a-workflow.md)  
 <span data-ttu-id="53383-114">Opisuje sposób tworzenia schematów blokowych, sekwencyjnego i przepływu pracy automatu przy użyciu wbudowanych działań i działań niestandardowych w poprzednim samouczku.</span><span class="sxs-lookup"><span data-stu-id="53383-114">Describes how to create flowchart, sequential, and state machine workflows by using built-in activities and the custom activities from the preceding tutorial.</span></span>  
  
 [<span data-ttu-id="53383-115">Instrukcje: Uruchamianie przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="53383-115">How to: Run a Workflow</span></span>](how-to-run-a-workflow.md)  
 <span data-ttu-id="53383-116">Opisuje sposób wywoływania przepływu pracy ze środowiska hosta, przekazywania danych do i z przepływu pracy oraz jak wznawiać zakładki.</span><span class="sxs-lookup"><span data-stu-id="53383-116">Describes how to invoke a workflow from a host environment, pass data into and out of a workflow, and how to resume bookmarks.</span></span>  
  
 [<span data-ttu-id="53383-117">Instrukcje: Tworzenie i uruchamianie długotrwałego przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="53383-117">How to: Create and Run a Long Running Workflow</span></span>](how-to-create-and-run-a-long-running-workflow.md)  
 <span data-ttu-id="53383-118">Opisuje sposób dodawania trwałości do aplikacji przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="53383-118">Describes how to add persistence to a workflow application.</span></span>  
  
 [<span data-ttu-id="53383-119">Instrukcje: Tworzenie niestandardowego uczestnika śledzenia</span><span class="sxs-lookup"><span data-stu-id="53383-119">How to: Create a Custom Tracking Participant</span></span>](how-to-create-a-custom-tracking-participant.md)  
 <span data-ttu-id="53383-120">Opisuje sposób tworzenia niestandardowych uczestników śledzenia i profilu śledzenia.</span><span class="sxs-lookup"><span data-stu-id="53383-120">Describes how to create a custom tracking participant and tracking profile.</span></span>  
  
 [<span data-ttu-id="53383-121">Instrukcje: Równoczesne hostowanie wielu wersji przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="53383-121">How to: Host Multiple Versions of a Workflow Side-by-Side</span></span>](how-to-host-multiple-versions-of-a-workflow-side-by-side.md)  
 <span data-ttu-id="53383-122">Opisuje, jak używać `WorkflowIdentity` do hostowania wielu wersji przepływu pracy obok siebie.</span><span class="sxs-lookup"><span data-stu-id="53383-122">Describes how to use `WorkflowIdentity` to host multiple versions of a workflow side-by-side.</span></span>  
  
 [<span data-ttu-id="53383-123">Instrukcje: Aktualizowanie definicji działającego wystąpienia przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="53383-123">How to: Update the Definition of a Running Workflow Instance</span></span>](how-to-update-the-definition-of-a-running-workflow-instance.md)  
 <span data-ttu-id="53383-124">Opisuje sposób korzystania z aktualizacji dynamicznej w celu modyfikowania uruchomionych wystąpień przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="53383-124">Describes how to use dynamic update to modify running workflow instances.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53383-125">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="53383-125">See also</span></span>

- [<span data-ttu-id="53383-126">Programowanie w programie Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="53383-126">Windows Workflow Foundation Programming</span></span>](programming.md)
