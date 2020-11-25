---
title: ICorProfilerInfo2::GetClassLayout — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetClassLayout
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetClassLayout
helpviewer_keywords:
- ICorProfilerInfo2::GetClassLayout method [.NET Framework profiling]
- GetClassLayout method, ICorProfilerInfo2 interface [.NET Framework profiling]
ms.assetid: a3a36987-5666-4e2f-95b5-d0cb246502ec
topic_type:
- apiref
ms.openlocfilehash: a2bac05e7471a0df8d624bf5dfbe2aa58c25cf4c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727175"
---
# <a name="icorprofilerinfo2getclasslayout-method"></a><span data-ttu-id="83bdf-102">ICorProfilerInfo2::GetClassLayout — Metoda</span><span class="sxs-lookup"><span data-stu-id="83bdf-102">ICorProfilerInfo2::GetClassLayout Method</span></span>

<span data-ttu-id="83bdf-103">Pobiera informacje o układzie, w pamięci, pól zdefiniowanych przez określoną klasę.</span><span class="sxs-lookup"><span data-stu-id="83bdf-103">Gets information about the layout, in memory, of the fields defined by the specified class.</span></span> <span data-ttu-id="83bdf-104">Oznacza to, że ta metoda pobiera przesunięcia pól klasy.</span><span class="sxs-lookup"><span data-stu-id="83bdf-104">That is, this method gets the offsets of the class's fields.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83bdf-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="83bdf-105">Syntax</span></span>  
  
```cpp  
HRESULT GetClassLayout(  
    [in]  ClassID classID,  
    [in, out] COR_FIELD_OFFSET rFieldOffset[],  
    [in]  ULONG cFieldOffset,  
    [out] ULONG *pcFieldOffset,  
    [out] ULONG *pulClassSize);  
```  
  
