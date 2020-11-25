---
title: FunctionLeave — Funkcja
ms.date: 03/30/2017
api_name:
- FunctionLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionLeave
helpviewer_keywords:
- FunctionLeave function [.NET Framework profiling]
ms.assetid: 18e89f45-e068-426a-be16-9f53a4346860
topic_type:
- apiref
ms.openlocfilehash: 13636da9c3e8ac4aa9e8dc1fa02b2e33afef4717
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722261"
---
# <a name="functionleave-function"></a><span data-ttu-id="bba4a-102">FunctionLeave — Funkcja</span><span class="sxs-lookup"><span data-stu-id="bba4a-102">FunctionLeave Function</span></span>

<span data-ttu-id="bba4a-103">Powiadamia profiler, że funkcja ma zwrócić do obiektu wywołującego.</span><span class="sxs-lookup"><span data-stu-id="bba4a-103">Notifies the profiler that a function is about to return to the caller.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bba4a-104">`FunctionLeave`Funkcja jest przestarzała w .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="bba4a-104">The `FunctionLeave` function is deprecated in the .NET Framework 2.0.</span></span> <span data-ttu-id="bba4a-105">Będzie ona nadal działała, ale nastąpi spadek wydajności.</span><span class="sxs-lookup"><span data-stu-id="bba4a-105">It will continue to work, but will incur a performance penalty.</span></span> <span data-ttu-id="bba4a-106">Zamiast tego użyj funkcji [FunctionLeave2](functionleave2-function.md) .</span><span class="sxs-lookup"><span data-stu-id="bba4a-106">Use the [FunctionLeave2](functionleave2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bba4a-107">Składnia</span><span class="sxs-lookup"><span data-stu-id="bba4a-107">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionLeave (  
    [in] FunctionID funcID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bba4a-108">Parametry</span><span class="sxs-lookup"><span data-stu-id="bba4a-108">Parameters</span></span>

- `funcID`

  <span data-ttu-id="bba4a-109">\[in] Identyfikator zwracanej funkcji.</span><span class="sxs-lookup"><span data-stu-id="bba4a-109">\[in] The identifier of the function that is returning.</span></span>

## <a name="remarks"></a><span data-ttu-id="bba4a-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="bba4a-110">Remarks</span></span>  

 <span data-ttu-id="bba4a-111">`FunctionLeave`Funkcja jest wywołaniem zwrotnym, należy ją zaimplementować.</span><span class="sxs-lookup"><span data-stu-id="bba4a-111">The `FunctionLeave` function is a callback; you must implement it.</span></span> <span data-ttu-id="bba4a-112">Implementacja musi używać `__declspec` `naked` atrybutu klasy magazynu ().</span><span class="sxs-lookup"><span data-stu-id="bba4a-112">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="bba4a-113">Aparat wykonywania nie zapisuje żadnych rejestrów przed wywołaniem tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="bba4a-113">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="bba4a-114">We wpisie należy zapisać wszystkie używane rejestry, w tym te w jednostce zmiennoprzecinkowej (FPU).</span><span class="sxs-lookup"><span data-stu-id="bba4a-114">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="bba4a-115">Po zakończeniu należy przywrócić stos, usuwanie wyłączyć wszystkie parametry, które zostały wypchnięte przez jego obiekt wywołujący.</span><span class="sxs-lookup"><span data-stu-id="bba4a-115">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="bba4a-116">Implementacja `FunctionLeave` nie powinna być blokowana, ponieważ spowoduje opóźnienie wyrzucania elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="bba4a-116">The implementation of `FunctionLeave` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="bba4a-117">Implementacja nie powinna podejmować próby wyrzucania elementów bezużytecznych, ponieważ stos może nie znajdować się w stanie przyjaznym do wyrzucania elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="bba4a-117">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="bba4a-118">W przypadku próby wyrzucania elementów bezużytecznych środowisko uruchomieniowe zostanie zablokowane do momentu `FunctionLeave` powracania.</span><span class="sxs-lookup"><span data-stu-id="bba4a-118">If a garbage collection is attempted, the runtime will block until `FunctionLeave` returns.</span></span>  
  
 <span data-ttu-id="bba4a-119">Ponadto `FunctionLeave` Funkcja nie może wywołać kodu zarządzanego lub w jakikolwiek sposób może spowodować alokację pamięci zarządzanej.</span><span class="sxs-lookup"><span data-stu-id="bba4a-119">Also, the `FunctionLeave` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bba4a-120">Wymagania</span><span class="sxs-lookup"><span data-stu-id="bba4a-120">Requirements</span></span>  

 <span data-ttu-id="bba4a-121">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bba4a-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bba4a-122">**Nagłówek:** CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="bba4a-122">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="bba4a-123">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="bba4a-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bba4a-124">**.NET Framework wersje:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="bba4a-124">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bba4a-125">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="bba4a-125">See also</span></span>

- [<span data-ttu-id="bba4a-126">FunctionEnter2 — Funkcja</span><span class="sxs-lookup"><span data-stu-id="bba4a-126">FunctionEnter2 Function</span></span>](functionenter2-function.md)
- [<span data-ttu-id="bba4a-127">FunctionLeave2 — Funkcja</span><span class="sxs-lookup"><span data-stu-id="bba4a-127">FunctionLeave2 Function</span></span>](functionleave2-function.md)
- [<span data-ttu-id="bba4a-128">FunctionTailcall2 — Funkcja</span><span class="sxs-lookup"><span data-stu-id="bba4a-128">FunctionTailcall2 Function</span></span>](functiontailcall2-function.md)
- [<span data-ttu-id="bba4a-129">SetEnterLeaveFunctionHooks2, metoda</span><span class="sxs-lookup"><span data-stu-id="bba4a-129">SetEnterLeaveFunctionHooks2 Method</span></span>](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="bba4a-130">Profilowanie statycznych funkcji globalnych</span><span class="sxs-lookup"><span data-stu-id="bba4a-130">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
