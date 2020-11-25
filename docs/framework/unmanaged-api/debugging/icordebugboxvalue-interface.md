---
title: ICorDebugBoxValue, interfejs
ms.date: 03/30/2017
api_name:
- ICorDebugBoxValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBoxValue
helpviewer_keywords:
- ICorDebugBoxValue interface [.NET Framework debugging]
ms.assetid: 3d3ae7e2-97d4-46de-a2c3-cb78f3490f9d
topic_type:
- apiref
ms.openlocfilehash: 6d58ae048382a78c422703d5c6caeb3bbc739849
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723171"
---
# <a name="icordebugboxvalue-interface"></a><span data-ttu-id="9c8b2-102">ICorDebugBoxValue, interfejs</span><span class="sxs-lookup"><span data-stu-id="9c8b2-102">ICorDebugBoxValue Interface</span></span>

<span data-ttu-id="9c8b2-103">Podklasa elementu "ICorDebugHeapValue" reprezentująca obiekt klasy wartości w ramce.</span><span class="sxs-lookup"><span data-stu-id="9c8b2-103">A subclass of "ICorDebugHeapValue" that represents a boxed value class object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9c8b2-104">Metody</span><span class="sxs-lookup"><span data-stu-id="9c8b2-104">Methods</span></span>  
  
|<span data-ttu-id="9c8b2-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="9c8b2-105">Method</span></span>|<span data-ttu-id="9c8b2-106">Opis</span><span class="sxs-lookup"><span data-stu-id="9c8b2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9c8b2-107">GetObject — Metoda</span><span class="sxs-lookup"><span data-stu-id="9c8b2-107">GetObject Method</span></span>](icordebugboxvalue-getobject-method.md)|<span data-ttu-id="9c8b2-108">Pobiera wskaźnik interfejsu do zapakowanego wystąpienia "ICorDebugObjectValue".</span><span class="sxs-lookup"><span data-stu-id="9c8b2-108">Gets an interface pointer to the boxed "ICorDebugObjectValue" instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9c8b2-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="9c8b2-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9c8b2-110">Ten interfejs nie obsługuje wywoływania zdalnego na wielu maszynach ani wielu procesów.</span><span class="sxs-lookup"><span data-stu-id="9c8b2-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c8b2-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="9c8b2-111">Requirements</span></span>  

 <span data-ttu-id="9c8b2-112">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9c8b2-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c8b2-113">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="9c8b2-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9c8b2-114">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="9c8b2-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9c8b2-115">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c8b2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c8b2-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="9c8b2-116">See also</span></span>

- [<span data-ttu-id="9c8b2-117">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="9c8b2-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
