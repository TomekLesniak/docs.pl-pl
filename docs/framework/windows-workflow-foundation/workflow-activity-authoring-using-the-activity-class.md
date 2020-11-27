---
title: Tworzenie działań przepływu pracy przy użyciu klasy Activity
ms.date: 03/30/2017
ms.assetid: 7b7b1c66-f093-43c3-b4d1-7173b46516da
ms.openlocfilehash: 21f1c8b1249d41029fa7a19360e96ad866c823a7
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293848"
---
# <a name="workflow-activity-authoring-using-the-activity-class"></a><span data-ttu-id="7de26-102">Tworzenie działań przepływu pracy przy użyciu klasy Activity</span><span class="sxs-lookup"><span data-stu-id="7de26-102">Workflow Activity Authoring Using the Activity Class</span></span>

<span data-ttu-id="7de26-103">Najbardziej podstawowym sposobem utworzenia działania przy użyciu Windows Workflow Foundation (WF) w programie [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] jest utworzenie klasy, która dziedziczy po <xref:System.Activities.Activity> utworzeniu funkcji przez złożenie niestandardowych działań lub działań z [wbudowanej biblioteki działań](net-framework-4-5-built-in-activity-library.md).</span><span class="sxs-lookup"><span data-stu-id="7de26-103">The most basic way to create an activity using Windows Workflow Foundation (WF) in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] is to create a class that inherits from <xref:System.Activities.Activity> that creates functionality by assembling custom activities or activities from the [Built-In Activity Library](net-framework-4-5-built-in-activity-library.md).</span></span> <span data-ttu-id="7de26-104">W tym temacie pokazano, jak utworzyć działanie, które zapisuje dwa komunikaty w konsoli programu.</span><span class="sxs-lookup"><span data-stu-id="7de26-104">This topic demonstrates how to create an activity that writes two messages to the console.</span></span>

### <a name="to-create-a-custom-activity-using-the-activity-designer"></a><span data-ttu-id="7de26-105">Aby utworzyć działanie niestandardowe przy użyciu projektanta działań</span><span class="sxs-lookup"><span data-stu-id="7de26-105">To create a custom Activity using the activity designer</span></span>

1. <span data-ttu-id="7de26-106">Otwórz program Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="7de26-106">Open Visual Studio 2012.</span></span>

2. <span data-ttu-id="7de26-107">Wybierz plik, nowy, projekt.</span><span class="sxs-lookup"><span data-stu-id="7de26-107">Select File, New, Project.</span></span> <span data-ttu-id="7de26-108">Wybierz pozycję **Workflow 4,0** w obszarze **Visual C#** w oknie **typy projektów** , a następnie wybierz węzeł **V2010** .</span><span class="sxs-lookup"><span data-stu-id="7de26-108">Select **Workflow 4.0** under **Visual C#** in the **Project Types** window, and select the **v2010** node.</span></span> <span data-ttu-id="7de26-109">Wybierz pozycję **Biblioteka działań** w oknie **Szablony** .</span><span class="sxs-lookup"><span data-stu-id="7de26-109">Select **Activity Library** in the **Templates** window.</span></span> <span data-ttu-id="7de26-110">Nadaj nazwę nowej powitaniu projektu.</span><span class="sxs-lookup"><span data-stu-id="7de26-110">Name the new project HelloActivity.</span></span>

3. <span data-ttu-id="7de26-111">Otwórz nowe działanie.</span><span class="sxs-lookup"><span data-stu-id="7de26-111">Open the new activity.</span></span>  <span data-ttu-id="7de26-112">Przeciągnij <xref:System.Activities.Statements.Sequence> działanie z przybornika na powierzchnię projektanta.</span><span class="sxs-lookup"><span data-stu-id="7de26-112">Drag a <xref:System.Activities.Statements.Sequence> activity from the toolbox onto the designer surface.</span></span>

4. <span data-ttu-id="7de26-113">Przeciągnij <xref:System.Activities.Statements.WriteLine> działanie do <xref:System.Activities.Statements.Sequence> działania.</span><span class="sxs-lookup"><span data-stu-id="7de26-113">Drag a <xref:System.Activities.Statements.WriteLine> activity into the <xref:System.Activities.Statements.Sequence> activity.</span></span> <span data-ttu-id="7de26-114">Wprowadź `"Hello World"` (z cudzysłowami) w polu **tekstowym** .</span><span class="sxs-lookup"><span data-stu-id="7de26-114">Enter `"Hello World"` (with quotes) into the **Text** field.</span></span>

5. <span data-ttu-id="7de26-115">Przeciągnij drugie <xref:System.Activities.Statements.WriteLine> działanie do <xref:System.Activities.Statements.Sequence> działania poniżej pierwszego.</span><span class="sxs-lookup"><span data-stu-id="7de26-115">Drag a second <xref:System.Activities.Statements.WriteLine> activity into the <xref:System.Activities.Statements.Sequence> activity, below the first one.</span></span> <span data-ttu-id="7de26-116">Wprowadź `"Goodbye"` (z cudzysłowami) w polu **tekstowym** .</span><span class="sxs-lookup"><span data-stu-id="7de26-116">Enter `"Goodbye"` (with quotes) into the **Text** field.</span></span>
