---
title: CLR_DEBUGGING_PROCESS_FLAGS — Wyliczenie
ms.date: 03/30/2017
api_name:
- CLR_DEBUGGING_PROCESS_FLAGS
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CLR_DEBUGGING_PROCESS_FLAG
helpviewer_keywords:
- CLR_DEBUGGING_PROCESS_FLAGS enumeration [.NET Framework debugging]
ms.assetid: 85b85fde-1f87-490b-ba8d-d604670959c3
topic_type:
- apiref
ms.openlocfilehash: dd148d23d6e29f03052d3bbf1fcd5d02fb332a0a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729853"
---
# <a name="clr_debugging_process_flags-enumeration"></a><span data-ttu-id="2600f-102">CLR_DEBUGGING_PROCESS_FLAGS — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="2600f-102">CLR_DEBUGGING_PROCESS_FLAGS Enumeration</span></span>

<span data-ttu-id="2600f-103">Dostarcza wartości, które są używane przez metodę [ICLRDebugging:: OpenVirtualProcess —](iclrdebugging-openvirtualprocess-method.md) .</span><span class="sxs-lookup"><span data-stu-id="2600f-103">Provides values that are used by the [ICLRDebugging::OpenVirtualProcess](iclrdebugging-openvirtualprocess-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2600f-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="2600f-104">Syntax</span></span>  
  
```cpp  
typedef enum CLR_DEBUGGING_PROCESS_FLAGS  
{  
   CLR_DEBUGGING_MANAGED_EVENT_PENDING = 1,  
   CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH = 2  
}  CLR_DEBUGGING_PROCESS_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="2600f-105">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="2600f-105">Members</span></span>  
  
|<span data-ttu-id="2600f-106">Członek</span><span class="sxs-lookup"><span data-stu-id="2600f-106">Member</span></span>|<span data-ttu-id="2600f-107">Opis</span><span class="sxs-lookup"><span data-stu-id="2600f-107">Description</span></span>|  
|------------|-----------------|  
|`CLR_DEBUGGING_MANAGED_EVENT_PENDING`|<span data-ttu-id="2600f-108">To środowisko uruchomieniowe ma niecatche zarządzane zdarzenie debugera do wysłania.</span><span class="sxs-lookup"><span data-stu-id="2600f-108">This runtime has a non-catch-up managed debugger event to send.</span></span> <span data-ttu-id="2600f-109">Zapoznaj się z sekcją uwagi w celu rozróżnienia między zdarzeniami przechwytywania i niecatch.</span><span class="sxs-lookup"><span data-stu-id="2600f-109">See the Remarks section for the distinction between catch-up and non-catch-up events.</span></span>|  
|`CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH`|<span data-ttu-id="2600f-110">Oczekiwane zdarzenie zarządzane to <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> żądanie.</span><span class="sxs-lookup"><span data-stu-id="2600f-110">The managed event that is pending is a <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2600f-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="2600f-111">Remarks</span></span>  

 <span data-ttu-id="2600f-112">Zdarzenia dotyczące przechwytywania obejmują proces, domenę aplikacji, zestaw, moduł i powiadomienia o tworzeniu wątku, które umożliwiają debugerowi dostęp do bieżącego stanu po dołączeniu go do procesu.</span><span class="sxs-lookup"><span data-stu-id="2600f-112">Catch-up events include process, application domain, assembly, module, and thread creation notifications that bring the debugger up to the current state after it has attached to a process.</span></span> <span data-ttu-id="2600f-113">Zdarzenia niecatch, które są wskazywane przez `CLR_DEBUGGING_MANAGED_EVENT_PENDING` flagę, obejmują wszystkie inne zdarzenia debugera, takie jak wyjątki i powiadomienia programu Managed Debug Assistant (MDA).</span><span class="sxs-lookup"><span data-stu-id="2600f-113">Non-catch-up events, which are indicated by the `CLR_DEBUGGING_MANAGED_EVENT_PENDING` flag, include all other debugger events, such as exceptions and managed debugging assistant (MDA) notifications.</span></span>  
  
 <span data-ttu-id="2600f-114">`CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH`Flaga włącza środowisko uruchomieniowe, aby odróżnić między wyjątkami kończącymi i żądaniem dołączenia zarządzanego debugera, który można anulować.</span><span class="sxs-lookup"><span data-stu-id="2600f-114">The `CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH` flag enables the runtime to differentiate between a terminating exception and a request to attach a managed debugger that can be canceled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2600f-115">Wymagania</span><span class="sxs-lookup"><span data-stu-id="2600f-115">Requirements</span></span>  

 <span data-ttu-id="2600f-116">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2600f-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2600f-117">**Nagłówek:** Obiekt ServiceHost. idl, dbhost. h</span><span class="sxs-lookup"><span data-stu-id="2600f-117">**Header:** Metahost.idl, Metahost.h</span></span>  
  
 <span data-ttu-id="2600f-118">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="2600f-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2600f-119">**.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2600f-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2600f-120">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="2600f-120">See also</span></span>

- [<span data-ttu-id="2600f-121">Debugowanie — wyliczenia</span><span class="sxs-lookup"><span data-stu-id="2600f-121">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="2600f-122">Debugowanie</span><span class="sxs-lookup"><span data-stu-id="2600f-122">Debugging</span></span>](index.md)
