---
title: CorGCReferenceType — Wyliczenie
ms.date: 03/30/2017
api_name:
- CorGCReferenceType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorGCReferenceType
helpviewer_keywords:
- CorGCReferenceType
ms.assetid: d9f16439-5a36-4474-8ffd-4f0b2c2bb686
topic_type:
- apiref
ms.openlocfilehash: e2903637faa11a3c0a62080cc6fafcf1fc668a56
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704997"
---
# <a name="corgcreferencetype-enumeration"></a><span data-ttu-id="d09d7-102">CorGCReferenceType — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="d09d7-102">CorGCReferenceType Enumeration</span></span>

<span data-ttu-id="d09d7-103">Określa źródło obiektu, które ma zostać pobrane jako elementy bezużyteczne.</span><span class="sxs-lookup"><span data-stu-id="d09d7-103">Identifies the source of an object to be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d09d7-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="d09d7-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    CorHandleStrong = 1,  
    CorHandleStrongPinning = 2,  
    CorHandleWeakShort = 4,  
    CorHandleWeakRefCount = 8,  
    CorHandleStrongRefCount = 32,  
    CorHandleStrongDependent = 64,  
    CorHandleStrongAsyncPinned = 128,  
    CorHandleStrongSizedByref = 256,  
  
    CorReferenceStack = 0x80000001,  
    CorReferenceFinalizer = 0x80000002,  
  
    CorHandleStrongOnly = 0x1E3,  
    CorHandleWeakOnly = 0xC,  
    CorHandleAll = 0x7FFFFFFF  
} CorGCReferenceType  
```  
  
## <a name="members"></a><span data-ttu-id="d09d7-105">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="d09d7-105">Members</span></span>  
  
|<span data-ttu-id="d09d7-106">Nazwa elementu członkowskiego</span><span class="sxs-lookup"><span data-stu-id="d09d7-106">Member name</span></span>|<span data-ttu-id="d09d7-107">Opis</span><span class="sxs-lookup"><span data-stu-id="d09d7-107">Description</span></span>|  
|-----------------|-----------------|  
|`CorHandleStrong`|<span data-ttu-id="d09d7-108">Dojście do silnego odwołania z tabeli uchwytów obiektów.</span><span class="sxs-lookup"><span data-stu-id="d09d7-108">A handle to a strong reference from the object handle table.</span></span>|  
|`CorHandleStrongPinning`|<span data-ttu-id="d09d7-109">Dojście do przypiętego silnego odwołania z tabeli uchwytów obiektów.</span><span class="sxs-lookup"><span data-stu-id="d09d7-109">A handle to a pinned strong reference from the object handle table.</span></span>|  
|`CorHandleWeakShort`|<span data-ttu-id="d09d7-110">Dojście do słabego odwołania z tabeli uchwytów obiektów.</span><span class="sxs-lookup"><span data-stu-id="d09d7-110">A handle to a weak reference from the object handle table.</span></span>|  
|`CorHandleWeakRefCount`|<span data-ttu-id="d09d7-111">Dojście do słabego odwołującego się obiektu z tabeli uchwytów obiektów.</span><span class="sxs-lookup"><span data-stu-id="d09d7-111">A handle to a weak reference-counted object from the object handle table.</span></span>|  
|`CorHandleStrongRefCount`|<span data-ttu-id="d09d7-112">Dojście do obiektu zliczanego odwołań z tabeli uchwytów obiektu.</span><span class="sxs-lookup"><span data-stu-id="d09d7-112">A handle to a reference-counted object from the object handle table.</span></span>|  
|`CorHandleStrongDependent`|<span data-ttu-id="d09d7-113">Dojście do obiektu zależnego z tabeli uchwytów obiektów.</span><span class="sxs-lookup"><span data-stu-id="d09d7-113">A handle to a dependent object from the object handle table.</span></span>|  
|`CorHandleStrongAsyncPinned`|<span data-ttu-id="d09d7-114">Asynchroniczny obiekt przypięty z tabeli uchwytów obiektu.</span><span class="sxs-lookup"><span data-stu-id="d09d7-114">An asynchronous pinned object from the object handle table.</span></span>|  
|`CorHandleStrongSizedByref`|<span data-ttu-id="d09d7-115">Silne dojście, które utrzymuje przybliżony rozmiar całego rozłącznego zamykania wszystkich obiektów i katalogów głównych obiektów w czasie odzyskiwania pamięci.</span><span class="sxs-lookup"><span data-stu-id="d09d7-115">A strong handle that keeps an approximate size of the collective closure of all objects and object roots at garbage collection time.</span></span>|  
|`CorReferenceStack`|<span data-ttu-id="d09d7-116">Odwołanie z zarządzanego stosu.</span><span class="sxs-lookup"><span data-stu-id="d09d7-116">A reference from the managed stack.</span></span>|  
|`CorReferenceFinalizer`|<span data-ttu-id="d09d7-117">Odwołanie z kolejki finalizatora.</span><span class="sxs-lookup"><span data-stu-id="d09d7-117">A reference from the finalizer queue.</span></span>|  
|<span data-ttu-id="d09d7-118">CorHandleStrongOnly</span><span class="sxs-lookup"><span data-stu-id="d09d7-118">CorHandleStrongOnly</span></span>|<span data-ttu-id="d09d7-119">Zwróć tylko silne odwołania z tabeli uchwytów.</span><span class="sxs-lookup"><span data-stu-id="d09d7-119">Return only strong references from the handle table.</span></span> <span data-ttu-id="d09d7-120">Ta wartość jest używana tylko przez metodę [ICorDebugProcess5:: EnumerateHandles —](icordebugprocess5-enumeratehandles-method.md) .</span><span class="sxs-lookup"><span data-stu-id="d09d7-120">This value is used by the [ICorDebugProcess5::EnumerateHandles](icordebugprocess5-enumeratehandles-method.md) method only.</span></span>|  
|`CorHandleWeakOnly`|<span data-ttu-id="d09d7-121">Zwróć tylko słabe odwołania z tabeli dojścia.</span><span class="sxs-lookup"><span data-stu-id="d09d7-121">Return only weak references from the handle table.</span></span> <span data-ttu-id="d09d7-122">Ta wartość jest używana tylko przez metodę [ICorDebugProcess5:: EnumerateHandles —](icordebugprocess5-enumeratehandles-method.md) .</span><span class="sxs-lookup"><span data-stu-id="d09d7-122">This value is used by the [ICorDebugProcess5::EnumerateHandles](icordebugprocess5-enumeratehandles-method.md) method only.</span></span>|  
|`CorHandleAll`|<span data-ttu-id="d09d7-123">Zwróć wszystkie odwołania z tabeli uchwytów.</span><span class="sxs-lookup"><span data-stu-id="d09d7-123">Return all references from the handle table.</span></span> <span data-ttu-id="d09d7-124">Ta wartość jest używana tylko przez metodę [ICorDebugProcess5:: EnumerateHandles —](icordebugprocess5-enumeratehandles-method.md) .</span><span class="sxs-lookup"><span data-stu-id="d09d7-124">This value is used by the [ICorDebugProcess5::EnumerateHandles](icordebugprocess5-enumeratehandles-method.md) method only.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d09d7-125">Uwagi</span><span class="sxs-lookup"><span data-stu-id="d09d7-125">Remarks</span></span>  

 <span data-ttu-id="d09d7-126">`CorGCReferenceType`Wyliczenie jest używane w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="d09d7-126">The `CorGCReferenceType` enumeration is used as follows:</span></span>  
  
- <span data-ttu-id="d09d7-127">Jako wartość `type` pola struktury [COR_GC_REFERENCE](cor-gc-reference-structure.md) wskazuje Źródło odwołania lub dojścia.</span><span class="sxs-lookup"><span data-stu-id="d09d7-127">As the value of the `type` field of the [COR_GC_REFERENCE](cor-gc-reference-structure.md) structure, it indicates the source of a reference or handle.</span></span>  
  
- <span data-ttu-id="d09d7-128">Jako `types` argument metody [ICorDebugProcess5:: EnumerateHandles —](icordebugprocess5-enumeratehandles-method.md) określa typy dojść do uwzględnienia w wyliczeniu.</span><span class="sxs-lookup"><span data-stu-id="d09d7-128">As the `types` argument to the [ICorDebugProcess5::EnumerateHandles](icordebugprocess5-enumeratehandles-method.md) method, it specifies the types of handles to include in the enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d09d7-129">Wymagania</span><span class="sxs-lookup"><span data-stu-id="d09d7-129">Requirements</span></span>  

 <span data-ttu-id="d09d7-130">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d09d7-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d09d7-131">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="d09d7-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d09d7-132">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="d09d7-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d09d7-133">**.NET Framework wersje:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d09d7-133">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d09d7-134">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="d09d7-134">See also</span></span>

- [<span data-ttu-id="d09d7-135">Debugowanie — wyliczenia</span><span class="sxs-lookup"><span data-stu-id="d09d7-135">Debugging Enumerations</span></span>](debugging-enumerations.md)
