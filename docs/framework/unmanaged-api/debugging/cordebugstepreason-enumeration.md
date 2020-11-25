---
title: CorDebugStepReason — Wyliczenie
ms.date: 03/30/2017
api_name:
- CorDebugStepReason
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugStepReason
helpviewer_keywords:
- CorDebugStepReason enumeration [.NET Framework debugging]
ms.assetid: fe248069-b33c-48e1-a777-06ac9b239c54
topic_type:
- apiref
ms.openlocfilehash: 50903b3737c0fc63eda2b1190e4c3d961ce3ae7b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726044"
---
# <a name="cordebugstepreason-enumeration"></a><span data-ttu-id="de853-102">CorDebugStepReason — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="de853-102">CorDebugStepReason Enumeration</span></span>

<span data-ttu-id="de853-103">Wskazuje wynik pojedynczego kroku.</span><span class="sxs-lookup"><span data-stu-id="de853-103">Indicates the outcome of an individual step.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de853-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="de853-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugStepReason {  
    STEP_NORMAL,  
    STEP_RETURN,  
    STEP_CALL,  
    STEP_EXCEPTION_FILTER,  
    STEP_EXCEPTION_HANDLER,  
    STEP_INTERCEPT,  
    STEP_EXIT  
} CorDebugStepReason;  
```  
  
## <a name="members"></a><span data-ttu-id="de853-105">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="de853-105">Members</span></span>  
  
|<span data-ttu-id="de853-106">Członek</span><span class="sxs-lookup"><span data-stu-id="de853-106">Member</span></span>|<span data-ttu-id="de853-107">Opis</span><span class="sxs-lookup"><span data-stu-id="de853-107">Description</span></span>|  
|------------|-----------------|  
|`STEP_NORMAL`|<span data-ttu-id="de853-108">Przechodzenie do normalnego działania w ramach tej samej funkcji.</span><span class="sxs-lookup"><span data-stu-id="de853-108">Stepping completed normally, within the same function.</span></span>|  
|`STEP_RETURN`|<span data-ttu-id="de853-109">Dalsze dalsze przechodzenie po zwróceniu funkcji.</span><span class="sxs-lookup"><span data-stu-id="de853-109">Stepping continued normally, after the function returned.</span></span>|  
|`STEP_CALL`|<span data-ttu-id="de853-110">Dalsze przechodzenie dalej na początku nowo wywołanej funkcji.</span><span class="sxs-lookup"><span data-stu-id="de853-110">Stepping continued normally, at the beginning of a newly called function.</span></span>|  
|`STEP_EXCEPTION_FILTER`|<span data-ttu-id="de853-111">Wygenerowano wyjątek i kontrola została przeniesiona do filtru wyjątków.</span><span class="sxs-lookup"><span data-stu-id="de853-111">An exception was generated and control was passed to an exception filter.</span></span>|  
|`STEP_EXCEPTION_HANDLER`|<span data-ttu-id="de853-112">Wygenerowano wyjątek i kontrola została przeniesiona do procedury obsługi wyjątków.</span><span class="sxs-lookup"><span data-stu-id="de853-112">An exception was generated and control was passed to an exception handler.</span></span>|  
|`STEP_INTERCEPT`|<span data-ttu-id="de853-113">Kontrolka została przeniesiona do interceptora.</span><span class="sxs-lookup"><span data-stu-id="de853-113">Control was passed to an interceptor.</span></span>|  
|`STEP_EXIT`|<span data-ttu-id="de853-114">Wątek zakończył działanie przed ukończeniem kroku.</span><span class="sxs-lookup"><span data-stu-id="de853-114">The thread exited before the step was completed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="de853-115">Wymagania</span><span class="sxs-lookup"><span data-stu-id="de853-115">Requirements</span></span>  

 <span data-ttu-id="de853-116">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="de853-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de853-117">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="de853-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="de853-118">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="de853-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="de853-119">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de853-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de853-120">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="de853-120">See also</span></span>

- [<span data-ttu-id="de853-121">StepComplete, metoda</span><span class="sxs-lookup"><span data-stu-id="de853-121">StepComplete Method</span></span>](icordebugmanagedcallback-stepcomplete-method.md)
- [<span data-ttu-id="de853-122">Debugowanie — wyliczenia</span><span class="sxs-lookup"><span data-stu-id="de853-122">Debugging Enumerations</span></span>](debugging-enumerations.md)
