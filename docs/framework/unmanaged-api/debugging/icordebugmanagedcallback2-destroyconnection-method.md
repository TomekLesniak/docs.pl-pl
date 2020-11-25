---
title: ICorDebugManagedCallback2::DestroyConnection — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.DestroyConnection
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::DestroyConnection
helpviewer_keywords:
- DestroyConnection method [.NET Framework debugging]
- ICorDebugManagedCallback2::DestroyConnection method [.NET Framework debugging]
ms.assetid: cf7940e9-4558-4319-925c-09f6c98c8fcd
topic_type:
- apiref
ms.openlocfilehash: d725cbe89e0631630affb6b0540a7d5f57ab6b89
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720116"
---
# <a name="icordebugmanagedcallback2destroyconnection-method"></a><span data-ttu-id="e84d2-102">ICorDebugManagedCallback2::DestroyConnection — Metoda</span><span class="sxs-lookup"><span data-stu-id="e84d2-102">ICorDebugManagedCallback2::DestroyConnection Method</span></span>

<span data-ttu-id="e84d2-103">Powiadamia debuger o przerwaniu określonego połączenia.</span><span class="sxs-lookup"><span data-stu-id="e84d2-103">Notifies the debugger that the specified connection has been terminated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e84d2-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="e84d2-104">Syntax</span></span>  
  
```cpp  
HRESULT DestroyConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e84d2-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="e84d2-105">Parameters</span></span>  

 `pProcess`  
 <span data-ttu-id="e84d2-106">podczas Wskaźnik do obiektu ICorDebugProcess, który reprezentuje proces zawierający zniszczone połączenie.</span><span class="sxs-lookup"><span data-stu-id="e84d2-106">[in] A pointer to an ICorDebugProcess object that represents the process containing the connection that was destroyed.</span></span>  
  
 `dwConnectionId`  
 <span data-ttu-id="e84d2-107">podczas Identyfikator zerwanego połączenia.</span><span class="sxs-lookup"><span data-stu-id="e84d2-107">[in] The ID of the connection that was destroyed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e84d2-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="e84d2-108">Remarks</span></span>  

 <span data-ttu-id="e84d2-109">`DestroyConnection`Wywołanie zwrotne zostanie wyzwolone, gdy host wywoła [ICLRDebugManager:: EndConnection —](../hosting/iclrdebugmanager-endconnection-method.md) w [interfejsie API hostingu](../hosting/index.md).</span><span class="sxs-lookup"><span data-stu-id="e84d2-109">A `DestroyConnection` callback will be fired when a host calls [ICLRDebugManager::EndConnection](../hosting/iclrdebugmanager-endconnection-method.md) in the [Hosting API](../hosting/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e84d2-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="e84d2-110">Requirements</span></span>  

 <span data-ttu-id="e84d2-111">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e84d2-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e84d2-112">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="e84d2-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e84d2-113">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="e84d2-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e84d2-114">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e84d2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e84d2-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="e84d2-115">See also</span></span>

- [<span data-ttu-id="e84d2-116">ICorDebugManagedCallback2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="e84d2-116">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="e84d2-117">ICorDebugManagedCallback — Interfejs</span><span class="sxs-lookup"><span data-stu-id="e84d2-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
