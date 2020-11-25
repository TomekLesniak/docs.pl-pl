---
title: ICorDebugManagedCallback::UnloadAssembly — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.UnloadAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UnloadAssembly
helpviewer_keywords:
- ICorDebugManagedCallback::UnloadAssembly method [.NET Framework debugging]
- UnloadAssembly method [.NET Framework debugging]
ms.assetid: 6734321c-c8a9-401f-a558-cad715ec4a77
topic_type:
- apiref
ms.openlocfilehash: e89b425afb63de8ef496fe545873ce33e5ff828c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724016"
---
# <a name="icordebugmanagedcallbackunloadassembly-method"></a><span data-ttu-id="64e57-102">ICorDebugManagedCallback::UnloadAssembly — Metoda</span><span class="sxs-lookup"><span data-stu-id="64e57-102">ICorDebugManagedCallback::UnloadAssembly Method</span></span>

<span data-ttu-id="64e57-103">Powiadamia debuger, że zestaw środowiska uruchomieniowego języka wspólnego został zwolniony.</span><span class="sxs-lookup"><span data-stu-id="64e57-103">Notifies the debugger that a common language runtime assembly has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64e57-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="64e57-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadAssembly (  
    [in] IcorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugAssembly   *pAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="64e57-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="64e57-105">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="64e57-106">podczas Wskaźnik do obiektu ICorDebugAppDomain, który reprezentuje domenę aplikacji, która zawiera zestaw.</span><span class="sxs-lookup"><span data-stu-id="64e57-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contained the assembly.</span></span>  
  
 `pAssembly`  
 <span data-ttu-id="64e57-107">podczas Wskaźnik do obiektu ICorDebugAssembly, który reprezentuje zestaw.</span><span class="sxs-lookup"><span data-stu-id="64e57-107">[in] A pointer to an ICorDebugAssembly object that represents the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="64e57-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="64e57-108">Remarks</span></span>  

 <span data-ttu-id="64e57-109">Zestawu nie należy używać po tym wywołaniu zwrotnym.</span><span class="sxs-lookup"><span data-stu-id="64e57-109">The assembly should not be used after this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64e57-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="64e57-110">Requirements</span></span>  

 <span data-ttu-id="64e57-111">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="64e57-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64e57-112">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="64e57-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="64e57-113">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="64e57-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="64e57-114">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64e57-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64e57-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="64e57-115">See also</span></span>

- [<span data-ttu-id="64e57-116">LoadAssembly, metoda</span><span class="sxs-lookup"><span data-stu-id="64e57-116">LoadAssembly Method</span></span>](icordebugmanagedcallback-loadassembly-method.md)
- [<span data-ttu-id="64e57-117">ICorDebugManagedCallback — Interfejs</span><span class="sxs-lookup"><span data-stu-id="64e57-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
