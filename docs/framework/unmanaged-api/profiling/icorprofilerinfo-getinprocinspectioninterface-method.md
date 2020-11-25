---
title: ICorProfilerInfo::GetInprocInspectionInterface — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetInprocInspectionInterface
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetInprocInspectionInterface
helpviewer_keywords:
- GetInprocInspectionInterface method [.NET Framework profiling]
- ICorProfilerInfo::GetInprocInspectionInterface method [.NET Framework profiling]
ms.assetid: 22a92d1d-8849-4af6-8304-ecc53dd1d289
topic_type:
- apiref
ms.openlocfilehash: cc8bdfb1e46e5304227a40f869856f07e1f90bed
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707493"
---
# <a name="icorprofilerinfogetinprocinspectioninterface-method"></a><span data-ttu-id="2b842-102">ICorProfilerInfo::GetInprocInspectionInterface — Metoda</span><span class="sxs-lookup"><span data-stu-id="2b842-102">ICorProfilerInfo::GetInprocInspectionInterface Method</span></span>

<span data-ttu-id="2b842-103">Pobiera obiekt, który może być badany dla interfejsu "ICorDebugProcess".</span><span class="sxs-lookup"><span data-stu-id="2b842-103">Gets an object that can be queried for an "ICorDebugProcess" interface.</span></span> <span data-ttu-id="2b842-104">Ta metoda jest przestarzała w .NET Framework w wersji 2,0.</span><span class="sxs-lookup"><span data-stu-id="2b842-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b842-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="2b842-105">Syntax</span></span>  
  
```cpp  
HRESULT GetInprocInspectionInterface(  
    [out] IUnknown **ppicd);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2b842-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="2b842-106">Parameters</span></span>  

 `ppicd`  
 <span data-ttu-id="2b842-107">Obiekt [out](/cpp/atl/iunknown) , który może być badany dla `ICorDebugProcess` interfejsu.</span><span class="sxs-lookup"><span data-stu-id="2b842-107">[out](/cpp/atl/iunknown) object that can be queried for an `ICorDebugProcess` interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2b842-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="2b842-108">Remarks</span></span>  

 <span data-ttu-id="2b842-109">Interfejs API debugowania środowiska uruchomieniowego języka wspólnego (CLR) obsługuje ograniczone debugowanie w procesie w .NET Framework w wersji 1,0.</span><span class="sxs-lookup"><span data-stu-id="2b842-109">The common language runtime (CLR) debugging API supported limited in-process debugging in the .NET Framework version 1.0.</span></span> <span data-ttu-id="2b842-110">Debugowanie w procesie umożliwia profilerowi użycie części inspekcji interfejsu API debugowania.</span><span class="sxs-lookup"><span data-stu-id="2b842-110">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="2b842-111">W wyniku opinii klientów, debugowanie w procesie zostało usunięte z .NET Framework w wersji 2,0 i zastąpione zestawem funkcji, który jest bardziej aktualny z profilem API profilowania.</span><span class="sxs-lookup"><span data-stu-id="2b842-111">As a result of customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b842-112">Wymagania</span><span class="sxs-lookup"><span data-stu-id="2b842-112">Requirements</span></span>  

 <span data-ttu-id="2b842-113">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2b842-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b842-114">**Nagłówek:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="2b842-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2b842-115">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="2b842-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2b842-116">**Wersja .NET Framework:** 1,0</span><span class="sxs-lookup"><span data-stu-id="2b842-116">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b842-117">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="2b842-117">See also</span></span>

- [<span data-ttu-id="2b842-118">ICorProfilerInfo — Interfejs</span><span class="sxs-lookup"><span data-stu-id="2b842-118">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
