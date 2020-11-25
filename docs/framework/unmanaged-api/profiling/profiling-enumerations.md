---
title: Profilowanie — Wyliczenia
ms.date: 03/30/2017
helpviewer_keywords:
- profiling enumerations [.NET Framework]
- enumerations [.NET Framework profiling]
- unmanaged enumerations [.NET Framework], profiling
ms.assetid: 8d5f9570-9853-4ce8-8101-df235d5b258e
ms.openlocfilehash: 8956a09cf76aa54452e8c020239e650e55d8a0d1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95701617"
---
# <a name="profiling-enumerations"></a><span data-ttu-id="5bb3c-102">Profilowanie — Wyliczenia</span><span class="sxs-lookup"><span data-stu-id="5bb3c-102">Profiling Enumerations</span></span>

<span data-ttu-id="5bb3c-103">W tej sekcji opisano niezarządzane wyliczenia, które są używane przez interfejs API profilowania.</span><span class="sxs-lookup"><span data-stu-id="5bb3c-103">This section describes the unmanaged enumerations that the profiling API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5bb3c-104">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="5bb3c-104">In This Section</span></span>  

 [<span data-ttu-id="5bb3c-105">COR_PRF_CLAUSE_TYPE — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="5bb3c-105">COR_PRF_CLAUSE_TYPE Enumeration</span></span>](cor-prf-clause-type-enumeration.md)  
 <span data-ttu-id="5bb3c-106">Wskazuje typ klauzuli wyjątku, który został właśnie wprowadzony lub pozostawiony w kodzie.</span><span class="sxs-lookup"><span data-stu-id="5bb3c-106">Indicates the type of exception clause that the code has just entered or left.</span></span>  
  
 [<span data-ttu-id="5bb3c-107">COR_PRF_CODEGEN_FLAGS — Wyliczanie</span><span class="sxs-lookup"><span data-stu-id="5bb3c-107">COR_PRF_CODEGEN_FLAGS Enumeration</span></span>](cor-prf-codegen-flags-enumeration.md)  
 <span data-ttu-id="5bb3c-108">Definiuje flagi generowania kodu, które można ustawić za pomocą metody [ICorProfilerFunctionControl:: SetCodegenFlags —](icorprofilerfunctioncontrol-setcodegenflags-method.md) .</span><span class="sxs-lookup"><span data-stu-id="5bb3c-108">Defines the code generation flags that can be set with the [ICorProfilerFunctionControl::SetCodegenFlags](icorprofilerfunctioncontrol-setcodegenflags-method.md) method.</span></span>  
  
 [<span data-ttu-id="5bb3c-109">COR_PRF_FINALIZER_FLAGS — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="5bb3c-109">COR_PRF_FINALIZER_FLAGS Enumeration</span></span>](cor-prf-finalizer-flags-enumeration.md)  
 <span data-ttu-id="5bb3c-110">Opisuje finalizator dla obiektu.</span><span class="sxs-lookup"><span data-stu-id="5bb3c-110">Describes the finalizer for an object.</span></span>  
  
 [<span data-ttu-id="5bb3c-111">COR_PRF_GC_GENERATION — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="5bb3c-111">COR_PRF_GC_GENERATION Enumeration</span></span>](cor-prf-gc-generation-enumeration.md)  
 <span data-ttu-id="5bb3c-112">Identyfikuje generowanie wyrzucania elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="5bb3c-112">Identifies a garbage collection generation.</span></span>  
  
 [<span data-ttu-id="5bb3c-113">COR_PRF_GC_REASON — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="5bb3c-113">COR_PRF_GC_REASON Enumeration</span></span>](cor-prf-gc-reason-enumeration.md)  
 <span data-ttu-id="5bb3c-114">Wskazuje przyczynę wyrzucania elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="5bb3c-114">Indicates the reason that garbage collection is occurring.</span></span>  
  
 [<span data-ttu-id="5bb3c-115">COR_PRF_GC_ROOT_FLAGS — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="5bb3c-115">COR_PRF_GC_ROOT_FLAGS Enumeration</span></span>](cor-prf-gc-root-flags-enumeration.md)  
 <span data-ttu-id="5bb3c-116">Wskazuje właściwości elementu głównego modułu wyrzucania elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="5bb3c-116">Indicates properties of a garbage collector root.</span></span>  
  
 [<span data-ttu-id="5bb3c-117">COR_PRF_GC_ROOT_KIND — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="5bb3c-117">COR_PRF_GC_ROOT_KIND Enumeration</span></span>](cor-prf-gc-root-kind-enumeration.md)  
 <span data-ttu-id="5bb3c-118">Wskazuje rodzaj elementu głównego modułu wyrzucania elementów bezużytecznych, który jest udostępniany przez wywołanie zwrotne [ICorProfilerCallback2:: RootReferences2 —](icorprofilercallback2-rootreferences2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="5bb3c-118">Indicates the kind of garbage collector root that is exposed by the [ICorProfilerCallback2::RootReferences2](icorprofilercallback2-rootreferences2-method.md) callback.</span></span>  
  
 [<span data-ttu-id="5bb3c-119">Wyliczenie COR_PRF_HIGH_MONITOR</span><span class="sxs-lookup"><span data-stu-id="5bb3c-119">COR_PRF_HIGH_MONITOR Enumeration</span></span>](cor-prf-high-monitor-enumeration.md)  
 <span data-ttu-id="5bb3c-120">Oferuje flagi oprócz tych, które znajdują się w wyliczeniu [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) , który profiler może określić do metody [ICorProfilerInfo5:: SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) podczas ładowania.</span><span class="sxs-lookup"><span data-stu-id="5bb3c-120">Provides flags in addition to those found in the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration that the profiler can specify to the [ICorProfilerInfo5::SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) method when it is loading.</span></span>  
  
 [<span data-ttu-id="5bb3c-121">COR_PRF_JIT_CACHE — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="5bb3c-121">COR_PRF_JIT_CACHE Enumeration</span></span>](cor-prf-jit-cache-enumeration.md)  
 <span data-ttu-id="5bb3c-122">Wskazuje wynik funkcji wyszukiwania w pamięci podręcznej.</span><span class="sxs-lookup"><span data-stu-id="5bb3c-122">Indicates the result of a cached function search.</span></span>  
  
 [<span data-ttu-id="5bb3c-123">COR_PRF_MISC — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="5bb3c-123">COR_PRF_MISC Enumeration</span></span>](cor-prf-misc-enumeration.md)  
 <span data-ttu-id="5bb3c-124">Zawiera wartości stałe, które określają identyfikatory specjalne.</span><span class="sxs-lookup"><span data-stu-id="5bb3c-124">Contains constant values that specify special identifiers.</span></span>  
  
 [<span data-ttu-id="5bb3c-125">COR_PRF_MODULE_FLAGS — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="5bb3c-125">COR_PRF_MODULE_FLAGS Enumeration</span></span>](cor-prf-module-flags-enumeration.md)  
 <span data-ttu-id="5bb3c-126">Określa właściwości modułu.</span><span class="sxs-lookup"><span data-stu-id="5bb3c-126">Specifies the properties of a module.</span></span>  
  
 [<span data-ttu-id="5bb3c-127">COR_PRF_MONITOR — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="5bb3c-127">COR_PRF_MONITOR Enumeration</span></span>](cor-prf-monitor-enumeration.md)  
 <span data-ttu-id="5bb3c-128">Zawiera wartości, które są używane do określania zachowania, możliwości lub zdarzeń, do których profiler chce subskrybować.</span><span class="sxs-lookup"><span data-stu-id="5bb3c-128">Contains values that are used to specify behavior, capabilities, or events to which the profiler wishes to subscribe.</span></span>  
  
 [<span data-ttu-id="5bb3c-129">COR_PRF_RUNTIME_TYPE — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="5bb3c-129">COR_PRF_RUNTIME_TYPE Enumeration</span></span>](cor-prf-runtime-type-enumeration.md)  
 <span data-ttu-id="5bb3c-130">Zawiera wartości wskazujące wersję środowiska uruchomieniowego języka wspólnego.</span><span class="sxs-lookup"><span data-stu-id="5bb3c-130">Contains values that indicate the version of the common language runtime.</span></span>  
  
 [<span data-ttu-id="5bb3c-131">COR_PRF_SNAPSHOT_INFO — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="5bb3c-131">COR_PRF_SNAPSHOT_INFO Enumeration</span></span>](cor-prf-snapshot-info-enumeration.md)  
 <span data-ttu-id="5bb3c-132">Określa ilość danych, które mają zostać przekazane z migawki stosu w każdym wywołaniu `StackSnapshotCallback` funkcji profilera.</span><span class="sxs-lookup"><span data-stu-id="5bb3c-132">Specifies how much data to pass back with a stack snapshot in each call to the profiler's `StackSnapshotCallback` function.</span></span>  
  
 [<span data-ttu-id="5bb3c-133">COR_PRF_STATIC_TYPE — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="5bb3c-133">COR_PRF_STATIC_TYPE Enumeration</span></span>](cor-prf-static-type-enumeration.md)  
 <span data-ttu-id="5bb3c-134">Wskazuje, czy pole jest statyczne i, jeśli tak, statyczna jakość stosowana do pola.</span><span class="sxs-lookup"><span data-stu-id="5bb3c-134">Indicates whether a field is static and, if so, the static quality that applies to the field.</span></span>  
  
 [<span data-ttu-id="5bb3c-135">COR_PRF_SUSPEND_REASON — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="5bb3c-135">COR_PRF_SUSPEND_REASON Enumeration</span></span>](cor-prf-suspend-reason-enumeration.md)  
 <span data-ttu-id="5bb3c-136">Wskazuje przyczynę wstrzymania środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="5bb3c-136">Indicates the reason that the runtime was suspended.</span></span>  
  
 [<span data-ttu-id="5bb3c-137">COR_PRF_TRANSITION_REASON — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="5bb3c-137">COR_PRF_TRANSITION_REASON Enumeration</span></span>](cor-prf-transition-reason-enumeration.md)  
 <span data-ttu-id="5bb3c-138">Wskazuje przyczynę przejścia z zarządzanego do kodu niezarządzanego lub odwrotnie.</span><span class="sxs-lookup"><span data-stu-id="5bb3c-138">Indicates the reason for a transition from managed to unmanaged code, or vice versa.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="5bb3c-139">Sekcje pokrewne</span><span class="sxs-lookup"><span data-stu-id="5bb3c-139">Related Sections</span></span>  

 [<span data-ttu-id="5bb3c-140">Omówienie profilowania</span><span class="sxs-lookup"><span data-stu-id="5bb3c-140">Profiling Overview</span></span>](profiling-overview.md)  
  
 [<span data-ttu-id="5bb3c-141">Interfejsy profilowania</span><span class="sxs-lookup"><span data-stu-id="5bb3c-141">Profiling Interfaces</span></span>](profiling-interfaces.md)  
  
 [<span data-ttu-id="5bb3c-142">Profilowanie statycznych funkcji globalnych</span><span class="sxs-lookup"><span data-stu-id="5bb3c-142">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)  
  
 [<span data-ttu-id="5bb3c-143">Profiling — Struktury</span><span class="sxs-lookup"><span data-stu-id="5bb3c-143">Profiling Structures</span></span>](profiling-structures.md)
