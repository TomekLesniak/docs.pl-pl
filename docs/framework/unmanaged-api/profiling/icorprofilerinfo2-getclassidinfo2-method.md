---
title: ICorProfilerInfo2::GetClassIDInfo2 — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetClassIDInfo2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetClassIDInfo2
helpviewer_keywords:
- GetClassIDInfo2 method [.NET Framework profiling]
- ICorProfilerInfo2::GetClassIDInfo2 method [.NET Framework profiling]
ms.assetid: 0141d582-d066-4d49-8d1f-ae82129a1960
topic_type:
- apiref
ms.openlocfilehash: 4b018a329396e0be684c999a33d4ef7c3518cb1c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703909"
---
# <a name="icorprofilerinfo2getclassidinfo2-method"></a><span data-ttu-id="95f20-102">ICorProfilerInfo2::GetClassIDInfo2 — Metoda</span><span class="sxs-lookup"><span data-stu-id="95f20-102">ICorProfilerInfo2::GetClassIDInfo2 Method</span></span>

<span data-ttu-id="95f20-103">Pobiera moduł nadrzędny i token metadanych dla otwartej definicji ogólnej określonej klasy, `ClassID` klasy nadrzędnej i `ClassID` argumentu dla każdego typu, jeśli istnieje, klasy.</span><span class="sxs-lookup"><span data-stu-id="95f20-103">Gets the parent module and metadata token for the open generic definition of the specified class, the `ClassID` of its parent class, and the `ClassID` for each type argument, if present, of the class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95f20-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="95f20-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClassIDInfo2(  
    [in]  ClassID classId,  
    [out] ModuleID *pModuleId,  
    [out] mdTypeDef *pTypeDefToken,  
    [out] ClassID *pParentClassId,  
    [in]  ULONG32 cNumTypeArgs,  
    [out] ULONG32 *pcNumTypeArgs,  
    [out] ClassID typeArgs[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="95f20-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="95f20-105">Parameters</span></span>  

 `classId`  
 <span data-ttu-id="95f20-106">podczas Identyfikator klasy, dla której będą pobierane informacje.</span><span class="sxs-lookup"><span data-stu-id="95f20-106">[in] The ID of the class for which information will be retrieved.</span></span>  
  
 `pModuleId`  
 <span data-ttu-id="95f20-107">określoną Wskaźnik na identyfikator modułu nadrzędnego dla otwartej definicji ogólnej dla określonej klasy.</span><span class="sxs-lookup"><span data-stu-id="95f20-107">[out] Pointer to the ID of the parent module for the open generic definition of the specified class.</span></span>  
  
 `pTypeDefToken`  
 <span data-ttu-id="95f20-108">określoną Wskaźnik do tokenu metadanych dla otwartej definicji ogólnej określonej klasy.</span><span class="sxs-lookup"><span data-stu-id="95f20-108">[out] Pointer to the metadata token for the open generic definition of the specified class.</span></span>  
  
 `pParentClassId`  
 <span data-ttu-id="95f20-109">określoną Wskaźnik na identyfikator klasy nadrzędnej.</span><span class="sxs-lookup"><span data-stu-id="95f20-109">[out] Pointer to the ID of the parent class.</span></span>  
  
 `cNumTypeArgs`  
 <span data-ttu-id="95f20-110">podczas Rozmiar `typeArgs` tablicy.</span><span class="sxs-lookup"><span data-stu-id="95f20-110">[in] The size of the `typeArgs` array.</span></span>  
  
 `pcNumTypeArgs`  
 <span data-ttu-id="95f20-111">określoną Wskaźnik do całkowitej liczby dostępnych elementów.</span><span class="sxs-lookup"><span data-stu-id="95f20-111">[out] Pointer to the total number of available elements.</span></span>  
  
 `typeArgs`  
 <span data-ttu-id="95f20-112">określoną Tablica `ClassID` wartości, z których każdy reprezentuje identyfikator argumentu typu klasy.</span><span class="sxs-lookup"><span data-stu-id="95f20-112">[out] An array of `ClassID` values, each of which represents the ID of a type argument of the class.</span></span> <span data-ttu-id="95f20-113">Gdy metoda zwraca, `typeArgs` będzie zawierać niektóre lub wszystkie dostępne `ClassID` wartości.</span><span class="sxs-lookup"><span data-stu-id="95f20-113">When the method returns, `typeArgs` will contain some or all the available `ClassID` values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="95f20-114">Uwagi</span><span class="sxs-lookup"><span data-stu-id="95f20-114">Remarks</span></span>  

 <span data-ttu-id="95f20-115">`GetClassIDInfo2`Metoda jest podobna do metody [ICorProfilerInfo:: GetClassIDInfo —](icorprofilerinfo-getclassidinfo-method.md) , ale `GetClassIDInfo2` uzyskuje dodatkowe informacje o typie ogólnym.</span><span class="sxs-lookup"><span data-stu-id="95f20-115">The `GetClassIDInfo2` method is similar to the [ICorProfilerInfo::GetClassIDInfo](icorprofilerinfo-getclassidinfo-method.md) method, but `GetClassIDInfo2` obtains additional information about a generic type.</span></span>  
  
 <span data-ttu-id="95f20-116">Kod profilera może wywołać [ICorProfilerInfo:: GetModuleMetaData —](icorprofilerinfo-getmodulemetadata-method.md) w celu uzyskania interfejsu [metadanych](../metadata/index.md) dla danego modułu.</span><span class="sxs-lookup"><span data-stu-id="95f20-116">The profiler code can call [ICorProfilerInfo::GetModuleMetaData](icorprofilerinfo-getmodulemetadata-method.md) to obtain a [metadata](../metadata/index.md) interface for a given module.</span></span> <span data-ttu-id="95f20-117">Token metadanych, który jest zwracany do lokalizacji, do której się odwołuje się, `pTypeDefToken` może następnie zostać użyty w celu uzyskania dostępu do metadanych dla klasy.</span><span class="sxs-lookup"><span data-stu-id="95f20-117">The metadata token that is returned to the location referenced by `pTypeDefToken` can then be used to access the metadata for the class.</span></span>  
  
 <span data-ttu-id="95f20-118">Po `GetClassIDInfo2` powrocie należy sprawdzić, czy `typeArgs` bufor jest wystarczająco duży, aby można było zawierać wszystkie `ClassID` wartości.</span><span class="sxs-lookup"><span data-stu-id="95f20-118">After `GetClassIDInfo2` returns, you must verify that the `typeArgs` buffer was large enough to contain all the `ClassID` values.</span></span> <span data-ttu-id="95f20-119">W tym celu należy porównać wartość wskazującą wartość `pcNumTypeArgs` `cNumTypeArgs` parametru.</span><span class="sxs-lookup"><span data-stu-id="95f20-119">To do this, compare the value that `pcNumTypeArgs` points to with the value of the `cNumTypeArgs` parameter.</span></span> <span data-ttu-id="95f20-120">Jeśli `pcNumTypeArgs` wskazuje wartość, która jest większa niż `cNumTypeArgs` , Przydziel większy `typeArgs` bufor, zaktualizuj `cNumTypeArgs` przy użyciu nowego, większego rozmiaru i ponownie wywołaj `GetClassIDInfo2` .</span><span class="sxs-lookup"><span data-stu-id="95f20-120">If `pcNumTypeArgs` points to a value that is larger than `cNumTypeArgs`, allocate a larger `typeArgs` buffer, update `cNumTypeArgs` with the new, larger size, and call `GetClassIDInfo2` again.</span></span>  
  
 <span data-ttu-id="95f20-121">Alternatywnie, można najpierw wywołać `GetClassIDInfo2` z buforem o zerowej długości, `typeArgs` Aby uzyskać prawidłowy rozmiar buforu.</span><span class="sxs-lookup"><span data-stu-id="95f20-121">Alternatively, you can first call `GetClassIDInfo2` with a zero-length `typeArgs` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="95f20-122">Następnie można ustawić `typeArgs` rozmiar buforu na wartość zwracaną w `pcNumTypeArgs` i `GetClassIDInfo2` ponownie wywołać.</span><span class="sxs-lookup"><span data-stu-id="95f20-122">You can then set the `typeArgs` buffer size to the value returned in `pcNumTypeArgs` and call `GetClassIDInfo2` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95f20-123">Wymagania</span><span class="sxs-lookup"><span data-stu-id="95f20-123">Requirements</span></span>  

 <span data-ttu-id="95f20-124">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95f20-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95f20-125">**Nagłówek:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="95f20-125">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="95f20-126">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="95f20-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="95f20-127">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95f20-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95f20-128">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="95f20-128">See also</span></span>

- [<span data-ttu-id="95f20-129">ICorProfilerInfo — Interfejs</span><span class="sxs-lookup"><span data-stu-id="95f20-129">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="95f20-130">ICorProfilerInfo2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="95f20-130">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
- [<span data-ttu-id="95f20-131">Interfejsy profilowania</span><span class="sxs-lookup"><span data-stu-id="95f20-131">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="95f20-132">Profilowanie</span><span class="sxs-lookup"><span data-stu-id="95f20-132">Profiling</span></span>](index.md)
