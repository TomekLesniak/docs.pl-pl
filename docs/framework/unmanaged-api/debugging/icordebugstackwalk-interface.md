---
title: ICorDebugStackWalk — Interfejs
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk
helpviewer_keywords:
- ICorDebugStackWalk interface [.NET Framework debugging]
ms.assetid: 16d695e8-975d-431b-8421-e9e6c3e3f476
topic_type:
- apiref
ms.openlocfilehash: b37a89c0a86df49c894dc43676f8feafb80f5c95
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687518"
---
# <a name="icordebugstackwalk-interface"></a><span data-ttu-id="002c1-102">ICorDebugStackWalk — Interfejs</span><span class="sxs-lookup"><span data-stu-id="002c1-102">ICorDebugStackWalk Interface</span></span>

<span data-ttu-id="002c1-103">Dostarcza metody pobierania zarządzanych metod, lub ramek, znajdujących się na stosie wątku.</span><span class="sxs-lookup"><span data-stu-id="002c1-103">Provides methods for getting the managed methods, or frames, on a thread’s stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="002c1-104">Metody</span><span class="sxs-lookup"><span data-stu-id="002c1-104">Methods</span></span>  
  
|<span data-ttu-id="002c1-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="002c1-105">Method</span></span>|<span data-ttu-id="002c1-106">Opis</span><span class="sxs-lookup"><span data-stu-id="002c1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="002c1-107">GetContext — Metoda</span><span class="sxs-lookup"><span data-stu-id="002c1-107">GetContext Method</span></span>](icordebugstackwalk-getcontext-method.md)|<span data-ttu-id="002c1-108">Zwraca kontekst dla bieżącej ramki w `ICorDebugStackWalk` obiekcie.</span><span class="sxs-lookup"><span data-stu-id="002c1-108">Returns the context for the current frame in the `ICorDebugStackWalk` object.</span></span>|  
|[<span data-ttu-id="002c1-109">SetContext, metoda</span><span class="sxs-lookup"><span data-stu-id="002c1-109">SetContext Method</span></span>](icordebugstackwalk-setcontext-method.md)|<span data-ttu-id="002c1-110">Ustawia `ICorDebugStackWalk` bieżący kontekst obiektu na prawidłowy kontekst dla wątku.</span><span class="sxs-lookup"><span data-stu-id="002c1-110">Sets the `ICorDebugStackWalk` object’s current context to a valid context for the thread.</span></span>|  
|[<span data-ttu-id="002c1-111">Next, metoda</span><span class="sxs-lookup"><span data-stu-id="002c1-111">Next Method</span></span>](icordebugstackwalk-next-method.md)|<span data-ttu-id="002c1-112">Przenosi `ICorDebugStackWalk` obiekt do następnej ramki.</span><span class="sxs-lookup"><span data-stu-id="002c1-112">Moves the `ICorDebugStackWalk` object to the next frame.</span></span>|  
|[<span data-ttu-id="002c1-113">GetFrame, metoda</span><span class="sxs-lookup"><span data-stu-id="002c1-113">GetFrame Method</span></span>](icordebugstackwalk-getframe-method.md)|<span data-ttu-id="002c1-114">Pobiera bieżącą ramkę w `ICorDebugStackWalk` obiekcie.</span><span class="sxs-lookup"><span data-stu-id="002c1-114">Gets the current frame in the `ICorDebugStackWalk` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="002c1-115">Uwagi</span><span class="sxs-lookup"><span data-stu-id="002c1-115">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="002c1-116">Ten interfejs nie obsługuje wywoływania zdalnego na wielu maszynach ani wielu procesów.</span><span class="sxs-lookup"><span data-stu-id="002c1-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="002c1-117">Wymagania</span><span class="sxs-lookup"><span data-stu-id="002c1-117">Requirements</span></span>  

 <span data-ttu-id="002c1-118">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="002c1-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="002c1-119">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="002c1-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="002c1-120">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="002c1-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="002c1-121">**.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="002c1-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="002c1-122">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="002c1-122">See also</span></span>

- [<span data-ttu-id="002c1-123">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="002c1-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="002c1-124">Debugowanie</span><span class="sxs-lookup"><span data-stu-id="002c1-124">Debugging</span></span>](index.md)
