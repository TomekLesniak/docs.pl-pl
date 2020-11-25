---
title: ICorDebugManagedCallback::EditAndContinueRemap — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.EditAndContinueRemap
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::EditAndContinueRemap
helpviewer_keywords:
- EditAndContinueRemap method [.NET Framework debugging]
- ICorDebugManagedCallback::EditAndContinueRemap method [.NET Framework debugging]
ms.assetid: 24a8fcce-317e-48ff-aefc-d86123ada935
topic_type:
- apiref
ms.openlocfilehash: 1d8aa2cca9dbbeaa9e03813b177ca59125770803
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721286"
---
# <a name="icordebugmanagedcallbackeditandcontinueremap-method"></a><span data-ttu-id="a492a-102">ICorDebugManagedCallback::EditAndContinueRemap — Metoda</span><span class="sxs-lookup"><span data-stu-id="a492a-102">ICorDebugManagedCallback::EditAndContinueRemap Method</span></span>

<span data-ttu-id="a492a-103">Ta metoda jest przestarzała.</span><span class="sxs-lookup"><span data-stu-id="a492a-103">This method has been deprecated.</span></span> <span data-ttu-id="a492a-104">Powiadamia on debuger o wysłaniu zdarzenia ponownego mapowania do zintegrowanego środowiska programistycznego (IDE).</span><span class="sxs-lookup"><span data-stu-id="a492a-104">It notifies the debugger that a remap event has been sent to the integrated development environment (IDE).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a492a-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="a492a-105">Syntax</span></span>  
  
```cpp  
HRESULT EditAndContinueRemap (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread *pThread,  
    [in] ICorDebugFunction *pFunction,  
    [in] BOOL fAccurate  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="a492a-106">Uwagi</span><span class="sxs-lookup"><span data-stu-id="a492a-106">Remarks</span></span>  

 <span data-ttu-id="a492a-107">`EditAndContinueRemap`Metoda jest wywoływana, gdy podjęto próbę wykonania kodu w starej wersji zaktualizowanej funkcji.</span><span class="sxs-lookup"><span data-stu-id="a492a-107">The `EditAndContinueRemap` method is called when the execution of the code in an old version of an updated function has been attempted.</span></span> <span data-ttu-id="a492a-108">Środowisko uruchomieniowe języka wspólnego wywołuje `EditAndContinueRemap` metodę wysyłania zdarzenia ponownego mapowania do środowiska IDE.</span><span class="sxs-lookup"><span data-stu-id="a492a-108">The common language runtime calls the `EditAndContinueRemap` method to send a remap event to the IDE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a492a-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="a492a-109">Requirements</span></span>  

 <span data-ttu-id="a492a-110">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a492a-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a492a-111">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="a492a-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a492a-112">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="a492a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a492a-113">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a492a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a492a-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="a492a-114">See also</span></span>

- [<span data-ttu-id="a492a-115">ICorDebugManagedCallback — Interfejs</span><span class="sxs-lookup"><span data-stu-id="a492a-115">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
