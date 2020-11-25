---
title: ICorProfilerObjectEnum::Next — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerObjectEnum.Next
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerObjectEnum::Next
helpviewer_keywords:
- Next method, ICorProfilerObjectEnum interface [.NET Framework profiling]
- ICorProfilerObjectEnum::Next method [.NET Framework profiling]
ms.assetid: b420433c-5ebe-4986-bba1-97902e6db819
topic_type:
- apiref
ms.openlocfilehash: e0c10549ab9075c2e7604a9adb18cae8b9a3b32b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702371"
---
# <a name="icorprofilerobjectenumnext-method"></a><span data-ttu-id="13aec-102">ICorProfilerObjectEnum::Next — Metoda</span><span class="sxs-lookup"><span data-stu-id="13aec-102">ICorProfilerObjectEnum::Next Method</span></span>

<span data-ttu-id="13aec-103">Pobiera określoną liczbę obiektów ciągłego z kolekcji sekwencyjnej obiektów, rozpoczynając od bieżącej pozycji modułu wyliczającego w sekwencji.</span><span class="sxs-lookup"><span data-stu-id="13aec-103">Gets the specified number of contiguous objects from a sequential collection of objects, starting at the enumerator's current position in the sequence.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13aec-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="13aec-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG                    celt,  
    [out, size_is(celt), length_is(*pceltFetched)]
        ObjectID                  objects[],  
    [out] ULONG                   *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="13aec-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="13aec-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="13aec-106">podczas Liczba obiektów do pobrania.</span><span class="sxs-lookup"><span data-stu-id="13aec-106">[in] The number of objects to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="13aec-107">określoną Tablica `ObjectID` wartości, z których każdy reprezentuje pobrany obiekt.</span><span class="sxs-lookup"><span data-stu-id="13aec-107">[out] An array of `ObjectID` values, each of which represents a retrieved object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="13aec-108">określoną Wskaźnik do liczby elementów faktycznie zwracanych w `objects` tablicy.</span><span class="sxs-lookup"><span data-stu-id="13aec-108">[out] A pointer to the number of elements actually returned in the `objects` array.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13aec-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="13aec-109">Requirements</span></span>  

 <span data-ttu-id="13aec-110">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="13aec-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13aec-111">**Nagłówek:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="13aec-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="13aec-112">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="13aec-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="13aec-113">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13aec-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13aec-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="13aec-114">See also</span></span>

- [<span data-ttu-id="13aec-115">ICorProfilerObjectEnum — Interfejs</span><span class="sxs-lookup"><span data-stu-id="13aec-115">ICorProfilerObjectEnum Interface</span></span>](icorprofilerobjectenum-interface.md)
