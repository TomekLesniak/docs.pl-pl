---
title: ICorProfilerCallback::AssemblyLoadStarted — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyLoadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyLoadStarted
helpviewer_keywords:
- ICorProfilerCallback::AssemblyLoadStarted method [.NET Framework profiling]
- AssemblyLoadStarted method [.NET Framework profiling]
ms.assetid: 67e8209d-a0ca-4118-a6e6-c1ee0abc2221
topic_type:
- apiref
ms.openlocfilehash: c2fbc0ae8cdeb79b65cbad9a055a8051acf67e50
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700421"
---
# <a name="icorprofilercallbackassemblyloadstarted-method"></a><span data-ttu-id="ee0c6-102">ICorProfilerCallback::AssemblyLoadStarted — Metoda</span><span class="sxs-lookup"><span data-stu-id="ee0c6-102">ICorProfilerCallback::AssemblyLoadStarted Method</span></span>

<span data-ttu-id="ee0c6-103">Powiadamia program profilujący, że zestaw jest ładowany.</span><span class="sxs-lookup"><span data-stu-id="ee0c6-103">Notifies the profiler that an assembly is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee0c6-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="ee0c6-104">Syntax</span></span>  
  
```cpp  
HRESULT AssemblyLoadStarted(  
    [in] AssemblyID assemblyId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ee0c6-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="ee0c6-105">Parameters</span></span>

- `assemblyId`

  <span data-ttu-id="ee0c6-106">\[w] identyfikuje zestaw, który jest ładowany.</span><span class="sxs-lookup"><span data-stu-id="ee0c6-106">\[in] Identifies the assembly that is being loaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="ee0c6-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="ee0c6-107">Remarks</span></span>  

 <span data-ttu-id="ee0c6-108">Wartość `assemblyId` nie jest prawidłowa dla żądania informacji, dopóki nie zostanie wywołana metoda [ICorProfilerCallback:: AssemblyLoadFinished —](icorprofilercallback-assemblyloadfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="ee0c6-108">The value of `assemblyId` is not valid for an information request until the [ICorProfilerCallback::AssemblyLoadFinished](icorprofilercallback-assemblyloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee0c6-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="ee0c6-109">Requirements</span></span>  

 <span data-ttu-id="ee0c6-110">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ee0c6-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee0c6-111">**Nagłówek:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="ee0c6-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ee0c6-112">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="ee0c6-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ee0c6-113">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee0c6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee0c6-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="ee0c6-114">See also</span></span>

- [<span data-ttu-id="ee0c6-115">ICorProfilerCallback — Interfejs</span><span class="sxs-lookup"><span data-stu-id="ee0c6-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
