---
title: ICorDebugModuleEnum::Next — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugModuleEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModuleEnum::Next
helpviewer_keywords:
- ICorDebugModuleEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugModuleEnum interface [.NET Framework debugging]
ms.assetid: 9ff3fcd6-38fe-41f8-bfd3-f0ab6c7d77ca
topic_type:
- apiref
ms.openlocfilehash: a4bdac42c584d5d34b072354de65ed20c6a80609
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709495"
---
# <a name="icordebugmoduleenumnext-method"></a><span data-ttu-id="e216c-102">ICorDebugModuleEnum::Next — Metoda</span><span class="sxs-lookup"><span data-stu-id="e216c-102">ICorDebugModuleEnum::Next Method</span></span>

<span data-ttu-id="e216c-103">Pobiera liczbę wystąpień "ICorDebugModule" określonych przez `celt` Wyliczenie z wyliczenia, rozpoczynając od bieżącego położenia.</span><span class="sxs-lookup"><span data-stu-id="e216c-103">Gets the number of "ICorDebugModule" instances specified by `celt` from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e216c-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="e216c-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in]  ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugModule *modules[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e216c-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="e216c-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="e216c-106">podczas Liczba `ICorDebugModule` wystąpień do pobrania.</span><span class="sxs-lookup"><span data-stu-id="e216c-106">[in] The number of `ICorDebugModule` instances to be retrieved.</span></span>  
  
 `modules`  
 <span data-ttu-id="e216c-107">określoną Tablica wskaźników, z których każdy wskazuje `ICorDebugModule` obiekt.</span><span class="sxs-lookup"><span data-stu-id="e216c-107">[out] An array of pointers, each of which points to an `ICorDebugModule` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="e216c-108">określoną Wskaźnik do liczby `ICorDebugModule` faktycznie zwróconych wystąpień.</span><span class="sxs-lookup"><span data-stu-id="e216c-108">[out] Pointer to the number of `ICorDebugModule` instances actually returned.</span></span> <span data-ttu-id="e216c-109">Ta wartość może być równa null, jeśli `celt` jest taka.</span><span class="sxs-lookup"><span data-stu-id="e216c-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e216c-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="e216c-110">Requirements</span></span>  

 <span data-ttu-id="e216c-111">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e216c-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e216c-112">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="e216c-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e216c-113">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="e216c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e216c-114">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e216c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e216c-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="e216c-115">See also</span></span>
