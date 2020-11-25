---
title: ICorProfilerCallback::RuntimeResumeStarted — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeResumeStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeResumeStarted
helpviewer_keywords:
- ICorProfilerCallback::RuntimeResumeStarted method [.NET Framework profiling]
- RuntimeResumeStarted method [.NET Framework profiling]
ms.assetid: 5854bfb2-c568-4f19-904a-7c9d41e7b995
topic_type:
- apiref
ms.openlocfilehash: 9a283d305c1a19112574cbf3486b1c67e64ed24c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717268"
---
# <a name="icorprofilercallbackruntimeresumestarted-method"></a><span data-ttu-id="84e70-102">ICorProfilerCallback::RuntimeResumeStarted — Metoda</span><span class="sxs-lookup"><span data-stu-id="84e70-102">ICorProfilerCallback::RuntimeResumeStarted Method</span></span>

<span data-ttu-id="84e70-103">Powiadamia program profilujący, że środowisko uruchomieniowe wznawia wszystkie wątki czasu wykonywania.</span><span class="sxs-lookup"><span data-stu-id="84e70-103">Notifies the profiler that the runtime is resuming all run-time threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84e70-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="84e70-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeResumeStarted();  
```  
  
## <a name="requirements"></a><span data-ttu-id="84e70-105">Wymagania</span><span class="sxs-lookup"><span data-stu-id="84e70-105">Requirements</span></span>  

 <span data-ttu-id="84e70-106">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84e70-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84e70-107">**Nagłówek:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="84e70-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="84e70-108">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="84e70-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="84e70-109">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84e70-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84e70-110">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="84e70-110">See also</span></span>

- [<span data-ttu-id="84e70-111">ICorProfilerCallback — Interfejs</span><span class="sxs-lookup"><span data-stu-id="84e70-111">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="84e70-112">RuntimeResumeFinished, metoda</span><span class="sxs-lookup"><span data-stu-id="84e70-112">RuntimeResumeFinished Method</span></span>](icorprofilercallback-runtimeresumefinished-method.md)
