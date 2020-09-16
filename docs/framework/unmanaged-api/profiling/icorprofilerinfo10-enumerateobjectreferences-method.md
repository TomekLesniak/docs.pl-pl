---
title: ICorProfilerInfo10::EnumerateObjectReferences
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.EnumerateObjectReferences
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: a276ecfe65ed9752f39ed68a36e8e17a24255508
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90558319"
---
# <a name="icorprofilerinfo10enumerateobjectreferences-method"></a><span data-ttu-id="a3d61-102">ICorProfilerInfo10:: EnumerateObjectReferences, Metoda</span><span class="sxs-lookup"><span data-stu-id="a3d61-102">ICorProfilerInfo10::EnumerateObjectReferences Method</span></span>

<span data-ttu-id="a3d61-103">Podanym identyfikatorem ObjectID, wywołaniem zwrotnym i clientData, wylicza każde odwołanie do obiektu (jeśli istnieje).</span><span class="sxs-lookup"><span data-stu-id="a3d61-103">Given an ObjectID, callback and clientData, enumerates each object reference (if any).</span></span>

## <a name="syntax"></a><span data-ttu-id="a3d61-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="a3d61-104">Syntax</span></span>

```cpp
HRESULT EnumerateObjectReferences( [in] ObjectID objectId,
                                   [in] ObjectReferenceCallback callback,
                                   [in] void* clientData);
```

## <a name="parameters"></a><span data-ttu-id="a3d61-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="a3d61-105">Parameters</span></span>

- `objectId`

  <span data-ttu-id="a3d61-106">\[in] obiekt, na którym mają zostać wyliczone odwołania.</span><span class="sxs-lookup"><span data-stu-id="a3d61-106">\[in] The object to enumerate references on.</span></span>

- `callback`

  <span data-ttu-id="a3d61-107">\[w] funkcja, która zostanie wywołana z odwołaniami dla obiektu.</span><span class="sxs-lookup"><span data-stu-id="a3d61-107">\[in] The function that will be called with the references for the object.</span></span>

- `clientData`

  <span data-ttu-id="a3d61-108">\[in] dane dostarczone przez profiler do przekazania do `callback` funkcji.</span><span class="sxs-lookup"><span data-stu-id="a3d61-108">\[in] Profiler-provided data to pass to the `callback` function.</span></span>

## <a name="remarks"></a><span data-ttu-id="a3d61-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="a3d61-109">Remarks</span></span>

<span data-ttu-id="a3d61-110">`EnumerateObjectReferences`Metoda jest podobna do [ObjectReferences —](icorprofilercallback-objectreferences-method.md), z tą różnicą, że przeprowadza odwołania na żądanie dla profilera zamiast wstępnie przydzielić tablicę do przechowywania odwołań.</span><span class="sxs-lookup"><span data-stu-id="a3d61-110">The `EnumerateObjectReferences` method is similar to [ObjectReferences](icorprofilercallback-objectreferences-method.md), except that it walks the references on demand for the profiler instead of pre-allocating an array to store the references.</span></span>

## <a name="requirements"></a><span data-ttu-id="a3d61-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="a3d61-111">Requirements</span></span>

<span data-ttu-id="a3d61-112">**Platformy:** Zobacz [obsługiwane systemy operacyjne .NET Core](../../../core/install/windows.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="a3d61-112">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>

<span data-ttu-id="a3d61-113">**Nagłówek:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="a3d61-113">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="a3d61-114">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="a3d61-114">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="a3d61-115">**Wersje .NET:**[!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3d61-115">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="a3d61-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="a3d61-116">See also</span></span>

- [<span data-ttu-id="a3d61-117">ICorProfilerInfo10, interfejs</span><span class="sxs-lookup"><span data-stu-id="a3d61-117">ICorProfilerInfo10 Interface</span></span>](icorprofilerinfo10-interface.md)
