---
title: ICorDebugExceptionObjectValue — Interfejs
ms.date: 03/30/2017
api_name:
- ICorDebugExceptionObjectValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugExceptionObjectValue
helpviewer_keywords:
- ICorDebugExceptionObjectValue interface [.NET Framework debugging]
ms.assetid: 43416dd5-8892-4106-9f59-f9143b19ddb4
topic_type:
- apiref
ms.openlocfilehash: 6a0c33799b2b2aaa48e3b18b7b4bb37643508bd4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678886"
---
# <a name="icordebugexceptionobjectvalue-interface"></a><span data-ttu-id="37094-102">ICorDebugExceptionObjectValue — Interfejs</span><span class="sxs-lookup"><span data-stu-id="37094-102">ICorDebugExceptionObjectValue Interface</span></span>

<span data-ttu-id="37094-103">Rozszerza interfejs "ICorDebugObjectValue", aby dostarczyć informacje o śledzeniu stosu z obiektu wyjątku zarządzanego.</span><span class="sxs-lookup"><span data-stu-id="37094-103">Extends the "ICorDebugObjectValue" interface to provide stack trace information from a managed exception object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="37094-104">Metody</span><span class="sxs-lookup"><span data-stu-id="37094-104">Methods</span></span>  
  
|<span data-ttu-id="37094-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="37094-105">Method</span></span>|<span data-ttu-id="37094-106">Opis</span><span class="sxs-lookup"><span data-stu-id="37094-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="37094-107">EnumerateExceptionCallStack, metoda</span><span class="sxs-lookup"><span data-stu-id="37094-107">EnumerateExceptionCallStack Method</span></span>](icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md)|<span data-ttu-id="37094-108">Pobiera moduł wyliczający w stosie wywołań osadzonym w obiekcie wyjątku.</span><span class="sxs-lookup"><span data-stu-id="37094-108">Gets an enumerator to the call stack embedded in an exception object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="37094-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="37094-109">Remarks</span></span>  

 <span data-ttu-id="37094-110">Wywołanie powiedzie `QueryInterface` się dla obiektów zarządzanych, które pochodzą od <xref:System.Exception?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="37094-110">The call to `QueryInterface` will succeed for managed objects that derive from <xref:System.Exception?displayProperty=nameWithType>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37094-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="37094-111">Requirements</span></span>  

 <span data-ttu-id="37094-112">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="37094-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37094-113">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="37094-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="37094-114">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="37094-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="37094-115">**.NET Framework wersje:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37094-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37094-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="37094-116">See also</span></span>

- [<span data-ttu-id="37094-117">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="37094-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="37094-118">Debugowanie</span><span class="sxs-lookup"><span data-stu-id="37094-118">Debugging</span></span>](index.md)
