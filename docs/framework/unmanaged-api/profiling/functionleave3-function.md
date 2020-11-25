---
title: FunctionLeave3 — Funkcja
ms.date: 03/30/2017
api_name:
- FunctionLeave3
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionLeave3
helpviewer_keywords:
- FunctionLeave3 function [.NET Framework profiling]
ms.assetid: 5d798088-7992-48a0-ae55-d2a7ee31913f
topic_type:
- apiref
ms.openlocfilehash: 8eaf36579bb82d66ff356aa68afc38c70d7eaca3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720389"
---
# <a name="functionleave3-function"></a><span data-ttu-id="8d09c-102">FunctionLeave3 — Funkcja</span><span class="sxs-lookup"><span data-stu-id="8d09c-102">FunctionLeave3 Function</span></span>

<span data-ttu-id="8d09c-103">Powiadamia profiler, że formant jest zwracany przez funkcję.</span><span class="sxs-lookup"><span data-stu-id="8d09c-103">Notifies the profiler that control is being returned from a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d09c-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="8d09c-104">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionLeave3(FunctionOrRemappedID functionOrRemappedID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8d09c-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="8d09c-105">Parameters</span></span>  

- `functionOrRemappedID`

  <span data-ttu-id="8d09c-106">\[in] identyfikator funkcji, z której jest zwracany formant.</span><span class="sxs-lookup"><span data-stu-id="8d09c-106">\[in] The identifier of the function from which control is returned.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="8d09c-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="8d09c-107">Remarks</span></span>  

 <span data-ttu-id="8d09c-108">`FunctionLeave3`Funkcja wywołania zwrotnego powiadamia profiler w miarę wywoływania funkcji, ale nie obsługuje inspekcji wartości zwracanej.</span><span class="sxs-lookup"><span data-stu-id="8d09c-108">The `FunctionLeave3` callback function notifies the profiler as functions are being called, but does not support return value inspection.</span></span> <span data-ttu-id="8d09c-109">Użyj [metody ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3 —](icorprofilerinfo3-setenterleavefunctionhooks3-method.md) , aby zarejestrować implementację tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="8d09c-109">Use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 method](icorprofilerinfo3-setenterleavefunctionhooks3-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="8d09c-110">`FunctionLeave3`Funkcja jest wywołaniem zwrotnym, należy ją zaimplementować.</span><span class="sxs-lookup"><span data-stu-id="8d09c-110">The `FunctionLeave3` function is a callback; you must implement it.</span></span> <span data-ttu-id="8d09c-111">Implementacja musi używać `__declspec(naked)` atrybutu klasy magazynu.</span><span class="sxs-lookup"><span data-stu-id="8d09c-111">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="8d09c-112">Aparat wykonywania nie zapisuje żadnych rejestrów przed wywołaniem tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="8d09c-112">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="8d09c-113">We wpisie należy zapisać wszystkie używane rejestry, w tym te w jednostce zmiennoprzecinkowej (FPU).</span><span class="sxs-lookup"><span data-stu-id="8d09c-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="8d09c-114">Po zakończeniu należy przywrócić stos, usuwanie wyłączyć wszystkie parametry, które zostały wypchnięte przez jego obiekt wywołujący.</span><span class="sxs-lookup"><span data-stu-id="8d09c-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="8d09c-115">Implementacja `FunctionLeave3` nie powinna być blokowana, ponieważ spowoduje opóźnienie wyrzucania elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="8d09c-115">The implementation of `FunctionLeave3` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="8d09c-116">Implementacja nie powinna podejmować próby wyrzucania elementów bezużytecznych, ponieważ stos może nie znajdować się w stanie przyjaznym do wyrzucania elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="8d09c-116">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="8d09c-117">W przypadku próby wyrzucania elementów bezużytecznych środowisko uruchomieniowe zostanie zablokowane do momentu `FunctionLeave3` powracania.</span><span class="sxs-lookup"><span data-stu-id="8d09c-117">If a garbage collection is attempted, the runtime will block until `FunctionLeave3` returns.</span></span>  
  
 <span data-ttu-id="8d09c-118">`FunctionLeave3`Funkcja nie może wywołać kodu zarządzanego lub spowodować alokacji pamięci zarządzanej w dowolny sposób.</span><span class="sxs-lookup"><span data-stu-id="8d09c-118">The `FunctionLeave3` function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d09c-119">Wymagania</span><span class="sxs-lookup"><span data-stu-id="8d09c-119">Requirements</span></span>  

 <span data-ttu-id="8d09c-120">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d09c-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d09c-121">**Nagłówek:** CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="8d09c-121">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="8d09c-122">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="8d09c-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8d09c-123">**.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d09c-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d09c-124">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="8d09c-124">See also</span></span>

- [<span data-ttu-id="8d09c-125">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="8d09c-125">FunctionEnter3</span></span>](functionenter3-function.md)
- [<span data-ttu-id="8d09c-126">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="8d09c-126">FunctionTailcall3</span></span>](functiontailcall3-function.md)
- [<span data-ttu-id="8d09c-127">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="8d09c-127">FunctionEnter3WithInfo</span></span>](functiontailcall3-function.md)
- [<span data-ttu-id="8d09c-128">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="8d09c-128">FunctionLeave3WithInfo</span></span>](functionleave3withinfo-function.md)
- [<span data-ttu-id="8d09c-129">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="8d09c-129">FunctionTailcall3WithInfo</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="8d09c-130">Setenterleavefunctionhooks3 —</span><span class="sxs-lookup"><span data-stu-id="8d09c-130">SetEnterLeaveFunctionHooks3</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="8d09c-131">Setenterleavefunctionhooks3withinfo —</span><span class="sxs-lookup"><span data-stu-id="8d09c-131">SetEnterLeaveFunctionHooks3WithInfo</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="8d09c-132">SetFunctionIDMapper —</span><span class="sxs-lookup"><span data-stu-id="8d09c-132">SetFunctionIDMapper</span></span>](icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="8d09c-133">Setfunctionidmapper2 —</span><span class="sxs-lookup"><span data-stu-id="8d09c-133">SetFunctionIDMapper2</span></span>](icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="8d09c-134">Profilowanie statycznych funkcji globalnych</span><span class="sxs-lookup"><span data-stu-id="8d09c-134">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
