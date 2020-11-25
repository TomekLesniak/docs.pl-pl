---
title: ICorProfilerCallback::AssemblyUnloadStarted — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyUnloadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyUnloadStarted
helpviewer_keywords:
- ICorProfilerCallback::AssemblyUnloadStarted method [.NET Framework profiling]
- AssemblyUnloadStarted method [.NET Framework profiling]
ms.assetid: 6e47b7e5-0335-4dd3-8c42-d3c07d62b102
topic_type:
- apiref
ms.openlocfilehash: bb7dade1ccd46cb9e13d45468c2ca2a8b451b70b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700304"
---
# <a name="icorprofilercallbackassemblyunloadstarted-method"></a><span data-ttu-id="a99f2-102">ICorProfilerCallback::AssemblyUnloadStarted — Metoda</span><span class="sxs-lookup"><span data-stu-id="a99f2-102">ICorProfilerCallback::AssemblyUnloadStarted Method</span></span>

<span data-ttu-id="a99f2-103">Powiadamia program profilujący, że zestaw jest zwolniony.</span><span class="sxs-lookup"><span data-stu-id="a99f2-103">Notifies the profiler that an assembly is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a99f2-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="a99f2-104">Syntax</span></span>  
  
```cpp  
HRESULT AssemblyUnloadStarted(  
    [in] AssemblyID assemblyId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a99f2-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="a99f2-105">Parameters</span></span>

- `assemblyId`

  <span data-ttu-id="a99f2-106">\[w programie] określa zestaw, który jest zwalniany.</span><span class="sxs-lookup"><span data-stu-id="a99f2-106">\[in] Identifies the assembly that is being unloaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="a99f2-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="a99f2-107">Remarks</span></span>  

 <span data-ttu-id="a99f2-108">Wartość `assemblyId` nie jest prawidłowa dla żądania informacji po `AssemblyUnloadStarted` powrocie metody — jest to Ostatnia szansa dla profilera, aby uzyskać informacje o tym zestawie.</span><span class="sxs-lookup"><span data-stu-id="a99f2-108">The value of `assemblyId` is not valid for an information request after the `AssemblyUnloadStarted` method returns — this is the profiler's last chance to get information about this assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a99f2-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="a99f2-109">Requirements</span></span>  

 <span data-ttu-id="a99f2-110">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a99f2-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a99f2-111">**Nagłówek:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="a99f2-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a99f2-112">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="a99f2-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a99f2-113">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a99f2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a99f2-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="a99f2-114">See also</span></span>

- [<span data-ttu-id="a99f2-115">ICorProfilerCallback — Interfejs</span><span class="sxs-lookup"><span data-stu-id="a99f2-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="a99f2-116">AssemblyUnloadFinished, metoda</span><span class="sxs-lookup"><span data-stu-id="a99f2-116">AssemblyUnloadFinished Method</span></span>](icorprofilercallback-assemblyunloadfinished-method.md)
