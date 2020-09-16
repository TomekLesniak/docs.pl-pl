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
# <a name="deprecated-types-in-windows-workflow-foundation"></a><span data-ttu-id="068fe-102">Przestarzałe typy w programie Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="068fe-102">Deprecated types in Windows Workflow Foundation</span></span>
<span data-ttu-id="068fe-103">W programie .NET 4 zespół przepływu pracy wydał cały nowy aparat przepływu pracy w <xref:System.Activities> przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="068fe-103">In .NET 4 the Workflow Team released an all new Workflow engine in the <xref:System.Activities> namespace.</span></span> <span data-ttu-id="068fe-104">W wersji programu .NET 4,5 beta oznaczamy większość typów w "WF 3" <xref:System.Workflow.Activities> , <xref:System.Workflow.ComponentModel> i  <xref:System.Workflow.Runtime> przestrzenie nazw jako przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="068fe-104">With the release of .NET 4.5 Beta we are marking most of the types in the "WF 3" <xref:System.Workflow.Activities>, <xref:System.Workflow.ComponentModel>, and  <xref:System.Workflow.Runtime> namespaces as obsolete.</span></span>  
  
## <a name="obsolete-namespaces-and-tools"></a><span data-ttu-id="068fe-105">Przestarzałe przestrzenie nazw i narzędzia</span><span class="sxs-lookup"><span data-stu-id="068fe-105">Obsolete namespaces and tools</span></span>  
 <span data-ttu-id="068fe-106">Następujące zestawy mają jeden lub więcej typów publicznych, które będą przestarzałe:</span><span class="sxs-lookup"><span data-stu-id="068fe-106">The following assemblies have one or more public types that will be deprecated:</span></span>  
  
- <span data-ttu-id="068fe-107">System.Workflow.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="068fe-107">System.Workflow.Activities.dll</span></span>  
  
- <span data-ttu-id="068fe-108">System.Workflow.ComponentModel.dll</span><span class="sxs-lookup"><span data-stu-id="068fe-108">System.Workflow.ComponentModel.dll</span></span>  
  
- <span data-ttu-id="068fe-109">System.Workflow.Runtime.dll</span><span class="sxs-lookup"><span data-stu-id="068fe-109">System.Workflow.Runtime.dll</span></span>  
  
- <span data-ttu-id="068fe-110">System.WorkflowServices.dll</span><span class="sxs-lookup"><span data-stu-id="068fe-110">System.WorkflowServices.dll</span></span>  
  
- <span data-ttu-id="068fe-111">Microsoft.Workflow.DebugController.dll</span><span class="sxs-lookup"><span data-stu-id="068fe-111">Microsoft.Workflow.DebugController.dll</span></span>  
  
- <span data-ttu-id="068fe-112">Microsoft.Workflow.Compiler.exe</span><span class="sxs-lookup"><span data-stu-id="068fe-112">Microsoft.Workflow.Compiler.exe</span></span>  
  
- <span data-ttu-id="068fe-113">Wfc.exe</span><span class="sxs-lookup"><span data-stu-id="068fe-113">Wfc.exe</span></span>  
  
 <span data-ttu-id="068fe-114">W związku z tym klienci korzystający z przestarzałych interfejsów API WF 3 będą napotykać ostrzeżenia kompilacji z komunikatem podobnym do poniższego:</span><span class="sxs-lookup"><span data-stu-id="068fe-114">As a result, customers who are using the deprecated WF 3 APIs will encounter build warnings with a message similar to the following:</span></span>  
  
 <span data-ttu-id="068fe-115">**Ostrzeżenie BC40000: X jest przestarzałe: Typy WF 3 są przestarzałe. Zamiast tego użyj polecenia WF 4.**</span><span class="sxs-lookup"><span data-stu-id="068fe-115">**Warning BC40000: X is obsolete: WF 3 types are deprecated. Please use WF 4 instead.**</span></span> <span data-ttu-id="068fe-116">Usuniemy typy z .NET Framework w przyszłej wersji, ale jeszcze nie określiłeś tego czasu (nie w 4,5).</span><span class="sxs-lookup"><span data-stu-id="068fe-116">We will remove the types from the .NET Framework in a future release, but we have not yet determined that timeframe (not in 4.5).</span></span> <span data-ttu-id="068fe-117">Ten bieżący krok pozwala nam komunikować się naszym naszym klientom i umożliwić im wiele czasu na przejście do nowego modelu WF4.</span><span class="sxs-lookup"><span data-stu-id="068fe-117">This current step allows us to communicate our direction to our customers and allow them plenty of time to move to the new WF4 model.</span></span> <span data-ttu-id="068fe-118">Będziemy oczywiście w dalszym ciągu obsługiwać te typy WF 3 w ramach [zasad cyklu życia pomoc techniczna firmy Microsoft](/lifecycle/).</span><span class="sxs-lookup"><span data-stu-id="068fe-118">We will, of course, continue to support these WF 3 types under the [Microsoft Support Lifecycle Policy](/lifecycle/).</span></span> <span data-ttu-id="068fe-119">Istniejące aplikacje WF3 będą uruchamiane bez problemu w programie .NET 4,5, a program Visual Studio 2012 będzie obsługiwał nowe i istniejące rozwiązania oparte na WF3.</span><span class="sxs-lookup"><span data-stu-id="068fe-119">Existing WF3 applications will run without issue on .NET 4.5, and Visual Studio 2012 will support new and existing WF3-based solutions.</span></span>  
  
 <span data-ttu-id="068fe-120">Reguły związane z typami w <xref:System.Workflow.Activities.Rules> przestrzeni nazw, które nie mają zamiennika WF 4,5, nie zostały wycofane.</span><span class="sxs-lookup"><span data-stu-id="068fe-120">Rules related types in the <xref:System.Workflow.Activities.Rules> namespace, which do not have a replacement in WF 4.5, have not been deprecated.</span></span>  
  
 <span data-ttu-id="068fe-121">Klienci, którzy chcą migrować swoje aplikacje do programu WF 4, zobaczą [wskazówki dotyczące migracji przepływu pracy 4](migration-guidance.md).</span><span class="sxs-lookup"><span data-stu-id="068fe-121">Customers who want to migrate their applications to WF 4 will find help in the [Workflow 4 Migration Guidance](migration-guidance.md).</span></span>
