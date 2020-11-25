---
title: ICorDebugProcessEnum::Next — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugProcessEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcessEnum::Next
helpviewer_keywords:
- Next method, ICorDebugProcessEnum interface [.NET Framework debugging]
- ICorDebugProcessEnum::Next method [.NET Framework debugging]
ms.assetid: 4ac7077c-8d88-49c4-b360-b3af0c541c63
topic_type:
- apiref
ms.openlocfilehash: 6aee88452819a4aabe2a29971ce86079ef7f0008
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732505"
---
# <a name="icordebugprocessenumnext-method"></a><span data-ttu-id="e860c-102">ICorDebugProcessEnum::Next — Metoda</span><span class="sxs-lookup"><span data-stu-id="e860c-102">ICorDebugProcessEnum::Next Method</span></span>

<span data-ttu-id="e860c-103">Pobiera określoną liczbę wystąpień ICorDebugProcess z wyliczenia, rozpoczynając od bieżącego położenia.</span><span class="sxs-lookup"><span data-stu-id="e860c-103">Gets the specified number of ICorDebugProcess instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e860c-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="e860c-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in]  ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugProcess *processes[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e860c-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="e860c-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="e860c-106">podczas Liczba `ICorDebugProcess` wystąpień do pobrania.</span><span class="sxs-lookup"><span data-stu-id="e860c-106">[in] The number of `ICorDebugProcess` instances to be retrieved.</span></span>  
  
 `processes`  
 <span data-ttu-id="e860c-107">określoną Tablica wskaźników, z których każdy wskazuje `ICorDebugProcess` obiekt, który reprezentuje proces.</span><span class="sxs-lookup"><span data-stu-id="e860c-107">[out] An array of pointers, each of which points to an `ICorDebugProcess` object that represents a process.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="e860c-108">określoną Wskaźnik do liczby `ICorDebugProcess` faktycznie zwróconych wystąpień.</span><span class="sxs-lookup"><span data-stu-id="e860c-108">[out] Pointer to the number of `ICorDebugProcess` instances actually returned.</span></span> <span data-ttu-id="e860c-109">Ta wartość może być równa null, jeśli `celt` jest taka.</span><span class="sxs-lookup"><span data-stu-id="e860c-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e860c-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="e860c-110">Requirements</span></span>  

 <span data-ttu-id="e860c-111">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e860c-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e860c-112">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="e860c-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e860c-113">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="e860c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e860c-114">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e860c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
