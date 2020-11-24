---
title: CorDebugBlockingReason — Wyliczenie
ms.date: 03/30/2017
api_name:
- CorDebugBlockingReason
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugBlockingReason
helpviewer_keywords:
- CorDebugBlockingReason enumeration [.NET Framework debugging]
ms.assetid: a6ac2531-ddfe-46fd-88fe-8b1eabe0b255
topic_type:
- apiref
ms.openlocfilehash: ddd03d70656ad52fd9d577beedc60b51c7b305d5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672854"
---
# <a name="cordebugblockingreason-enumeration"></a><span data-ttu-id="bfe79-102">CorDebugBlockingReason — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="bfe79-102">CorDebugBlockingReason Enumeration</span></span>

<span data-ttu-id="bfe79-103">Określa przyczyny, dla których wątek może zostać zablokowany dla danego obiektu.</span><span class="sxs-lookup"><span data-stu-id="bfe79-103">Specifies the reasons why a thread may become blocked on a given object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfe79-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="bfe79-104">Syntax</span></span>  
  
```cpp  
Typedef enum CorDebugBlockingReason  
{  
   BLOCKING_NONE = 0  
   BLOCKING_MONITOR_CRITICAL_SECTION = 1  
   BLOCKING_MONITOR_EVENT = 2  
}  CorDebugBlockingReason;  
```  
  
## <a name="members"></a><span data-ttu-id="bfe79-105">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="bfe79-105">Members</span></span>  
  
|<span data-ttu-id="bfe79-106">Członek</span><span class="sxs-lookup"><span data-stu-id="bfe79-106">Member</span></span>|<span data-ttu-id="bfe79-107">Opis</span><span class="sxs-lookup"><span data-stu-id="bfe79-107">Description</span></span>|  
|------------|-----------------|  
|`BLOCKING_NONE`|<span data-ttu-id="bfe79-108">Tylko do użytku wewnętrznego.</span><span class="sxs-lookup"><span data-stu-id="bfe79-108">Internal use only.</span></span>|  
|`BLOCKING_MONITOR_CRITICAL_SECTION`|<span data-ttu-id="bfe79-109">Wątek próbuje uzyskać sekcję krytyczną, która jest skojarzona z blokadą monitora dla obiektu.</span><span class="sxs-lookup"><span data-stu-id="bfe79-109">A thread is trying to acquire the critical section that is associated with the monitor lock on an object.</span></span> <span data-ttu-id="bfe79-110">Zwykle zdarza się to w przypadku wywołania jednej z <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> metod lub <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="bfe79-110">Typically, this occurs when you call one of the <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> or <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType> methods.</span></span>|  
|`BLOCKING_MONITOR_EVENT`|<span data-ttu-id="bfe79-111">Wątek oczekuje na zdarzenie skojarzone z blokadą monitora dla obiektu.</span><span class="sxs-lookup"><span data-stu-id="bfe79-111">A thread is waiting on the event that is associated with a monitor lock for an object.</span></span> <span data-ttu-id="bfe79-112">Zwykle zdarza się to w przypadku wywołania jednej z <xref:System.Threading.Monitor?displayProperty=nameWithType> `Wait` metod.</span><span class="sxs-lookup"><span data-stu-id="bfe79-112">Typically, this occurs when you call one of the <xref:System.Threading.Monitor?displayProperty=nameWithType>`Wait` methods.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bfe79-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="bfe79-113">Remarks</span></span>  

 <span data-ttu-id="bfe79-114">Gdy `BLOCKING_MONITOR_CRITICAL_SECTION` element or `BLOCKING_MONITOR_EVENT` jest używany w strukturze [CorDebugBlockingObject](cordebugblockingobject-structure.md) , `pBlockingObject` element członkowski struktury wskazuje interfejs "ICorDebugValue", który reprezentuje obiekt, który jest wprowadzany.</span><span class="sxs-lookup"><span data-stu-id="bfe79-114">When the `BLOCKING_MONITOR_CRITICAL_SECTION` or `BLOCKING_MONITOR_EVENT` member is used in a [CorDebugBlockingObject](cordebugblockingobject-structure.md) structure, the `pBlockingObject` member of the structure points to an "ICorDebugValue" interface that represents the object that is being entered.</span></span> <span data-ttu-id="bfe79-115">Należy również zastanowić się nad implementacją interfejsu [ICorDebugHeapValue3](icordebugheapvalue3-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="bfe79-115">It is also guaranteed to implement the [ICorDebugHeapValue3](icordebugheapvalue3-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bfe79-116">Wymagania</span><span class="sxs-lookup"><span data-stu-id="bfe79-116">Requirements</span></span>  

 <span data-ttu-id="bfe79-117">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bfe79-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bfe79-118">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="bfe79-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bfe79-119">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="bfe79-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bfe79-120">**.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bfe79-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfe79-121">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="bfe79-121">See also</span></span>

- [<span data-ttu-id="bfe79-122">Debugowanie — wyliczenia</span><span class="sxs-lookup"><span data-stu-id="bfe79-122">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="bfe79-123">Debugowanie</span><span class="sxs-lookup"><span data-stu-id="bfe79-123">Debugging</span></span>](index.md)
