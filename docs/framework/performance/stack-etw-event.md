---
title: Zdarzenie ETW stosu
description: Przeczytaj o zdarzeniu ETW stosu, który powinien być używany w połączeniu z innymi zdarzeniami w celu wygenerowania śladów stosu po podniesieniu zdarzenia.
ms.date: 03/30/2017
helpviewer_keywords:
- stack event [.NET Framework]
- ETW, stack event (CLR)
ms.assetid: f612fa5b-4b62-4593-a19e-85c9b1018dce
ms.openlocfilehash: 3b890e587abd5cb1b7315fe41897f24638fd4604
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236211"
---
# <a name="stack-etw-event"></a><span data-ttu-id="b6ca4-103">Zdarzenie ETW stosu</span><span class="sxs-lookup"><span data-stu-id="b6ca4-103">Stack ETW Event</span></span>

<span data-ttu-id="b6ca4-104">Zdarzenia stosu należy używać w połączeniu z innymi zdarzeniami w celu generowania śladów stosu po podniesieniu zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="b6ca4-104">The stack event should be used in conjunction with other events to generate stack traces after an event is raised.</span></span> <span data-ttu-id="b6ca4-105">Jest on rejestrowany po włączeniu dostawcy środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="b6ca4-105">It is logged when the runtime provider is enabled.</span></span> <span data-ttu-id="b6ca4-106">Jest to zdarzenie o dużej częstotliwości, ponieważ jest zgłaszane przy każdym wywołaniu innego zdarzenia środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="b6ca4-106">This is a very high frequency event, because it is raised whenever another runtime event is raised.</span></span> <span data-ttu-id="b6ca4-107">Z tego powodu zaleca się użycie tego zdarzenia z zachowaniem ostrożności.</span><span class="sxs-lookup"><span data-stu-id="b6ca4-107">For this reason, we recommend that you use this event with caution.</span></span>  
  
 <span data-ttu-id="b6ca4-108">W poniższej tabeli przedstawiono słowo kluczowe i poziom.</span><span class="sxs-lookup"><span data-stu-id="b6ca4-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="b6ca4-109">(Aby uzyskać więcej informacji, zobacz [słowa kluczowe i poziomy ETW CLR](clr-etw-keywords-and-levels.md)).</span><span class="sxs-lookup"><span data-stu-id="b6ca4-109">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="b6ca4-110">Słowo kluczowe do podniesienia zdarzenia</span><span class="sxs-lookup"><span data-stu-id="b6ca4-110">Keyword for raising the event</span></span>|<span data-ttu-id="b6ca4-111">Poziom</span><span class="sxs-lookup"><span data-stu-id="b6ca4-111">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="b6ca4-112">`StackKeyword` 0x40000000</span><span class="sxs-lookup"><span data-stu-id="b6ca4-112">`StackKeyword` (0x40000000)</span></span>|<span data-ttu-id="b6ca4-113">LogAlways (0)</span><span class="sxs-lookup"><span data-stu-id="b6ca4-113">LogAlways(0)</span></span>|  
  
 <span data-ttu-id="b6ca4-114">W poniższej tabeli przedstawiono informacje o zdarzeniu.</span><span class="sxs-lookup"><span data-stu-id="b6ca4-114">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="b6ca4-115">Zdarzenie</span><span class="sxs-lookup"><span data-stu-id="b6ca4-115">Event</span></span>|<span data-ttu-id="b6ca4-116">Identyfikator zdarzenia</span><span class="sxs-lookup"><span data-stu-id="b6ca4-116">Event ID</span></span>|<span data-ttu-id="b6ca4-117">Wywoływane, gdy</span><span class="sxs-lookup"><span data-stu-id="b6ca4-117">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`CLRStackWalk`|<span data-ttu-id="b6ca4-118">82</span><span class="sxs-lookup"><span data-stu-id="b6ca4-118">82</span></span>|<span data-ttu-id="b6ca4-119">W połączeniu z innymi zdarzeniami do generowania śladów stosu po zdarzeniu.</span><span class="sxs-lookup"><span data-stu-id="b6ca4-119">In conjunction with other events to generate stack traces following an event.</span></span>|  
  
 <span data-ttu-id="b6ca4-120">W poniższej tabeli przedstawiono dane zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="b6ca4-120">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="b6ca4-121">Nazwa pola</span><span class="sxs-lookup"><span data-stu-id="b6ca4-121">Field name</span></span>|<span data-ttu-id="b6ca4-122">Typ danych</span><span class="sxs-lookup"><span data-stu-id="b6ca4-122">Data Type</span></span>|<span data-ttu-id="b6ca4-123">Opis</span><span class="sxs-lookup"><span data-stu-id="b6ca4-123">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="b6ca4-124">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="b6ca4-124">ClrInstanceID</span></span>|<span data-ttu-id="b6ca4-125">win: UInt16</span><span class="sxs-lookup"><span data-stu-id="b6ca4-125">win:Uint16</span></span>|<span data-ttu-id="b6ca4-126">Unikatowy identyfikator środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="b6ca4-126">Unique runtime identifier.</span></span>|  
|<span data-ttu-id="b6ca4-127">Reserved1</span><span class="sxs-lookup"><span data-stu-id="b6ca4-127">Reserved1</span></span>|<span data-ttu-id="b6ca4-128">win: UInt8</span><span class="sxs-lookup"><span data-stu-id="b6ca4-128">win:UInt8</span></span>|<span data-ttu-id="b6ca4-129">Zarezerwowany.</span><span class="sxs-lookup"><span data-stu-id="b6ca4-129">Reserved.</span></span>|  
|<span data-ttu-id="b6ca4-130">Reserved2</span><span class="sxs-lookup"><span data-stu-id="b6ca4-130">Reserved2</span></span>|<span data-ttu-id="b6ca4-131">win: UInt8</span><span class="sxs-lookup"><span data-stu-id="b6ca4-131">win:UInt8</span></span>|<span data-ttu-id="b6ca4-132">Zarezerwowany.</span><span class="sxs-lookup"><span data-stu-id="b6ca4-132">Reserved.</span></span>|  
|<span data-ttu-id="b6ca4-133">FrameCount</span><span class="sxs-lookup"><span data-stu-id="b6ca4-133">FrameCount</span></span>|<span data-ttu-id="b6ca4-134">win: UInt32</span><span class="sxs-lookup"><span data-stu-id="b6ca4-134">win:UInt32</span></span>|<span data-ttu-id="b6ca4-135">Liczba ramek w śladzie stosu.</span><span class="sxs-lookup"><span data-stu-id="b6ca4-135">The number of frames in the stack trace.</span></span>|  
|<span data-ttu-id="b6ca4-136">Stos</span><span class="sxs-lookup"><span data-stu-id="b6ca4-136">Stack</span></span>|<span data-ttu-id="b6ca4-137">win: wskaźnik</span><span class="sxs-lookup"><span data-stu-id="b6ca4-137">win:Pointer</span></span>|<span data-ttu-id="b6ca4-138">Kolumny wskaźników instrukcji.</span><span class="sxs-lookup"><span data-stu-id="b6ca4-138">Columns of instruction pointers.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b6ca4-139">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b6ca4-139">See also</span></span>

- [<span data-ttu-id="b6ca4-140">Zdarzenia ETW CLR</span><span class="sxs-lookup"><span data-stu-id="b6ca4-140">CLR ETW Events</span></span>](clr-etw-events.md)
