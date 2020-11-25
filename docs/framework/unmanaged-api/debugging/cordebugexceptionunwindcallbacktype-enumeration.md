---
title: CorDebugExceptionUnwindCallbackType — Wyliczenie
ms.date: 03/30/2017
api_name:
- CorDebugExceptionUnwindCallbackType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugExceptionUnwindCallbackType
helpviewer_keywords:
- CorDebugExceptionUnwindCallbackType enumeration [.NET Framework debugging]
ms.assetid: 783dce92-8a98-43db-8f78-888d943dd5b2
topic_type:
- apiref
ms.openlocfilehash: 30de1448a7d1452e1e9049411010e7f43d13eb70
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712641"
---
# <a name="cordebugexceptionunwindcallbacktype-enumeration"></a><span data-ttu-id="c37bc-102">CorDebugExceptionUnwindCallbackType — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="c37bc-102">CorDebugExceptionUnwindCallbackType Enumeration</span></span>

<span data-ttu-id="c37bc-103">Wskazuje zdarzenie, które jest sygnalizowane przez wywołanie zwrotne w fazie unwind.</span><span class="sxs-lookup"><span data-stu-id="c37bc-103">Indicates the event that is being signaled by the callback during the unwind phase.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c37bc-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="c37bc-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugExceptionUnwindCallbackType {  
    DEBUG_EXCEPTION_UNWIND_BEGIN = 1,  
    DEBUG_EXCEPTION_INTERCEPTED  = 2  
} CorDebugExceptionUnwindCallbackType;  
```  
  
## <a name="members"></a><span data-ttu-id="c37bc-105">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="c37bc-105">Members</span></span>  
  
|<span data-ttu-id="c37bc-106">Członek</span><span class="sxs-lookup"><span data-stu-id="c37bc-106">Member</span></span>|<span data-ttu-id="c37bc-107">Opis</span><span class="sxs-lookup"><span data-stu-id="c37bc-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_UNWIND_BEGIN`|<span data-ttu-id="c37bc-108">Początek procesu unwind.</span><span class="sxs-lookup"><span data-stu-id="c37bc-108">The beginning of the unwind process.</span></span>|  
|`DEBUG_EXCEPTION_INTERCEPTED`|<span data-ttu-id="c37bc-109">Przechwycono wyjątek.</span><span class="sxs-lookup"><span data-stu-id="c37bc-109">The exception was intercepted.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c37bc-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="c37bc-110">Requirements</span></span>  

 <span data-ttu-id="c37bc-111">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c37bc-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c37bc-112">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="c37bc-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c37bc-113">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="c37bc-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c37bc-114">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c37bc-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c37bc-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="c37bc-115">See also</span></span>

- [<span data-ttu-id="c37bc-116">Debugowanie — wyliczenia</span><span class="sxs-lookup"><span data-stu-id="c37bc-116">Debugging Enumerations</span></span>](debugging-enumerations.md)
