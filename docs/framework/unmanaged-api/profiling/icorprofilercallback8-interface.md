---
title: ICorProfilerCallback8, interfejs
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 22a133d02bb69026190428905379323362943d40
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732388"
---
# <a name="icorprofilercallback8-interface"></a><span data-ttu-id="e5218-102">ICorProfilerCallback8, interfejs</span><span class="sxs-lookup"><span data-stu-id="e5218-102">ICorProfilerCallback8 Interface</span></span>

<span data-ttu-id="e5218-103">[Obsługiwane w .NET Framework 4,7 i nowszych wersjach]</span><span class="sxs-lookup"><span data-stu-id="e5218-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  

 <span data-ttu-id="e5218-104">Podklasa elementu [ICorProfilerCallback7](icorprofilercallback7-interface.md) , która zapewnia metody wywołania zwrotnego używane przez środowisko uruchomieniowe języka wspólnego do powiadamiania profilera o rozpoczęciu i zakończeniu kompilacji JIT metody dynamicznej.</span><span class="sxs-lookup"><span data-stu-id="e5218-104">A subclass of [ICorProfilerCallback7](icorprofilercallback7-interface.md) that provides callback methods used by the common language runtime to notify the profiler that JIT compilation of a dynamic method has started and finished.</span></span>
  
## <a name="methods"></a><span data-ttu-id="e5218-105">Metody</span><span class="sxs-lookup"><span data-stu-id="e5218-105">Methods</span></span>  
  
|<span data-ttu-id="e5218-106">Metoda</span><span class="sxs-lookup"><span data-stu-id="e5218-106">Method</span></span>|<span data-ttu-id="e5218-107">Opis</span><span class="sxs-lookup"><span data-stu-id="e5218-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e5218-108">DynamicMethodJITCompilationStarted, metoda</span><span class="sxs-lookup"><span data-stu-id="e5218-108">DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)|<span data-ttu-id="e5218-109">Powiadamia profiler, że została rozpoczęta kompilacja JIT metody dynamicznej.</span><span class="sxs-lookup"><span data-stu-id="e5218-109">Notifies the profiler that JIT compilation of a dynamic method has started.</span></span>|  
|[<span data-ttu-id="e5218-110">DynamicMethodJITCompilationFinished, metoda</span><span class="sxs-lookup"><span data-stu-id="e5218-110">DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)|<span data-ttu-id="e5218-111">Powiadamia profiler, że zakończyła się kompilacja JIT metody dynamicznej.</span><span class="sxs-lookup"><span data-stu-id="e5218-111">Notifies the profiler that JIT compilation of a dynamic method has finished.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e5218-112">Wymagania</span><span class="sxs-lookup"><span data-stu-id="e5218-112">Requirements</span></span>  

 <span data-ttu-id="e5218-113">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e5218-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5218-114">**Nagłówek:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="e5218-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
<span data-ttu-id="e5218-115">**.NET Framework wersje:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e5218-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="e5218-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="e5218-116">See also</span></span>

- [<span data-ttu-id="e5218-117">Interfejsy profilowania</span><span class="sxs-lookup"><span data-stu-id="e5218-117">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="e5218-118">ICorProfilerCallback9, interfejs</span><span class="sxs-lookup"><span data-stu-id="e5218-118">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)
