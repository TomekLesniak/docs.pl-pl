---
title: ICorProfilerCallback::FunctionUnloadStarted — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.FunctionUnloadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::FunctionUnloadStarted
helpviewer_keywords:
- FunctionUnloadStarted method [.NET Framework profiling]
- ICorProfilerCallback::FunctionUnloadStarted method [.NET Framework profiling]
ms.assetid: d6a5fa8b-09c6-47a5-b60e-6cf2e355df30
topic_type:
- apiref
ms.openlocfilehash: bab8d446347646081cee635035e954da58c3550c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733883"
---
# <a name="icorprofilercallbackfunctionunloadstarted-method"></a><span data-ttu-id="7aee2-102">ICorProfilerCallback::FunctionUnloadStarted — Metoda</span><span class="sxs-lookup"><span data-stu-id="7aee2-102">ICorProfilerCallback::FunctionUnloadStarted Method</span></span>

<span data-ttu-id="7aee2-103">Powiadamia profiler o rozpoczęciu pracy przez środowisko uruchomieniowe w celu zwolnienia funkcji.</span><span class="sxs-lookup"><span data-stu-id="7aee2-103">Notifies the profiler that the runtime has started to unload a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7aee2-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="7aee2-104">Syntax</span></span>  
  
```cpp  
HRESULT FunctionUnloadStarted(  
    [in] FunctionID functionId);
```  
  
## <a name="parameters"></a><span data-ttu-id="7aee2-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="7aee2-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="7aee2-106">\[in] identyfikator funkcji, która jest zwalniana.</span><span class="sxs-lookup"><span data-stu-id="7aee2-106">\[in] The ID of the function that is being unloaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="7aee2-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="7aee2-107">Remarks</span></span>  

 <span data-ttu-id="7aee2-108">Wartość `functionId` parametru nie jest już prawidłowa po powrocie tej metody do obiektu wywołującego.</span><span class="sxs-lookup"><span data-stu-id="7aee2-108">The value of the `functionId` parameter is no longer valid after this method returns to the caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7aee2-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="7aee2-109">Requirements</span></span>  

 <span data-ttu-id="7aee2-110">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7aee2-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7aee2-111">**Nagłówek:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="7aee2-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7aee2-112">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="7aee2-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7aee2-113">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7aee2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7aee2-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="7aee2-114">See also</span></span>

- [<span data-ttu-id="7aee2-115">ICorProfilerCallback — Interfejs</span><span class="sxs-lookup"><span data-stu-id="7aee2-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
