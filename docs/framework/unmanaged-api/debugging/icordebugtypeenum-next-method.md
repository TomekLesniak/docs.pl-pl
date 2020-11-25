---
title: ICorDebugTypeEnum::Next — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugTypeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugTypeEnum::Next
helpviewer_keywords:
- ICorDebugTypeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugTypeEnum interface [.NET Framework debugging]
ms.assetid: d0fdeba3-c195-4ece-8caf-79b1f40025d2
topic_type:
- apiref
ms.openlocfilehash: 78ea76033b0b83c84446e16fb330bd3ba34c6e21
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725706"
---
# <a name="icordebugtypeenumnext-method"></a><span data-ttu-id="28df1-102">ICorDebugTypeEnum::Next — Metoda</span><span class="sxs-lookup"><span data-stu-id="28df1-102">ICorDebugTypeEnum::Next Method</span></span>

<span data-ttu-id="28df1-103">Pobiera liczbę wystąpień "ICorDebugType" określonych przez `celt` Wyliczenie z wyliczenia, rozpoczynając od bieżącego położenia.</span><span class="sxs-lookup"><span data-stu-id="28df1-103">Gets the number of "ICorDebugType" instances specified by `celt` from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28df1-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="28df1-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in]  ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugType *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="28df1-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="28df1-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="28df1-106">podczas Liczba `ICorDebugType` wystąpień do pobrania.</span><span class="sxs-lookup"><span data-stu-id="28df1-106">[in] The number of `ICorDebugType` instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="28df1-107">określoną Tablica wskaźników, z których każdy wskazuje `ICorDebugType` obiekt.</span><span class="sxs-lookup"><span data-stu-id="28df1-107">[out] An array of pointers, each of which points to an `ICorDebugType` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="28df1-108">określoną Wskaźnik do liczby `ICorDebugType` faktycznie zwróconych wystąpień.</span><span class="sxs-lookup"><span data-stu-id="28df1-108">[out] Pointer to the number of `ICorDebugType` instances actually returned.</span></span> <span data-ttu-id="28df1-109">Ta wartość może być równa null, jeśli `celt` jest taka.</span><span class="sxs-lookup"><span data-stu-id="28df1-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28df1-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="28df1-110">Requirements</span></span>  

 <span data-ttu-id="28df1-111">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="28df1-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28df1-112">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="28df1-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="28df1-113">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="28df1-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="28df1-114">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28df1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28df1-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="28df1-115">See also</span></span>
