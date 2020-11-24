---
title: ICorProfilerInfo::SetFunctionIDMapper — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetFunctionIDMapper
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetFunctionIDMapper
helpviewer_keywords:
- ICorProfilerInfo::SetFunctionIDMapper method [.NET Framework profiling]
- SetFunctionIDMapper method [.NET Framework profiling]
ms.assetid: 1a6e5dae-d366-4497-9c02-7b5b1f43f9ec
topic_type:
- apiref
ms.openlocfilehash: 3a9ab64730feaa372f9b5d9ad7cefcb86580ca5e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95671177"
---
# <a name="icorprofilerinfosetfunctionidmapper-method"></a><span data-ttu-id="843cf-102">ICorProfilerInfo::SetFunctionIDMapper — Metoda</span><span class="sxs-lookup"><span data-stu-id="843cf-102">ICorProfilerInfo::SetFunctionIDMapper Method</span></span>

<span data-ttu-id="843cf-103">Określa funkcję zaimplementowaną przez profiler, która zostanie wywołana w celu mapowania `FunctionID` wartości na wartości alternatywne, które są przesyłane do punktów zaczepienia wejścia/wyjścia profilera.</span><span class="sxs-lookup"><span data-stu-id="843cf-103">Specifies the profiler-implemented function that will be called to map `FunctionID` values to alternative values, which are passed to the profiler's function entry/exit hooks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="843cf-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="843cf-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFunctionIDMapper (  
    [in] FunctionIDMapper *pFunc);  
```  
  
## <a name="parameters"></a><span data-ttu-id="843cf-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="843cf-105">Parameters</span></span>  

 `pFunc`  
 <span data-ttu-id="843cf-106">podczas Wskaźnik do implementacji [FunctionIDMapper](functionidmapper-function.md) , który zostanie wywołany w celu mapowania `FunctionID` wartości na ich wartości alternatywne.</span><span class="sxs-lookup"><span data-stu-id="843cf-106">[in] A pointer to the [FunctionIDMapper](functionidmapper-function.md) implementation that will be called to map the `FunctionID` values to their alternative values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="843cf-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="843cf-107">Remarks</span></span>  

 <span data-ttu-id="843cf-108">Alternatywy dla `FunctionID` wartości zostaną przesłane do punktów zaczepienia wejścia/wyjścia funkcji profilera ([FunctionEnter2](functionenter2-function.md), [FunctionLeave2](functionleave2-function.md)i [FunctionTailcall2](functiontailcall2-function.md)), które są określone przez metodę [ICorProfilerInfo2:: SetEnterLeaveFunctionHooks2 —](icorprofilerinfo2-setenterleavefunctionhooks2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="843cf-108">The alternatives for the `FunctionID` values will be passed to the profiler's function entry/exit hooks ([FunctionEnter2](functionenter2-function.md), [FunctionLeave2](functionleave2-function.md), and [FunctionTailcall2](functiontailcall2-function.md)) that are specified by the [ICorProfilerInfo2::SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md) method.</span></span>  
  
 <span data-ttu-id="843cf-109">`FunctionIDMapper`Można ją ustawić tylko raz i zaleca się jej ustawienie w [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) wywołania zwrotnego.</span><span class="sxs-lookup"><span data-stu-id="843cf-109">The `FunctionIDMapper` can be set only once and it is recommended that you set it in the [ICorProfilerCallback::Initialize](icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="843cf-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="843cf-110">Requirements</span></span>  

 <span data-ttu-id="843cf-111">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="843cf-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="843cf-112">**Nagłówek:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="843cf-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="843cf-113">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="843cf-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="843cf-114">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="843cf-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="843cf-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="843cf-115">See also</span></span>

- [<span data-ttu-id="843cf-116">ICorProfilerInfo — Interfejs</span><span class="sxs-lookup"><span data-stu-id="843cf-116">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
