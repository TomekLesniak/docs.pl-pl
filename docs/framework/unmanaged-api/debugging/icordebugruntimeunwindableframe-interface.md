---
title: ICorDebugRuntimeUnwindableFrame — Interfejs
ms.date: 03/30/2017
api_name:
- ICorDebugUnwindableFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugUnwindableFrame
helpviewer_keywords:
- ICorDebugUnwindableFrame interface [.NET Framework debugging]
ms.assetid: cd6a3982-6ed3-4909-808d-a66055e813e0
topic_type:
- apiref
ms.openlocfilehash: 6619b8888588341f23a93b83865cd2e75cc9b3db
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712017"
---
# <a name="icordebugruntimeunwindableframe-interface"></a><span data-ttu-id="79230-102">ICorDebugRuntimeUnwindableFrame — Interfejs</span><span class="sxs-lookup"><span data-stu-id="79230-102">ICorDebugRuntimeUnwindableFrame Interface</span></span>

<span data-ttu-id="79230-103">Zapewnia obsługę niezarządzanych metod, które wymagają środowiska uruchomieniowego języka wspólnego (CLR), aby zwolnić ramkę.</span><span class="sxs-lookup"><span data-stu-id="79230-103">Provides support for unmanaged methods that require the common language runtime (CLR) to unwind a frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="79230-104">Uwagi</span><span class="sxs-lookup"><span data-stu-id="79230-104">Remarks</span></span>  

 <span data-ttu-id="79230-105">`ICorDebugRuntimeUnwindableFrame` to wyspecjalizowana wersja interfejsu ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="79230-105">`ICorDebugRuntimeUnwindableFrame` is a specialized version of the ICorDebugFrame interface.</span></span> <span data-ttu-id="79230-106">Jest on używany przez metody niezarządzane, które wymagają wykonania przez środowisko uruchomieniowe ramki na bieżącym stosie.</span><span class="sxs-lookup"><span data-stu-id="79230-106">It is used by unmanaged methods that require the runtime to unwind a frame on the current stack.</span></span> <span data-ttu-id="79230-107">Istniejące konwencje odwinięcia nie działają, ponieważ nie używają kodu skompilowanego JIT.</span><span class="sxs-lookup"><span data-stu-id="79230-107">Existing unwinding conventions do not work, because they do not use JIT-compiled code.</span></span> <span data-ttu-id="79230-108">Gdy debuger widzi niewidocznyą ramkę, powinien użyć metody [ICorDebugStackWalk:: Next](icordebugstackwalk-next-method.md) , aby ją rozwinięcie, ale powinien wykonać inspekcję.</span><span class="sxs-lookup"><span data-stu-id="79230-108">When the debugger sees an unwindable frame, it should use the [ICorDebugStackWalk::Next](icordebugstackwalk-next-method.md) method to unwind it, but it should perform inspection itself.</span></span> <span data-ttu-id="79230-109">Gdy debuger odbiera `ICorDebugRuntimeUnwindableFrame` , może wywołać metodę [ICorDebugStackWalk:: GetContext](icordebugstackwalk-getcontext-method.md) w celu pobrania kontekstu ramki.</span><span class="sxs-lookup"><span data-stu-id="79230-109">When the debugger receives an `ICorDebugRuntimeUnwindableFrame`, it can call the [ICorDebugStackWalk::GetContext](icordebugstackwalk-getcontext-method.md) method to retrieve the context of the frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79230-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="79230-110">Requirements</span></span>  

 <span data-ttu-id="79230-111">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="79230-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79230-112">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="79230-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="79230-113">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="79230-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="79230-114">**.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="79230-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79230-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="79230-115">See also</span></span>

- [<span data-ttu-id="79230-116">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="79230-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="79230-117">Debugowanie</span><span class="sxs-lookup"><span data-stu-id="79230-117">Debugging</span></span>](index.md)
