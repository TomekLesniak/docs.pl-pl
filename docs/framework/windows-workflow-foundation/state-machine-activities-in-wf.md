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
# <a name="state-machine-activities-in-wf"></a>Działania automatu stanów w WF

.NET Framework 4,5 udostępnia kilka działań dostępnych w systemie i projektantów działań do tworzenia przepływów pracy automatu Stanów.  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.StateMachine>|Wykonuje zawarte działania przy użyciu modelu znanego komputera stanu.|  
|<xref:System.Activities.Statements.State>|Reprezentuje stan na komputerze stanu.|  
|<xref:System.Activities.Core.Presentation.FinalState>|Reprezentuje stan zakończenia na komputerze stanu. <xref:System.Activities.Core.Presentation.FinalState> jest projektantem działań, który jest używany do tworzenia <xref:System.Activities.Statements.State> wstępnie skonfigurowanego stanu zakończenia. Aby uzyskać więcej informacji, zobacz [FinalState Activity Designer](/visualstudio/workflow-designer/finalstate-activity-designer).|  
|<xref:System.Activities.Statements.Transition>|Reprezentuje przejście między dwoma stanami. Nie ma elementu **przybornika** <xref:System.Activities.Statements.Transition> ; przejścia są tworzone w Projektancie przepływu pracy przez przeciąganie i upuszczanie linii między dwoma stanami lub przez porzucanie stanu w trójkątach, które są wyświetlane, gdy jeden stan jest aktywowany na innym. Aby uzyskać więcej informacji, zobacz [Projektant działań przejścia](/visualstudio/workflow-designer/transition-activity-designer).|  
  
## <a name="see-also"></a>Zobacz też

- [Wprowadzenie — samouczek](getting-started-tutorial.md)
