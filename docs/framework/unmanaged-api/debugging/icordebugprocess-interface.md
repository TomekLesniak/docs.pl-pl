---
title: ICorDebugProcess, interfejs
ms.date: 03/30/2017
api_name:
- ICorDebugProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess
helpviewer_keywords:
- ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: be86f4b5-418a-4c5c-a67c-97148c65ed8c
topic_type:
- apiref
ms.openlocfilehash: 7f9d4ac99234545ef75d9b91e6e84f79a133ffef
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95694922"
---
# <a name="icordebugprocess-interface"></a><span data-ttu-id="7354b-102">ICorDebugProcess, interfejs</span><span class="sxs-lookup"><span data-stu-id="7354b-102">ICorDebugProcess Interface</span></span>

<span data-ttu-id="7354b-103">Reprezentuje proces, który wykonuje kod zarządzany.</span><span class="sxs-lookup"><span data-stu-id="7354b-103">Represents a process that is executing managed code.</span></span> <span data-ttu-id="7354b-104">Ten interfejs jest podklasą elementu ICorDebugController.</span><span class="sxs-lookup"><span data-stu-id="7354b-104">This interface is a subclass of ICorDebugController.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7354b-105">Metody</span><span class="sxs-lookup"><span data-stu-id="7354b-105">Methods</span></span>  
  
