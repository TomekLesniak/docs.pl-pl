---
title: ICorProfilerInfo2::SetEnterLeaveFunctionHooks2 — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.SetEnterLeaveFunctionHooks2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::SetEnterLeaveFunctionHooks2
helpviewer_keywords:
- ICorProfilerInfo2::SetEnterLeaveFunctionHooks2 method [.NET Framework profiling]
- SetEnterLeaveFunctionHooks2 method [.NET Framework profiling]
ms.assetid: 3c26b3e7-f72b-48a5-bf8c-edc122523a4b
topic_type:
- apiref
ms.openlocfilehash: f71d0b5c77d4a514001bcbe6904ed912be388d18
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95681551"
---
# <a name="icorprofilerinfo2setenterleavefunctionhooks2-method"></a><span data-ttu-id="b8a97-102">ICorProfilerInfo2::SetEnterLeaveFunctionHooks2 — Metoda</span><span class="sxs-lookup"><span data-stu-id="b8a97-102">ICorProfilerInfo2::SetEnterLeaveFunctionHooks2 Method</span></span>

<span data-ttu-id="b8a97-103">Określa funkcje zaimplementowane dla profilera, które mają być wywoływane na zaktualizowanych podpunktach "Enter", "urlop" i "tailcall" funkcji zarządzanych.</span><span class="sxs-lookup"><span data-stu-id="b8a97-103">Specifies profiler-implemented functions to be called on the updated versions of the "enter", "leave", and "tailcall" hooks of managed functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8a97-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="b8a97-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEnterLeaveFunctionHooks2(  
    [in] FunctionEnter2    *pFuncEnter,  
    [in] FunctionLeave2    *pFuncLeave,  
    [in] FunctionTailcall2 *pFuncTailcall);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b8a97-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="b8a97-105">Parameters</span></span>  

 `pFuncEnter`  
 <span data-ttu-id="b8a97-106">podczas Wskaźnik do implementacji, który ma być używany jako wywołanie zwrotne [FunctionEnter2](functionenter2-function.md) .</span><span class="sxs-lookup"><span data-stu-id="b8a97-106">[in] A pointer to the implementation to be used as the [FunctionEnter2](functionenter2-function.md) callback.</span></span>  
  
 `pFuncLeave`  
 <span data-ttu-id="b8a97-107">podczas Wskaźnik do implementacji, który ma być używany jako wywołanie zwrotne [FunctionLeave2](functionleave2-function.md) .</span><span class="sxs-lookup"><span data-stu-id="b8a97-107">[in] A pointer to the implementation to be used as the [FunctionLeave2](functionleave2-function.md) callback.</span></span>  
  
 `pFuncTailcall`  
 <span data-ttu-id="b8a97-108">podczas Wskaźnik do implementacji, który ma być używany jako wywołanie zwrotne [FunctionTailcall2](functiontailcall2-function.md) .</span><span class="sxs-lookup"><span data-stu-id="b8a97-108">[in] A pointer to the implementation to be used as the [FunctionTailcall2](functiontailcall2-function.md) callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b8a97-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="b8a97-109">Remarks</span></span>  

 <span data-ttu-id="b8a97-110">`SetEnterLeaveFunctionHooks2`Metoda jest podobna do metody [ICorProfilerInfo:: SetEnterLeaveFunctionHooks —](icorprofilerinfo-setenterleavefunctionhooks-method.md) .</span><span class="sxs-lookup"><span data-stu-id="b8a97-110">The `SetEnterLeaveFunctionHooks2` method is similar to the [ICorProfilerInfo::SetEnterLeaveFunctionHooks](icorprofilerinfo-setenterleavefunctionhooks-method.md) method.</span></span> <span data-ttu-id="b8a97-111">Użyj tej funkcji, aby określić funkcje, które mają być używane jako nowsze wersje wywołania zwrotnego Enter/opuścić/tailcall, a drugie, aby określić funkcje, które mają być używane jako starsze wersje wywołania zwrotnego Enter/opuścić/tailcall.</span><span class="sxs-lookup"><span data-stu-id="b8a97-111">Use the former to specify functions to be used as the newer versions of the enter/leave/tailcall callbacks, and the latter to specify functions to be used as the older versions of the enter/leave/tailcall callbacks.</span></span>  
  
 <span data-ttu-id="b8a97-112">Tylko jeden zestaw wywołań zwrotnych może być aktywny w danym momencie.</span><span class="sxs-lookup"><span data-stu-id="b8a97-112">Only one set of callbacks may be active at a time.</span></span> <span data-ttu-id="b8a97-113">W takim przypadku, jeśli Profiler wywołuje `ICorProfilerInfo::SetEnterLeaveFunctionHooks` zarówno `SetEnterLeaveFunctionHooks2` , jak i, `SetEnterLeaveFunctionHooks2` jest używany.</span><span class="sxs-lookup"><span data-stu-id="b8a97-113">Thus, if a profiler calls both `ICorProfilerInfo::SetEnterLeaveFunctionHooks` and `SetEnterLeaveFunctionHooks2`, `SetEnterLeaveFunctionHooks2` is used.</span></span>  
  
 <span data-ttu-id="b8a97-114">`SetEnterLeaveFunctionHooks2`Metoda może być wywoływana tylko z [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) wywołania zwrotnego.</span><span class="sxs-lookup"><span data-stu-id="b8a97-114">The `SetEnterLeaveFunctionHooks2` method may be called only from the profiler's [ICorProfilerCallback::Initialize](icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8a97-115">Wymagania</span><span class="sxs-lookup"><span data-stu-id="b8a97-115">Requirements</span></span>  

 <span data-ttu-id="b8a97-116">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8a97-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8a97-117">**Nagłówek:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="b8a97-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b8a97-118">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="b8a97-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b8a97-119">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8a97-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8a97-120">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="b8a97-120">See also</span></span>

- [<span data-ttu-id="b8a97-121">ICorProfilerInfo — Interfejs</span><span class="sxs-lookup"><span data-stu-id="b8a97-121">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="b8a97-122">ICorProfilerInfo2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="b8a97-122">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
