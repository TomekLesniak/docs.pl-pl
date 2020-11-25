---
title: ICorDebugStepperEnum, interfejs
ms.date: 03/30/2017
api_name:
- ICorDebugStepperEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepperEnum
helpviewer_keywords:
- ICorDebugStepperEnum interface [.NET Framework debugging]
ms.assetid: 988718c1-1a4a-40f2-a04c-7d67e5cfe1e2
topic_type:
- apiref
ms.openlocfilehash: facea5cd7f0b0e0e6c0b1049e87a2355f1d3965a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95697171"
---
# <a name="icordebugstepperenum-interface"></a><span data-ttu-id="65926-102">ICorDebugStepperEnum, interfejs</span><span class="sxs-lookup"><span data-stu-id="65926-102">ICorDebugStepperEnum Interface</span></span>

<span data-ttu-id="65926-103">Implementuje metody ICorDebugEnum i wylicza tablice ICorDebugStepper.</span><span class="sxs-lookup"><span data-stu-id="65926-103">Implements ICorDebugEnum methods, and enumerates ICorDebugStepper arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="65926-104">Metody</span><span class="sxs-lookup"><span data-stu-id="65926-104">Methods</span></span>  
  
|<span data-ttu-id="65926-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="65926-105">Method</span></span>|<span data-ttu-id="65926-106">Opis</span><span class="sxs-lookup"><span data-stu-id="65926-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="65926-107">Next, metoda</span><span class="sxs-lookup"><span data-stu-id="65926-107">Next Method</span></span>](icordebugstepperenum-next-method.md)|<span data-ttu-id="65926-108">Pobiera określoną liczbę `ICorDebugStepper` wystąpień z wyliczenia, rozpoczynając od bieżącego położenia.</span><span class="sxs-lookup"><span data-stu-id="65926-108">Gets the specified number of `ICorDebugStepper` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="65926-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="65926-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="65926-110">Ten interfejs nie obsługuje wywoływania zdalnego na wielu maszynach ani wielu procesów.</span><span class="sxs-lookup"><span data-stu-id="65926-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65926-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="65926-111">Requirements</span></span>  

 <span data-ttu-id="65926-112">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="65926-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65926-113">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="65926-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="65926-114">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="65926-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="65926-115">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65926-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65926-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="65926-116">See also</span></span>

- [<span data-ttu-id="65926-117">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="65926-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
