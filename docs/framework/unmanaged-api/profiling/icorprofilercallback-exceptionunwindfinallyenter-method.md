---
title: ICorProfilerCallback::ExceptionUnwindFinallyEnter — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionUnwindFinallyEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionUnwindFinallyEnter
helpviewer_keywords:
- ICorProfilerCallback::ExceptionUnwindFinallyEnter method [.NET Framework profiling]
- ExceptionUnwindFinallyEnter method [.NET Framework profiling]
ms.assetid: c7fab986-b69f-4ec8-b7b7-91dcfc239cd0
topic_type:
- apiref
ms.openlocfilehash: 46e1fccc40606e10d8ff4083c7fe51da711c039a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95686127"
---
# <a name="icorprofilercallbackexceptionunwindfinallyenter-method"></a><span data-ttu-id="d9ee6-102">ICorProfilerCallback::ExceptionUnwindFinallyEnter — Metoda</span><span class="sxs-lookup"><span data-stu-id="d9ee6-102">ICorProfilerCallback::ExceptionUnwindFinallyEnter Method</span></span>

<span data-ttu-id="d9ee6-103">Powiadamia profiler, że faza unwind dla obsługi wyjątków wprowadza `finally` klauzulę znajdującą się w określonej funkcji.</span><span class="sxs-lookup"><span data-stu-id="d9ee6-103">Notifies the profiler that the unwind phase of exception handling is entering a `finally` clause contained in the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9ee6-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="d9ee6-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionUnwindFinallyEnter(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d9ee6-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="d9ee6-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="d9ee6-106">\[in) identyfikator funkcji, która zawiera `finally` klauzulę.</span><span class="sxs-lookup"><span data-stu-id="d9ee6-106">\[in] The ID of the function that contains the `finally` clause.</span></span>

## <a name="remarks"></a><span data-ttu-id="d9ee6-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="d9ee6-107">Remarks</span></span>  

 <span data-ttu-id="d9ee6-108">Profiler nie powinien blokować swojej implementacji tej metody, ponieważ stos może nie znajdować się w stanie, który zezwala na wyrzucanie elementów bezużytecznych i dlatego nie można włączyć zastępujący elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="d9ee6-108">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="d9ee6-109">Jeśli profiler blokuje tutaj i zostanie podjęta próba wyrzucania elementów bezużytecznych, środowisko uruchomieniowe zostanie zablokowane do momentu wywołania zwrotnego.</span><span class="sxs-lookup"><span data-stu-id="d9ee6-109">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="d9ee6-110">Implementacja profilera nie powinna być wywoływana w kodzie zarządzanym lub w jakikolwiek sposób spowodować alokację pamięci zarządzanej.</span><span class="sxs-lookup"><span data-stu-id="d9ee6-110">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9ee6-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="d9ee6-111">Requirements</span></span>  

 <span data-ttu-id="d9ee6-112">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d9ee6-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9ee6-113">**Nagłówek:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="d9ee6-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d9ee6-114">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="d9ee6-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d9ee6-115">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9ee6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9ee6-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="d9ee6-116">See also</span></span>

- [<span data-ttu-id="d9ee6-117">ICorProfilerCallback — Interfejs</span><span class="sxs-lookup"><span data-stu-id="d9ee6-117">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="d9ee6-118">GetNotifiedExceptionClauseInfo, metoda</span><span class="sxs-lookup"><span data-stu-id="d9ee6-118">GetNotifiedExceptionClauseInfo Method</span></span>](icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md)
- [<span data-ttu-id="d9ee6-119">ExceptionUnwindFinallyLeave, metoda</span><span class="sxs-lookup"><span data-stu-id="d9ee6-119">ExceptionUnwindFinallyLeave Method</span></span>](icorprofilercallback-exceptionunwindfinallyleave-method.md)
