---
title: ICorProfilerInfo::GetCurrentThreadID — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetCurrentThreadID
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetCurrentThreadID
helpviewer_keywords:
- GetCurrentThreadID method, ICorProfilerInfo interface [.NET Framework profiling]
- ICorProfilerInfo::GetCurrentThreadID method [.NET Framework profiling]
ms.assetid: 39bbdb30-6a7a-4202-8da3-67ae9a0ab3a8
topic_type:
- apiref
ms.openlocfilehash: 18298c4c726d7d850e67afbf82ca77b7511d8917
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722597"
---
# <a name="icorprofilerinfogetcurrentthreadid-method"></a><span data-ttu-id="e36bd-102">ICorProfilerInfo::GetCurrentThreadID — Metoda</span><span class="sxs-lookup"><span data-stu-id="e36bd-102">ICorProfilerInfo::GetCurrentThreadID Method</span></span>

<span data-ttu-id="e36bd-103">Pobiera identyfikator bieżącego wątku, jeśli jest to wątek zarządzany.</span><span class="sxs-lookup"><span data-stu-id="e36bd-103">Gets the ID of the current thread, if it is a managed thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e36bd-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="e36bd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentThreadID(  
    [out] ThreadID *pThreadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e36bd-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="e36bd-105">Parameters</span></span>  

 `pThreadId`  
 <span data-ttu-id="e36bd-106">określoną Wskaźnik do zwróconego identyfikatora wątku zarządzanego.</span><span class="sxs-lookup"><span data-stu-id="e36bd-106">[out] A pointer to the returned ID of the managed thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e36bd-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="e36bd-107">Remarks</span></span>  

 <span data-ttu-id="e36bd-108">Jeśli bieżący wątek jest wewnętrznym wątkiem środowiska uruchomieniowego lub innego niezarządzanego wątku, `GetCurrentThreadID` zwraca CORPROF_E_NOT_MANAGED_THREAD jako HRESULT, a zwrócona wartość `pThreadId` parametru będzie równa null.</span><span class="sxs-lookup"><span data-stu-id="e36bd-108">If the current thread is an internal runtime thread or other unmanaged thread, `GetCurrentThreadID` returns CORPROF_E_NOT_MANAGED_THREAD as the HRESULT, and the returned value of the `pThreadId` parameter will be null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e36bd-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="e36bd-109">Requirements</span></span>  

 <span data-ttu-id="e36bd-110">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e36bd-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e36bd-111">**Nagłówek:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="e36bd-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e36bd-112">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="e36bd-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e36bd-113">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e36bd-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e36bd-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="e36bd-114">See also</span></span>

- [<span data-ttu-id="e36bd-115">ICorProfilerInfo — Interfejs</span><span class="sxs-lookup"><span data-stu-id="e36bd-115">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
