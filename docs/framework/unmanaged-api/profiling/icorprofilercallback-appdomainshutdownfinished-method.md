---
title: ICorProfilerCallback::AppDomainShutdownFinished — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AppDomainShutdownFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AppDomainShutdownFinished
helpviewer_keywords:
- AppDomainShutdownFinished method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainShutdownFinished method [.NET Framework profiling]
ms.assetid: 52794819-0a59-4bb1-a265-0f158cd5cd65
topic_type:
- apiref
ms.openlocfilehash: ddb2d6eeb75a118a12f681b354f6feccd1231c64
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95685392"
---
# <a name="icorprofilercallbackappdomainshutdownfinished-method"></a><span data-ttu-id="6217e-102">ICorProfilerCallback::AppDomainShutdownFinished — Metoda</span><span class="sxs-lookup"><span data-stu-id="6217e-102">ICorProfilerCallback::AppDomainShutdownFinished Method</span></span>

<span data-ttu-id="6217e-103">Powiadamia profiler o tym, że domena aplikacji została zwolniona z procesu.</span><span class="sxs-lookup"><span data-stu-id="6217e-103">Notifies the profiler that an application domain has been unloaded from a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6217e-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="6217e-104">Syntax</span></span>  
  
```cpp  
HRESULT AppDomainShutdownFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6217e-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="6217e-105">Parameters</span></span>

- `appDomainId`

  <span data-ttu-id="6217e-106">\[w programie] identyfikuje domenę, w której są przechowywane zestawy aplikacji.</span><span class="sxs-lookup"><span data-stu-id="6217e-106">\[in] Identifies the domain in which the application's assemblies are stored.</span></span>

- `hrStatus`

  <span data-ttu-id="6217e-107">\[w] wynik HRESULT wskazujący, czy domena aplikacji została zwolniona pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="6217e-107">\[in] An HRESULT that indicates whether the application domain was unloaded successfully.</span></span>

## <a name="remarks"></a><span data-ttu-id="6217e-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="6217e-108">Remarks</span></span>  

 <span data-ttu-id="6217e-109">Wartość `appDomainId` nie jest prawidłowa dla żądania informacji po powrocie metody [ICorProfilerCallback:: AppDomainShutdownStarted —](icorprofilercallback-appdomainshutdownstarted-method.md) .</span><span class="sxs-lookup"><span data-stu-id="6217e-109">The value of `appDomainId` is not valid for an information request after the [ICorProfilerCallback::AppDomainShutdownStarted](icorprofilercallback-appdomainshutdownstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="6217e-110">Niektóre części zwalniania domeny aplikacji mogą być kontynuowane po `AppDomainCreationFinished` wywołaniu wywołania zwrotnego.</span><span class="sxs-lookup"><span data-stu-id="6217e-110">Some parts of unloading the application domain might continue after the `AppDomainCreationFinished` callback.</span></span> <span data-ttu-id="6217e-111">Błąd HRESULT w elemencie `hrStatus` wskazuje na błąd.</span><span class="sxs-lookup"><span data-stu-id="6217e-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="6217e-112">Jednak powodzenie HRESULT w programie `hrStatus` wskazuje tylko, że pierwsza część zwalniania domeny aplikacji zakończyła się powodzeniem.</span><span class="sxs-lookup"><span data-stu-id="6217e-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the application domain has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6217e-113">Wymagania</span><span class="sxs-lookup"><span data-stu-id="6217e-113">Requirements</span></span>  

 <span data-ttu-id="6217e-114">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6217e-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6217e-115">**Nagłówek:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="6217e-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6217e-116">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="6217e-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6217e-117">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6217e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6217e-118">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="6217e-118">See also</span></span>

- [<span data-ttu-id="6217e-119">ICorProfilerCallback — Interfejs</span><span class="sxs-lookup"><span data-stu-id="6217e-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
