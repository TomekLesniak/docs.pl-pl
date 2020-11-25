---
title: ICorProfilerCallback::ExceptionUnwindFinallyLeave — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionUnwindFinallyLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionUnwindFinallyLeave
helpviewer_keywords:
- ICorProfilerCallback::ExceptionUnwindFinallyLeave method [.NET Framework profiling]
- ExceptionUnwindFinallyLeave method [.NET Framework profiling]
ms.assetid: 2350351e-f253-4c0c-a191-f952bc5700e6
topic_type:
- apiref
ms.openlocfilehash: e02716350aa2bf32bdd7c4b2e01841405de6dc14
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720402"
---
# <a name="icorprofilercallbackexceptionunwindfinallyleave-method"></a><span data-ttu-id="cbb5d-102">ICorProfilerCallback::ExceptionUnwindFinallyLeave — Metoda</span><span class="sxs-lookup"><span data-stu-id="cbb5d-102">ICorProfilerCallback::ExceptionUnwindFinallyLeave Method</span></span>

<span data-ttu-id="cbb5d-103">Powiadamia profiler, że faza unwind dla obsługi wyjątków opuściła `finally` klauzulę.</span><span class="sxs-lookup"><span data-stu-id="cbb5d-103">Notifies the profiler that the unwind phase of exception handling has left a `finally` clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbb5d-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="cbb5d-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionUnwindFinallyLeave();  
```  
  
## <a name="remarks"></a><span data-ttu-id="cbb5d-105">Uwagi</span><span class="sxs-lookup"><span data-stu-id="cbb5d-105">Remarks</span></span>  

 <span data-ttu-id="cbb5d-106">Profiler nie powinien blokować tego wywołania, ponieważ stos może nie znajdować się w stanie, który zezwala na wyrzucanie elementów bezużytecznych, a tym samym nie można włączyć przerzucania elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="cbb5d-106">The profiler should not block during this call because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="cbb5d-107">Jeśli profiler blokuje się w tym miejscu i podjęto próbę wyrzucania elementów bezużytecznych, środowisko uruchomieniowe zostanie zablokowane do momentu wywołania zwrotnego.</span><span class="sxs-lookup"><span data-stu-id="cbb5d-107">If the profiler blocks here and a garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="cbb5d-108">Ponadto w trakcie tego wywołania Profiler nie może wywołać kodu zarządzanego lub w jakikolwiek sposób spowodować alokację pamięci zarządzanej.</span><span class="sxs-lookup"><span data-stu-id="cbb5d-108">Also, during this call, the profiler must not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cbb5d-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="cbb5d-109">Requirements</span></span>  

 <span data-ttu-id="cbb5d-110">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cbb5d-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cbb5d-111">**Nagłówek:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="cbb5d-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cbb5d-112">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="cbb5d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cbb5d-113">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cbb5d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbb5d-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="cbb5d-114">See also</span></span>

- [<span data-ttu-id="cbb5d-115">ICorProfilerCallback — Interfejs</span><span class="sxs-lookup"><span data-stu-id="cbb5d-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="cbb5d-116">ExceptionUnwindFinallyEnter, metoda</span><span class="sxs-lookup"><span data-stu-id="cbb5d-116">ExceptionUnwindFinallyEnter Method</span></span>](icorprofilercallback-exceptionunwindfinallyenter-method.md)
