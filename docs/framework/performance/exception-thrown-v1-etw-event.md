---
title: Zdarzenia wyjątku ETW Thrown_V1
description: Wyświetl szczegółowe informacje o zdarzeniu ETW ExceptionThrown_V1. Dane zdarzenia, takie jak nazwy pól, typy danych i opisy, są przyznawane dla zgłaszanych wyjątków.
ms.date: 03/30/2017
helpviewer_keywords:
- ExceptionThrown_V1 event [.NET Framework]
- ETW, ExceptionThrown_V1 event (CLR)
ms.assetid: 0d3da389-6b7b-40f6-a877-fac546d6019c
ms.openlocfilehash: f4ae277b5dfb09d2676755fec2208b63906ead84
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554674"
---
# <a name="exception-thrown_v1-etw-event"></a><span data-ttu-id="6561a-104">Zdarzenia wyjątku ETW Thrown_V1</span><span class="sxs-lookup"><span data-stu-id="6561a-104">Exception Thrown_V1 ETW Event</span></span>
<span data-ttu-id="6561a-105">To zdarzenie przechwytuje informacje o wygenerowanych wyjątkach.</span><span class="sxs-lookup"><span data-stu-id="6561a-105">This event captures information about the exceptions that are thrown.</span></span>  
  
 <span data-ttu-id="6561a-106">W poniższej tabeli przedstawiono słowo kluczowe, pod którym zdarzenie jest zgłaszane, oraz poziom zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="6561a-106">The following table shows the keyword under which the event is raised, and the level of the event.</span></span> <span data-ttu-id="6561a-107">(Aby uzyskać więcej informacji, zobacz [słowa kluczowe i poziomy ETW CLR](clr-etw-keywords-and-levels.md)).</span><span class="sxs-lookup"><span data-stu-id="6561a-107">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="6561a-108">Słowo kluczowe do podniesienia zdarzenia</span><span class="sxs-lookup"><span data-stu-id="6561a-108">Keyword for raising the event</span></span>|<span data-ttu-id="6561a-109">Poziom</span><span class="sxs-lookup"><span data-stu-id="6561a-109">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="6561a-110">`ExceptionKeyword` 0x8000</span><span class="sxs-lookup"><span data-stu-id="6561a-110">`ExceptionKeyword` (0x8000)</span></span>|<span data-ttu-id="6561a-111">Ostrzeżenie (2)</span><span class="sxs-lookup"><span data-stu-id="6561a-111">Warning (2)</span></span>|  
  
 <span data-ttu-id="6561a-112">W poniższej tabeli przedstawiono informacje o zdarzeniach.</span><span class="sxs-lookup"><span data-stu-id="6561a-112">The following table shows event information.</span></span>  
  
