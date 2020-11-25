---
title: ICorProfilerCallback::AppDomainShutdownStarted — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AppDomainShutdownStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AppDomainShutdownStarted
helpviewer_keywords:
- AppDomainShutdownStarted method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainShutdownStarted method [.NET Framework profiling]
ms.assetid: d23a3408-b525-4aec-a186-2ac7ca65d7a4
topic_type:
- apiref
ms.openlocfilehash: cb0b763059c787b8f3e93e6c46b0e7fb2f8f8b2c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718465"
---
# <a name="icorprofilercallbackappdomainshutdownstarted-method"></a><span data-ttu-id="4c5ea-102">ICorProfilerCallback::AppDomainShutdownStarted — Metoda</span><span class="sxs-lookup"><span data-stu-id="4c5ea-102">ICorProfilerCallback::AppDomainShutdownStarted Method</span></span>

<span data-ttu-id="4c5ea-103">Powiadamia profiler o tym, że domena aplikacji jest zwalniana z procesu.</span><span class="sxs-lookup"><span data-stu-id="4c5ea-103">Notifies the profiler that an application domain is being unloaded from a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c5ea-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="4c5ea-104">Syntax</span></span>  
  
```cpp  
HRESULT AppDomainShutdownStarted(  
    [in] AppDomainID appDomainId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4c5ea-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="4c5ea-105">Parameters</span></span>

- `appDomainId`

  <span data-ttu-id="4c5ea-106">\[w programie] identyfikuje domenę, w której są przechowywane zestawy aplikacji.</span><span class="sxs-lookup"><span data-stu-id="4c5ea-106">\[in] Identifies the domain in which the application's assemblies are stored.</span></span>

## <a name="remarks"></a><span data-ttu-id="4c5ea-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="4c5ea-107">Remarks</span></span>  

 <span data-ttu-id="4c5ea-108">Wartość `appDomainId` nie jest prawidłowa dla żadnych żądań informacji po `AppDomainShutdownStarted` powrocie metody — jest to Ostatnia szansa dla profilera, aby uzyskać informacje o tej domenie aplikacji.</span><span class="sxs-lookup"><span data-stu-id="4c5ea-108">The value of `appDomainId` is not valid for any information request after the `AppDomainShutdownStarted` method returns — this is the profiler's last chance to get information about this application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c5ea-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="4c5ea-109">Requirements</span></span>  

 <span data-ttu-id="4c5ea-110">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4c5ea-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c5ea-111">**Nagłówek:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="4c5ea-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4c5ea-112">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="4c5ea-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4c5ea-113">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4c5ea-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c5ea-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="4c5ea-114">See also</span></span>

- [<span data-ttu-id="4c5ea-115">ICorProfilerCallback — Interfejs</span><span class="sxs-lookup"><span data-stu-id="4c5ea-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
