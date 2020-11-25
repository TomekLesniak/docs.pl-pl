---
title: 'ICorDebugExceptionDebugEvent:: GetStackPointer, Metoda'
ms.date: 03/30/2017
ms.assetid: d8f66a1c-16be-4264-afc5-bc2dfbb4a682
ms.openlocfilehash: 46906e7d3ce7f257eb776e50dc6097946eb77d1f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95697405"
---
# <a name="icordebugexceptiondebugeventgetstackpointer-method"></a><span data-ttu-id="e6283-102">ICorDebugExceptionDebugEvent:: GetStackPointer, Metoda</span><span class="sxs-lookup"><span data-stu-id="e6283-102">ICorDebugExceptionDebugEvent::GetStackPointer Method</span></span>

<span data-ttu-id="e6283-103">Pobiera wskaźnik stosu dla tego zdarzenia debugowania wyjątku.</span><span class="sxs-lookup"><span data-stu-id="e6283-103">Gets the stack pointer for this exception debug event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6283-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="e6283-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackPointer(  
   [out]CORDB_ADDRESS *pStackPointer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e6283-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="e6283-105">Parameters</span></span>  

 `pStackPointer`  
 <span data-ttu-id="e6283-106">określoną Wskaźnik do adresu wskaźnika stosu dla tego zdarzenia debugowania wyjątku.</span><span class="sxs-lookup"><span data-stu-id="e6283-106">[out] A pointer to the address of the stack pointer for this exception debug event.</span></span> <span data-ttu-id="e6283-107">Zobacz sekcję Spostrzeżenia, aby uzyskać więcej informacji.</span><span class="sxs-lookup"><span data-stu-id="e6283-107">See the Remarks section for more information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e6283-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="e6283-108">Remarks</span></span>  

 <span data-ttu-id="e6283-109">Znaczenie tego wskaźnika stosu zależy od typu zdarzenia, jak pokazano w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="e6283-109">The meaning of this stack pointer depends on the event type, as shown in the following table.</span></span>  
  
|<span data-ttu-id="e6283-110">Typ zdarzenia</span><span class="sxs-lookup"><span data-stu-id="e6283-110">Event type</span></span>|<span data-ttu-id="e6283-111">Znaczenie `pStackPointer` wartości</span><span class="sxs-lookup"><span data-stu-id="e6283-111">Meaning of `pStackPointer` value</span></span>|  
|----------------|--------------------------------------|  
|[<span data-ttu-id="e6283-112">MANAGED_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="e6283-112">MANAGED_EXCEPTION_FIRST_CHANCE</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="e6283-113">Wskaźnik stosu dla ramki, która wywołała wyjątek.</span><span class="sxs-lookup"><span data-stu-id="e6283-113">The stack pointer for the frame that threw the exception.</span></span>|  
|[<span data-ttu-id="e6283-114">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="e6283-114">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="e6283-115">Wskaźnik stosu dla ramki kodu użytkownika znajdującej się najbliżej punktu zgłoszonego wyjątku.</span><span class="sxs-lookup"><span data-stu-id="e6283-115">The stack pointer for the user-code frame closest to the point of the thrown exception.</span></span>|  
|[<span data-ttu-id="e6283-116">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="e6283-116">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="e6283-117">Wskaźnik stosu dla ramki, która zawiera procedurę obsługi catch.</span><span class="sxs-lookup"><span data-stu-id="e6283-117">The stack pointer for the frame that contains the catch handler.</span></span>|  
|[<span data-ttu-id="e6283-118">MANAGED_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="e6283-118">MANAGED_EXCEPTION_UNHANDLED</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="e6283-119">`pStackPointer` ma **wartość null**.</span><span class="sxs-lookup"><span data-stu-id="e6283-119">`pStackPointer` is **null**.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="e6283-120">Ta metoda jest dostępna tylko z .NET Native.</span><span class="sxs-lookup"><span data-stu-id="e6283-120">This method is available with .NET Native only.</span></span>  
  
 <span data-ttu-id="e6283-121">Typ zdarzenia jest dostępny w metodzie [ICorDebugDebugEvent:: GetEventKind](icordebugdebugevent-geteventkind-method.md) .</span><span class="sxs-lookup"><span data-stu-id="e6283-121">The event type is available from the [ICorDebugDebugEvent::GetEventKind](icordebugdebugevent-geteventkind-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6283-122">Wymagania</span><span class="sxs-lookup"><span data-stu-id="e6283-122">Requirements</span></span>  

 <span data-ttu-id="e6283-123">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e6283-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6283-124">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="e6283-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e6283-125">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="e6283-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e6283-126">**.NET Framework wersje:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6283-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6283-127">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="e6283-127">See also</span></span>

- [<span data-ttu-id="e6283-128">Interfejs ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="e6283-128">ICorDebugExceptionDebugEvent Interface</span></span>](icordebugexceptiondebugevent-interface.md)
- [<span data-ttu-id="e6283-129">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="e6283-129">Debugging Interfaces</span></span>](debugging-interfaces.md)
