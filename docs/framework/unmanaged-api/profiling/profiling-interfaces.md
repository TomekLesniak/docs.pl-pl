---
title: Interfejsy profilowania
ms.date: 04/10/2018
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], profiling
- profiling interfaces [.NET Framework]
- interfaces [.NET Framework profiling]
ms.assetid: d9303db8-e881-4217-91b7-8c7573c8ef9e
ms.openlocfilehash: dd6999e9f9e16264bde3cf62ce3a888841347607
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727474"
---
# <a name="profiling-interfaces"></a><span data-ttu-id="8b3d2-102">Interfejsy profilowania</span><span class="sxs-lookup"><span data-stu-id="8b3d2-102">Profiling Interfaces</span></span>

<span data-ttu-id="8b3d2-103">W tej sekcji opisano niezarządzane interfejsy, które umożliwiają profilowanie programu wykonywanego przez środowisko uruchomieniowe języka wspólnego (CLR).</span><span class="sxs-lookup"><span data-stu-id="8b3d2-103">This section describes the unmanaged interfaces that enable you to profile a program that is being executed by the common language runtime (CLR).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8b3d2-104">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="8b3d2-104">In This Section</span></span>  

 [<span data-ttu-id="8b3d2-105">ICLRProfiling — Interfejs</span><span class="sxs-lookup"><span data-stu-id="8b3d2-105">ICLRProfiling Interface</span></span>](iclrprofiling-interface.md)  
 <span data-ttu-id="8b3d2-106">Udostępnia metodę [AttachProfiler —](iclrprofiling-attachprofiler-method.md) , która umożliwia profilerowi dołączenie do uruchomionego procesu.</span><span class="sxs-lookup"><span data-stu-id="8b3d2-106">Provides the [AttachProfiler](iclrprofiling-attachprofiler-method.md) method, which enables a profiler to attach to a running process.</span></span>  
  
 [<span data-ttu-id="8b3d2-107">Interfejs ICorProfilerAssemblyReferenceProvider</span><span class="sxs-lookup"><span data-stu-id="8b3d2-107">ICorProfilerAssemblyReferenceProvider Interface</span></span>](icorprofilerassemblyreferenceprovider-interface.md)  
 <span data-ttu-id="8b3d2-108">Umożliwia programowi Profiler informowanie CLR o odwołaniach do zestawów, które Profiler doda do wywołania zwrotnego [ICorProfilerCallback:: ModuleLoadFinished —](icorprofilercallback-moduleloadfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="8b3d2-108">Enables the profiler to inform the CLR of assembly references that the profiler will add in the [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>  
  
 [<span data-ttu-id="8b3d2-109">ICorProfilerCallback — Interfejs</span><span class="sxs-lookup"><span data-stu-id="8b3d2-109">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)  
 <span data-ttu-id="8b3d2-110">Dostarcza metody, które są używane przez środowisko CLR do powiadamiania profilera kodu o wystąpieniu zdarzeń subskrybowanych przez profiler.</span><span class="sxs-lookup"><span data-stu-id="8b3d2-110">Provides methods that are used by the CLR to notify a code profiler when the events to which the profiler has subscribed occur.</span></span>  
  
 [<span data-ttu-id="8b3d2-111">ICorProfilerCallback2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="8b3d2-111">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)  
 <span data-ttu-id="8b3d2-112">Rozszerza `ICorProfilerCallback` interfejs z wywołaniami zwrotnymi obsługiwanymi w .NET Framework 2,0 i nowszych.</span><span class="sxs-lookup"><span data-stu-id="8b3d2-112">Extends the `ICorProfilerCallback` interface with callbacks supported in the .NET Framework 2.0 and later versions.</span></span>  
  
 [<span data-ttu-id="8b3d2-113">ICorProfilerCallback3 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="8b3d2-113">ICorProfilerCallback3 Interface</span></span>](icorprofilercallback3-interface.md)  
 <span data-ttu-id="8b3d2-114">Zapewnia metody wywołania zwrotnego używane przez środowisko CLR do przekazywania informacji o stanie dołączania i odłączania do profilera.</span><span class="sxs-lookup"><span data-stu-id="8b3d2-114">Provides callback methods that the CLR uses to communicate attach and detach state information to the profiler.</span></span>  
  
 [<span data-ttu-id="8b3d2-115">ICorProfilerCallback4 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="8b3d2-115">ICorProfilerCallback4 Interface</span></span>](icorprofilercallback4-interface.md)  
 <span data-ttu-id="8b3d2-116">Zapewnia metody wywołania zwrotnego używane przez środowisko CLR do przekazywania informacji do profilera.</span><span class="sxs-lookup"><span data-stu-id="8b3d2-116">Provides callback methods that the CLR uses to communicate information to the profiler.</span></span>  
  
 [<span data-ttu-id="8b3d2-117">ICorProfilerCallback5 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="8b3d2-117">ICorProfilerCallback5 Interface</span></span>](icorprofilercallback5-interface.md)  
 <span data-ttu-id="8b3d2-118">Zapewnia metodę, która identyfikuje przechodnie zamknięcie obiektów, do których odwołują się katalogi główne wyrzucania elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="8b3d2-118">Provides a method that identifies the transitive closure of objects referenced by garbage collection roots.</span></span>  
  
 [<span data-ttu-id="8b3d2-119">Interfejs ICorProfilerCallback6</span><span class="sxs-lookup"><span data-stu-id="8b3d2-119">ICorProfilerCallback6 Interface</span></span>](icorprofilercallback6-interface.md)  
 <span data-ttu-id="8b3d2-120">Zapewnia metodę wywołania zwrotnego używaną przez środowisko CLR do powiadomienia profilera o ładowaniu zestawu.</span><span class="sxs-lookup"><span data-stu-id="8b3d2-120">Provides a callback method that the CLR uses to notify a profiler that an assembly is loading.</span></span>  
  
 [<span data-ttu-id="8b3d2-121">ICorProfilerCallback7, interfejs</span><span class="sxs-lookup"><span data-stu-id="8b3d2-121">ICorProfilerCallback7 Interface</span></span>](icorprofilercallback7-interface.md)  
 <span data-ttu-id="8b3d2-122">Zapewnia metodę wywołania zwrotnego używaną przez środowisko uruchomieniowe języka wspólnego do powiadamiania profilera o aktualizowaniu strumienia symboli skojarzonego z modułem w pamięci.</span><span class="sxs-lookup"><span data-stu-id="8b3d2-122">Provides a callback method that the common language runtime uses to notify the profiler that the symbol stream associated with an in-memory module is updated.</span></span>  

[<span data-ttu-id="8b3d2-123">ICorProfilerCallback8, interfejs</span><span class="sxs-lookup"><span data-stu-id="8b3d2-123">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback8-interface.md)  
<span data-ttu-id="8b3d2-124">Zapewnia metody wywołania zwrotnego używane przez środowisko uruchomieniowe języka wspólnego do powiadamiania profilera o rozpoczęciu i zakończeniu kompilacji JIT metody dynamicznej.</span><span class="sxs-lookup"><span data-stu-id="8b3d2-124">Provides callback methods that the common language runtime uses to notify the profiler that JIT compilation of a dynamic method has started and finished.</span></span>

[<span data-ttu-id="8b3d2-125">ICorProfilerCallback9, interfejs</span><span class="sxs-lookup"><span data-stu-id="8b3d2-125">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)  
<span data-ttu-id="8b3d2-126">Zapewnia metodę wywołania zwrotnego używaną przez środowisko uruchomieniowe języka wspólnego do powiadomienia profilera, że metoda dynamiczna jest odzyskiwana, a następnie zwolniona.</span><span class="sxs-lookup"><span data-stu-id="8b3d2-126">Provides a callback method that the common language runtime uses to notify the profiler that a dynamic method is garbage collected and subsequently unloaded.</span></span>

 [<span data-ttu-id="8b3d2-127">ICorProfilerFunctionControl — Interfejs</span><span class="sxs-lookup"><span data-stu-id="8b3d2-127">ICorProfilerFunctionControl Interface</span></span>](icorprofilerfunctioncontrol-interface.md)  
 <span data-ttu-id="8b3d2-128">Dostarcza metody, które umożliwiają profilerowi kodu komunikowanie się z środowiskiem CLR w celu kontrolowania sposobu generowania kodu przez kompilator JIT podczas ponownego kompilowania określonej metody.</span><span class="sxs-lookup"><span data-stu-id="8b3d2-128">Provides methods that allow a code profiler to communicate with the CLR to control how the JIT compiler should generate code when recompiling a specific method.</span></span>  
  
 [<span data-ttu-id="8b3d2-129">ICorProfilerFunctionEnum — Interfejs</span><span class="sxs-lookup"><span data-stu-id="8b3d2-129">ICorProfilerFunctionEnum Interface</span></span>](icorprofilerfunctionenum-interface.md)  
 <span data-ttu-id="8b3d2-130">Zapewnia metody sekwencyjnej iteracji przez kolekcję funkcji w środowisku CLR.</span><span class="sxs-lookup"><span data-stu-id="8b3d2-130">Provides methods to sequentially iterate through a collection of functions in the CLR.</span></span>  
  
 [<span data-ttu-id="8b3d2-131">ICorProfilerInfo — Interfejs</span><span class="sxs-lookup"><span data-stu-id="8b3d2-131">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)  
 <span data-ttu-id="8b3d2-132">Zapewnia metody do użycia przez program Code profilowas do komunikowania się z środowiskiem CLR w celu kontrolowania informacji o monitorowaniu zdarzeń i żądaniu.</span><span class="sxs-lookup"><span data-stu-id="8b3d2-132">Provides methods for use by code profilers to communicate with the CLR to control event monitoring and request information.</span></span>  
  
 [<span data-ttu-id="8b3d2-133">ICorProfilerInfo2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="8b3d2-133">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)  
 <span data-ttu-id="8b3d2-134">Rozszerza `ICorProfilerInfo` interfejs przy użyciu metod obsługiwanych w .NET Framework 2,0 i nowszych.</span><span class="sxs-lookup"><span data-stu-id="8b3d2-134">Extends the `ICorProfilerInfo` interface with methods supported in the .NET Framework 2.0 and later versions.</span></span>  
  
 [<span data-ttu-id="8b3d2-135">ICorProfilerInfo3 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="8b3d2-135">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)  
 <span data-ttu-id="8b3d2-136">Rozszerza `ICorProfilerInfo2` interfejs z metodami obsługiwanymi w .NET Framework 4 i nowszych.</span><span class="sxs-lookup"><span data-stu-id="8b3d2-136">Extends the `ICorProfilerInfo2` interface with methods supported in the .NET Framework 4 and later versions.</span></span>  
  
 [<span data-ttu-id="8b3d2-137">ICorProfilerInfo4 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="8b3d2-137">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)  
 <span data-ttu-id="8b3d2-138">Dostarcza metody, których program codeer używa do komunikacji z środowiskiem CLR w celu kontrolowania monitorowania zdarzeń oraz żądania informacji.</span><span class="sxs-lookup"><span data-stu-id="8b3d2-138">Provides methods that code profilers use to communicate with the CLR to control event monitoring and to request information.</span></span>  
  
 [<span data-ttu-id="8b3d2-139">Interfejs ICorProfilerInfo5</span><span class="sxs-lookup"><span data-stu-id="8b3d2-139">ICorProfilerInfo5 Interface</span></span>](icorprofilerinfo5-interface.md)  
 <span data-ttu-id="8b3d2-140">Zapewnia metody do użycia przez program Code profilowas do komunikowania się z środowiskiem CLR w celu kontrolowania monitorowania zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="8b3d2-140">Provides methods for use by code profilers to communicate with the CLR to control event monitoring.</span></span>  
  
 [<span data-ttu-id="8b3d2-141">ICorProfilerInfo6, interfejs</span><span class="sxs-lookup"><span data-stu-id="8b3d2-141">ICorProfilerInfo6 Interface</span></span>](icorprofilerinfo6-interface.md)  
 <span data-ttu-id="8b3d2-142">Dostarcza moduł wyliczający do wszystkich metod, które należą do danego modułu NGen i są zawarte w treści danej metody.</span><span class="sxs-lookup"><span data-stu-id="8b3d2-142">Provides an enumerator to all the methods that belong to a given NGen module and that are inlined in the body of a given method.</span></span>  
  
 [<span data-ttu-id="8b3d2-143">ICorProfilerInfo7, interfejs</span><span class="sxs-lookup"><span data-stu-id="8b3d2-143">ICorProfilerInfo7 Interface</span></span>](icorprofilerinfo7-interface.md)  
 <span data-ttu-id="8b3d2-144">Zapewnia metodę zastosowania nowo zdefiniowanych metadanych do modułu, który zapewnia dostęp do strumienia symboli w pamięci.</span><span class="sxs-lookup"><span data-stu-id="8b3d2-144">Provides a method to apply newly defined metadata to a module and that provides access to an in-memory symbol stream.</span></span>  
  
 [<span data-ttu-id="8b3d2-145">ICorProfilerModuleEnum — Interfejs</span><span class="sxs-lookup"><span data-stu-id="8b3d2-145">ICorProfilerModuleEnum Interface</span></span>](icorprofilermoduleenum-interface.md)  
 <span data-ttu-id="8b3d2-146">Dostarcza metody sekwencyjnie iteracji przez kolekcję modułów ładowanych przez aplikację lub profiler.</span><span class="sxs-lookup"><span data-stu-id="8b3d2-146">Provides methods to sequentially iterate through a collection of modules loaded by the application or the profiler.</span></span>  
  
 [<span data-ttu-id="8b3d2-147">ICorProfilerObjectEnum — Interfejs</span><span class="sxs-lookup"><span data-stu-id="8b3d2-147">ICorProfilerObjectEnum Interface</span></span>](icorprofilerobjectenum-interface.md)  
 <span data-ttu-id="8b3d2-148">Zapewnia metody sekwencyjnej iteracji przez kolekcję zamrożonych obiektów, które są generowane przez [Ngen.exe (Generator obrazu natywnego)](../../tools/ngen-exe-native-image-generator.md).</span><span class="sxs-lookup"><span data-stu-id="8b3d2-148">Provides methods to sequentially iterate through a collection of frozen objects that are generated by [Ngen.exe (Native Image Generator)](../../tools/ngen-exe-native-image-generator.md).</span></span>  
  
 [<span data-ttu-id="8b3d2-149">ICorProfilerThreadEnum — Interfejs</span><span class="sxs-lookup"><span data-stu-id="8b3d2-149">ICorProfilerThreadEnum Interface</span></span>](icorprofilerthreadenum-interface.md)  
 <span data-ttu-id="8b3d2-150">Zapewnia metody sekwencyjnej iteracji przez kolekcję wątków w środowisku CLR.</span><span class="sxs-lookup"><span data-stu-id="8b3d2-150">Provides methods to sequentially iterate through a collection of threads in the CLR.</span></span>  
  
 [<span data-ttu-id="8b3d2-151">IMethodMalloc — Interfejs</span><span class="sxs-lookup"><span data-stu-id="8b3d2-151">IMethodMalloc Interface</span></span>](imethodmalloc-interface.md)  
 <span data-ttu-id="8b3d2-152">Udostępnia metodę [Alloc](imethodmalloc-alloc-method.md) do przydzielania pamięci dla nowej treści funkcji języka pośredniego (MSIL) firmy Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8b3d2-152">Provides the [Alloc](imethodmalloc-alloc-method.md) method to allocate memory for a new Microsoft intermediate language (MSIL) function body.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="8b3d2-153">Sekcje pokrewne</span><span class="sxs-lookup"><span data-stu-id="8b3d2-153">Related Sections</span></span>  

 [<span data-ttu-id="8b3d2-154">Omówienie profilowania</span><span class="sxs-lookup"><span data-stu-id="8b3d2-154">Profiling Overview</span></span>](profiling-overview.md)  
  
 [<span data-ttu-id="8b3d2-155">Profilowanie statycznych funkcji globalnych</span><span class="sxs-lookup"><span data-stu-id="8b3d2-155">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)  
  
 [<span data-ttu-id="8b3d2-156">Profilowanie — Wyliczenia</span><span class="sxs-lookup"><span data-stu-id="8b3d2-156">Profiling Enumerations</span></span>](profiling-enumerations.md)  
  
 [<span data-ttu-id="8b3d2-157">Profiling — Struktury</span><span class="sxs-lookup"><span data-stu-id="8b3d2-157">Profiling Structures</span></span>](profiling-structures.md)
