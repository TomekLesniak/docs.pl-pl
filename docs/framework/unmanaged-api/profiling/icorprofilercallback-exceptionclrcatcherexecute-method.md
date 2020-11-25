---
title: ICorProfilerCallback::ExceptionCLRCatcherExecute — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionCLRCatcherExecute
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionCLRCatcherExecute
helpviewer_keywords:
- ExceptionCLRCatcherExecute method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionCLRCatcherExecute method [.NET Framework profiling]
ms.assetid: aaac8f98-5cf4-42c7-b04b-556cce367e36
topic_type:
- apiref
ms.openlocfilehash: 1a9e377ba98c0c2302e341149bd5acb46c24051a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699992"
---
# <a name="icorprofilercallbackexceptionclrcatcherexecute-method"></a><span data-ttu-id="f57f6-102">ICorProfilerCallback::ExceptionCLRCatcherExecute — Metoda</span><span class="sxs-lookup"><span data-stu-id="f57f6-102">ICorProfilerCallback::ExceptionCLRCatcherExecute Method</span></span>

<span data-ttu-id="f57f6-103">Wywołuje się, gdy `catch` blok dla wyjątku jest wykonywany wewnątrz samego środowiska uruchomieniowego języka wspólnego (CLR).</span><span class="sxs-lookup"><span data-stu-id="f57f6-103">Called when a `catch` block for an exception is executed inside the common language runtime (CLR) itself.</span></span> <span data-ttu-id="f57f6-104">Ta metoda jest przestarzała w .NET Framework w wersji 2,0.</span><span class="sxs-lookup"><span data-stu-id="f57f6-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f57f6-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="f57f6-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionCLRCatcherExecute();  
```  
  
## <a name="requirements"></a><span data-ttu-id="f57f6-106">Wymagania</span><span class="sxs-lookup"><span data-stu-id="f57f6-106">Requirements</span></span>  

 <span data-ttu-id="f57f6-107">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f57f6-107">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f57f6-108">**Nagłówek:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="f57f6-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f57f6-109">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="f57f6-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f57f6-110">**.NET Framework wersje:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="f57f6-110">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f57f6-111">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="f57f6-111">See also</span></span>

- [<span data-ttu-id="f57f6-112">ICorProfilerCallback — Interfejs</span><span class="sxs-lookup"><span data-stu-id="f57f6-112">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="f57f6-113">ExceptionCLRCatcherFound, metoda</span><span class="sxs-lookup"><span data-stu-id="f57f6-113">ExceptionCLRCatcherFound Method</span></span>](icorprofilercallback-exceptionclrcatcherfound-method.md)
