---
title: ICorDebugManagedCallback::UnloadModule — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.UnloadModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UnloadModule
helpviewer_keywords:
- ICorDebugManagedCallback::UnloadModule method [.NET Framework debugging]
- UnloadModule method [.NET Framework debugging]
ms.assetid: b12bfcd9-1e29-48bf-9a3d-44bfae5df5e8
topic_type:
- apiref
ms.openlocfilehash: f24d49189ee81a80397b94ee4113c9514c083dbc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723990"
---
# <a name="icordebugmanagedcallbackunloadmodule-method"></a><span data-ttu-id="b82a5-102">ICorDebugManagedCallback::UnloadModule — Metoda</span><span class="sxs-lookup"><span data-stu-id="b82a5-102">ICorDebugManagedCallback::UnloadModule Method</span></span>

<span data-ttu-id="b82a5-103">Powiadamia debuger, że moduł środowiska uruchomieniowego języka wspólnego (DLL) został zwolniony.</span><span class="sxs-lookup"><span data-stu-id="b82a5-103">Notifies the debugger that a common language runtime module (DLL) has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b82a5-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="b82a5-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadModule (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugModule     *pModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b82a5-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="b82a5-105">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="b82a5-106">podczas Wskaźnik do obiektu ICorDebugAppDomain, który reprezentuje domenę aplikacji, która zawiera moduł.</span><span class="sxs-lookup"><span data-stu-id="b82a5-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contained the module.</span></span>  
  
 `pModule`  
 <span data-ttu-id="b82a5-107">podczas Wskaźnik do obiektu ICorDebugModule, który reprezentuje moduł.</span><span class="sxs-lookup"><span data-stu-id="b82a5-107">[in] A pointer to an ICorDebugModule object that represents the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b82a5-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="b82a5-108">Remarks</span></span>  

 <span data-ttu-id="b82a5-109">Modułu nie należy używać po tym wywołaniu.</span><span class="sxs-lookup"><span data-stu-id="b82a5-109">The module should not be used after this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b82a5-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="b82a5-110">Requirements</span></span>  

 <span data-ttu-id="b82a5-111">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b82a5-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b82a5-112">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="b82a5-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b82a5-113">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="b82a5-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b82a5-114">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b82a5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b82a5-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="b82a5-115">See also</span></span>

- [<span data-ttu-id="b82a5-116">LoadModule, metoda</span><span class="sxs-lookup"><span data-stu-id="b82a5-116">LoadModule Method</span></span>](icordebugmanagedcallback-loadmodule-method.md)
- [<span data-ttu-id="b82a5-117">ICorDebugManagedCallback — Interfejs</span><span class="sxs-lookup"><span data-stu-id="b82a5-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
