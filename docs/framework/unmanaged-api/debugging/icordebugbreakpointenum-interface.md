---
title: ICorDebugBreakpointEnum, interfejs
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpointEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpointEnum
helpviewer_keywords:
- ICorDebugBreakpointEnum interface [.NET Framework debugging]
ms.assetid: 4c6f4f6e-52cc-402e-881b-7b8526544c90
topic_type:
- apiref
ms.openlocfilehash: 97e06a2f20dcc2bb3815b98ba29ff230e37ff29d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730165"
---
# <a name="icordebugbreakpointenum-interface"></a><span data-ttu-id="6eaa5-102">ICorDebugBreakpointEnum, interfejs</span><span class="sxs-lookup"><span data-stu-id="6eaa5-102">ICorDebugBreakpointEnum Interface</span></span>

<span data-ttu-id="6eaa5-103">Implementuje metody ICorDebugEnum i wylicza tablice ICorDebugBreakpoint.</span><span class="sxs-lookup"><span data-stu-id="6eaa5-103">Implements ICorDebugEnum methods, and enumerates ICorDebugBreakpoint arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6eaa5-104">Metody</span><span class="sxs-lookup"><span data-stu-id="6eaa5-104">Methods</span></span>  
  
|<span data-ttu-id="6eaa5-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="6eaa5-105">Method</span></span>|<span data-ttu-id="6eaa5-106">Opis</span><span class="sxs-lookup"><span data-stu-id="6eaa5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6eaa5-107">Next, metoda</span><span class="sxs-lookup"><span data-stu-id="6eaa5-107">Next Method</span></span>](icordebugbreakpointenum-next-method.md)|<span data-ttu-id="6eaa5-108">Pobiera określoną liczbę `ICorDebugBreakpoint` wystąpień z wyliczenia, rozpoczynając od bieżącego położenia.</span><span class="sxs-lookup"><span data-stu-id="6eaa5-108">Gets the specified number of `ICorDebugBreakpoint` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6eaa5-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="6eaa5-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6eaa5-110">Ten interfejs nie obsługuje wywoływania zdalnego na wielu maszynach ani wielu procesów.</span><span class="sxs-lookup"><span data-stu-id="6eaa5-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6eaa5-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="6eaa5-111">Requirements</span></span>  

 <span data-ttu-id="6eaa5-112">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6eaa5-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6eaa5-113">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="6eaa5-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6eaa5-114">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="6eaa5-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6eaa5-115">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6eaa5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6eaa5-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="6eaa5-116">See also</span></span>

- [<span data-ttu-id="6eaa5-117">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="6eaa5-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
