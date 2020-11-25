---
title: ICorProfilerCallback::ModuleAttachedToAssembly — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleAttachedToAssembly
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleAttachedToAssembly
helpviewer_keywords:
- ICorProfilerCallback::ModuleAttachedToAssembly method [.NET Framework profiling]
- ModuleAttachedToAssembly method [.NET Framework profiling]
ms.assetid: b595798a-5d40-4cac-ab4f-911c61d2c5d2
topic_type:
- apiref
ms.openlocfilehash: bcf5c5c9044a30fc8259dbc54bad8f3141f0f926
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733116"
---
# <a name="icorprofilercallbackmoduleattachedtoassembly-method"></a><span data-ttu-id="d11c9-102">ICorProfilerCallback::ModuleAttachedToAssembly — Metoda</span><span class="sxs-lookup"><span data-stu-id="d11c9-102">ICorProfilerCallback::ModuleAttachedToAssembly Method</span></span>

<span data-ttu-id="d11c9-103">Powiadamia program profilujący, że moduł jest dołączony do jego zestawu nadrzędnego.</span><span class="sxs-lookup"><span data-stu-id="d11c9-103">Notifies the profiler that a module is being attached to its parent assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d11c9-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="d11c9-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleAttachedToAssembly(  
    [in] ModuleID   moduleId,  
    [in] AssemblyID AssemblyId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d11c9-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="d11c9-105">Parameters</span></span>  

 `moduleId`  
 <span data-ttu-id="d11c9-106">podczas Identyfikator dołączanego modułu.</span><span class="sxs-lookup"><span data-stu-id="d11c9-106">[in] The ID of the module that is being attached.</span></span>  
  
 `AssemblyId`  
 <span data-ttu-id="d11c9-107">podczas Identyfikator zestawu nadrzędnego, do którego jest dołączony moduł.</span><span class="sxs-lookup"><span data-stu-id="d11c9-107">[in] The ID of the parent assembly to which the module is attached.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d11c9-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="d11c9-108">Remarks</span></span>  

 <span data-ttu-id="d11c9-109">Moduł może zostać załadowany za pomocą tabeli adresów importu (IAT), przez wywołanie do `LoadLibrary` lub przez odwołanie do metadanych.</span><span class="sxs-lookup"><span data-stu-id="d11c9-109">A module can be loaded through an import address table (IAT), through a call to `LoadLibrary`, or through a metadata reference.</span></span> <span data-ttu-id="d11c9-110">W związku z tym moduł ładujący środowisko uruchomieniowe języka wspólnego (CLR) ma wiele ścieżek kodu do określenia zestawu, w którym przebywa moduł.</span><span class="sxs-lookup"><span data-stu-id="d11c9-110">As a result, the common language runtime (CLR) loader has multiple code paths for determining the assembly in which a module lives.</span></span> <span data-ttu-id="d11c9-111">W związku z tym jest możliwe, że po wywołaniu [ICorProfilerCallback:: ModuleLoadFinished —](icorprofilercallback-moduleloadfinished-method.md) moduł nie wie, w jakim zestawie znajduje się i nie jest możliwe uzyskanie identyfikatora zestawu nadrzędnego.</span><span class="sxs-lookup"><span data-stu-id="d11c9-111">Therefore, it is possible that after [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) is called, the module does not know what assembly it is in and getting the parent assembly ID is not possible.</span></span> <span data-ttu-id="d11c9-112">`ModuleAttachedToAssembly`Metoda jest wywoływana, gdy moduł jest dołączony do jego zestawu nadrzędnego i można uzyskać jego identyfikator zestawu nadrzędnego.</span><span class="sxs-lookup"><span data-stu-id="d11c9-112">The `ModuleAttachedToAssembly` method is called when the module is attached to its parent assembly and its parent assembly ID can be obtained.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d11c9-113">Wymagania</span><span class="sxs-lookup"><span data-stu-id="d11c9-113">Requirements</span></span>  

 <span data-ttu-id="d11c9-114">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d11c9-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d11c9-115">**Nagłówek:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="d11c9-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d11c9-116">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="d11c9-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d11c9-117">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d11c9-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d11c9-118">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="d11c9-118">See also</span></span>

- [<span data-ttu-id="d11c9-119">ICorProfilerCallback — Interfejs</span><span class="sxs-lookup"><span data-stu-id="d11c9-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
