---
title: ICorProfilerFunctionEnum::Skip — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionEnum.Skip Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionEnum::Skip
helpviewer_keywords:
- Skip method, ICorProfilerFunctionEnum interface [.NET Framework profiling]
- ICorProfilerFunctionEnum::Skip method [.NET Framework profiling]
ms.assetid: 051465b9-e479-494a-804b-c880323b4cbe
topic_type:
- apiref
ms.openlocfilehash: da578e02db0744b1f64c1d392844aa020721e784
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95669263"
---
# <a name="icorprofilerfunctionenumskip-method"></a><span data-ttu-id="9a526-102">ICorProfilerFunctionEnum::Skip — Metoda</span><span class="sxs-lookup"><span data-stu-id="9a526-102">ICorProfilerFunctionEnum::Skip Method</span></span>

<span data-ttu-id="9a526-103">Przesuwa kursor modułu wyliczającego z jego bieżącej pozycji, tak aby określona liczba elementów została pominięta.</span><span class="sxs-lookup"><span data-stu-id="9a526-103">Advances the enumerator's cursor from its current position so that the specified number of elements are skipped.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a526-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="9a526-104">Syntax</span></span>  
  
```cpp  
HRESULT Skip([in] ULONG celt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9a526-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="9a526-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="9a526-106">podczas Liczba elementów, które mają zostać pominięte.</span><span class="sxs-lookup"><span data-stu-id="9a526-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9a526-107">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="9a526-107">Return Value</span></span>  

 <span data-ttu-id="9a526-108">Ta metoda zwraca następujące określone wartości HRESULT oraz błędy HRESULT wskazujące niepowodzenie metody.</span><span class="sxs-lookup"><span data-stu-id="9a526-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="9a526-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9a526-109">HRESULT</span></span>|<span data-ttu-id="9a526-110">Opis</span><span class="sxs-lookup"><span data-stu-id="9a526-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9a526-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="9a526-111">S_OK</span></span>|<span data-ttu-id="9a526-112">`celt` elementy zostały pominięte.</span><span class="sxs-lookup"><span data-stu-id="9a526-112">`celt` elements were skipped.</span></span>|  
|<span data-ttu-id="9a526-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="9a526-113">S_FALSE</span></span>|<span data-ttu-id="9a526-114">`celt`Pominięto mniej niż elementy, co oznacza, że nie ma więcej elementów.</span><span class="sxs-lookup"><span data-stu-id="9a526-114">Fewer than `celt` elements were skipped, which indicates that there are no more elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9a526-115">Uwagi</span><span class="sxs-lookup"><span data-stu-id="9a526-115">Remarks</span></span>  

 <span data-ttu-id="9a526-116">Nowa pozycja kursora tego modułu wyliczającego to (bieżąca pozycja) + `celt` .</span><span class="sxs-lookup"><span data-stu-id="9a526-116">The new position of this enumerator's cursor is (current position) + `celt`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a526-117">Wymagania</span><span class="sxs-lookup"><span data-stu-id="9a526-117">Requirements</span></span>  

 <span data-ttu-id="9a526-118">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a526-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a526-119">**Nagłówek:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="9a526-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9a526-120">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="9a526-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9a526-121">**.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a526-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a526-122">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="9a526-122">See also</span></span>

- [<span data-ttu-id="9a526-123">ICorProfilerFunctionEnum — Interfejs</span><span class="sxs-lookup"><span data-stu-id="9a526-123">ICorProfilerFunctionEnum Interface</span></span>](icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="9a526-124">Interfejsy profilowania</span><span class="sxs-lookup"><span data-stu-id="9a526-124">Profiling Interfaces</span></span>](profiling-interfaces.md)
