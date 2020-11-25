---
title: ICorDebugBlockingObjectEnum::Next — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugBlockingObjectEnum.Next Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBlockingObjectEnum::Next
helpviewer_keywords:
- Next method, ICorDebugBlockingObjectEnum interface [.NET Framework debugging]
- ICorDebugBlockingObjectEnum::Next method [.NET Framework debugging]
ms.assetid: 0121753f-ebea-48d0-aeb2-ed7fda76dc60
topic_type:
- apiref
ms.openlocfilehash: 232068a5fee8f7bd3dfbddf4d9452e80d6fd6170
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719193"
---
# <a name="icordebugblockingobjectenumnext-method"></a><span data-ttu-id="dc2b5-102">ICorDebugBlockingObjectEnum::Next — Metoda</span><span class="sxs-lookup"><span data-stu-id="dc2b5-102">ICorDebugBlockingObjectEnum::Next Method</span></span>

<span data-ttu-id="dc2b5-103">Pobiera określoną liczbę obiektów [CorDebugBlockingObject](cordebugblockingobject-structure.md) z wyliczenia, rozpoczynając od bieżącego położenia.</span><span class="sxs-lookup"><span data-stu-id="dc2b5-103">Gets the specified number of [CorDebugBlockingObject](cordebugblockingobject-structure.md) objects from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc2b5-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="dc2b5-104">Syntax</span></span>  
  
```cpp  
HRESULT Next([in] ULONG  celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                           CorDebugBlockingObject values[],  
             [out] ULONG *pceltFetched;  
```  
  
## <a name="parameters"></a><span data-ttu-id="dc2b5-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="dc2b5-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="dc2b5-106">podczas Liczba obiektów do pobrania.</span><span class="sxs-lookup"><span data-stu-id="dc2b5-106">[in] The number of objects to retrieve.</span></span>  
  
 `values`  
 <span data-ttu-id="dc2b5-107">określoną Tablica wskaźników do obiektów [CorDebugBlockingObject](cordebugblockingobject-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="dc2b5-107">[out] An array of pointers to [CorDebugBlockingObject](cordebugblockingobject-structure.md) objects.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="dc2b5-108">określoną Wskaźnik do liczby obiektów, które zostały pobrane.</span><span class="sxs-lookup"><span data-stu-id="dc2b5-108">[out] A pointer to the number of objects that were retrieved.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dc2b5-109">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="dc2b5-109">Return Value</span></span>  

 <span data-ttu-id="dc2b5-110">Ta metoda zwraca następujące specyficzne wyniki HRESULT.</span><span class="sxs-lookup"><span data-stu-id="dc2b5-110">This method returns the following specific HRESULTs.</span></span>  
  
|<span data-ttu-id="dc2b5-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="dc2b5-111">HRESULT</span></span>|<span data-ttu-id="dc2b5-112">Opis</span><span class="sxs-lookup"><span data-stu-id="dc2b5-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dc2b5-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="dc2b5-113">S_OK</span></span>|<span data-ttu-id="dc2b5-114">Metoda została ukończona pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="dc2b5-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="dc2b5-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="dc2b5-115">S_FALSE</span></span>|<span data-ttu-id="dc2b5-116">`pceltFetched` nie równa się `celt` .</span><span class="sxs-lookup"><span data-stu-id="dc2b5-116">`pceltFetched` does not equal `celt`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dc2b5-117">Uwagi</span><span class="sxs-lookup"><span data-stu-id="dc2b5-117">Remarks</span></span>  

 <span data-ttu-id="dc2b5-118">Ta metoda działa jak typowy moduł wyliczający COM.</span><span class="sxs-lookup"><span data-stu-id="dc2b5-118">This method functions like a typical COM enumerator.</span></span>  
  
 <span data-ttu-id="dc2b5-119">Wartości tablicy wejściowej muszą mieć rozmiar co najmniej `celt` .</span><span class="sxs-lookup"><span data-stu-id="dc2b5-119">The input array values must be at least of size `celt`.</span></span> <span data-ttu-id="dc2b5-120">Tablica zostanie uzupełniona na następne `celt` wartości w wyliczeniu lub wszystkie pozostałe wartości, jeśli nie `celt` pozostaną.</span><span class="sxs-lookup"><span data-stu-id="dc2b5-120">The array will be filled with either the next `celt` values in the enumeration or with all remaining values if fewer than `celt` remain.</span></span> <span data-ttu-id="dc2b5-121">Gdy ta metoda zostanie zwrócona, `pceltFetched` zostanie wypełniona liczba pobieranych wartości.</span><span class="sxs-lookup"><span data-stu-id="dc2b5-121">When this method returns, `pceltFetched` will be filled with the number of values that were retrieved.</span></span> <span data-ttu-id="dc2b5-122">Jeśli `values` zawiera nieprawidłowe wskaźniki lub wskazuje bufor, który jest mniejszy niż `celt` lub jeśli `pceltFetched` jest nieprawidłowym wskaźnikiem, wynik jest niezdefiniowany.</span><span class="sxs-lookup"><span data-stu-id="dc2b5-122">If `values` contains invalid pointers or points to a buffer that is smaller than `celt`, or if `pceltFetched` is an invalid pointer, the result is undefined.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="dc2b5-123">Mimo że struktura [CorDebugBlockingObject](cordebugblockingobject-structure.md) nie musi zostać wydana, należy wydać interfejs "ICorDebugValue" wewnątrz niego.</span><span class="sxs-lookup"><span data-stu-id="dc2b5-123">Although the [CorDebugBlockingObject](cordebugblockingobject-structure.md) structure does not need to be released, the "ICorDebugValue" interface inside of it does need to be released.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc2b5-124">Wymagania</span><span class="sxs-lookup"><span data-stu-id="dc2b5-124">Requirements</span></span>  

 <span data-ttu-id="dc2b5-125">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dc2b5-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc2b5-126">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="dc2b5-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dc2b5-127">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="dc2b5-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dc2b5-128">**.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc2b5-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc2b5-129">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="dc2b5-129">See also</span></span>

- [<span data-ttu-id="dc2b5-130">ICorDebugDataTarget — Interfejs</span><span class="sxs-lookup"><span data-stu-id="dc2b5-130">ICorDebugDataTarget Interface</span></span>](icordebugdatatarget-interface.md)
- [<span data-ttu-id="dc2b5-131">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="dc2b5-131">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="dc2b5-132">Debugowanie</span><span class="sxs-lookup"><span data-stu-id="dc2b5-132">Debugging</span></span>](index.md)