## <a name="parameters"></a><span data-ttu-id="83bdf-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="83bdf-106">Parameters</span></span>  

 `classID`  
 <span data-ttu-id="83bdf-107">podczas Identyfikator klasy, dla której zostanie pobrany układ.</span><span class="sxs-lookup"><span data-stu-id="83bdf-107">[in] The ID of the class for which the layout will be retrieved.</span></span>  
  
 `rFieldOffset`  
 <span data-ttu-id="83bdf-108">[in. out] Tablica struktur [COR_FIELD_OFFSET](../metadata/cor-field-offset-structure.md) , z których każdy zawiera tokeny i przesunięcia pól klasy.</span><span class="sxs-lookup"><span data-stu-id="83bdf-108">[in, out] An array of [COR_FIELD_OFFSET](../metadata/cor-field-offset-structure.md) structures, each of which contains the tokens and offsets of the class's fields.</span></span>  
  
 `cFieldOffset`  
 <span data-ttu-id="83bdf-109">podczas Rozmiar `rFieldOffset` tablicy.</span><span class="sxs-lookup"><span data-stu-id="83bdf-109">[in] The size of the `rFieldOffset` array.</span></span>  
  
 `pcFieldOffset`  
 <span data-ttu-id="83bdf-110">określoną Wskaźnik do łącznej liczby dostępnych elementów.</span><span class="sxs-lookup"><span data-stu-id="83bdf-110">[out] A pointer to the total number of available elements.</span></span> <span data-ttu-id="83bdf-111">Jeśli `cFieldOffset` jest równa 0, ta wartość wskazuje wymaganą liczbę elementów.</span><span class="sxs-lookup"><span data-stu-id="83bdf-111">If `cFieldOffset` is 0, this value indicates the number of elements needed.</span></span>  
  
 `pulClassSize`  
 <span data-ttu-id="83bdf-112">określoną Wskaźnik do lokalizacji zawierającej rozmiar (w bajtach) klasy.</span><span class="sxs-lookup"><span data-stu-id="83bdf-112">[out] A pointer to a location that contains the size, in bytes, of the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="83bdf-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="83bdf-113">Remarks</span></span>  

 <span data-ttu-id="83bdf-114">`GetClassLayout`Metoda zwraca tylko pola zdefiniowane przez samą klasę.</span><span class="sxs-lookup"><span data-stu-id="83bdf-114">The `GetClassLayout` method returns only the fields defined by the class itself.</span></span> <span data-ttu-id="83bdf-115">Jeśli Klasa nadrzędna klasy ma również zdefiniowane pola, profiler musi wywołać `GetClassLayout` klasy nadrzędnej, aby uzyskać te pola.</span><span class="sxs-lookup"><span data-stu-id="83bdf-115">If the class's parent class has defined fields as well, the profiler must call `GetClassLayout` on the parent class to obtain those fields.</span></span>  
  
 <span data-ttu-id="83bdf-116">Jeśli używasz `GetClassLayout` z klasami ciągów, metoda zakończy się niepowodzeniem z kodem błędu E_INVALIDARG.</span><span class="sxs-lookup"><span data-stu-id="83bdf-116">If you use `GetClassLayout` with string classes, the method will fail with error code E_INVALIDARG.</span></span> <span data-ttu-id="83bdf-117">Użyj [ICorProfilerInfo2:: GetStringLayout —](icorprofilerinfo2-getstringlayout-method.md) , aby uzyskać informacje na temat układu ciągu.</span><span class="sxs-lookup"><span data-stu-id="83bdf-117">Use [ICorProfilerInfo2::GetStringLayout](icorprofilerinfo2-getstringlayout-method.md) to get information about the layout of a string.</span></span> <span data-ttu-id="83bdf-118">`GetClassLayout` również zakończy się niepowodzeniem w przypadku wywołania z klasą Array.</span><span class="sxs-lookup"><span data-stu-id="83bdf-118">`GetClassLayout` will also fail when called with an array class.</span></span>  
  
 <span data-ttu-id="83bdf-119">Po `GetClassLayout` powrocie należy sprawdzić, czy `rFieldOffset` bufor jest wystarczająco duży, aby można było zawierać wszystkie dostępne `COR_FIELD_OFFSET` struktury.</span><span class="sxs-lookup"><span data-stu-id="83bdf-119">After `GetClassLayout` returns, you must verify that the `rFieldOffset` buffer was large enough to contain all the available `COR_FIELD_OFFSET` structures.</span></span> <span data-ttu-id="83bdf-120">W tym celu należy porównać wartość, która `pcFieldOffset` wskazuje na wielkość `rFieldOffset` podzieloną przez rozmiar `COR_FIELD_OFFSET` struktury.</span><span class="sxs-lookup"><span data-stu-id="83bdf-120">To do this, compare the value that `pcFieldOffset` points to with the size of `rFieldOffset` divided by the size of a `COR_FIELD_OFFSET` structure.</span></span> <span data-ttu-id="83bdf-121">Jeśli `rFieldOffset` nie jest wystarczająco duży, Przydziel większy `rFieldOffset` bufor, zaktualizuj `cFieldOffset` go przy użyciu nowego, większego rozmiaru i ponownie wywołaj `GetClassLayout` .</span><span class="sxs-lookup"><span data-stu-id="83bdf-121">If `rFieldOffset` is not large enough, allocate a larger `rFieldOffset` buffer, update `cFieldOffset` with the new, larger size, and call `GetClassLayout` again.</span></span>  
  
 <span data-ttu-id="83bdf-122">Alternatywnie, można najpierw wywołać `GetClassLayout` z buforem o zerowej długości, `rFieldOffset` Aby uzyskać prawidłowy rozmiar buforu.</span><span class="sxs-lookup"><span data-stu-id="83bdf-122">Alternatively, you can first call `GetClassLayout` with a zero-length `rFieldOffset` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="83bdf-123">Następnie można ustawić rozmiar buforu na wartość zwracaną w `pcFieldOffset` i `GetClassLayout` ponownie wywołać.</span><span class="sxs-lookup"><span data-stu-id="83bdf-123">You can then set the buffer size to the value returned in `pcFieldOffset` and call `GetClassLayout` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83bdf-124">Wymagania</span><span class="sxs-lookup"><span data-stu-id="83bdf-124">Requirements</span></span>  

 <span data-ttu-id="83bdf-125">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83bdf-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83bdf-126">**Nagłówek:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="83bdf-126">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="83bdf-127">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="83bdf-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="83bdf-128">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83bdf-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83bdf-129">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="83bdf-129">See also</span></span>

- [<span data-ttu-id="83bdf-130">ICorProfilerInfo — Interfejs</span><span class="sxs-lookup"><span data-stu-id="83bdf-130">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="83bdf-131">ICorProfilerInfo2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="83bdf-131">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
- [<span data-ttu-id="83bdf-132">Interfejsy profilowania</span><span class="sxs-lookup"><span data-stu-id="83bdf-132">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="83bdf-133">Profilowanie</span><span class="sxs-lookup"><span data-stu-id="83bdf-133">Profiling</span></span>](index.md)
