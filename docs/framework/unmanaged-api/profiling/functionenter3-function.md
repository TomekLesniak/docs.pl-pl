---
title: FunctionEnter3 — Funkcja
ms.date: 03/30/2017
api_name:
- FunctionEnter3
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionEnter3
helpviewer_keywords:
- FunctionEnter3 function [.NET Framework profiling]
ms.assetid: ef782c53-dae7-4990-b4ad-fddb1e690d4e
topic_type:
- apiref
ms.openlocfilehash: 98a821eabb393d8b5042647e6ef6ffce7ab10783
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722885"
---
# <a name="functionenter3-function"></a><span data-ttu-id="2f314-102">FunctionEnter3 — Funkcja</span><span class="sxs-lookup"><span data-stu-id="2f314-102">FunctionEnter3 Function</span></span>

<span data-ttu-id="2f314-103">Powiadamia profiler, że sterowanie jest przesyłane do funkcji.</span><span class="sxs-lookup"><span data-stu-id="2f314-103">Notifies the profiler that control is being passed to a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f314-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="2f314-104">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionEnter3(FunctionOrRemappedID functionOrRemappedID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2f314-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="2f314-105">Parameters</span></span>

- `functionOrRemappedID`

  <span data-ttu-id="2f314-106">\[in) identyfikator funkcji, do której jest przenoszona kontrola.</span><span class="sxs-lookup"><span data-stu-id="2f314-106">\[in] The identifier of the function to which control is passed.</span></span>

## <a name="remarks"></a><span data-ttu-id="2f314-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="2f314-107">Remarks</span></span>  

 <span data-ttu-id="2f314-108">`FunctionEnter3`Funkcja wywołania zwrotnego powiadamia profiler w miarę wywoływania funkcji, ale nie obsługuje inspekcji argumentów.</span><span class="sxs-lookup"><span data-stu-id="2f314-108">The `FunctionEnter3` callback function notifies the profiler as functions are being called, but does not support argument inspection.</span></span> <span data-ttu-id="2f314-109">Użyj [metody ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3 —](icorprofilerinfo3-setenterleavefunctionhooks3-method.md) , aby zarejestrować implementację tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="2f314-109">Use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 method](icorprofilerinfo3-setenterleavefunctionhooks3-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="2f314-110">`FunctionEnter3`Funkcja jest wywołaniem zwrotnym, należy ją zaimplementować.</span><span class="sxs-lookup"><span data-stu-id="2f314-110">The `FunctionEnter3` function is a callback; you must implement it.</span></span> <span data-ttu-id="2f314-111">Implementacja musi używać `__declspec(naked)` atrybutu klasy magazynu.</span><span class="sxs-lookup"><span data-stu-id="2f314-111">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="2f314-112">Aparat wykonywania nie zapisuje żadnych rejestrów przed wywołaniem tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="2f314-112">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="2f314-113">We wpisie należy zapisać wszystkie używane rejestry, w tym te w jednostce zmiennoprzecinkowej (FPU).</span><span class="sxs-lookup"><span data-stu-id="2f314-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="2f314-114">Po zakończeniu należy przywrócić stos, usuwanie wyłączyć wszystkie parametry, które zostały wypchnięte przez jego obiekt wywołujący.</span><span class="sxs-lookup"><span data-stu-id="2f314-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f314-115">Wymagania</span><span class="sxs-lookup"><span data-stu-id="2f314-115">Requirements</span></span>  

 <span data-ttu-id="2f314-116">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2f314-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f314-117">**Nagłówek:** CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="2f314-117">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="2f314-118">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="2f314-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2f314-119">**.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f314-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f314-120">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="2f314-120">See also</span></span>

- [<span data-ttu-id="2f314-121">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="2f314-121">FunctionLeave3</span></span>](functionleave3-function.md)
- [<span data-ttu-id="2f314-122">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="2f314-122">FunctionTailcall3</span></span>](functiontailcall3-function.md)
- [<span data-ttu-id="2f314-123">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="2f314-123">FunctionEnter3WithInfo</span></span>](functionenter3withinfo-function.md)
- [<span data-ttu-id="2f314-124">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="2f314-124">FunctionLeave3WithInfo</span></span>](functionleave3withinfo-function.md)
- [<span data-ttu-id="2f314-125">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="2f314-125">FunctionTailcall3WithInfo</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="2f314-126">Setenterleavefunctionhooks3 —</span><span class="sxs-lookup"><span data-stu-id="2f314-126">SetEnterLeaveFunctionHooks3</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="2f314-127">Setenterleavefunctionhooks3withinfo —</span><span class="sxs-lookup"><span data-stu-id="2f314-127">SetEnterLeaveFunctionHooks3WithInfo</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="2f314-128">SetFunctionIDMapper —</span><span class="sxs-lookup"><span data-stu-id="2f314-128">SetFunctionIDMapper</span></span>](icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="2f314-129">Setfunctionidmapper2 —</span><span class="sxs-lookup"><span data-stu-id="2f314-129">SetFunctionIDMapper2</span></span>](icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="2f314-130">Profilowanie statycznych funkcji globalnych</span><span class="sxs-lookup"><span data-stu-id="2f314-130">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
