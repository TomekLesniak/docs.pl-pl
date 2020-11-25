---
title: ICorDebugChainEnum::Next — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugChainEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChainEnum::Next
helpviewer_keywords:
- ICorDebugChainEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugChainEnum interface [.NET Framework debugging]
ms.assetid: 6b791351-bcc5-4ddd-9cab-eff2f7dd5142
topic_type:
- apiref
ms.openlocfilehash: 0f42020821ec71d1e59ae8097f22ee530e16a576
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706180"
---
# <a name="icordebugchainenumnext-method"></a><span data-ttu-id="164e0-102">ICorDebugChainEnum::Next — Metoda</span><span class="sxs-lookup"><span data-stu-id="164e0-102">ICorDebugChainEnum::Next Method</span></span>

<span data-ttu-id="164e0-103">Pobiera określoną liczbę wystąpień ICorDebugChain z wyliczenia, rozpoczynając od bieżącego położenia.</span><span class="sxs-lookup"><span data-stu-id="164e0-103">Gets the specified number of ICorDebugChain instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="164e0-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="164e0-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugChain *chains[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="164e0-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="164e0-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="164e0-106">podczas Liczba `ICorDebugChain` wystąpień do pobrania.</span><span class="sxs-lookup"><span data-stu-id="164e0-106">[in] The number of `ICorDebugChain` instances to be retrieved.</span></span>  
  
 `chains`  
 <span data-ttu-id="164e0-107">określoną Tablica wskaźników, z których każdy wskazuje `ICorDebugChain` obiekt, który reprezentuje łańcuch.</span><span class="sxs-lookup"><span data-stu-id="164e0-107">[out] An array of pointers, each of which points to an `ICorDebugChain` object that represents a chain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="164e0-108">określoną Wskaźnik do liczby `ICorDebugChain` faktycznie zwróconych wystąpień.</span><span class="sxs-lookup"><span data-stu-id="164e0-108">[out] A pointer to the number of `ICorDebugChain` instances actually returned.</span></span> <span data-ttu-id="164e0-109">Ta wartość może być równa null, jeśli `celt` jest taka.</span><span class="sxs-lookup"><span data-stu-id="164e0-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="164e0-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="164e0-110">Requirements</span></span>  

 <span data-ttu-id="164e0-111">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="164e0-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="164e0-112">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="164e0-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="164e0-113">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="164e0-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="164e0-114">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="164e0-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
