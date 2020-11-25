---
title: Interfejs ICorDebugDebugEvent
ms.date: 03/30/2017
ms.assetid: a226737a-cb99-4e97-bd94-9a37094ded41
ms.openlocfilehash: d73857bd9d0d5dd9e5eff0c89dcc573ae0d93f0e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731881"
---
# <a name="icordebugdebugevent-interface"></a><span data-ttu-id="9487d-102">Interfejs ICorDebugDebugEvent</span><span class="sxs-lookup"><span data-stu-id="9487d-102">ICorDebugDebugEvent Interface</span></span>

<span data-ttu-id="9487d-103">Definiuje interfejs podstawowy, z którego `ICorDebug` pochodzą wszystkie zdarzenia debugowania.</span><span class="sxs-lookup"><span data-stu-id="9487d-103">Defines the base interface from which all `ICorDebug` debug events derive.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9487d-104">Metody</span><span class="sxs-lookup"><span data-stu-id="9487d-104">Methods</span></span>  
  
|<span data-ttu-id="9487d-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="9487d-105">Method</span></span>|<span data-ttu-id="9487d-106">Opis</span><span class="sxs-lookup"><span data-stu-id="9487d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9487d-107">GetEventKind, metoda</span><span class="sxs-lookup"><span data-stu-id="9487d-107">GetEventKind Method</span></span>](icordebugdebugevent-geteventkind-method.md)|<span data-ttu-id="9487d-108">Wskazuje, jaki rodzaj zdarzenia `ICorDebugDebugEvent` reprezentuje ten obiekt.</span><span class="sxs-lookup"><span data-stu-id="9487d-108">Indicates what kind of event this `ICorDebugDebugEvent` object represents.</span></span>|  
|[<span data-ttu-id="9487d-109">GetThread, metoda</span><span class="sxs-lookup"><span data-stu-id="9487d-109">GetThread Method</span></span>](icordebugdebugevent-getthread-method.md)|<span data-ttu-id="9487d-110">Pobiera wątek, w którym wystąpiło zdarzenie.</span><span class="sxs-lookup"><span data-stu-id="9487d-110">Gets the thread on which the event occurred.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9487d-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="9487d-111">Remarks</span></span>  

 <span data-ttu-id="9487d-112">Następujące interfejsy pochodzą od `ICorDebugDebugEvent` interfejsu:</span><span class="sxs-lookup"><span data-stu-id="9487d-112">The following interfaces are derived from the `ICorDebugDebugEvent` interface:</span></span>  
  
- [<span data-ttu-id="9487d-113">ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="9487d-113">ICorDebugExceptionDebugEvent</span></span>](icordebugexceptiondebugevent-interface.md)  
  
- [<span data-ttu-id="9487d-114">ICorDebugModuleDebugEvent</span><span class="sxs-lookup"><span data-stu-id="9487d-114">ICorDebugModuleDebugEvent</span></span>](icordebugmoduledebugevent-interface.md)  
  
> [!NOTE]
> <span data-ttu-id="9487d-115">Interfejs jest dostępny tylko z .NET Native.</span><span class="sxs-lookup"><span data-stu-id="9487d-115">The interface is available with .NET Native only.</span></span> <span data-ttu-id="9487d-116">Próba wywołania metody `QueryInterface` pobierającej wskaźnik interfejsu zwraca `E_NOINTERFACE` dla scenariuszy ICorDebug poza .NET Native.</span><span class="sxs-lookup"><span data-stu-id="9487d-116">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9487d-117">Wymagania</span><span class="sxs-lookup"><span data-stu-id="9487d-117">Requirements</span></span>  

 <span data-ttu-id="9487d-118">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9487d-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9487d-119">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="9487d-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9487d-120">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="9487d-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9487d-121">**.NET Framework wersje:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9487d-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9487d-122">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="9487d-122">See also</span></span>

- [<span data-ttu-id="9487d-123">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="9487d-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="9487d-124">Debugowanie</span><span class="sxs-lookup"><span data-stu-id="9487d-124">Debugging</span></span>](index.md)
