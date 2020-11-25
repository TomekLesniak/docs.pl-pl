---
title: ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.SetEnterLeaveFunctionHooks3WithInfo Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo
helpviewer_keywords:
- SetEnterLeaveFunctionHooks3WithInfo method [.NET Framework profiling]
- ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo method [.NET Framework profiling]
ms.assetid: ca8ea534-e441-47b8-be85-466410988c0a
topic_type:
- apiref
ms.openlocfilehash: 2ae4b35feb2441fdd66fb68ba9bb3649269a983c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95697821"
---
# <a name="icorprofilerinfo3setenterleavefunctionhooks3withinfo-method"></a><span data-ttu-id="c0457-102">ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo — Metoda</span><span class="sxs-lookup"><span data-stu-id="c0457-102">ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo Method</span></span>

<span data-ttu-id="c0457-103">Określa funkcje zaimplementowane przez profiler, które będą wywoływane w podpunktach [FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md)i [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) funkcji zarządzanych.</span><span class="sxs-lookup"><span data-stu-id="c0457-103">Specifies the profiler-implemented functions that will be called on the [FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) hooks of managed functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0457-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="c0457-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEnterLeaveFunctionHooks3WithInfo(  
            [in] FunctionEnter3WithInfo    *pFuncEnter3,  
            [in] FunctionLeave3withInfo    *pFuncLeave3,  
            [in] FunctionTailcall3WithInfo *pFuncTailcall3);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c0457-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="c0457-105">Parameters</span></span>  

 `pFuncEnter3`  
 <span data-ttu-id="c0457-106">podczas Wskaźnik do implementacji, który ma być używany jako `FunctionEnter3WithInfo` wywołanie zwrotne.</span><span class="sxs-lookup"><span data-stu-id="c0457-106">[in] A pointer to the implementation to be used as the `FunctionEnter3WithInfo` callback.</span></span>  
  
 `pFuncLeave3`  
 <span data-ttu-id="c0457-107">podczas Wskaźnik do implementacji, który ma być używany jako `FunctionLeave3WithInfo` wywołanie zwrotne.</span><span class="sxs-lookup"><span data-stu-id="c0457-107">[in] A pointer to the implementation to be used as the `FunctionLeave3WithInfo` callback.</span></span>  
  
 `pFuncTailcall3`  
 <span data-ttu-id="c0457-108">podczas Wskaźnik do implementacji, który ma być używany jako `FunctionTailcall3WithInfo` wywołanie zwrotne.</span><span class="sxs-lookup"><span data-stu-id="c0457-108">[in] A pointer to the implementation to be used as the `FunctionTailcall3WithInfo` callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c0457-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="c0457-109">Remarks</span></span>  

 <span data-ttu-id="c0457-110">Haki [FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md)i [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) zapewniają inspekcję ramek stosu i argumentów.</span><span class="sxs-lookup"><span data-stu-id="c0457-110">The [FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) hooks provide stack frame and argument inspection.</span></span> <span data-ttu-id="c0457-111">Aby uzyskać dostęp do tych informacji, należy `COR_PRF_ENABLE_FUNCTION_ARGS` `COR_PRF_ENABLE_FUNCTION_RETVAL` ustawić flagi, i/lub `COR_PRF_ENABLE_FRAME_INFO` .</span><span class="sxs-lookup"><span data-stu-id="c0457-111">To access that information, the `COR_PRF_ENABLE_FUNCTION_ARGS`, `COR_PRF_ENABLE_FUNCTION_RETVAL`, and/or `COR_PRF_ENABLE_FRAME_INFO` flags have to be set.</span></span> <span data-ttu-id="c0457-112">Profiler może użyć metody [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) , aby ustawić flagi zdarzeń, a następnie użyć `SetEnterLeaveFunctionHooks3WithInfo` metody do zarejestrowania implementacji tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="c0457-112">The profiler can use the [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) method to set the event flags, and then use the `SetEnterLeaveFunctionHooks3WithInfo` method to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="c0457-113">Tylko jeden zestaw wywołań zwrotnych może być aktywny w danym momencie, a Najnowsza wersja ma pierwszeństwo.</span><span class="sxs-lookup"><span data-stu-id="c0457-113">Only one set of callbacks may be active at a time, and the newest version takes precedence.</span></span> <span data-ttu-id="c0457-114">W związku z tym, jeśli Profiler wywoła zarówno [SetEnterLeaveFunctionHooks2 —](icorprofilerinfo2-setenterleavefunctionhooks2-method.md) , jak i `SetEnterLeaveFunctionHooks3WithInfo` , `SetEnterLeaveFunctionHooks3WithInfo` jest używany.</span><span class="sxs-lookup"><span data-stu-id="c0457-114">Therefore, if a profiler calls both [SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md) and `SetEnterLeaveFunctionHooks3WithInfo`, `SetEnterLeaveFunctionHooks3WithInfo` is used.</span></span>  
  
 <span data-ttu-id="c0457-115">`SetEnterLeaveFunctionHooks3WithInfo`Metoda może być wywoływana tylko z [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) wywołania zwrotnego.</span><span class="sxs-lookup"><span data-stu-id="c0457-115">The `SetEnterLeaveFunctionHooks3WithInfo` method may be called only from the profiler's [ICorProfilerCallback::Initialize](icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0457-116">Wymagania</span><span class="sxs-lookup"><span data-stu-id="c0457-116">Requirements</span></span>  

 <span data-ttu-id="c0457-117">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c0457-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0457-118">**Nagłówek:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="c0457-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c0457-119">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="c0457-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c0457-120">**.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0457-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0457-121">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="c0457-121">See also</span></span>

- [<span data-ttu-id="c0457-122">Setenterleavefunctionhooks3 —</span><span class="sxs-lookup"><span data-stu-id="c0457-122">SetEnterLeaveFunctionHooks3</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="c0457-123">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="c0457-123">FunctionEnter3</span></span>](functionenter3-function.md)
- [<span data-ttu-id="c0457-124">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="c0457-124">FunctionLeave3</span></span>](functionleave3-function.md)
- [<span data-ttu-id="c0457-125">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="c0457-125">FunctionTailcall3</span></span>](functiontailcall3-function.md)
- [<span data-ttu-id="c0457-126">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="c0457-126">FunctionEnter3WithInfo</span></span>](functionenter3withinfo-function.md)
- [<span data-ttu-id="c0457-127">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="c0457-127">FunctionLeave3WithInfo</span></span>](functionleave3withinfo-function.md)
- [<span data-ttu-id="c0457-128">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="c0457-128">FunctionTailcall3WithInfo</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="c0457-129">Profilowanie statycznych funkcji globalnych</span><span class="sxs-lookup"><span data-stu-id="c0457-129">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
- [<span data-ttu-id="c0457-130">ICorProfilerInfo3 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="c0457-130">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="c0457-131">Interfejsy profilowania</span><span class="sxs-lookup"><span data-stu-id="c0457-131">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="c0457-132">Profilowanie</span><span class="sxs-lookup"><span data-stu-id="c0457-132">Profiling</span></span>](index.md)
