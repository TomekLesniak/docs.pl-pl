---
title: ICorProfilerModuleEnum::Next — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerModuleEnum.Next Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerModuleEnum::Next
helpviewer_keywords:
- ICorProfilerModuleEnum::Next method [.NET Framework profiling]
- Next method, ICorProfilerModuleEnum interface [.NET Framework profiling]
ms.assetid: a3cea59d-7622-4323-897a-0a464c40f77f
topic_type:
- apiref
ms.openlocfilehash: 94c2c159cf386e00dfc0d1df97536d7ade53407e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732947"
---
# <a name="icorprofilermoduleenumnext-method"></a><span data-ttu-id="f4a97-102">ICorProfilerModuleEnum::Next — Metoda</span><span class="sxs-lookup"><span data-stu-id="f4a97-102">ICorProfilerModuleEnum::Next Method</span></span>

<span data-ttu-id="f4a97-103">Pobiera określoną liczbę modułów ciągłych z sekwencyjnego zbioru modułów, rozpoczynając od bieżącej pozycji modułu wyliczającego w sekwencji.</span><span class="sxs-lookup"><span data-stu-id="f4a97-103">Gets the specified number of contiguous modules from a sequential collection of modules, starting at the enumerator's current position in the sequence.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4a97-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="f4a97-104">Syntax</span></span>  
  
```cpp  
HRESULT Next([in]  ULONG      celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                    ModuleID ids[],  
             [out] ULONG *   pceltFetched);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f4a97-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="f4a97-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="f4a97-106">podczas Liczba modułów do pobrania.</span><span class="sxs-lookup"><span data-stu-id="f4a97-106">[in] The number of modules to retrieve.</span></span>  
  
 `ids`  
 <span data-ttu-id="f4a97-107">określoną Tablica `ModuleID` wartości, z których każdy reprezentuje pobrany moduł.</span><span class="sxs-lookup"><span data-stu-id="f4a97-107">[out] An array of `ModuleID` values, each of which represents a retrieved module.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="f4a97-108">określoną Wskaźnik do liczby elementów faktycznie zwracanych w `ids` tablicy.</span><span class="sxs-lookup"><span data-stu-id="f4a97-108">[out] A pointer to the number of elements actually returned in the `ids` array.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f4a97-109">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="f4a97-109">Return Value</span></span>  

 <span data-ttu-id="f4a97-110">Ta metoda zwraca następujące określone wartości HRESULT oraz błędy HRESULT wskazujące niepowodzenie metody.</span><span class="sxs-lookup"><span data-stu-id="f4a97-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="f4a97-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f4a97-111">HRESULT</span></span>|<span data-ttu-id="f4a97-112">Opis</span><span class="sxs-lookup"><span data-stu-id="f4a97-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f4a97-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="f4a97-113">S_OK</span></span>|<span data-ttu-id="f4a97-114">`celt` elementy zostały zwrócone.</span><span class="sxs-lookup"><span data-stu-id="f4a97-114">`celt` elements were returned.</span></span>|  
|<span data-ttu-id="f4a97-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="f4a97-115">S_FALSE</span></span>|<span data-ttu-id="f4a97-116">`celt`Zwrócono mniej niż elementy, co oznacza, że Wyliczenie zostało zakończone.</span><span class="sxs-lookup"><span data-stu-id="f4a97-116">Fewer than `celt` elements were returned, which indicates that the enumeration is complete.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f4a97-117">Wymagania</span><span class="sxs-lookup"><span data-stu-id="f4a97-117">Requirements</span></span>  

 <span data-ttu-id="f4a97-118">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4a97-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4a97-119">**Nagłówek:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="f4a97-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f4a97-120">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="f4a97-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f4a97-121">**.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4a97-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4a97-122">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="f4a97-122">See also</span></span>

- [<span data-ttu-id="f4a97-123">ICorProfilerModuleEnum — Interfejs</span><span class="sxs-lookup"><span data-stu-id="f4a97-123">ICorProfilerModuleEnum Interface</span></span>](icorprofilermoduleenum-interface.md)
- [<span data-ttu-id="f4a97-124">Interfejsy profilowania</span><span class="sxs-lookup"><span data-stu-id="f4a97-124">Profiling Interfaces</span></span>](profiling-interfaces.md)
