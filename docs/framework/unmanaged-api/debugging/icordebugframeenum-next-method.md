---
title: ICorDebugFrameEnum::Next — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugFrameEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrameEnum::Next
helpviewer_keywords:
- ICorDebugFrameEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugFrameEnum interface [.NET Framework debugging]
ms.assetid: 0bc96acb-6179-4328-a447-cda562ce9e98
topic_type:
- apiref
ms.openlocfilehash: 76b96dfd9d22c7e770671dcc01cb421430df729f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728189"
---
# <a name="icordebugframeenumnext-method"></a><span data-ttu-id="0fb87-102">ICorDebugFrameEnum::Next — Metoda</span><span class="sxs-lookup"><span data-stu-id="0fb87-102">ICorDebugFrameEnum::Next Method</span></span>

<span data-ttu-id="0fb87-103">Pobiera określoną liczbę wystąpień ICorDebugFrame, rozpoczynając od bieżącego położenia.</span><span class="sxs-lookup"><span data-stu-id="0fb87-103">Gets the specified number of ICorDebugFrame instances, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fb87-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="0fb87-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugFrame *frames[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0fb87-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="0fb87-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="0fb87-106">podczas Liczba `ICorDebugFrame` wystąpień do pobrania.</span><span class="sxs-lookup"><span data-stu-id="0fb87-106">[in] The number of `ICorDebugFrame` instances to be retrieved.</span></span>  
  
 `frames`  
 <span data-ttu-id="0fb87-107">określoną Tablica wskaźników, z których każdy wskazuje `ICorDebugFrame` obiekt.</span><span class="sxs-lookup"><span data-stu-id="0fb87-107">[out] An array of pointers, each of which points to an `ICorDebugFrame` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="0fb87-108">określoną Wskaźnik do liczby `ICorDebugFrame` faktycznie zwróconych wystąpień.</span><span class="sxs-lookup"><span data-stu-id="0fb87-108">[out] A pointer to the number of `ICorDebugFrame` instances actually returned.</span></span> <span data-ttu-id="0fb87-109">Ta wartość może być równa null, jeśli `celt` jest taka.</span><span class="sxs-lookup"><span data-stu-id="0fb87-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0fb87-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="0fb87-110">Requirements</span></span>  

 <span data-ttu-id="0fb87-111">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0fb87-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0fb87-112">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="0fb87-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0fb87-113">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="0fb87-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0fb87-114">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0fb87-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
