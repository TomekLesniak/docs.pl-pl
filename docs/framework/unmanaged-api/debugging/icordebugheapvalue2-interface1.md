---
title: ICorDebugHeapValue2, interfejs
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue2
helpviewer_keywords:
- ICorDebugHeapValue2 interface [.NET Framework debugging]
ms.assetid: 87360a52-90b1-4ada-80c0-589a556116d8
topic_type:
- apiref
ms.openlocfilehash: c959856e8c019f95d38cac9bc4d8d03bc31ef195
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726551"
---
# <a name="icordebugheapvalue2-interface"></a><span data-ttu-id="73af9-102">ICorDebugHeapValue2, interfejs</span><span class="sxs-lookup"><span data-stu-id="73af9-102">ICorDebugHeapValue2 Interface</span></span>

<span data-ttu-id="73af9-103">Rozszerzenie ICorDebugHeapValue, które zapewnia obsługę uchwytów środowiska uruchomieniowego języka wspólnego (CLR).</span><span class="sxs-lookup"><span data-stu-id="73af9-103">An extension of ICorDebugHeapValue that provides support for common language runtime (CLR) handles.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="73af9-104">Metody</span><span class="sxs-lookup"><span data-stu-id="73af9-104">Methods</span></span>  
  
|<span data-ttu-id="73af9-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="73af9-105">Method</span></span>|<span data-ttu-id="73af9-106">Opis</span><span class="sxs-lookup"><span data-stu-id="73af9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="73af9-107">CreateHandle, metoda</span><span class="sxs-lookup"><span data-stu-id="73af9-107">CreateHandle Method</span></span>](icordebugheapvalue2-createhandle-method.md)|<span data-ttu-id="73af9-108">Tworzy dojście określonego typu dla tego `ICorDebugHeapValue2` obiektu.</span><span class="sxs-lookup"><span data-stu-id="73af9-108">Creates a handle of the specified type for this `ICorDebugHeapValue2` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="73af9-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="73af9-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="73af9-110">Ten interfejs nie obsługuje wywoływania zdalnego na wielu maszynach ani wielu procesów.</span><span class="sxs-lookup"><span data-stu-id="73af9-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73af9-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="73af9-111">Requirements</span></span>  

 <span data-ttu-id="73af9-112">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="73af9-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73af9-113">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="73af9-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="73af9-114">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="73af9-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="73af9-115">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73af9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73af9-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="73af9-116">See also</span></span>

- [<span data-ttu-id="73af9-117">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="73af9-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
