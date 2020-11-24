---
title: ICorDebugManagedCallback::ExitAppDomain — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.ExitAppDomain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::ExitAppDomain
helpviewer_keywords:
- ICorDebugManagedCallback::ExitAppDomain method [.NET Framework debugging]
- ExitAppDomain method [.NET Framework debugging]
ms.assetid: d815486e-b3bd-4fe8-ba28-02abdb4d67ba
topic_type:
- apiref
ms.openlocfilehash: 51beed47e7187d6fa22e60baed16598a8ad73adb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688994"
---
# <a name="icordebugmanagedcallbackexitappdomain-method"></a><span data-ttu-id="5ab4b-102">ICorDebugManagedCallback::ExitAppDomain — Metoda</span><span class="sxs-lookup"><span data-stu-id="5ab4b-102">ICorDebugManagedCallback::ExitAppDomain Method</span></span>

<span data-ttu-id="5ab4b-103">Powiadamia debuger o zakończeniu domeny aplikacji.</span><span class="sxs-lookup"><span data-stu-id="5ab4b-103">Notifies the debugger that an application domain has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ab4b-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="5ab4b-104">Syntax</span></span>  
  
```cpp  
HRESULT ExitAppDomain (  
    [in] ICorDebugProcess   *pProcess,  
    [in] ICorDebugAppDomain *pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5ab4b-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="5ab4b-105">Parameters</span></span>  

 `pProcess`  
 <span data-ttu-id="5ab4b-106">podczas Wskaźnik do obiektu ICorDebugProcess, który reprezentuje proces, który zawiera daną domenę aplikacji.</span><span class="sxs-lookup"><span data-stu-id="5ab4b-106">[in] A pointer to an ICorDebugProcess object that represents the process that contains the given application domain.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="5ab4b-107">podczas Wskaźnik do obiektu ICorDebugAppDomain, który reprezentuje domenę aplikacji, która została zakończona.</span><span class="sxs-lookup"><span data-stu-id="5ab4b-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that has exited.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ab4b-108">Wymagania</span><span class="sxs-lookup"><span data-stu-id="5ab4b-108">Requirements</span></span>  

 <span data-ttu-id="5ab4b-109">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ab4b-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ab4b-110">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="5ab4b-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5ab4b-111">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="5ab4b-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5ab4b-112">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ab4b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ab4b-113">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="5ab4b-113">See also</span></span>

- [<span data-ttu-id="5ab4b-114">ICorDebugManagedCallback — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5ab4b-114">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
