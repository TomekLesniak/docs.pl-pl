---
title: ICorDebugAppDomain2, interfejs
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain2
helpviewer_keywords:
- ICorDebugAppDomain2 interface [.NET Framework debugging]
ms.assetid: 314d29f3-feb0-4a92-9530-b569c280cc31
topic_type:
- apiref
ms.openlocfilehash: f20ae6977504f958b7bfa8e2f073b7db6e8b822b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731478"
---
# <a name="icordebugappdomain2-interface"></a><span data-ttu-id="fe4e7-102">ICorDebugAppDomain2, interfejs</span><span class="sxs-lookup"><span data-stu-id="fe4e7-102">ICorDebugAppDomain2 Interface</span></span>

<span data-ttu-id="fe4e7-103">Dostarcza metody do pracy z tablicami, wskaźnikami, wskaźnikami funkcji i typami referencyjnymi.</span><span class="sxs-lookup"><span data-stu-id="fe4e7-103">Provides methods to work with arrays, pointers, function pointers, and reference types.</span></span> <span data-ttu-id="fe4e7-104">Ten interfejs jest rozszerzeniem interfejsu ICorDebugAppDomain.</span><span class="sxs-lookup"><span data-stu-id="fe4e7-104">This interface is an extension of the ICorDebugAppDomain interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fe4e7-105">Metody</span><span class="sxs-lookup"><span data-stu-id="fe4e7-105">Methods</span></span>  
  
|<span data-ttu-id="fe4e7-106">Metoda</span><span class="sxs-lookup"><span data-stu-id="fe4e7-106">Method</span></span>|<span data-ttu-id="fe4e7-107">Opis</span><span class="sxs-lookup"><span data-stu-id="fe4e7-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fe4e7-108">GetArrayOrPointerType, metoda</span><span class="sxs-lookup"><span data-stu-id="fe4e7-108">GetArrayOrPointerType Method</span></span>](icordebugappdomain2-getarrayorpointertype-method.md)|<span data-ttu-id="fe4e7-109">Pobiera tablicę określonego typu lub wskaźnik lub odwołanie do określonego typu.</span><span class="sxs-lookup"><span data-stu-id="fe4e7-109">Gets an array of the specified type, or a pointer or reference to the specified type.</span></span>|  
|[<span data-ttu-id="fe4e7-110">GetFunctionPointerType</span><span class="sxs-lookup"><span data-stu-id="fe4e7-110">GetFunctionPointerType</span></span>](icordebugappdomain2-getfunctionpointertype-method.md)|<span data-ttu-id="fe4e7-111">Pobiera wskaźnik do funkcji, która ma daną sygnaturę.</span><span class="sxs-lookup"><span data-stu-id="fe4e7-111">Gets a pointer to a function that has a given signature.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fe4e7-112">Uwagi</span><span class="sxs-lookup"><span data-stu-id="fe4e7-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fe4e7-113">Ten interfejs nie obsługuje wywoływania zdalnego na wielu maszynach ani wielu procesów.</span><span class="sxs-lookup"><span data-stu-id="fe4e7-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe4e7-114">Wymagania</span><span class="sxs-lookup"><span data-stu-id="fe4e7-114">Requirements</span></span>  

 <span data-ttu-id="fe4e7-115">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fe4e7-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe4e7-116">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="fe4e7-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fe4e7-117">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="fe4e7-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fe4e7-118">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe4e7-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe4e7-119">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="fe4e7-119">See also</span></span>

- [<span data-ttu-id="fe4e7-120">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="fe4e7-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
