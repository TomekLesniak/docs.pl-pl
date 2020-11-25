---
title: ICorDebugHeapValue3 — Interfejs
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue3
helpviewer_keywords:
- ICorDebugHeapValue3 interface [.NET Framework debugging]
ms.assetid: 9c421bb0-e647-4b2d-a986-f3d578cc7f20
topic_type:
- apiref
ms.openlocfilehash: a1f4964c89aa3b658c57946d4b5a0327797118f1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728709"
---
# <a name="icordebugheapvalue3-interface"></a><span data-ttu-id="3f45d-102">ICorDebugHeapValue3 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="3f45d-102">ICorDebugHeapValue3 Interface</span></span>

<span data-ttu-id="3f45d-103">Udostępnia właściwości blokady monitora obiektów.</span><span class="sxs-lookup"><span data-stu-id="3f45d-103">Exposes the monitor lock properties of objects.</span></span> <span data-ttu-id="3f45d-104">Ten interfejs rozszerza interfejsy ICorDebugHeapValue i ICorDebugHeapValue2.</span><span class="sxs-lookup"><span data-stu-id="3f45d-104">This interface extends the ICorDebugHeapValue and ICorDebugHeapValue2 interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3f45d-105">Metody</span><span class="sxs-lookup"><span data-stu-id="3f45d-105">Methods</span></span>  
  
|<span data-ttu-id="3f45d-106">Metoda</span><span class="sxs-lookup"><span data-stu-id="3f45d-106">Method</span></span>|<span data-ttu-id="3f45d-107">Opis</span><span class="sxs-lookup"><span data-stu-id="3f45d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3f45d-108">GetThreadOwningMonitorLock, metoda</span><span class="sxs-lookup"><span data-stu-id="3f45d-108">GetThreadOwningMonitorLock Method</span></span>](icordebugheapvalue3-getthreadowningmonitorlock-method.md)|<span data-ttu-id="3f45d-109">Zwraca zarządzany wątek, który jest właścicielem blokady monitora dla tego obiektu.</span><span class="sxs-lookup"><span data-stu-id="3f45d-109">Returns the managed thread that owns the monitor lock on this object.</span></span>|  
|[<span data-ttu-id="3f45d-110">GetMonitorEventWaitList, metoda</span><span class="sxs-lookup"><span data-stu-id="3f45d-110">GetMonitorEventWaitList Method</span></span>](icordebugheapvalue3-getmonitoreventwaitlist-method.md)|<span data-ttu-id="3f45d-111">Udostępnia uporządkowaną listę wątków, które są umieszczane w kolejce dla zdarzenia, które jest skojarzone z blokadą monitora.</span><span class="sxs-lookup"><span data-stu-id="3f45d-111">Provides an ordered list of threads that are queued on the event that is associated with a monitor lock.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3f45d-112">Uwagi</span><span class="sxs-lookup"><span data-stu-id="3f45d-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3f45d-113">Ten interfejs nie obsługuje wywoływania zdalnego na wielu maszynach ani wielu procesów.</span><span class="sxs-lookup"><span data-stu-id="3f45d-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f45d-114">Wymagania</span><span class="sxs-lookup"><span data-stu-id="3f45d-114">Requirements</span></span>  

 <span data-ttu-id="3f45d-115">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3f45d-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f45d-116">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="3f45d-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3f45d-117">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="3f45d-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3f45d-118">**.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f45d-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f45d-119">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="3f45d-119">See also</span></span>

- [<span data-ttu-id="3f45d-120">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="3f45d-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="3f45d-121">Debugowanie</span><span class="sxs-lookup"><span data-stu-id="3f45d-121">Debugging</span></span>](index.md)
