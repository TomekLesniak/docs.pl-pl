---
title: Przestarzałe typy w programie Windows Workflow Foundation
ms.date: 03/30/2017
ms.assetid: 4aebe928-a964-4c1c-abf7-0dbbd3604b13
ms.openlocfilehash: b0ec30d2778333537e781e6681927f7048b630ea
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90543787"
---
# <a name="deprecated-types-in-windows-workflow-foundation"></a>Przestarzałe typy w programie Windows Workflow Foundation
W programie .NET 4 zespół przepływu pracy wydał cały nowy aparat przepływu pracy w <xref:System.Activities> przestrzeni nazw. W wersji programu .NET 4,5 beta oznaczamy większość typów w "WF 3" <xref:System.Workflow.Activities> , <xref:System.Workflow.ComponentModel> i  <xref:System.Workflow.Runtime> przestrzenie nazw jako przestarzałe.  
  
## <a name="obsolete-namespaces-and-tools"></a>Przestarzałe przestrzenie nazw i narzędzia  
 Następujące zestawy mają jeden lub więcej typów publicznych, które będą przestarzałe:  
  
- System.Workflow.Activities.dll  
  
- System.Workflow.ComponentModel.dll  
  
- System.Workflow.Runtime.dll  
  
- System.WorkflowServices.dll  
  
- Microsoft.Workflow.DebugController.dll  
  
- Microsoft.Workflow.Compiler.exe  
  
- Wfc.exe  
  
 W związku z tym klienci korzystający z przestarzałych interfejsów API WF 3 będą napotykać ostrzeżenia kompilacji z komunikatem podobnym do poniższego:  
  
 **Ostrzeżenie BC40000: X jest przestarzałe: Typy WF 3 są przestarzałe. Zamiast tego użyj polecenia WF 4.** Usuniemy typy z .NET Framework w przyszłej wersji, ale jeszcze nie określiłeś tego czasu (nie w 4,5). Ten bieżący krok pozwala nam komunikować się naszym naszym klientom i umożliwić im wiele czasu na przejście do nowego modelu WF4. Będziemy oczywiście w dalszym ciągu obsługiwać te typy WF 3 w ramach [zasad cyklu życia pomoc techniczna firmy Microsoft](/lifecycle/). Istniejące aplikacje WF3 będą uruchamiane bez problemu w programie .NET 4,5, a program Visual Studio 2012 będzie obsługiwał nowe i istniejące rozwiązania oparte na WF3.  
  
 Reguły związane z typami w <xref:System.Workflow.Activities.Rules> przestrzeni nazw, które nie mają zamiennika WF 4,5, nie zostały wycofane.  
  
 Klienci, którzy chcą migrować swoje aplikacje do programu WF 4, zobaczą [wskazówki dotyczące migracji przepływu pracy 4](migration-guidance.md).
