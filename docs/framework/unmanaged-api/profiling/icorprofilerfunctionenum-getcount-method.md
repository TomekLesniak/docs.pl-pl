---
title: ICorProfilerFunctionEnum::GetCount — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionEnum.GetCount Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionEnum::GetCount
helpviewer_keywords:
- ICorProfilerFunctionEnum::GetCount method [.NET Framework profiling]
- GetCount method, ICorProfilerFunctionEnum interface [.NET Framework profiling]
ms.assetid: 62ec65e3-3e9d-400b-ae61-d24b8963995b
topic_type:
- apiref
ms.openlocfilehash: 3ccf75523eb9362b8ef5c38d224a419502cb8b92
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724149"
---
# <a name="icorprofilerfunctionenumgetcount-method"></a><span data-ttu-id="108d1-102">ICorProfilerFunctionEnum::GetCount — Metoda</span><span class="sxs-lookup"><span data-stu-id="108d1-102">ICorProfilerFunctionEnum::GetCount Method</span></span>

<span data-ttu-id="108d1-103">Pobiera liczbę funkcji, które zostały załadowane przez aplikację lub wymuszanie załadowane przez profiler.</span><span class="sxs-lookup"><span data-stu-id="108d1-103">Gets the number of functions that were loaded by the application or forcibly loaded by the profiler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="108d1-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="108d1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount([out] ULONG * pcelt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="108d1-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="108d1-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="108d1-106">określoną Liczba załadowanych funkcji.</span><span class="sxs-lookup"><span data-stu-id="108d1-106">[out] The number of functions that were loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="108d1-107">Wymagania</span><span class="sxs-lookup"><span data-stu-id="108d1-107">Requirements</span></span>  

 <span data-ttu-id="108d1-108">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="108d1-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="108d1-109">**Nagłówek:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="108d1-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="108d1-110">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="108d1-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="108d1-111">**.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="108d1-111">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="108d1-112">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="108d1-112">See also</span></span>

- [<span data-ttu-id="108d1-113">ICorProfilerFunctionEnum — Interfejs</span><span class="sxs-lookup"><span data-stu-id="108d1-113">ICorProfilerFunctionEnum Interface</span></span>](icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="108d1-114">Interfejsy profilowania</span><span class="sxs-lookup"><span data-stu-id="108d1-114">Profiling Interfaces</span></span>](profiling-interfaces.md)
