---
title: ICorDebugGenericValue, interfejs
ms.date: 03/30/2017
api_name:
- ICorDebugGenericValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGenericValue
helpviewer_keywords:
- ICorDebugGenericValue interface [.NET Framework debugging]
ms.assetid: bc14f408-b359-4c8c-ade2-888ccdf7261b
topic_type:
- apiref
ms.openlocfilehash: cfa0950ca2ef4e969258c147b762fa95e52a82e5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705823"
---
# <a name="icordebuggenericvalue-interface"></a><span data-ttu-id="aa4ae-102">ICorDebugGenericValue, interfejs</span><span class="sxs-lookup"><span data-stu-id="aa4ae-102">ICorDebugGenericValue Interface</span></span>

<span data-ttu-id="aa4ae-103">Podklasa elementu "ICorDebugValue", która odnosi się do wszystkich wartości.</span><span class="sxs-lookup"><span data-stu-id="aa4ae-103">A subclass of "ICorDebugValue" that applies to all values.</span></span> <span data-ttu-id="aa4ae-104">Ten interfejs zapewnia metody Get i Set dla wartości.</span><span class="sxs-lookup"><span data-stu-id="aa4ae-104">This interface provides Get and Set methods for the value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="aa4ae-105">Metody</span><span class="sxs-lookup"><span data-stu-id="aa4ae-105">Methods</span></span>  
  
|<span data-ttu-id="aa4ae-106">Metoda</span><span class="sxs-lookup"><span data-stu-id="aa4ae-106">Method</span></span>|<span data-ttu-id="aa4ae-107">Opis</span><span class="sxs-lookup"><span data-stu-id="aa4ae-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="aa4ae-108">GetValue — Metoda</span><span class="sxs-lookup"><span data-stu-id="aa4ae-108">GetValue Method</span></span>](icordebuggenericvalue-getvalue-method.md)|<span data-ttu-id="aa4ae-109">Kopiuje wartość do określonego buforu.</span><span class="sxs-lookup"><span data-stu-id="aa4ae-109">Copies the value into the specified buffer.</span></span>|  
|[<span data-ttu-id="aa4ae-110">SetValue — Metoda</span><span class="sxs-lookup"><span data-stu-id="aa4ae-110">SetValue Method</span></span>](icordebuggenericvalue-setvalue-method.md)|<span data-ttu-id="aa4ae-111">Kopiuje nową wartość z określonego buforu.</span><span class="sxs-lookup"><span data-stu-id="aa4ae-111">Copies a new value from the specified buffer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aa4ae-112">Uwagi</span><span class="sxs-lookup"><span data-stu-id="aa4ae-112">Remarks</span></span>  

 <span data-ttu-id="aa4ae-113">`ICorDebugGenericValue` jest interfejsem podrzędnym, ponieważ nie jest zdalnie.</span><span class="sxs-lookup"><span data-stu-id="aa4ae-113">`ICorDebugGenericValue` is a sub-interface because it is non-remotable.</span></span>  
  
 <span data-ttu-id="aa4ae-114">W przypadku typów referencyjnych wartością jest odwołanie, a nie zawartość odwołania.</span><span class="sxs-lookup"><span data-stu-id="aa4ae-114">For reference types, the value is the reference rather than the contents of the reference.</span></span>  
  
 <span data-ttu-id="aa4ae-115">Ten interfejs nie obsługuje wywoływania zdalnego na wielu maszynach ani wielu procesów.</span><span class="sxs-lookup"><span data-stu-id="aa4ae-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="aa4ae-116">Ten interfejs nie obsługuje wywoływania zdalnego na wielu maszynach ani wielu procesów.</span><span class="sxs-lookup"><span data-stu-id="aa4ae-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa4ae-117">Wymagania</span><span class="sxs-lookup"><span data-stu-id="aa4ae-117">Requirements</span></span>  

 <span data-ttu-id="aa4ae-118">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa4ae-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa4ae-119">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="aa4ae-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="aa4ae-120">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="aa4ae-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aa4ae-121">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa4ae-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa4ae-122">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="aa4ae-122">See also</span></span>

- [<span data-ttu-id="aa4ae-123">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="aa4ae-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
