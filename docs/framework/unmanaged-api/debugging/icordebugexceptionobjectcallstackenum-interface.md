---
title: ICorDebugExceptionObjectCallStackEnum — Interfejs
ms.date: 03/30/2017
api_name:
- ICorDebugExceptionObjectCallStackEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugExceptionObjectCallStackEnum
helpviewer_keywords:
- ICorDebugExceptionObjectCallStackEnum interface [.NET Framework debugging]
ms.assetid: 39dffa18-c71b-48c4-b11d-e814631ab1e9
topic_type:
- apiref
ms.openlocfilehash: 1c45faecdb8b95af8d9e981962151c2c5d071a4f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731894"
---
# <a name="icordebugexceptionobjectcallstackenum-interface"></a><span data-ttu-id="9138d-102">ICorDebugExceptionObjectCallStackEnum — Interfejs</span><span class="sxs-lookup"><span data-stu-id="9138d-102">ICorDebugExceptionObjectCallStackEnum Interface</span></span>

<span data-ttu-id="9138d-103">Dostarcza moduł wyliczający informacje stosu wywołań, który jest wbudowany w obiekt wyjątku.</span><span class="sxs-lookup"><span data-stu-id="9138d-103">Provides an enumerator for call stack information that is embedded in an exception object.</span></span> <span data-ttu-id="9138d-104">Ten interfejs jest podklasą interfejsu ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="9138d-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9138d-105">Metody</span><span class="sxs-lookup"><span data-stu-id="9138d-105">Methods</span></span>  
  
|<span data-ttu-id="9138d-106">Metoda</span><span class="sxs-lookup"><span data-stu-id="9138d-106">Method</span></span>|<span data-ttu-id="9138d-107">Opis</span><span class="sxs-lookup"><span data-stu-id="9138d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9138d-108">ICorDebugExceptionObjectCallStackEnum:: Next</span><span class="sxs-lookup"><span data-stu-id="9138d-108">ICorDebugExceptionObjectCallStackEnum::Next</span></span>](icordebugexceptionobjectcallstackenum-next-method.md)|<span data-ttu-id="9138d-109">Pobiera określoną liczbę obiektów [CorDebugExceptionObjectStackFrame —](cordebugexceptionobjectstackframe-structure.md) , które zawierają informacje o stosie wywołań obiektu wyjątku.</span><span class="sxs-lookup"><span data-stu-id="9138d-109">Gets a specified number of [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) objects that contain information about an exception object's call stack.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9138d-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="9138d-110">Remarks</span></span>  

 <span data-ttu-id="9138d-111">`ICorDebugExceptionObjectCallStackEnum`Interfejs implementuje interfejs ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="9138d-111">The `ICorDebugExceptionObjectCallStackEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="9138d-112">`ICorDebugExceptionObjectCallStackEnum`Wystąpienie jest wypełniane obiektami [CorDebugExceptionObjectStackFrame —](cordebugexceptionobjectstackframe-structure.md) przez wywołanie metody [ICorDebugExceptionObjectValue:: EnumerateExceptionCallStack —](icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md) .</span><span class="sxs-lookup"><span data-stu-id="9138d-112">An `ICorDebugExceptionObjectCallStackEnum` instance is populated with [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) objects by calling the [ICorDebugExceptionObjectValue::EnumerateExceptionCallStack](icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md) method.</span></span> <span data-ttu-id="9138d-113">Elementy stosu wywołań w kolekcji mogą być wyliczane przez wywołanie metody [ICorDebugExceptionObjectCallStackEnum:: Next](icordebugexceptionobjectcallstackenum-next-method.md)</span><span class="sxs-lookup"><span data-stu-id="9138d-113">The call stack items in the collection can be enumerated by calling the [ICorDebugExceptionObjectCallStackEnum::Next](icordebugexceptionobjectcallstackenum-next-method.md) method</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9138d-114">Wymagania</span><span class="sxs-lookup"><span data-stu-id="9138d-114">Requirements</span></span>  

 <span data-ttu-id="9138d-115">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9138d-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9138d-116">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="9138d-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9138d-117">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="9138d-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9138d-118">**.NET Framework wersje:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9138d-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9138d-119">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="9138d-119">See also</span></span>

- [<span data-ttu-id="9138d-120">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="9138d-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="9138d-121">Debugowanie</span><span class="sxs-lookup"><span data-stu-id="9138d-121">Debugging</span></span>](index.md)