|<span data-ttu-id="7354b-106">Metoda</span><span class="sxs-lookup"><span data-stu-id="7354b-106">Method</span></span>|<span data-ttu-id="7354b-107">Opis</span><span class="sxs-lookup"><span data-stu-id="7354b-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7354b-108">ClearCurrentException, metoda</span><span class="sxs-lookup"><span data-stu-id="7354b-108">ClearCurrentException Method</span></span>](icordebugprocess-clearcurrentexception-method.md)|<span data-ttu-id="7354b-109">Czyści bieżący wyjątek niezarządzany w danym wątku.</span><span class="sxs-lookup"><span data-stu-id="7354b-109">Clears the current unmanaged exception on the given thread.</span></span>|  
|[<span data-ttu-id="7354b-110">EnableLogMessages, metoda</span><span class="sxs-lookup"><span data-stu-id="7354b-110">EnableLogMessages Method</span></span>](icordebugprocess-enablelogmessages-method.md)|<span data-ttu-id="7354b-111">Włącza i wyłącza wysyłanie komunikatów dziennika do debugera.</span><span class="sxs-lookup"><span data-stu-id="7354b-111">Enables and disables the sending of log messages to the debugger.</span></span>|  
|[<span data-ttu-id="7354b-112">EnumerateAppDomains, metoda</span><span class="sxs-lookup"><span data-stu-id="7354b-112">EnumerateAppDomains Method</span></span>](icordebugprocess-enumerateappdomains-method.md)|<span data-ttu-id="7354b-113">Wylicza wszystkie domeny aplikacji w procesie.</span><span class="sxs-lookup"><span data-stu-id="7354b-113">Enumerates all of the application domains in the process.</span></span>|  
|[<span data-ttu-id="7354b-114">EnumerateObjects, metoda</span><span class="sxs-lookup"><span data-stu-id="7354b-114">EnumerateObjects Method</span></span>](icordebugprocess-enumerateobjects-method.md)|<span data-ttu-id="7354b-115">Nie zaimplementowano.</span><span class="sxs-lookup"><span data-stu-id="7354b-115">Not implemented.</span></span>|  
|[<span data-ttu-id="7354b-116">GetHandle, metoda</span><span class="sxs-lookup"><span data-stu-id="7354b-116">GetHandle Method</span></span>](icordebugprocess-gethandle-method.md)|<span data-ttu-id="7354b-117">Pobiera dojście do procesu.</span><span class="sxs-lookup"><span data-stu-id="7354b-117">Gets a handle to the process.</span></span>|  
|[<span data-ttu-id="7354b-118">GetHelperThreadID, metoda</span><span class="sxs-lookup"><span data-stu-id="7354b-118">GetHelperThreadID Method</span></span>](icordebugprocess-gethelperthreadid-method.md)|<span data-ttu-id="7354b-119">Pobiera identyfikator wątku systemu operacyjnego dla wewnętrznego wątku pomocnika debugera.</span><span class="sxs-lookup"><span data-stu-id="7354b-119">Gets the operating system (OS) thread ID for the debugger's internal helper thread.</span></span>|  
|[<span data-ttu-id="7354b-120">GetID, metoda</span><span class="sxs-lookup"><span data-stu-id="7354b-120">GetID Method</span></span>](icordebugprocess-getid-method.md)|<span data-ttu-id="7354b-121">Pobiera identyfikator systemu operacyjnego (OS) procesu.</span><span class="sxs-lookup"><span data-stu-id="7354b-121">Gets the operating system (OS) ID of the process.</span></span>|  
|[<span data-ttu-id="7354b-122">GetObject — Metoda</span><span class="sxs-lookup"><span data-stu-id="7354b-122">GetObject Method</span></span>](icordebugprocess-getobject-method.md)|<span data-ttu-id="7354b-123">Nie zaimplementowano.</span><span class="sxs-lookup"><span data-stu-id="7354b-123">Not implemented.</span></span>|  
|[<span data-ttu-id="7354b-124">GetThread, metoda</span><span class="sxs-lookup"><span data-stu-id="7354b-124">GetThread Method</span></span>](icordebugprocess-getthread-method.md)|<span data-ttu-id="7354b-125">Pobiera wystąpienie ICorDebugThread o określonym IDENTYFIKATORze wątku systemu operacyjnego.</span><span class="sxs-lookup"><span data-stu-id="7354b-125">Gets the ICorDebugThread instance that has the specified OS thread ID.</span></span>|  
|[<span data-ttu-id="7354b-126">GetThreadContext, metoda</span><span class="sxs-lookup"><span data-stu-id="7354b-126">GetThreadContext Method</span></span>](icordebugprocess-getthreadcontext-method.md)|<span data-ttu-id="7354b-127">Pobiera kontekst dla danego wątku.</span><span class="sxs-lookup"><span data-stu-id="7354b-127">Gets the context for the given thread.</span></span>|  
|[<span data-ttu-id="7354b-128">IsOSSuspended, metoda</span><span class="sxs-lookup"><span data-stu-id="7354b-128">IsOSSuspended Method</span></span>](icordebugprocess-isossuspended-method.md)|<span data-ttu-id="7354b-129">Określa, czy wątek został wstrzymany w wyniku debugera zatrzymywania procesu.</span><span class="sxs-lookup"><span data-stu-id="7354b-129">Determines whether the thread has been suspended as a result of the debugger stopping the process.</span></span>|  
|[<span data-ttu-id="7354b-130">IsTransitionStub, metoda</span><span class="sxs-lookup"><span data-stu-id="7354b-130">IsTransitionStub Method</span></span>](icordebugprocess-istransitionstub-method.md)|<span data-ttu-id="7354b-131">Określa, czy adres znajduje się wewnątrz klasy zastępczej, która spowoduje przejście do kodu zarządzanego.</span><span class="sxs-lookup"><span data-stu-id="7354b-131">Determines whether an address is inside a stub that will cause a transition to managed code.</span></span>|  
|[<span data-ttu-id="7354b-132">ModifyLogSwitch, metoda</span><span class="sxs-lookup"><span data-stu-id="7354b-132">ModifyLogSwitch Method</span></span>](icordebugprocess-modifylogswitch-method.md)|<span data-ttu-id="7354b-133">Ustawia poziom ważności określonego przełącznika dziennika.</span><span class="sxs-lookup"><span data-stu-id="7354b-133">Sets the severity level of the specified log switch.</span></span>|  
|[<span data-ttu-id="7354b-134">ReadMemory, metoda</span><span class="sxs-lookup"><span data-stu-id="7354b-134">ReadMemory Method</span></span>](icordebugprocess-readmemory-method.md)|<span data-ttu-id="7354b-135">Odczytuje pamięć z procesu.</span><span class="sxs-lookup"><span data-stu-id="7354b-135">Reads memory from the process.</span></span>|  
|[<span data-ttu-id="7354b-136">SetThreadContext, metoda</span><span class="sxs-lookup"><span data-stu-id="7354b-136">SetThreadContext Method</span></span>](icordebugprocess-setthreadcontext-method.md)|<span data-ttu-id="7354b-137">Ustawia kontekst dla danego wątku.</span><span class="sxs-lookup"><span data-stu-id="7354b-137">Sets the context for the given thread.</span></span>|  
|[<span data-ttu-id="7354b-138">ThreadForFiberCookie, metoda</span><span class="sxs-lookup"><span data-stu-id="7354b-138">ThreadForFiberCookie Method</span></span>](icordebugprocess-threadforfibercookie-method.md)|<span data-ttu-id="7354b-139">Przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="7354b-139">Deprecated.</span></span>|  
|[<span data-ttu-id="7354b-140">WriteMemory, metoda</span><span class="sxs-lookup"><span data-stu-id="7354b-140">WriteMemory Method</span></span>](icordebugprocess-writememory-method.md)|<span data-ttu-id="7354b-141">Zapisuje dane w obszarze pamięci w procesie.</span><span class="sxs-lookup"><span data-stu-id="7354b-141">Writes data to an area of memory in the process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7354b-142">Uwagi</span><span class="sxs-lookup"><span data-stu-id="7354b-142">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7354b-143">Ten interfejs nie obsługuje wywoływania zdalnego na wielu maszynach ani wielu procesów.</span><span class="sxs-lookup"><span data-stu-id="7354b-143">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7354b-144">Wymagania</span><span class="sxs-lookup"><span data-stu-id="7354b-144">Requirements</span></span>  

 <span data-ttu-id="7354b-145">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7354b-145">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7354b-146">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="7354b-146">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7354b-147">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="7354b-147">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7354b-148">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7354b-148">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7354b-149">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="7354b-149">See also</span></span>

- [<span data-ttu-id="7354b-150">ICorDebug — Interfejs</span><span class="sxs-lookup"><span data-stu-id="7354b-150">ICorDebug Interface</span></span>](icordebug-interface.md)
- [<span data-ttu-id="7354b-151">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="7354b-151">Debugging Interfaces</span></span>](debugging-interfaces.md)
