---
title: ICorProfilerCallback3::InitializeForAttach — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback3.InitializeForAttach Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback3::InitializeForAttach
helpviewer_keywords:
- InitializeForAttach method [.NET Framework profiling]
- ICorProfilerCallback3::InitializeForAttach method [.NET Framework profiling]
ms.assetid: bed097b3-6d52-46c9-bee7-ac7910b6fc3f
topic_type:
- apiref
ms.openlocfilehash: c85bba9a5d913820b69cbc214275b733a53197ee
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729450"
---
# <a name="icorprofilercallback3initializeforattach-method"></a><span data-ttu-id="620eb-102">ICorProfilerCallback3::InitializeForAttach — Metoda</span><span class="sxs-lookup"><span data-stu-id="620eb-102">ICorProfilerCallback3::InitializeForAttach Method</span></span>

<span data-ttu-id="620eb-103">Wywoływane przez środowisko uruchomieniowe języka wspólnego (CLR), aby Profiler mógł zainicjować swój stan po operacji dołączania.</span><span class="sxs-lookup"><span data-stu-id="620eb-103">Called by the common language runtime (CLR) to give the profiler an opportunity to initialize its state after an attach operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="620eb-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="620eb-104">Syntax</span></span>  
  
```cpp  
HRESULT InitializeForAttach(  
            [in] IUnknown * pCorProfilerInfoUnk,  
            [in] void * pvClientData,  
            [in] UINT cbClientData);  
```  
  
## <a name="parameters"></a><span data-ttu-id="620eb-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="620eb-105">Parameters</span></span>  

 `pCorProfilerInfoUnk`  
 <span data-ttu-id="620eb-106">podczas Wskaźnik interfejsu dla `ICorProfilerInfo*` interfejsu.</span><span class="sxs-lookup"><span data-stu-id="620eb-106">[in] An interface pointer for the `ICorProfilerInfo*` interface.</span></span>  
  
 `pvClientData`  
 <span data-ttu-id="620eb-107">podczas Wskaźnik do danych przesłany do metody [IClrProfiling:: AttachProfiler —](iclrprofiling-attachprofiler-method.md) w jej `pvClientData` parametrze.</span><span class="sxs-lookup"><span data-stu-id="620eb-107">[in] A pointer to the data passed to the [IClrProfiling::AttachProfiler](iclrprofiling-attachprofiler-method.md) method in its `pvClientData` parameter.</span></span> <span data-ttu-id="620eb-108">Jeśli ten parametr ma wartość null, `cbClientData` będzie miał wartość 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="620eb-108">If this parameter is null, `cbClientData` will be 0 (zero).</span></span> <span data-ttu-id="620eb-109">Środowisko CLR zwalnia tę pamięć po powrocie z programu `InitializeForAttach` .</span><span class="sxs-lookup"><span data-stu-id="620eb-109">The CLR frees this memory when it returns from `InitializeForAttach`.</span></span>  
  
 `cbClientData`  
 <span data-ttu-id="620eb-110">podczas Rozmiar, w bajtach, danych, które `pvClientData` wskazują.</span><span class="sxs-lookup"><span data-stu-id="620eb-110">[in] The size, in bytes, of the data that `pvClientData` points to.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="620eb-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="620eb-111">Remarks</span></span>  

 <span data-ttu-id="620eb-112">Środowisko CLR wywołuje, `InitializeForAttach` aby dać profilerowi możliwość żądania wywołania zwrotnego.</span><span class="sxs-lookup"><span data-stu-id="620eb-112">The CLR calls `InitializeForAttach` to give the profiler an opportunity to request callbacks.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="620eb-113">Wymagania</span><span class="sxs-lookup"><span data-stu-id="620eb-113">Requirements</span></span>  

 <span data-ttu-id="620eb-114">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="620eb-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="620eb-115">**Nagłówek:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="620eb-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="620eb-116">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="620eb-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="620eb-117">**.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="620eb-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="620eb-118">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="620eb-118">See also</span></span>

- [<span data-ttu-id="620eb-119">ICorProfilerCallback — Interfejs</span><span class="sxs-lookup"><span data-stu-id="620eb-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="620eb-120">ICorProfilerInfo3 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="620eb-120">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="620eb-121">Interfejsy profilowania</span><span class="sxs-lookup"><span data-stu-id="620eb-121">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="620eb-122">Profilowanie</span><span class="sxs-lookup"><span data-stu-id="620eb-122">Profiling</span></span>](index.md)
