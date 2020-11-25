---
title: ICorProfilerThreadEnum::GetCount — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerThreadEnum.GetCount
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerThreadEnum::GetCount
helpviewer_keywords:
- ICorProfilerThreadEnum::GetCount method [.NET Framework profiling]
- GetCount method, ICorProfilerThreadEnum interface [.NET Framework profiling]
ms.assetid: d6dbdc4a-6115-455d-a3f3-704a81d3646b
topic_type:
- apiref
ms.openlocfilehash: a35f2e69515ea520396641effc05371b54ad8afc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702332"
---
# <a name="icorprofilerthreadenumgetcount-method"></a><span data-ttu-id="58abc-102">ICorProfilerThreadEnum::GetCount — Metoda</span><span class="sxs-lookup"><span data-stu-id="58abc-102">ICorProfilerThreadEnum::GetCount Method</span></span>

<span data-ttu-id="58abc-103">Pobiera liczbę wątków, które są używane przez aplikację.</span><span class="sxs-lookup"><span data-stu-id="58abc-103">Gets the number of threads that are used by the application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58abc-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="58abc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount (    [out] ULONG * pcelt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="58abc-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="58abc-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="58abc-106">określoną Liczba wątków używanych przez aplikację.</span><span class="sxs-lookup"><span data-stu-id="58abc-106">[out] The number of threads used by the application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58abc-107">Wymagania</span><span class="sxs-lookup"><span data-stu-id="58abc-107">Requirements</span></span>  

 <span data-ttu-id="58abc-108">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58abc-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58abc-109">**Nagłówek:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="58abc-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="58abc-110">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="58abc-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="58abc-111">**.NET Framework wersje:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58abc-111">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58abc-112">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="58abc-112">See also</span></span>

- [<span data-ttu-id="58abc-113">ICorProfilerThreadEnum — Interfejs</span><span class="sxs-lookup"><span data-stu-id="58abc-113">ICorProfilerThreadEnum Interface</span></span>](icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="58abc-114">Interfejsy profilowania</span><span class="sxs-lookup"><span data-stu-id="58abc-114">Profiling Interfaces</span></span>](profiling-interfaces.md)
