---
title: ICorProfilerInfo4::GetReJITIDs — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetReJITIDs
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetReJITIDs
helpviewer_keywords:
- GetReJITIDs method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::GetReJITIDs method [.NET Framework profiling]
ms.assetid: 634ac28c-a5b7-4fc3-af84-256c24ca8177
topic_type:
- apiref
ms.openlocfilehash: 2ac645cbaaa45554568874653be016e4691bbd2f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707480"
---
# <a name="icorprofilerinfo4getrejitids-method"></a><span data-ttu-id="b71ff-102">ICorProfilerInfo4::GetReJITIDs — Metoda</span><span class="sxs-lookup"><span data-stu-id="b71ff-102">ICorProfilerInfo4::GetReJITIDs Method</span></span>

<span data-ttu-id="b71ff-103">Zwraca tablicę identyfikatorów, które identyfikują wszystkie wersje JIT-ponownie skompilowane określonej funkcji, które są nadal przydzieleni.</span><span class="sxs-lookup"><span data-stu-id="b71ff-103">Returns an array of IDs that identify all JIT-recompiled versions of the specified function that are still allocated.</span></span> <span data-ttu-id="b71ff-104">Obejmuje to ponowne skompilowane przez JIT wersje funkcji, które zostały później przywrócone, ale nie zostały jeszcze zwolnione (na przykład wtedy, gdy domena aplikacji zawierająca przywróconą funkcję jest nadal w użyciu).</span><span class="sxs-lookup"><span data-stu-id="b71ff-104">This includes JIT-recompiled versions of functions that have been subsequently reverted but not yet freed (for example, when the application domain that contains the reverted function is still in use).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b71ff-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="b71ff-105">Syntax</span></span>  
  
```cpp
HRESULT GetReJITIDs (  
     [in]  FunctionID          functionId,  
     [in]  ULONG               cReJitIds,  
     [out] ULONG *             pcReJitIds,  
     [out, size_is(cReJitIds), length_is(*pcReJitIds)]   ReJITID        reJitIds[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b71ff-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="b71ff-106">Parameters</span></span>  

 `functionId`  
 <span data-ttu-id="b71ff-107">podczas `FunctionID` Wystąpienia funkcji, dla którego mają zostać wyliczone wersje.</span><span class="sxs-lookup"><span data-stu-id="b71ff-107">[in] The `FunctionID` of the function instance for which to enumerate versions.</span></span>  
  
 `cReJitIds`  
 <span data-ttu-id="b71ff-108">podczas Liczba identyfikatorów ponownych kompilacji JIT przypisywanych w `reJitIds` tablicy.</span><span class="sxs-lookup"><span data-stu-id="b71ff-108">[in] The number of JIT-recompiled IDs allocated in the `reJitIds` array.</span></span>  
  
 `pcReJitIds`  
 <span data-ttu-id="b71ff-109">określoną Rzeczywista liczba identyfikatorów ponownych kompilacji JIT.</span><span class="sxs-lookup"><span data-stu-id="b71ff-109">[out] The actual number of JIT-recompiled IDs.</span></span>  
  
 `reJitIds`  
 <span data-ttu-id="b71ff-110">określoną Tablica przypisana przez obiekt wywołujący, która będzie zawierać identyfikatory ponownie skompilowane JIT dla określonej funkcji.</span><span class="sxs-lookup"><span data-stu-id="b71ff-110">[out] A caller-allocated array that will contain the JIT-recompiled IDs for the specified function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b71ff-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="b71ff-111">Remarks</span></span>  

 <span data-ttu-id="b71ff-112">`GetReJITIDs` wylicza aktywne, ponownie skompilowane identyfikatory JIT dla danego wystąpienia funkcji.</span><span class="sxs-lookup"><span data-stu-id="b71ff-112">`GetReJITIDs` enumerates the active JIT-recompiled IDs for a given function instance.</span></span> <span data-ttu-id="b71ff-113">Jest on zgodny z tym samym wzorcem użycia, co inne `ICorProfilerInfo` funkcje, które akceptują bufory przydzieloną przez proces wywołujący.</span><span class="sxs-lookup"><span data-stu-id="b71ff-113">It follows the same usage pattern as other `ICorProfilerInfo` functions that accept caller-allocated buffers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b71ff-114">Wymagania</span><span class="sxs-lookup"><span data-stu-id="b71ff-114">Requirements</span></span>  

 <span data-ttu-id="b71ff-115">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b71ff-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b71ff-116">**Nagłówek:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="b71ff-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b71ff-117">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="b71ff-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b71ff-118">**.NET Framework wersje:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b71ff-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b71ff-119">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="b71ff-119">See also</span></span>

- [<span data-ttu-id="b71ff-120">ICorProfilerInfo4 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="b71ff-120">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)
- [<span data-ttu-id="b71ff-121">Interfejsy profilowania</span><span class="sxs-lookup"><span data-stu-id="b71ff-121">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="b71ff-122">Profilowanie</span><span class="sxs-lookup"><span data-stu-id="b71ff-122">Profiling</span></span>](index.md)
