---
title: ICorProfilerInfo2::GetGenerationBounds — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetGenerationBounds
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetGenerationBounds
helpviewer_keywords:
- ICorProfilerInfo2::GetGenerationBounds method [.NET Framework profiling]
- GetGenerationBounds method [.NET Framework profiling]
ms.assetid: 9c37185f-d1e0-4a6e-8b99-707f7df61d88
topic_type:
- apiref
ms.openlocfilehash: 2b9bf1a9f40764f6d0544bafb91f967905eb40c7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703918"
---
# <a name="icorprofilerinfo2getgenerationbounds-method"></a><span data-ttu-id="d8997-102">ICorProfilerInfo2::GetGenerationBounds — Metoda</span><span class="sxs-lookup"><span data-stu-id="d8997-102">ICorProfilerInfo2::GetGenerationBounds Method</span></span>

<span data-ttu-id="d8997-103">Pobiera obszary pamięci, które są segmentami sterty, które tworzą różne generacje wyrzucania elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="d8997-103">Gets the memory regions, which are segments of the heap, that make up the various garbage collection generations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8997-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="d8997-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGenerationBounds(  
    [in]  ULONG cObjectRanges,  
    [out] ULONG *pcObjectRanges,  
    [out, size_is(cObjectRanges), length_is(*pcObjectRanges)] COR_PRF_GC_GENERATION_RANGE ranges[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d8997-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="d8997-105">Parameters</span></span>  

 `cObjectRanges`  
 <span data-ttu-id="d8997-106">podczas Liczba elementów przyznanych przez obiekt wywołujący dla `ranges` tablicy.</span><span class="sxs-lookup"><span data-stu-id="d8997-106">[in] The number of elements allocated by the caller for the `ranges` array.</span></span>  
  
 `pcObjectRanges`  
 <span data-ttu-id="d8997-107">określoną Wskaźnik do liczby całkowitej, która określa łączną liczbę zakresów, część lub wszystkie zostaną zwrócone w `ranges` tablicy.</span><span class="sxs-lookup"><span data-stu-id="d8997-107">[out] A pointer to an integer that specifies the total number of ranges, some or all of which will be returned in the `ranges` array.</span></span>  
  
 `ranges`  
 <span data-ttu-id="d8997-108">określoną Tablica struktur [COR_PRF_GC_GENERATION_RANGE](cor-prf-gc-generation-range-structure.md) , z których każdy opisuje zakres (czyli blok) pamięci w ramach generacji, która nie powoduje wyrzucania elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="d8997-108">[out] An array of [COR_PRF_GC_GENERATION_RANGE](cor-prf-gc-generation-range-structure.md) structures, each of which describes a range (that is, block) of memory within the generation that is undergoing garbage collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d8997-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="d8997-109">Remarks</span></span>  

 <span data-ttu-id="d8997-110">`GetGenerationBounds`Metodę można wywołać z dowolnego wywołania zwrotnego profilera, pod warunkiem, że odzyskiwanie pamięci nie jest w toku.</span><span class="sxs-lookup"><span data-stu-id="d8997-110">The `GetGenerationBounds` method can be called from any profiler callback, provided that garbage collection is not in progress.</span></span>

 <span data-ttu-id="d8997-111">Większość przesunięć generacji odbywa się podczas odzyskiwania pamięci.</span><span class="sxs-lookup"><span data-stu-id="d8997-111">Most shifting of generations takes place during garbage collections.</span></span> <span data-ttu-id="d8997-112">Generacji mogą wzrosnąć między kolekcjami, ale zazwyczaj nie można ich przenosić.</span><span class="sxs-lookup"><span data-stu-id="d8997-112">Generations might grow between collections but generally do not move around.</span></span> <span data-ttu-id="d8997-113">W związku z tym najbardziej interesujące miejsca do wywołania `GetGenerationBounds` to w `ICorProfilerCallback2::GarbageCollectionStarted` i `ICorProfilerCallback2::GarbageCollectionFinished` .</span><span class="sxs-lookup"><span data-stu-id="d8997-113">Therefore, the most interesting places to call `GetGenerationBounds` are in `ICorProfilerCallback2::GarbageCollectionStarted` and `ICorProfilerCallback2::GarbageCollectionFinished`.</span></span>  
  
 <span data-ttu-id="d8997-114">Podczas uruchamiania programu niektóre obiekty są przydzielone przez środowisko uruchomieniowe języka wspólnego (CLR), zazwyczaj w generacjach 3 i 0.</span><span class="sxs-lookup"><span data-stu-id="d8997-114">During program startup, some objects are allocated by the common language runtime (CLR) itself, generally in generations 3 and 0.</span></span> <span data-ttu-id="d8997-115">W rezultacie przez kod zarządzany przez czas, te generacje zawierają już obiekty.</span><span class="sxs-lookup"><span data-stu-id="d8997-115">Thus, by the time managed code starts executing, these generations will already contain objects.</span></span> <span data-ttu-id="d8997-116">Generacje 1 i 2 zwykle będą puste, z wyjątkiem obiektów fikcyjnych generowanych przez moduł wyrzucania elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="d8997-116">Generations 1 and 2 will normally be empty, except for dummy objects that are generated by the garbage collector.</span></span> <span data-ttu-id="d8997-117">(Rozmiar fikcyjnych obiektów to 12 bajtów w 32-bitowych implementacjach środowiska CLR; rozmiar jest większy w przypadku implementacji 64-bitowych). Możesz również zobaczyć zakresy generacji 2, które znajdują się w modułach wytwarzanych przez generator obrazu natywnego (NGen.exe).</span><span class="sxs-lookup"><span data-stu-id="d8997-117">(The size of dummy objects is 12 bytes in 32-bit implementations of the CLR; the size is larger in 64-bit implementations.) You might also see generation 2 ranges that are inside modules produced by the Native Image Generator (NGen.exe).</span></span> <span data-ttu-id="d8997-118">W takim przypadku obiekty w generacji 2 są *obiektami zablokowanymi*, które są przydzielone podczas uruchamiania NGen.exe, a nie przez moduł wyrzucania elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="d8997-118">In this case, the objects in generation 2 are *frozen objects*, which are allocated when NGen.exe runs rather than by the garbage collector.</span></span>  
  
 <span data-ttu-id="d8997-119">Ta funkcja używa buforów przyznanych przez obiekt wywołujący.</span><span class="sxs-lookup"><span data-stu-id="d8997-119">This function uses caller-allocated buffers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8997-120">Wymagania</span><span class="sxs-lookup"><span data-stu-id="d8997-120">Requirements</span></span>  

 <span data-ttu-id="d8997-121">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8997-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8997-122">**Nagłówek:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="d8997-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d8997-123">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="d8997-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d8997-124">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8997-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8997-125">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="d8997-125">See also</span></span>

- [<span data-ttu-id="d8997-126">ICorProfilerInfo — Interfejs</span><span class="sxs-lookup"><span data-stu-id="d8997-126">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="d8997-127">ICorProfilerInfo2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="d8997-127">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
- [<span data-ttu-id="d8997-128">Interfejsy profilowania</span><span class="sxs-lookup"><span data-stu-id="d8997-128">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="d8997-129">Profilowanie</span><span class="sxs-lookup"><span data-stu-id="d8997-129">Profiling</span></span>](index.md)
