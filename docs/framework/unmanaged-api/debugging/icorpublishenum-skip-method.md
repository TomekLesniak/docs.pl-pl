---
title: ICorPublishEnum::Skip — Metoda
ms.date: 03/30/2017
api_name:
- ICorPublishEnum.Skip
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishEnum::Skip
helpviewer_keywords:
- ICorPublishEnum::Skip method [.NET Framework debugging]
- Skip method, ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: 1680ec06-4ab0-447e-93ad-cdb8693fde5c
topic_type:
- apiref
ms.openlocfilehash: 888cc40c194cb86b0f898f5556ea14b8897e08c7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95693310"
---
# <a name="icorpublishenumskip-method"></a><span data-ttu-id="df194-102">ICorPublishEnum::Skip — Metoda</span><span class="sxs-lookup"><span data-stu-id="df194-102">ICorPublishEnum::Skip Method</span></span>

<span data-ttu-id="df194-103">Przenosi kursor do przodu w wyliczeniu o określoną liczbę elementów.</span><span class="sxs-lookup"><span data-stu-id="df194-103">Moves the cursor forward in the enumeration by the specified number of items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df194-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="df194-104">Syntax</span></span>  
  
```cpp  
HRESULT Skip (  
    [in] ULONG   celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="df194-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="df194-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="df194-106">podczas Liczba elementów, przez którą ma zostać przesunięty kursor do przodu.</span><span class="sxs-lookup"><span data-stu-id="df194-106">[in] The number of items by which to move the cursor forward.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df194-107">Wymagania</span><span class="sxs-lookup"><span data-stu-id="df194-107">Requirements</span></span>  

 <span data-ttu-id="df194-108">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="df194-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df194-109">**Nagłówek:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="df194-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="df194-110">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="df194-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="df194-111">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df194-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df194-112">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="df194-112">See also</span></span>

- [<span data-ttu-id="df194-113">ICorPublishEnum — Interfejs</span><span class="sxs-lookup"><span data-stu-id="df194-113">ICorPublishEnum Interface</span></span>](icorpublishenum-interface.md)
