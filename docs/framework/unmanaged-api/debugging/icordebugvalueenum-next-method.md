---
title: ICorDebugValueEnum::Next — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugValueEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValueEnum::Next
helpviewer_keywords:
- ICorDebugValueEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugValueEnum interface [.NET Framework debugging]
ms.assetid: f5ef94dd-dfee-49d3-a398-b110f8906dd8
topic_type:
- apiref
ms.openlocfilehash: e1c8d94a90092b1497267c78d5fadf5a6e6de707
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684333"
---
# <a name="icordebugvalueenumnext-method"></a><span data-ttu-id="2267f-102">ICorDebugValueEnum::Next — Metoda</span><span class="sxs-lookup"><span data-stu-id="2267f-102">ICorDebugValueEnum::Next Method</span></span>

<span data-ttu-id="2267f-103">Pobiera określoną liczbę wystąpień "ICorDebugValue" z wyliczenia, rozpoczynając od bieżącego położenia.</span><span class="sxs-lookup"><span data-stu-id="2267f-103">Gets the specified number of "ICorDebugValue" instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2267f-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="2267f-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in]  ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugValue *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2267f-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="2267f-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="2267f-106">podczas Liczba `ICorDebugValue` wystąpień do pobrania.</span><span class="sxs-lookup"><span data-stu-id="2267f-106">[in] The number of `ICorDebugValue` instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="2267f-107">określoną Tablica wskaźników, z których każdy wskazuje `ICorDebugValue` obiekt.</span><span class="sxs-lookup"><span data-stu-id="2267f-107">[out] An array of pointers, each of which points to an `ICorDebugValue` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="2267f-108">określoną Wskaźnik do liczby `ICorDebugValue` faktycznie zwróconych wystąpień.</span><span class="sxs-lookup"><span data-stu-id="2267f-108">[out] Pointer to the number of `ICorDebugValue` instances actually returned.</span></span> <span data-ttu-id="2267f-109">Ta wartość może być równa null, jeśli `celt` jest taka.</span><span class="sxs-lookup"><span data-stu-id="2267f-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2267f-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="2267f-110">Requirements</span></span>  

 <span data-ttu-id="2267f-111">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2267f-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2267f-112">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="2267f-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2267f-113">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="2267f-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2267f-114">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2267f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2267f-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="2267f-115">See also</span></span>
