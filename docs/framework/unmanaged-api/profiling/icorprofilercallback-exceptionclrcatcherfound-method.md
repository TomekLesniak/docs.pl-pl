---
title: ICorProfilerCallback::ExceptionCLRCatcherFound — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionCLRCatcherFound
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionCLRCatcherFound
helpviewer_keywords:
- ICorProfilerCallback::ExceptionCLRCatcherFound method [.NET Framework profiling]
- ExceptionCLRCatcherFound method [.NET Framework profiling]
ms.assetid: 73fe8b4b-8f9a-4ba5-a10c-b26521396a66
topic_type:
- apiref
ms.openlocfilehash: 894084978f976bcee71138d35534a80b5f9cda5f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699979"
---
# <a name="icorprofilercallbackexceptionclrcatcherfound-method"></a><span data-ttu-id="1634e-102">ICorProfilerCallback::ExceptionCLRCatcherFound — Metoda</span><span class="sxs-lookup"><span data-stu-id="1634e-102">ICorProfilerCallback::ExceptionCLRCatcherFound Method</span></span>

<span data-ttu-id="1634e-103">Wywołuje się, gdy `catch` znaleziono blok wyjątku wewnątrz samego środowiska uruchomieniowego języka wspólnego (CLR).</span><span class="sxs-lookup"><span data-stu-id="1634e-103">Called when a `catch` block for an exception is found inside the common language runtime (CLR) itself.</span></span> <span data-ttu-id="1634e-104">Ta metoda jest przestarzała w .NET Framework w wersji 2,0.</span><span class="sxs-lookup"><span data-stu-id="1634e-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1634e-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="1634e-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionCLRCatcherFound();  
```  
  
## <a name="requirements"></a><span data-ttu-id="1634e-106">Wymagania</span><span class="sxs-lookup"><span data-stu-id="1634e-106">Requirements</span></span>  

 <span data-ttu-id="1634e-107">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1634e-107">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1634e-108">**Nagłówek:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="1634e-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1634e-109">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="1634e-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1634e-110">**Wersja .NET Framework:** 1,0</span><span class="sxs-lookup"><span data-stu-id="1634e-110">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1634e-111">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="1634e-111">See also</span></span>

- [<span data-ttu-id="1634e-112">ICorProfilerCallback — Interfejs</span><span class="sxs-lookup"><span data-stu-id="1634e-112">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="1634e-113">ExceptionCLRCatcherExecute, metoda</span><span class="sxs-lookup"><span data-stu-id="1634e-113">ExceptionCLRCatcherExecute Method</span></span>](icorprofilercallback-exceptionclrcatcherexecute-method.md)
