---
title: ICorProfilerThreadEnum::Clone — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerThreadEnum.Clone
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerThreadEnum::Clone
helpviewer_keywords:
- Clone method, ICorProfilerThreadEnum interface [.NET Framework profiling]
- ICorProfilerThreadEnum::Clone method [.NET Framework profiling]
ms.assetid: 5a278bc9-88e2-4c69-b035-9d550dd77081
topic_type:
- apiref
ms.openlocfilehash: de2584b56701f4cffb6a108a5872641ec40e5762
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702527"
---
# <a name="icorprofilerthreadenumclone-method"></a><span data-ttu-id="d4f4c-102">ICorProfilerThreadEnum::Clone — Metoda</span><span class="sxs-lookup"><span data-stu-id="d4f4c-102">ICorProfilerThreadEnum::Clone Method</span></span>

<span data-ttu-id="d4f4c-103">Pobiera wskaźnik interfejsu do kopii tego interfejsu [ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="d4f4c-103">Gets an interface pointer to a copy of this [ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4f4c-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="d4f4c-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone (    [out] ICorProfilerThreadEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d4f4c-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="d4f4c-105">Parameters</span></span>  

 `ppEnum`  
 <span data-ttu-id="d4f4c-106">określoną Wskaźnik do wskaźnika interfejsu, który z kolei wskazuje na kopię tego interfejsu [ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="d4f4c-106">[out] A pointer to the interface pointer, which, in turn, points to the copy of this [ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md) interface.</span></span> <span data-ttu-id="d4f4c-107">Kopia modułu wyliczającego utrzymuje swój własny stan wyliczenia niezależnie od tego modułu wyliczającego.</span><span class="sxs-lookup"><span data-stu-id="d4f4c-107">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span></span> <span data-ttu-id="d4f4c-108">Jednak początkowa pozycja kursora kopii jest taka sama, jak bieżąca pozycja kursora modułu wyliczającego.</span><span class="sxs-lookup"><span data-stu-id="d4f4c-108">However, the initial cursor position of the copy is the same as this current cursor position of the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4f4c-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="d4f4c-109">Requirements</span></span>  

 <span data-ttu-id="d4f4c-110">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d4f4c-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4f4c-111">**Nagłówek:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="d4f4c-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d4f4c-112">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="d4f4c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d4f4c-113">**.NET Framework wersje:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4f4c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4f4c-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="d4f4c-114">See also</span></span>

- [<span data-ttu-id="d4f4c-115">ICorProfilerThreadEnum</span><span class="sxs-lookup"><span data-stu-id="d4f4c-115">ICorProfilerThreadEnum</span></span>](icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="d4f4c-116">Interfejsy profilowania</span><span class="sxs-lookup"><span data-stu-id="d4f4c-116">Profiling Interfaces</span></span>](profiling-interfaces.md)
