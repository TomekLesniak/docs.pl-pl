---
title: Działania automatu stanów w WF
ms.date: 03/30/2017
ms.assetid: 93312eaf-07e0-4a55-b4f7-4cdbbc4dee2d
ms.openlocfilehash: dd0bfae1f24ecd9f98c0a2f04265581f880202a7
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96261725"
---
# <a name="state-machine-activities-in-wf"></a><span data-ttu-id="f49e1-102">Działania automatu stanów w WF</span><span class="sxs-lookup"><span data-stu-id="f49e1-102">State Machine Activities in WF</span></span>

<span data-ttu-id="f49e1-103">.NET Framework 4,5 udostępnia kilka działań dostępnych w systemie i projektantów działań do tworzenia przepływów pracy automatu Stanów.</span><span class="sxs-lookup"><span data-stu-id="f49e1-103">.NET Framework 4.5 provides several system-provided activities and activity designers for creating state machine workflows.</span></span>  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.StateMachine>|<span data-ttu-id="f49e1-104">Wykonuje zawarte działania przy użyciu modelu znanego komputera stanu.</span><span class="sxs-lookup"><span data-stu-id="f49e1-104">Executes contained activities using the familiar state machine paradigm.</span></span>|  
|<xref:System.Activities.Statements.State>|<span data-ttu-id="f49e1-105">Reprezentuje stan na komputerze stanu.</span><span class="sxs-lookup"><span data-stu-id="f49e1-105">Represents a state in a state machine.</span></span>|  
|<xref:System.Activities.Core.Presentation.FinalState>|<span data-ttu-id="f49e1-106">Reprezentuje stan zakończenia na komputerze stanu.</span><span class="sxs-lookup"><span data-stu-id="f49e1-106">Represents a terminating state in a state machine.</span></span> <span data-ttu-id="f49e1-107"><xref:System.Activities.Core.Presentation.FinalState> jest projektantem działań, który jest używany do tworzenia <xref:System.Activities.Statements.State> wstępnie skonfigurowanego stanu zakończenia.</span><span class="sxs-lookup"><span data-stu-id="f49e1-107"><xref:System.Activities.Core.Presentation.FinalState> is an activity designer that when used creates a <xref:System.Activities.Statements.State> preconfigured as a terminating state.</span></span> <span data-ttu-id="f49e1-108">Aby uzyskać więcej informacji, zobacz [FinalState Activity Designer](/visualstudio/workflow-designer/finalstate-activity-designer).</span><span class="sxs-lookup"><span data-stu-id="f49e1-108">For more information, see [FinalState Activity Designer](/visualstudio/workflow-designer/finalstate-activity-designer).</span></span>|  
|<xref:System.Activities.Statements.Transition>|<span data-ttu-id="f49e1-109">Reprezentuje przejście między dwoma stanami.</span><span class="sxs-lookup"><span data-stu-id="f49e1-109">Represents the transition between two states.</span></span> <span data-ttu-id="f49e1-110">Nie ma elementu **przybornika** <xref:System.Activities.Statements.Transition> ; przejścia są tworzone w Projektancie przepływu pracy przez przeciąganie i upuszczanie linii między dwoma stanami lub przez porzucanie stanu w trójkątach, które są wyświetlane, gdy jeden stan jest aktywowany na innym.</span><span class="sxs-lookup"><span data-stu-id="f49e1-110">There is no **Toolbox** item for <xref:System.Activities.Statements.Transition>; transitions are created on the workflow designer by dragging and dropping a line between two states, or by dropping a state on the triangles that appear when one state is hovered over another.</span></span> <span data-ttu-id="f49e1-111">Aby uzyskać więcej informacji, zobacz [Projektant działań przejścia](/visualstudio/workflow-designer/transition-activity-designer).</span><span class="sxs-lookup"><span data-stu-id="f49e1-111">For more information, see [Transition Activity Designer](/visualstudio/workflow-designer/transition-activity-designer).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f49e1-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="f49e1-112">See also</span></span>

- [<span data-ttu-id="f49e1-113">Wprowadzenie — samouczek</span><span class="sxs-lookup"><span data-stu-id="f49e1-113">Getting Started Tutorial</span></span>](getting-started-tutorial.md)
