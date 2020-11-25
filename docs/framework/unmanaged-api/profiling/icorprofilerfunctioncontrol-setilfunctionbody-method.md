---
title: ICorProfilerFunctionControl::SetILFunctionBody — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionControl.SetILFunctionBody
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionControl::SetILFunctionBody
helpviewer_keywords:
- ICorProfilerFunctionControl::SetILFunctionBody method [.NET Framework profiling]
- SetILFunctionBody method, ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: 2c33f0f7-75b2-4c19-b2c7-c94b54997576
topic_type:
- apiref
ms.openlocfilehash: fa82cd1e646777c9841c1b3d653134aa7ba7ed7c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712745"
---
# <a name="icorprofilerfunctioncontrolsetilfunctionbody-method"></a><span data-ttu-id="d0c83-102">ICorProfilerFunctionControl::SetILFunctionBody — Metoda</span><span class="sxs-lookup"><span data-stu-id="d0c83-102">ICorProfilerFunctionControl::SetILFunctionBody Method</span></span>

<span data-ttu-id="d0c83-103">Zastępuje treść wspólnego języka pośredniego (CIL) metody.</span><span class="sxs-lookup"><span data-stu-id="d0c83-103">Replaces the Common Intermediate Language (CIL) body of the method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0c83-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="d0c83-104">Syntax</span></span>  
  
```cpp  
HRESULT SetILFunctionBody(  
    [in]  ULONG   cbNewILMethodHeader,  
    [in, size_is(cbNewILMethodHeader)] LPCBYTE pbNewILMethodHeader);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d0c83-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="d0c83-105">Parameters</span></span>  

 `cbNewILMethodHeader`  
 <span data-ttu-id="d0c83-106">[in] Całkowity rozmiar nowego CIL, łącznie z nagłówkiem i wszelkimi strukturami, które pochodzą z treści.</span><span class="sxs-lookup"><span data-stu-id="d0c83-106">[in] The total size of the new CIL, including the header and any structures that come after the body.</span></span>  
  
 `pbNewILMethodHeader`  
 <span data-ttu-id="d0c83-107">[in] Wskaźnik do nowego nagłówka CIL.</span><span class="sxs-lookup"><span data-stu-id="d0c83-107">[in] A pointer to the new CIL header.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d0c83-108">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="d0c83-108">Return Value</span></span>  

 <span data-ttu-id="d0c83-109">Ta metoda zwraca następujące specyficzne wyniki HRESULT.</span><span class="sxs-lookup"><span data-stu-id="d0c83-109">This method returns the following specific HRESULTs.</span></span>  
  
|<span data-ttu-id="d0c83-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d0c83-110">HRESULT</span></span>|<span data-ttu-id="d0c83-111">Opis</span><span class="sxs-lookup"><span data-stu-id="d0c83-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d0c83-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="d0c83-112">S_OK</span></span>|<span data-ttu-id="d0c83-113">Zamiana powiodła się.</span><span class="sxs-lookup"><span data-stu-id="d0c83-113">The replacement was successful.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d0c83-114">Uwagi</span><span class="sxs-lookup"><span data-stu-id="d0c83-114">Remarks</span></span>  

 <span data-ttu-id="d0c83-115">W przeciwieństwie do metody [ICorProfilerInfo:: SetILFunctionBody —](icorprofilerinfo-setilfunctionbody-method.md) `SetILFunctionBody` Metoda zarządza pamięcią wymaganą dla nowej treści CIL.</span><span class="sxs-lookup"><span data-stu-id="d0c83-115">Unlike the [ICorProfilerInfo::SetILFunctionBody](icorprofilerinfo-setilfunctionbody-method.md) method, the `SetILFunctionBody` method manages the memory required for the new CIL body.</span></span> <span data-ttu-id="d0c83-116">Oznacza to, że treści CIL dostarczone przez profiler nie muszą być przydzielone za pomocą interfejsu [IMethodMalloc](imethodmalloc-interface.md) ani przydzielone w ramach określonego zakresu.</span><span class="sxs-lookup"><span data-stu-id="d0c83-116">This means that the CIL body provided by the profiler does not have to be allocated by using the [IMethodMalloc](imethodmalloc-interface.md) interface or allocated within a particular range.</span></span> <span data-ttu-id="d0c83-117">Może być alokowana na dowolnej stercie.</span><span class="sxs-lookup"><span data-stu-id="d0c83-117">It can be allocated on any heap.</span></span> <span data-ttu-id="d0c83-118">Profiler może zwolnić pamięć używaną dla swojej treści CIL po `SetILFunctionBody` powrocie.</span><span class="sxs-lookup"><span data-stu-id="d0c83-118">The profiler can free the memory used for its CIL body after `SetILFunctionBody` returns.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0c83-119">Wymagania</span><span class="sxs-lookup"><span data-stu-id="d0c83-119">Requirements</span></span>  

 <span data-ttu-id="d0c83-120">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d0c83-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0c83-121">**Nagłówek:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="d0c83-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d0c83-122">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="d0c83-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d0c83-123">**.NET Framework wersje:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0c83-123">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0c83-124">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="d0c83-124">See also</span></span>

- [<span data-ttu-id="d0c83-125">ICorProfilerFunctionControl — Interfejs</span><span class="sxs-lookup"><span data-stu-id="d0c83-125">ICorProfilerFunctionControl Interface</span></span>](icorprofilerfunctioncontrol-interface.md)