|<span data-ttu-id="6561a-113">Wydarzenie</span><span class="sxs-lookup"><span data-stu-id="6561a-113">Event</span></span>|<span data-ttu-id="6561a-114">Identyfikator zdarzenia</span><span class="sxs-lookup"><span data-stu-id="6561a-114">Event ID</span></span>|<span data-ttu-id="6561a-115">Wywoływane, gdy</span><span class="sxs-lookup"><span data-stu-id="6561a-115">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ExceptionThrown_V1`|<span data-ttu-id="6561a-116">80</span><span class="sxs-lookup"><span data-stu-id="6561a-116">80</span></span>|<span data-ttu-id="6561a-117">Generowany jest wyjątek zarządzany.</span><span class="sxs-lookup"><span data-stu-id="6561a-117">A managed exception is thrown.</span></span>|  
  
 <span data-ttu-id="6561a-118">W poniższej tabeli przedstawiono dane zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="6561a-118">The following table shows event data.</span></span>  
  
|<span data-ttu-id="6561a-119">Nazwa pola</span><span class="sxs-lookup"><span data-stu-id="6561a-119">Field name</span></span>|<span data-ttu-id="6561a-120">Typ danych</span><span class="sxs-lookup"><span data-stu-id="6561a-120">Data type</span></span>|<span data-ttu-id="6561a-121">Opis</span><span class="sxs-lookup"><span data-stu-id="6561a-121">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="6561a-122">Typ wyjątku</span><span class="sxs-lookup"><span data-stu-id="6561a-122">Exception Type</span></span>|<span data-ttu-id="6561a-123">win: UnicodeString</span><span class="sxs-lookup"><span data-stu-id="6561a-123">win:UnicodeString</span></span>|<span data-ttu-id="6561a-124">Typ wyjątku; na przykład `System.NullReferenceException` .</span><span class="sxs-lookup"><span data-stu-id="6561a-124">Type of the exception; for example, `System.NullReferenceException`.</span></span>|  
|<span data-ttu-id="6561a-125">Komunikat o wyjątku</span><span class="sxs-lookup"><span data-stu-id="6561a-125">Exception Message</span></span>|<span data-ttu-id="6561a-126">win: UnicodeString</span><span class="sxs-lookup"><span data-stu-id="6561a-126">win:UnicodeString</span></span>|<span data-ttu-id="6561a-127">Rzeczywisty komunikat o wyjątku.</span><span class="sxs-lookup"><span data-stu-id="6561a-127">Actual exception message.</span></span>|  
|<span data-ttu-id="6561a-128">EIPCodeThrow</span><span class="sxs-lookup"><span data-stu-id="6561a-128">EIPCodeThrow</span></span>|<span data-ttu-id="6561a-129">win: wskaźnik</span><span class="sxs-lookup"><span data-stu-id="6561a-129">win:Pointer</span></span>|<span data-ttu-id="6561a-130">Wskaźnik instrukcji, w którym wystąpił wyjątek.</span><span class="sxs-lookup"><span data-stu-id="6561a-130">Instruction pointer where exception occurred.</span></span>|  
|<span data-ttu-id="6561a-131">ExceptionHR</span><span class="sxs-lookup"><span data-stu-id="6561a-131">ExceptionHR</span></span>|<span data-ttu-id="6561a-132">win: UInt32</span><span class="sxs-lookup"><span data-stu-id="6561a-132">win:UInt32</span></span>|<span data-ttu-id="6561a-133">Wyjątek [HRESULT](/openspecs/windows_protocols/ms-erref/0642cb2f-2075-4469-918c-4441e69c548a).</span><span class="sxs-lookup"><span data-stu-id="6561a-133">Exception [HRESULT](/openspecs/windows_protocols/ms-erref/0642cb2f-2075-4469-918c-4441e69c548a).</span></span>|  
|<span data-ttu-id="6561a-134">ExceptionFlags</span><span class="sxs-lookup"><span data-stu-id="6561a-134">ExceptionFlags</span></span>|<span data-ttu-id="6561a-135">win: UInt16</span><span class="sxs-lookup"><span data-stu-id="6561a-135">win:UInt16</span></span>|<span data-ttu-id="6561a-136">0x01: HasInnerException (zobacz [zdarzenia ETW CLR](clr-etw-events.md) w dokumentacji Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="6561a-136">0x01: HasInnerException (see [CLR ETW Events](clr-etw-events.md) in the Visual Basic documentation).</span></span><br /><br /> <span data-ttu-id="6561a-137">0x02: isnestexception.</span><span class="sxs-lookup"><span data-stu-id="6561a-137">0x02: IsNestedException.</span></span><br /><br /> <span data-ttu-id="6561a-138">0x04: IsRethrownException.</span><span class="sxs-lookup"><span data-stu-id="6561a-138">0x04: IsRethrownException.</span></span><br /><br /> <span data-ttu-id="6561a-139">0x08: IsCorruptedStateException (wskazuje, że stan procesu jest uszkodzony; zobacz [Obsługa wyjątków uszkodzonego stanu](/archive/msdn-magazine/2009/february/clr-inside-out-handling-corrupted-state-exceptions)).</span><span class="sxs-lookup"><span data-stu-id="6561a-139">0x08: IsCorruptedStateException (indicates that the process state is corrupt; see [Handling Corrupted State Exceptions](/archive/msdn-magazine/2009/february/clr-inside-out-handling-corrupted-state-exceptions)).</span></span><br /><br /> <span data-ttu-id="6561a-140">0x10: IsCLSCompliant (wyjątek pochodzący z <xref:System.Exception> jest zgodny ze specyfikacją CLS; w przeciwnym razie jest to niezgodne ze specyfikacją CLS).</span><span class="sxs-lookup"><span data-stu-id="6561a-140">0x10: IsCLSCompliant (an exception that derives from <xref:System.Exception> is CLS-compliant; otherwise, it is not CLS-compliant).</span></span>|  
|<span data-ttu-id="6561a-141">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="6561a-141">ClrInstanceID</span></span>|<span data-ttu-id="6561a-142">win: UInt16</span><span class="sxs-lookup"><span data-stu-id="6561a-142">win:UInt16</span></span>|<span data-ttu-id="6561a-143">Unikatowy identyfikator wystąpienia CLR lub CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="6561a-143">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6561a-144">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="6561a-144">See also</span></span>

- [<span data-ttu-id="6561a-145">Zdarzenia ETW CLR</span><span class="sxs-lookup"><span data-stu-id="6561a-145">CLR ETW Events</span></span>](clr-etw-events.md)
