---
title: 'ICorDebugMutableDataTarget:: ContinueStatusChanged, Metoda'
ms.date: 03/30/2017
ms.assetid: 5a66d3f4-dd16-4d62-9dcc-0eab7041d894
ms.openlocfilehash: 4910b125c2344505128a6979dfe4c9fad2b72c19
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695793"
---
# <a name="icordebugmutabledatatargetcontinuestatuschanged-method"></a><span data-ttu-id="6337e-102">ICorDebugMutableDataTarget:: ContinueStatusChanged, Metoda</span><span class="sxs-lookup"><span data-stu-id="6337e-102">ICorDebugMutableDataTarget::ContinueStatusChanged Method</span></span>

<span data-ttu-id="6337e-103">Zmienia stan kontynuacji dla zaległego zdarzenia debugowania w określonym wątku.</span><span class="sxs-lookup"><span data-stu-id="6337e-103">Changes the continuation status for the outstanding debug event on the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6337e-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="6337e-104">Syntax</span></span>  
  
```cpp  
HRESULT ContinueStatusChanged(  
   [in] DWORD dwThreadId,  
   [in] CORDB_CONTINUE_STATUS continueStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6337e-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="6337e-105">Parameters</span></span>  

 `dwThreadId`  
 <span data-ttu-id="6337e-106">Identyfikator wątku zdefiniowanego przez system operacyjny.</span><span class="sxs-lookup"><span data-stu-id="6337e-106">The operating system-defined thread identifier.</span></span>  
  
 `continueStatus`  
 <span data-ttu-id="6337e-107">Wartość [COREDB_CONTINUE_STATUS](../common-data-types-unmanaged-api-reference.md) , która reprezentuje nowy żądany stan kontynuacji.</span><span class="sxs-lookup"><span data-stu-id="6337e-107">A [COREDB_CONTINUE_STATUS](../common-data-types-unmanaged-api-reference.md) value that represents the new requested continuation status.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6337e-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="6337e-108">Remarks</span></span>  

 <span data-ttu-id="6337e-109">Debuger wywołuje metodę, `ContinueStatusChanged` gdy wywołuje metodę ICorDebug, która wymaga, aby bieżące zdarzenie debugowania zostało obsłużone w sposób, który może się różnić od sposobu, w jaki zwykle jest obsługiwany.</span><span class="sxs-lookup"><span data-stu-id="6337e-109">The debugger calls the `ContinueStatusChanged` method when it calls an ICorDebug method that requires the current debug event to be handled in a way that is potentially different from the way in which it normally would be handled.</span></span> <span data-ttu-id="6337e-110">Na przykład jeśli wystąpi wyjątek, a debuger żąda operacji, która spowodowałaby anulowanie wyjątku (na przykład [ICorDebugILFrame:: SetIP](icordebugilframe-setip-method.md) lub `FuncEval` ), ten interfejs API jest używany do żądania anulowania wyjątku.</span><span class="sxs-lookup"><span data-stu-id="6337e-110">For example, if there is an outstanding exception, and the debugger requests an operation that would cancel the exception (such as [ICorDebugILFrame::SetIP](icordebugilframe-setip-method.md) or `FuncEval`), this API is used to request that the exception be cancelled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6337e-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="6337e-111">Requirements</span></span>  

 <span data-ttu-id="6337e-112">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6337e-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6337e-113">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="6337e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6337e-114">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="6337e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6337e-115">**.NET Framework wersje:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6337e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6337e-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="6337e-116">See also</span></span>

- [<span data-ttu-id="6337e-117">ICorDebugMutableDataTarget, interfejs</span><span class="sxs-lookup"><span data-stu-id="6337e-117">ICorDebugMutableDataTarget Interface</span></span>](icordebugmutabledatatarget-interface.md)
- [<span data-ttu-id="6337e-118">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="6337e-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
