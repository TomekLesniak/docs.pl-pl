---
title: ICorDebugCodeEnum, interfejs
ms.date: 03/30/2017
api_name:
- ICorDebugCodeEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCodeEnum
helpviewer_keywords:
- ICorDebugCodeEnum interface [.NET Framework debugging]
ms.assetid: b5589171-a4a0-4c00-bbdc-6e0a42233b75
topic_type:
- apiref
ms.openlocfilehash: b611dcabc1e5cc36f5c6342f0a832cc81de8c1d5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720740"
---
# <a name="icordebugcodeenum-interface"></a><span data-ttu-id="baf1a-102">ICorDebugCodeEnum, interfejs</span><span class="sxs-lookup"><span data-stu-id="baf1a-102">ICorDebugCodeEnum Interface</span></span>

<span data-ttu-id="baf1a-103">Implementuje metody "ICorDebugEnum" i wylicza tablice "ICorDebugCode".</span><span class="sxs-lookup"><span data-stu-id="baf1a-103">Implements "ICorDebugEnum" methods, and enumerates "ICorDebugCode" arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="baf1a-104">Metody</span><span class="sxs-lookup"><span data-stu-id="baf1a-104">Methods</span></span>  
  
|<span data-ttu-id="baf1a-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="baf1a-105">Method</span></span>|<span data-ttu-id="baf1a-106">Opis</span><span class="sxs-lookup"><span data-stu-id="baf1a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="baf1a-107">Next, metoda</span><span class="sxs-lookup"><span data-stu-id="baf1a-107">Next Method</span></span>](icordebugcodeenum-next-method.md)|<span data-ttu-id="baf1a-108">Pobiera określoną liczbę `ICorDebugCode` wystąpień z wyliczenia, rozpoczynając od bieżącego położenia.</span><span class="sxs-lookup"><span data-stu-id="baf1a-108">Gets the specified number of `ICorDebugCode` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="baf1a-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="baf1a-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="baf1a-110">Ten interfejs nie obsługuje wywoływania zdalnego na wielu maszynach ani wielu procesów.</span><span class="sxs-lookup"><span data-stu-id="baf1a-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="baf1a-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="baf1a-111">Requirements</span></span>  

 <span data-ttu-id="baf1a-112">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="baf1a-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="baf1a-113">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="baf1a-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="baf1a-114">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="baf1a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="baf1a-115">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="baf1a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="baf1a-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="baf1a-116">See also</span></span>

- [<span data-ttu-id="baf1a-117">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="baf1a-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
