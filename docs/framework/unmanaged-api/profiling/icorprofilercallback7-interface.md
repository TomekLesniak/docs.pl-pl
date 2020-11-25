---
title: ICorProfilerCallback7, interfejs
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback7
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: a0be019e-aaa1-4036-990f-565f114d4b5c
ms.openlocfilehash: e9c7186b3217c29805327e6c1d6b10f580c3a9e9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725459"
---
# <a name="icorprofilercallback7-interface"></a><span data-ttu-id="8262a-102">ICorProfilerCallback7, interfejs</span><span class="sxs-lookup"><span data-stu-id="8262a-102">ICorProfilerCallback7 Interface</span></span>

<span data-ttu-id="8262a-103">[Obsługiwane w .NET Framework 4.6.1 i nowszych wersjach]</span><span class="sxs-lookup"><span data-stu-id="8262a-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="8262a-104">Podklasa elementu [ICorProfilerCallback6](icorprofilercallback6-interface.md) , która zapewnia metodę wywołania zwrotnego używaną przez środowisko uruchomieniowe języka wspólnego do powiadamiania profilera o aktualizacji strumienia symboli skojarzonego z modułem w pamięci.</span><span class="sxs-lookup"><span data-stu-id="8262a-104">A subclass of [ICorProfilerCallback6](icorprofilercallback6-interface.md) that provides a callback method that the common language runtime uses to notify the profiler that the symbol stream associated with an in-memory module is updated.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8262a-105">Metody</span><span class="sxs-lookup"><span data-stu-id="8262a-105">Methods</span></span>  
  
|<span data-ttu-id="8262a-106">Metoda</span><span class="sxs-lookup"><span data-stu-id="8262a-106">Method</span></span>|<span data-ttu-id="8262a-107">Opis</span><span class="sxs-lookup"><span data-stu-id="8262a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8262a-108">ModuleInMemorySymbolsUpdated, metoda</span><span class="sxs-lookup"><span data-stu-id="8262a-108">ModuleInMemorySymbolsUpdated Method</span></span>](icorprofilercallback7-moduleinmemorysymbolsupdated-method.md)|<span data-ttu-id="8262a-109">Powiadamia program profilujący, że jest aktualizowany strumień symboli skojarzony z modułem w pamięci.</span><span class="sxs-lookup"><span data-stu-id="8262a-109">Notifies the profiler that the symbol stream associated with an in-memory module is updated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8262a-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="8262a-110">Requirements</span></span>  

 <span data-ttu-id="8262a-111">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8262a-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8262a-112">**Nagłówek:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="8262a-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8262a-113">**.NET Framework wersje:**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8262a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8262a-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="8262a-114">See also</span></span>

- [<span data-ttu-id="8262a-115">Interfejsy profilowania</span><span class="sxs-lookup"><span data-stu-id="8262a-115">Profiling Interfaces</span></span>](profiling-interfaces.md)
