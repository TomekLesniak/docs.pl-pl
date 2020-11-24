---
title: ICorDebugThreadEnum::Next — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugThreadEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThreadEnum::Next
helpviewer_keywords:
- ICorDebugThreadEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugThreadEnum interface [.NET Framework debugging]
ms.assetid: f967c93d-9a7f-4aaf-99a1-a1317899ff3f
topic_type:
- apiref
ms.openlocfilehash: 226b386c7a38c9a0b28b3bcc0420d14f6f4f4e7c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678431"
---
# <a name="icordebugthreadenumnext-method"></a><span data-ttu-id="b87c5-102">ICorDebugThreadEnum::Next — Metoda</span><span class="sxs-lookup"><span data-stu-id="b87c5-102">ICorDebugThreadEnum::Next Method</span></span>

<span data-ttu-id="b87c5-103">Pobiera liczbę określonych wystąpień ICorDebugThread z wyliczenia, rozpoczynając od bieżącego położenia.</span><span class="sxs-lookup"><span data-stu-id="b87c5-103">Gets the number of specified ICorDebugThread instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b87c5-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="b87c5-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugThread *threads[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b87c5-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="b87c5-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="b87c5-106">podczas Liczba `ICorDebugThread` wystąpień do pobrania.</span><span class="sxs-lookup"><span data-stu-id="b87c5-106">[in] The number of `ICorDebugThread` instances to be retrieved.</span></span>  
  
 `threads`  
 <span data-ttu-id="b87c5-107">określoną Tablica wskaźników, z których każdy wskazuje `ICorDebugThread` obiekt, który reprezentuje wątek.</span><span class="sxs-lookup"><span data-stu-id="b87c5-107">[out] An array of pointers, each of which points to an `ICorDebugThread` object that represents a thread.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="b87c5-108">określoną Wskaźnik do liczby `ICorDebugThread` faktycznie zwróconych wystąpień.</span><span class="sxs-lookup"><span data-stu-id="b87c5-108">[out] Pointer to the number of `ICorDebugThread` instances actually returned.</span></span> <span data-ttu-id="b87c5-109">Ta wartość może być równa null, jeśli `celt` jest taka.</span><span class="sxs-lookup"><span data-stu-id="b87c5-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b87c5-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="b87c5-110">Requirements</span></span>  

 <span data-ttu-id="b87c5-111">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b87c5-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b87c5-112">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="b87c5-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b87c5-113">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="b87c5-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b87c5-114">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b87c5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
