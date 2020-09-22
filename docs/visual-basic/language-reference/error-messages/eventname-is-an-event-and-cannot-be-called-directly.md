---
title: Element „<eventname>” jest zdarzeniem i nie można go wywołać bezpośrednio
ms.date: 07/20/2015
f1_keywords:
- bc32022
- vbc32022
helpviewer_keywords:
- BC32022
ms.assetid: 4dcfcb8d-a9fa-46a7-a034-29d9ff3a59b3
ms.openlocfilehash: 3366bc215a45cd7de9dc2de285758a78144df509
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874312"
---
# <a name="eventname-is-an-event-and-cannot-be-called-directly"></a><span data-ttu-id="ef16d-102">Element „\<eventname>” jest zdarzeniem i nie można go wywołać bezpośrednio</span><span class="sxs-lookup"><span data-stu-id="ef16d-102">'\<eventname>' is an event, and cannot be called directly</span></span>

<span data-ttu-id="ef16d-103">"<`eventname`>" jest zdarzeniem i dlatego nie można go wywołać bezpośrednio.</span><span class="sxs-lookup"><span data-stu-id="ef16d-103">'<`eventname`>' is an event, and so cannot be called directly.</span></span> <span data-ttu-id="ef16d-104">Użyj `RaiseEvent` instrukcji, aby zgłosić zdarzenie.</span><span class="sxs-lookup"><span data-stu-id="ef16d-104">Use a `RaiseEvent` statement to raise an event.</span></span>  
  
 <span data-ttu-id="ef16d-105">Wywołanie procedury określa zdarzenie dla nazwy procedury.</span><span class="sxs-lookup"><span data-stu-id="ef16d-105">A procedure call specifies an event for the procedure name.</span></span> <span data-ttu-id="ef16d-106">Procedura obsługi zdarzeń jest procedurą, ale samo zdarzenie jest urządzeniem sygnalizującym, które musi zostać podniesione i obsłużone.</span><span class="sxs-lookup"><span data-stu-id="ef16d-106">An event handler is a procedure, but the event itself is a signaling device, which must be raised and handled.</span></span>  
  
 <span data-ttu-id="ef16d-107">**Identyfikator błędu:** BC32022</span><span class="sxs-lookup"><span data-stu-id="ef16d-107">**Error ID:** BC32022</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ef16d-108">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="ef16d-108">To correct this error</span></span>  
  
1. <span data-ttu-id="ef16d-109">Użyj `RaiseEvent` instrukcji, aby sygnalizować zdarzenie i wywołać procedury lub procedury, które je obsługują.</span><span class="sxs-lookup"><span data-stu-id="ef16d-109">Use a `RaiseEvent` statement to signal an event and invoke the procedure or procedures that handle it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef16d-110">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ef16d-110">See also</span></span>

- [<span data-ttu-id="ef16d-111">RaiseEvent — Instrukcja</span><span class="sxs-lookup"><span data-stu-id="ef16d-111">RaiseEvent Statement</span></span>](../statements/raiseevent-statement.md)
