---
title: ICorProfilerCallback2::GarbageCollectionFinished — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.GarbageCollectionFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::GarbageCollectionFinished
helpviewer_keywords:
- ICorProfilerCallback2::GarbageCollectionFinished method [.NET Framework profiling]
- GarbageCollectionFinished method [.NET Framework profiling]
ms.assetid: 1a5758ea-2354-43c0-92a3-32c9909d64e1
topic_type:
- apiref
ms.openlocfilehash: 84a71853ba2ccc8b95e4a8936005f2790d09a2c4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717317"
---
# <a name="icorprofilercallback2garbagecollectionfinished-method"></a><span data-ttu-id="07e31-102">ICorProfilerCallback2::GarbageCollectionFinished — Metoda</span><span class="sxs-lookup"><span data-stu-id="07e31-102">ICorProfilerCallback2::GarbageCollectionFinished Method</span></span>

<span data-ttu-id="07e31-103">Powiadamia profiler, że wyrzucanie elementów bezużytecznych zostało ukończone i wydano wszystkie wywołania zwrotne elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="07e31-103">Notifies the profiler that garbage collection has completed and all garbage collection callbacks have been issued for it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07e31-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="07e31-104">Syntax</span></span>  
  
```cpp  
HRESULT GarbageCollectionFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="07e31-105">Uwagi</span><span class="sxs-lookup"><span data-stu-id="07e31-105">Remarks</span></span>  

 <span data-ttu-id="07e31-106">Program profilujący może bezpiecznie zbadać obiekty w ich końcowych lokalizacjach, gdy `GarbageCollectionFinished` wywoływana jest metoda.</span><span class="sxs-lookup"><span data-stu-id="07e31-106">It is safe for the profiler to inspect objects in their final locations when the `GarbageCollectionFinished` method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07e31-107">Wymagania</span><span class="sxs-lookup"><span data-stu-id="07e31-107">Requirements</span></span>  

 <span data-ttu-id="07e31-108">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="07e31-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07e31-109">**Nagłówek:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="07e31-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="07e31-110">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="07e31-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="07e31-111">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07e31-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07e31-112">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="07e31-112">See also</span></span>

- [<span data-ttu-id="07e31-113">ICorProfilerCallback — Interfejs</span><span class="sxs-lookup"><span data-stu-id="07e31-113">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="07e31-114">ICorProfilerCallback2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="07e31-114">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
