---
title: ICorProfilerCallback::ObjectsAllocatedByClass — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ObjectsAllocatedByClass
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ObjectsAllocatedByClass
helpviewer_keywords:
- ObjectsAllocatedByClass method [.NET Framework profiling]
- ICorProfilerCallback::ObjectsAllocatedByClass method [.NET Framework profiling]
ms.assetid: 91d688f3-a80e-419d-9755-ff94bc04188a
topic_type:
- apiref
ms.openlocfilehash: 70d43d7526376c40d0f8358ebd65e4a00a41b969
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95701671"
---
# <a name="icorprofilercallbackobjectsallocatedbyclass-method"></a><span data-ttu-id="54f81-102">ICorProfilerCallback::ObjectsAllocatedByClass — Metoda</span><span class="sxs-lookup"><span data-stu-id="54f81-102">ICorProfilerCallback::ObjectsAllocatedByClass Method</span></span>

<span data-ttu-id="54f81-103">Powiadamia profiler o liczbie wystąpień każdej określonej klasy, które zostały utworzone od czasu ostatniego wyrzucania elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="54f81-103">Notifies the profiler about the number of instances of each specified class that have been created since the most recent garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54f81-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="54f81-104">Syntax</span></span>  
  
```cpp  
HRESULT ObjectsAllocatedByClass(  
    [in] ULONG   cClassCount,  
    [in, size_is(cClassCount)] ClassID classIds[] ,  
    [in, size_is(cClassCount)] ULONG   cObjects[] );  
```  
  
## <a name="parameters"></a><span data-ttu-id="54f81-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="54f81-105">Parameters</span></span>  

 `cClassCount`  
 <span data-ttu-id="54f81-106">podczas Rozmiar `classIds` `cObjects` tablic i.</span><span class="sxs-lookup"><span data-stu-id="54f81-106">[in] The size of the `classIds` and `cObjects` arrays.</span></span>  
  
 `classIds`  
 <span data-ttu-id="54f81-107">podczas Tablica identyfikatorów klasy, gdzie każdy identyfikator Określa klasę z co najmniej jednym wystąpieniem.</span><span class="sxs-lookup"><span data-stu-id="54f81-107">[in] An array of class IDs, where each ID specifies a class with one or more instances.</span></span>  
  
 `cObjects`  
 <span data-ttu-id="54f81-108">podczas Tablica liczb całkowitych, gdzie każda liczba całkowita określa liczbę wystąpień odpowiadającej klasie w `classIds` tablicy.</span><span class="sxs-lookup"><span data-stu-id="54f81-108">[in] An array of integers, where each integer specifies the number of instances for the corresponding class in the `classIds` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="54f81-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="54f81-109">Remarks</span></span>  

 <span data-ttu-id="54f81-110">`classIds`Tablice i `cObjects` są tablicami równoległymi.</span><span class="sxs-lookup"><span data-stu-id="54f81-110">The `classIds` and `cObjects` arrays are parallel arrays.</span></span> <span data-ttu-id="54f81-111">Na przykład, `classIds[i]` i `cObjects[i]` odwoływać się do tej samej klasy.</span><span class="sxs-lookup"><span data-stu-id="54f81-111">For example, `classIds[i]` and `cObjects[i]` reference the same class.</span></span> <span data-ttu-id="54f81-112">Jeśli żadne wystąpienie klasy nie zostało utworzone od czasu wcześniejszego wyrzucania elementów bezużytecznych, Klasa zostanie pominięta.</span><span class="sxs-lookup"><span data-stu-id="54f81-112">If no instance of a class has been created since the previous garbage collection, the class is omitted.</span></span> <span data-ttu-id="54f81-113">`ObjectsAllocatedByClass`Wywołanie zwrotne nie będzie zgłaszać obiektów przyznanych w stercie dużego obiektu.</span><span class="sxs-lookup"><span data-stu-id="54f81-113">The `ObjectsAllocatedByClass` callback will not report objects allocated in the large object heap.</span></span>  
  
 <span data-ttu-id="54f81-114">Liczby raportowane przez `ObjectsAllocatedByClass` są tylko Szacowana.</span><span class="sxs-lookup"><span data-stu-id="54f81-114">The numbers reported by `ObjectsAllocatedByClass` are only estimates.</span></span> <span data-ttu-id="54f81-115">Aby uzyskać dokładne liczby, użyj [ICorProfilerCallback:: ObjectAllocated —](icorprofilercallback-objectallocated-method.md).</span><span class="sxs-lookup"><span data-stu-id="54f81-115">For exact counts, use [ICorProfilerCallback::ObjectAllocated](icorprofilercallback-objectallocated-method.md).</span></span>  
  
 <span data-ttu-id="54f81-116">`classIds`Tablica może zawierać jeden lub więcej wpisów o wartości null, Jeśli odpowiednia `cObjects` Tablica zawiera typy, które są zwalniane.</span><span class="sxs-lookup"><span data-stu-id="54f81-116">The `classIds` array may contain one or more null entries if the corresponding `cObjects` array has types that are unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54f81-117">Wymagania</span><span class="sxs-lookup"><span data-stu-id="54f81-117">Requirements</span></span>  

 <span data-ttu-id="54f81-118">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="54f81-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54f81-119">**Nagłówek:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="54f81-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="54f81-120">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="54f81-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="54f81-121">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54f81-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54f81-122">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="54f81-122">See also</span></span>

- [<span data-ttu-id="54f81-123">ICorProfilerCallback — Interfejs</span><span class="sxs-lookup"><span data-stu-id="54f81-123">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
