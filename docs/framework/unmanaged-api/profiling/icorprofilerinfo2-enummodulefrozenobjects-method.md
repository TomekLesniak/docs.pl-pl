---
title: ICorProfilerInfo2::EnumModuleFrozenObjects — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.EnumModuleFrozenObjects
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::EnumModuleFrozenObjects
helpviewer_keywords:
- EnumModuleFrozenObjects method [.NET Framework profiling]
- ICorProfilerInfo2::EnumModuleFrozenObjects method [.NET Framework profiling]
ms.assetid: 920b6483-7064-4d64-8613-fcc38ccf9b1e
topic_type:
- apiref
ms.openlocfilehash: fe4f3a7355339c9b5adbe5de062f0a5688d81c23
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727188"
---
# <a name="icorprofilerinfo2enummodulefrozenobjects-method"></a><span data-ttu-id="65924-102">ICorProfilerInfo2::EnumModuleFrozenObjects — Metoda</span><span class="sxs-lookup"><span data-stu-id="65924-102">ICorProfilerInfo2::EnumModuleFrozenObjects Method</span></span>

<span data-ttu-id="65924-103">Pobiera moduł wyliczający, który umożliwia iterację w odniesieniu do zablokowanych obiektów w określonym module. Ta metoda jest przestarzała.</span><span class="sxs-lookup"><span data-stu-id="65924-103">Gets an enumerator that allows iteration over the frozen objects in the specified module.This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65924-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="65924-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumModuleFrozenObjects(  
    [in] ModuleID moduleID,  
    [out] ICorProfilerObjectEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="65924-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="65924-105">Parameters</span></span>  

 `moduleID`  
 <span data-ttu-id="65924-106">podczas Identyfikator modułu zawierającego zamrożone obiekty, które mają zostać wyliczone.</span><span class="sxs-lookup"><span data-stu-id="65924-106">[in] The ID of the module that contains the frozen objects to be enumerated.</span></span>  
  
 `ppEnum`  
 <span data-ttu-id="65924-107">określoną Wskaźnik do adresu interfejsu [ICorProfilerObjectEnum](icorprofilerobjectenum-interface.md) , który wylicza zamrożone obiekty.</span><span class="sxs-lookup"><span data-stu-id="65924-107">[out] A pointer to the address of an [ICorProfilerObjectEnum](icorprofilerobjectenum-interface.md) interface, which enumerates the frozen objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65924-108">Wymagania</span><span class="sxs-lookup"><span data-stu-id="65924-108">Requirements</span></span>  

 <span data-ttu-id="65924-109">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="65924-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65924-110">**Nagłówek:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="65924-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="65924-111">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="65924-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="65924-112">**.NET Framework wersje:** 3,5, 3,0 sp1, 3,0, 2,0 SP1, 2,0</span><span class="sxs-lookup"><span data-stu-id="65924-112">**.NET Framework Versions:** 3.5, 3.0 SP1, 3.0, 2.0 SP1, 2.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65924-113">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="65924-113">See also</span></span>

- [<span data-ttu-id="65924-114">ICorProfilerInfo — Interfejs</span><span class="sxs-lookup"><span data-stu-id="65924-114">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="65924-115">ICorProfilerInfo2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="65924-115">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
