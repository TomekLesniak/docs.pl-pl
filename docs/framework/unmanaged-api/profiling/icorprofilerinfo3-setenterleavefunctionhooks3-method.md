---
title: ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.SetEnterLeaveFunctionHooks3 Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::SetEnterLeaveFunctionHooks3
helpviewer_keywords:
- SetEnterLeaveFunctionHooks3 method [.NET Framework profiling]
- ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 method [.NET Framework profiling]
ms.assetid: f0621465-b84f-40ab-a4e5-56a7abc776a7
topic_type:
- apiref
ms.openlocfilehash: a7272d55771620db129125ce543d12d19a0b4dfb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95697847"
---
# <a name="icorprofilerinfo3setenterleavefunctionhooks3-method"></a><span data-ttu-id="9a868-102">ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 — Metoda</span><span class="sxs-lookup"><span data-stu-id="9a868-102">ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 Method</span></span>

<span data-ttu-id="9a868-103">Określa funkcje zaimplementowane przez profiler, które będą wywoływane w funkcjach [FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md)i [FunctionTailcall3](functiontailcall3-function.md) .</span><span class="sxs-lookup"><span data-stu-id="9a868-103">Specifies the profiler-implemented functions that will be called on the [FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md), and [FunctionTailcall3](functiontailcall3-function.md) functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a868-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="9a868-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEnterLeaveFunctionHooks3(  
            [in] FunctionEnter3    *pFuncEnter3,  
            [in] FunctionLeave3    *pFuncLeave3,  
            [in] FunctionTailcall3 *pFuncTailcall3);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9a868-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="9a868-105">Parameters</span></span>  

 `pFuncEnter3`  
 <span data-ttu-id="9a868-106">podczas Wskaźnik do implementacji, który ma być używany jako `FunctionEnter3` wywołanie zwrotne.</span><span class="sxs-lookup"><span data-stu-id="9a868-106">[in] A pointer to the implementation to be used as the `FunctionEnter3` callback.</span></span>  
  
 `pFuncLeave3`  
 <span data-ttu-id="9a868-107">podczas Wskaźnik do implementacji, który ma być używany jako `FunctionLeave3` wywołanie zwrotne.</span><span class="sxs-lookup"><span data-stu-id="9a868-107">[in] A pointer to the implementation to be used as the `FunctionLeave3` callback.</span></span>  
  
 `pFuncTailcall3`  
 <span data-ttu-id="9a868-108">podczas Wskaźnik do implementacji, który ma być używany jako `FunctionTailcall3` wywołanie zwrotne.</span><span class="sxs-lookup"><span data-stu-id="9a868-108">[in] A pointer to the implementation to be used as the `FunctionTailcall3` callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9a868-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="9a868-109">Remarks</span></span>  

 <span data-ttu-id="9a868-110">Haki [FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md)i [FunctionTailcall3](functiontailcall3-function.md) nie zapewniają przeprowadzenia inspekcji ramki i argumentu stosu.</span><span class="sxs-lookup"><span data-stu-id="9a868-110">[FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md), and [FunctionTailcall3](functiontailcall3-function.md) hooks do not provide stack frame and argument inspection.</span></span> <span data-ttu-id="9a868-111">Aby uzyskać dostęp do tych informacji, należy `COR_PRF_ENABLE_FUNCTION_ARGS` `COR_PRF_ENABLE_FUNCTION_RETVAL` ustawić flagi, i/lub  `COR_PRF_ENABLE_FRAME_INFO` .</span><span class="sxs-lookup"><span data-stu-id="9a868-111">To access that information, the `COR_PRF_ENABLE_FUNCTION_ARGS`, `COR_PRF_ENABLE_FUNCTION_RETVAL`, and/or  `COR_PRF_ENABLE_FRAME_INFO` flags have to be set.</span></span> <span data-ttu-id="9a868-112">Profiler może użyć metody [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) , aby ustawić flagi zdarzeń, a następnie użyć metody [ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3WithInfo —](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) do zarejestrowania implementacji tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="9a868-112">The profiler can use the [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) method to set the event flags, and then use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) method to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="9a868-113">Tylko jeden zestaw wywołań zwrotnych może być aktywny w danym momencie, a Najnowsza wersja ma pierwszeństwo.</span><span class="sxs-lookup"><span data-stu-id="9a868-113">Only one set of callbacks may be active at a time, and the newest version takes precedence.</span></span> <span data-ttu-id="9a868-114">W związku z tym, jeśli Profiler wywołuje zarówno [metodę SetEnterLeaveFunctionHooks2 —](icorprofilerinfo2-setenterleavefunctionhooks2-method.md) , jak i `SetEnterLeaveFunctionHooks3` metodę, `SetEnterLeaveFunctionHooks3` jest używana.</span><span class="sxs-lookup"><span data-stu-id="9a868-114">Therefore, if a profiler calls both the [SetEnterLeaveFunctionHooks2 Method](icorprofilerinfo2-setenterleavefunctionhooks2-method.md) and the `SetEnterLeaveFunctionHooks3` method, `SetEnterLeaveFunctionHooks3` is used.</span></span>  
  
 <span data-ttu-id="9a868-115">`SetEnterLeaveFunctionHooks3`Metoda może być wywoływana tylko z [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) wywołania zwrotnego.</span><span class="sxs-lookup"><span data-stu-id="9a868-115">The `SetEnterLeaveFunctionHooks3` method may be called only from the profiler's [ICorProfilerCallback::Initialize](icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a868-116">Wymagania</span><span class="sxs-lookup"><span data-stu-id="9a868-116">Requirements</span></span>  

 <span data-ttu-id="9a868-117">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a868-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a868-118">**Nagłówek:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="9a868-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9a868-119">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="9a868-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9a868-120">**.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a868-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a868-121">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="9a868-121">See also</span></span>

- [<span data-ttu-id="9a868-122">Setenterleavefunctionhooks3withinfo —</span><span class="sxs-lookup"><span data-stu-id="9a868-122">SetEnterLeaveFunctionHooks3WithInfo</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="9a868-123">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="9a868-123">FunctionEnter3</span></span>](functionenter3-function.md)
- [<span data-ttu-id="9a868-124">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="9a868-124">FunctionLeave3</span></span>](functionleave3-function.md)
- [<span data-ttu-id="9a868-125">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="9a868-125">FunctionTailcall3</span></span>](functiontailcall3-function.md)
- [<span data-ttu-id="9a868-126">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="9a868-126">FunctionEnter3WithInfo</span></span>](functionenter3withinfo-function.md)
- [<span data-ttu-id="9a868-127">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="9a868-127">FunctionLeave3WithInfo</span></span>](functionleave3withinfo-function.md)
- [<span data-ttu-id="9a868-128">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="9a868-128">FunctionTailcall3WithInfo</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="9a868-129">Profilowanie statycznych funkcji globalnych</span><span class="sxs-lookup"><span data-stu-id="9a868-129">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
- [<span data-ttu-id="9a868-130">ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="9a868-130">ICorProfilerInfo3</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="9a868-131">Interfejsy profilowania</span><span class="sxs-lookup"><span data-stu-id="9a868-131">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="9a868-132">Profilowanie</span><span class="sxs-lookup"><span data-stu-id="9a868-132">Profiling</span></span>](index.md)
