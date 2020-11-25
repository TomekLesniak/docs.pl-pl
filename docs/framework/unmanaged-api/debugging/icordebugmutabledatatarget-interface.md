---
title: ICorDebugMutableDataTarget, interfejs
ms.date: 03/30/2017
ms.assetid: 14aad5b3-84ab-4bbc-94e3-1eb92e258d10
ms.openlocfilehash: cd22707832504ca2f08299872bc39bca2af782bb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709352"
---
# <a name="icordebugmutabledatatarget-interface"></a><span data-ttu-id="9afbc-102">ICorDebugMutableDataTarget, interfejs</span><span class="sxs-lookup"><span data-stu-id="9afbc-102">ICorDebugMutableDataTarget Interface</span></span>

<span data-ttu-id="9afbc-103">Rozszerza interfejs [ICorDebugDataTarget](icordebugdatatarget-interface.md) w celu obsługi modyfikowalnych obiektów docelowych danych.</span><span class="sxs-lookup"><span data-stu-id="9afbc-103">Extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface to support mutable data targets.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9afbc-104">Metody</span><span class="sxs-lookup"><span data-stu-id="9afbc-104">Methods</span></span>  
  
|<span data-ttu-id="9afbc-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="9afbc-105">Method</span></span>|<span data-ttu-id="9afbc-106">Opis</span><span class="sxs-lookup"><span data-stu-id="9afbc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9afbc-107">ContinueStatusChanged, metoda</span><span class="sxs-lookup"><span data-stu-id="9afbc-107">ContinueStatusChanged Method</span></span>](icordebugmutabledatatarget-continuestatuschanged-method.md)|<span data-ttu-id="9afbc-108">Zmienia stan kontynuacji dla zaległego zdarzenia debugowania w określonym wątku.</span><span class="sxs-lookup"><span data-stu-id="9afbc-108">Changes the continuation status for the outstanding debug event on the specified thread.</span></span>|  
|[<span data-ttu-id="9afbc-109">SetThreadContext, metoda</span><span class="sxs-lookup"><span data-stu-id="9afbc-109">SetThreadContext Method</span></span>](icordebugmutabledatatarget-setthreadcontext-method.md)|<span data-ttu-id="9afbc-110">Ustawia kontekst (wartości rejestru) dla wątku.</span><span class="sxs-lookup"><span data-stu-id="9afbc-110">Sets the context (register values) for a thread.</span></span>|  
|[<span data-ttu-id="9afbc-111">WriteVirtual, metoda</span><span class="sxs-lookup"><span data-stu-id="9afbc-111">WriteVirtual Method</span></span>](icordebugmutabledatatarget-writevirtual-method.md)|<span data-ttu-id="9afbc-112">Zapisuje pamięć w przestrzeni adresowej procesu docelowego.</span><span class="sxs-lookup"><span data-stu-id="9afbc-112">Writes memory into the target process address space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9afbc-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="9afbc-113">Remarks</span></span>  

 <span data-ttu-id="9afbc-114">To rozszerzenie interfejsu [ICorDebugDataTarget](icordebugdatatarget-interface.md) może zostać zaimplementowane przez narzędzia debugowania, które chcą zmodyfikować proces docelowy (na przykład w celu przeprowadzenia aktywnego debugowania).</span><span class="sxs-lookup"><span data-stu-id="9afbc-114">This extension to the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface can be implemented by debugging tools that wish to modify the target process (for example, to perform live invasive debugging).</span></span>  
  
 <span data-ttu-id="9afbc-115">Wszystkie te metody są opcjonalne w tym sensie, że żadne podstawowe funkcje debugowania nie są tracone przez zaimplementowanie tego interfejsu lub niepowodzenie wywołań tych metod.</span><span class="sxs-lookup"><span data-stu-id="9afbc-115">All of these methods are optional in the sense that no core inspection-based debugging functionality is lost by not implementing this interface or by the failure of calls to these methods.</span></span>  <span data-ttu-id="9afbc-116">Wszelkie błędy `HRESULT` z tych metod zostaną rozpropagowane jako `HRESULT` z wywołania metody ICorDebug.</span><span class="sxs-lookup"><span data-stu-id="9afbc-116">Any failure `HRESULT` from these methods will propagate out as the `HRESULT` from the ICorDebug method call.</span></span>  
  
 <span data-ttu-id="9afbc-117">Należy zauważyć, że pojedyncze wywołanie metody ICorDebug może spowodować wielokrotne mutacje i że nie ma mechanizmu zapewnienia, że powiązane mutacje są stosowane transakcyjnie (wszystkie-lub-None).</span><span class="sxs-lookup"><span data-stu-id="9afbc-117">Note that a single ICorDebug method call may result in multiple mutations, and that there is no mechanism for ensuring related mutations are applied transactionally (all-or-none).</span></span>  <span data-ttu-id="9afbc-118">Oznacza to, że jeśli mutacja nie powiedzie się po pomyślnym przejściu (dla tego samego wywołania ICorDebug), proces docelowy może pozostać w niespójnym stanie, a debugowanie może stać się niezawodne.</span><span class="sxs-lookup"><span data-stu-id="9afbc-118">This means that if a mutation fails after others (for the same ICorDebug call) have succeeded, the target process may be left in an inconsistent state and debugging may become unreliable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9afbc-119">Wymagania</span><span class="sxs-lookup"><span data-stu-id="9afbc-119">Requirements</span></span>  

 <span data-ttu-id="9afbc-120">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9afbc-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9afbc-121">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="9afbc-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9afbc-122">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="9afbc-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9afbc-123">**.NET Framework wersje:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9afbc-123">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9afbc-124">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="9afbc-124">See also</span></span>

- [<span data-ttu-id="9afbc-125">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="9afbc-125">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="9afbc-126">Debugowanie</span><span class="sxs-lookup"><span data-stu-id="9afbc-126">Debugging</span></span>](index.md)
