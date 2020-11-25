---
title: ICorDebugEnum::Skip — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugEnum.Skip
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEnum::Skip
helpviewer_keywords:
- ICorDebugEnum::Skip method [.NET Framework debugging]
- Skip method, ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: e925d88a-67a5-4f76-88b8-09cedeed0232
topic_type:
- apiref
ms.openlocfilehash: ae88336b9640b68b97522d252b3e8334c20ed9bc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705868"
---
# <a name="icordebugenumskip-method"></a><span data-ttu-id="4ad3d-102">ICorDebugEnum::Skip — Metoda</span><span class="sxs-lookup"><span data-stu-id="4ad3d-102">ICorDebugEnum::Skip Method</span></span>

<span data-ttu-id="4ad3d-103">Przenosi kursor do przodu w wyliczeniu o określoną liczbę elementów.</span><span class="sxs-lookup"><span data-stu-id="4ad3d-103">Moves the cursor forward in the enumeration by the specified number of items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ad3d-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="4ad3d-104">Syntax</span></span>  
  
```cpp  
HRESULT Skip (  
    [in] ULONG celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4ad3d-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="4ad3d-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="4ad3d-106">podczas Liczba elementów, przez którą ma zostać przesunięty kursor do przodu.</span><span class="sxs-lookup"><span data-stu-id="4ad3d-106">[in] The number of items by which to move the cursor forward.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ad3d-107">Wymagania</span><span class="sxs-lookup"><span data-stu-id="4ad3d-107">Requirements</span></span>  

 <span data-ttu-id="4ad3d-108">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4ad3d-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ad3d-109">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="4ad3d-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4ad3d-110">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="4ad3d-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4ad3d-111">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ad3d-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ad3d-112">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="4ad3d-112">See also</span></span>

- [<span data-ttu-id="4ad3d-113">ICorDebugEnum, interfejs</span><span class="sxs-lookup"><span data-stu-id="4ad3d-113">ICorDebugEnum Interface</span></span>](icordebugenum-interface1.md)
