---
title: CorDebugChainReason — Wyliczenie
ms.date: 03/30/2017
api_name:
- CorDebugChainReason
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugChainReason
helpviewer_keywords:
- CorDebugChainReason enumeration [.NET Framework debugging]
ms.assetid: c915da51-50b2-41df-841a-2b971f4d0975
topic_type:
- apiref
ms.openlocfilehash: 6185c5dda69a0cf7e9847ddc021448612a426b19
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716060"
---
# <a name="cordebugchainreason-enumeration"></a><span data-ttu-id="9a720-102">CorDebugChainReason — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="9a720-102">CorDebugChainReason Enumeration</span></span>

<span data-ttu-id="9a720-103">Wskazuje przyczynę lub przyczyny inicjacji łańcucha wywołań.</span><span class="sxs-lookup"><span data-stu-id="9a720-103">Indicates the reason or reasons for the initiation of a call chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a720-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="9a720-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugChainReason {  
    CHAIN_NONE              = 0x000,  
    CHAIN_CLASS_INIT        = 0x001,  
    CHAIN_EXCEPTION_FILTER  = 0x002,  
    CHAIN_SECURITY          = 0x004,  
    CHAIN_CONTEXT_POLICY    = 0x008,  
    CHAIN_INTERCEPTION      = 0x010,  
    CHAIN_PROCESS_START     = 0x020,  
    CHAIN_THREAD_START      = 0x040,  
    CHAIN_ENTER_MANAGED     = 0x080,  
    CHAIN_ENTER_UNMANAGED   = 0x100,  
    CHAIN_DEBUGGER_EVAL     = 0x200,  
    CHAIN_CONTEXT_SWITCH    = 0x400,  
    CHAIN_FUNC_EVAL         = 0x800  
} CorDebugChainReason;  
```  
  
## <a name="members"></a><span data-ttu-id="9a720-105">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="9a720-105">Members</span></span>  
  
|<span data-ttu-id="9a720-106">Członek</span><span class="sxs-lookup"><span data-stu-id="9a720-106">Member</span></span>|<span data-ttu-id="9a720-107">Opis</span><span class="sxs-lookup"><span data-stu-id="9a720-107">Description</span></span>|  
|------------|-----------------|  
|`CHAIN_NONE`|<span data-ttu-id="9a720-108">Nie zainicjowano łańcucha wywołań.</span><span class="sxs-lookup"><span data-stu-id="9a720-108">No call chain has been initiated.</span></span>|  
|`CHAIN_CLASS_INIT`|<span data-ttu-id="9a720-109">Łańcuch został zainicjowany przez konstruktora.</span><span class="sxs-lookup"><span data-stu-id="9a720-109">The chain was initiated by a constructor.</span></span>|  
|`CHAIN_EXCEPTION_FILTER`|<span data-ttu-id="9a720-110">Łańcuch został zainicjowany przez filtr wyjątków.</span><span class="sxs-lookup"><span data-stu-id="9a720-110">The chain was initiated by an exception filter.</span></span>|  
|`CHAIN_SECURITY`|<span data-ttu-id="9a720-111">Łańcuch został zainicjowany przez kod, który wymusza zabezpieczenia.</span><span class="sxs-lookup"><span data-stu-id="9a720-111">The chain was initiated by code that enforces security.</span></span>|  
|`CHAIN_CONTEXT_POLICY`|<span data-ttu-id="9a720-112">Łańcuch został zainicjowany przez zasady kontekstowe.</span><span class="sxs-lookup"><span data-stu-id="9a720-112">The chain was initiated by a context policy.</span></span>|  
|`CHAIN_INTERCEPTION`|<span data-ttu-id="9a720-113">Nie używany.</span><span class="sxs-lookup"><span data-stu-id="9a720-113">Not used.</span></span>|  
|`CHAIN_PROCESS_START`|<span data-ttu-id="9a720-114">Nie używany.</span><span class="sxs-lookup"><span data-stu-id="9a720-114">Not used.</span></span>|  
|`CHAIN_THREAD_START`|<span data-ttu-id="9a720-115">Łańcuch został zainicjowany przez rozpoczęcie wykonywania wątku.</span><span class="sxs-lookup"><span data-stu-id="9a720-115">The chain was initiated by the start of a thread execution.</span></span>|  
|`CHAIN_ENTER_MANAGED`|<span data-ttu-id="9a720-116">Łańcuch został zainicjowany przez wpis do kodu zarządzanego.</span><span class="sxs-lookup"><span data-stu-id="9a720-116">The chain was initiated by entry into managed code.</span></span>|  
|`CHAIN_ENTER_UNMANAGED`|<span data-ttu-id="9a720-117">Łańcuch został zainicjowany przez wpis w kodzie niezarządzanym.</span><span class="sxs-lookup"><span data-stu-id="9a720-117">The chain was initiated by entry into unmanaged code.</span></span>|  
|`CHAIN_DEBUGGER_EVAL`|<span data-ttu-id="9a720-118">Nie używany.</span><span class="sxs-lookup"><span data-stu-id="9a720-118">Not used.</span></span>|  
|`CHAIN_CONTEXT_SWITCH`|<span data-ttu-id="9a720-119">Nie używany.</span><span class="sxs-lookup"><span data-stu-id="9a720-119">Not used.</span></span>|  
|`CHAIN_FUNC_EVAL`|<span data-ttu-id="9a720-120">Łańcuch został zainicjowany przez funkcję oceny funkcji.</span><span class="sxs-lookup"><span data-stu-id="9a720-120">The chain was initiated by a function evaluation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9a720-121">Uwagi</span><span class="sxs-lookup"><span data-stu-id="9a720-121">Remarks</span></span>  

 <span data-ttu-id="9a720-122">Użyj metody [ICorDebugChain:: Getpowód](icordebugchain-getreason-method.md) , aby określić przyczyny inicjacji łańcucha wywołań.</span><span class="sxs-lookup"><span data-stu-id="9a720-122">Use the [ICorDebugChain::GetReason](icordebugchain-getreason-method.md) method to ascertain the reasons for the initiation of a call chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a720-123">Wymagania</span><span class="sxs-lookup"><span data-stu-id="9a720-123">Requirements</span></span>  

 <span data-ttu-id="9a720-124">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a720-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a720-125">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="9a720-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9a720-126">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="9a720-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9a720-127">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a720-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a720-128">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="9a720-128">See also</span></span>

- [<span data-ttu-id="9a720-129">Debugowanie — wyliczenia</span><span class="sxs-lookup"><span data-stu-id="9a720-129">Debugging Enumerations</span></span>](debugging-enumerations.md)
