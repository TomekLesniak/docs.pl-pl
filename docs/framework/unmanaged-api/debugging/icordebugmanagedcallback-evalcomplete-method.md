---
title: ICorDebugManagedCallback::EvalComplete — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.EvalComplete
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::EvalComplete
helpviewer_keywords:
- ICorDebugManagedCallback::EvalComplete method [.NET Framework debugging]
- EvalComplete method [.NET Framework debugging]
ms.assetid: f74ab4eb-cd1b-407c-a66d-8ec0d85647f3
topic_type:
- apiref
ms.openlocfilehash: e95874447528989af68f5c97825691532195889f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731803"
---
# <a name="icordebugmanagedcallbackevalcomplete-method"></a><span data-ttu-id="e8f33-102">ICorDebugManagedCallback::EvalComplete — Metoda</span><span class="sxs-lookup"><span data-stu-id="e8f33-102">ICorDebugManagedCallback::EvalComplete Method</span></span>

<span data-ttu-id="e8f33-103">Powiadamia debuger o ukończeniu oceny.</span><span class="sxs-lookup"><span data-stu-id="e8f33-103">Notifies the debugger that an evaluation has been completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8f33-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="e8f33-104">Syntax</span></span>  
  
```cpp  
HRESULT EvalComplete (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] ICorDebugEval      *pEval  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e8f33-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="e8f33-105">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="e8f33-106">podczas Wskaźnik do obiektu ICorDebugAppDomain, który reprezentuje domenę aplikacji, w której wykonano ocenę.</span><span class="sxs-lookup"><span data-stu-id="e8f33-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the evaluation was performed.</span></span>  
  
 `pThread`  
 <span data-ttu-id="e8f33-107">podczas Wskaźnik do obiektu ICorDebugThread, który reprezentuje wątek, w którym wykonano ocenę.</span><span class="sxs-lookup"><span data-stu-id="e8f33-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the evaluation was performed.</span></span>  
  
 `pEval`  
 <span data-ttu-id="e8f33-108">podczas Wskaźnik do obiektu ICorDebugEval, który reprezentuje kod, który przeprowadził ocenę.</span><span class="sxs-lookup"><span data-stu-id="e8f33-108">[in] A pointer to an ICorDebugEval object that represents the code that performed the evaluation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8f33-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="e8f33-109">Requirements</span></span>  

 <span data-ttu-id="e8f33-110">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8f33-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8f33-111">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="e8f33-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e8f33-112">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="e8f33-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e8f33-113">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8f33-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8f33-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="e8f33-114">See also</span></span>

- [<span data-ttu-id="e8f33-115">ICorDebugManagedCallback — Interfejs</span><span class="sxs-lookup"><span data-stu-id="e8f33-115">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
