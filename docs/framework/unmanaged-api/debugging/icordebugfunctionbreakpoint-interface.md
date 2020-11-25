---
title: ICorDebugFunctionBreakpoint, interfejs
ms.date: 03/30/2017
api_name:
- ICorDebugFunctionBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunctionBreakpoint
helpviewer_keywords:
- ICorDebugFunctionBreakpoint interface [.NET Framework debugging]
ms.assetid: 9c149303-14b1-4138-83d7-e8c3e0fcd332
topic_type:
- apiref
ms.openlocfilehash: 0f1e6bbdf16c953b0dd22d9dfa44bc3585f1269e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726252"
---
# <a name="icordebugfunctionbreakpoint-interface"></a><span data-ttu-id="db908-102">ICorDebugFunctionBreakpoint, interfejs</span><span class="sxs-lookup"><span data-stu-id="db908-102">ICorDebugFunctionBreakpoint Interface</span></span>

<span data-ttu-id="db908-103">Rozszerza interfejs ICorDebugBreakpoint w celu obsługi punktów przerwania w funkcjach.</span><span class="sxs-lookup"><span data-stu-id="db908-103">Extends the ICorDebugBreakpoint interface to support breakpoints within functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="db908-104">Metody</span><span class="sxs-lookup"><span data-stu-id="db908-104">Methods</span></span>  
  
|<span data-ttu-id="db908-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="db908-105">Method</span></span>|<span data-ttu-id="db908-106">Opis</span><span class="sxs-lookup"><span data-stu-id="db908-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="db908-107">GetFunction, metoda</span><span class="sxs-lookup"><span data-stu-id="db908-107">GetFunction Method</span></span>](icordebugfunctionbreakpoint-getfunction-method.md)|<span data-ttu-id="db908-108">Pobiera wskaźnik interfejsu do elementu ICorDebugFunction, który odwołuje się do funkcji, w której jest ustawiony punkt przerwania.</span><span class="sxs-lookup"><span data-stu-id="db908-108">Gets an interface pointer to an ICorDebugFunction that references the function in which the breakpoint is set.</span></span>|  
|[<span data-ttu-id="db908-109">GetOffset — Metoda</span><span class="sxs-lookup"><span data-stu-id="db908-109">GetOffset Method</span></span>](icordebugfunctionbreakpoint-getoffset-method.md)|<span data-ttu-id="db908-110">Pobiera przesunięcie punktu przerwania w funkcji.</span><span class="sxs-lookup"><span data-stu-id="db908-110">Gets the offset of the breakpoint within the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="db908-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="db908-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="db908-112">Ten interfejs nie obsługuje wywoływania zdalnego na wielu maszynach ani wielu procesów.</span><span class="sxs-lookup"><span data-stu-id="db908-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db908-113">Wymagania</span><span class="sxs-lookup"><span data-stu-id="db908-113">Requirements</span></span>  

 <span data-ttu-id="db908-114">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db908-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db908-115">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="db908-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="db908-116">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="db908-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="db908-117">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db908-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db908-118">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="db908-118">See also</span></span>

- [<span data-ttu-id="db908-119">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="db908-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
