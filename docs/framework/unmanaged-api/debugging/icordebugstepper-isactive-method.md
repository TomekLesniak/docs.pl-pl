---
title: ICorDebugStepper::IsActive — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.IsActive
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::IsActive
helpviewer_keywords:
- IsActive method, ICorDebugStepper interface [.NET Framework debugging]
- ICorDebugStepper::IsActive method [.NET Framework debugging]
ms.assetid: 8b35e7a9-b40e-40a9-8d8e-b82e823fc575
topic_type:
- apiref
ms.openlocfilehash: 0a57dfe5bb4dfdc08a5e3f2238da6794e62bd958
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718283"
---
# <a name="icordebugstepperisactive-method"></a><span data-ttu-id="f6424-102">ICorDebugStepper::IsActive — Metoda</span><span class="sxs-lookup"><span data-stu-id="f6424-102">ICorDebugStepper::IsActive Method</span></span>

<span data-ttu-id="f6424-103">Pobiera wartość wskazującą, czy ten ICorDebugStepper aktualnie wykonuje krok.</span><span class="sxs-lookup"><span data-stu-id="f6424-103">Gets a value that indicates whether this ICorDebugStepper is currently executing a step.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6424-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="f6424-104">Syntax</span></span>  
  
```cpp  
HRESULT IsActive (  
    [out] BOOL   *pbActive  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f6424-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="f6424-105">Parameters</span></span>  

 `pbActive`  
 <span data-ttu-id="f6424-106">określoną Zwraca `true` czy stepper jest aktualnie wykonywany krok; w przeciwnym razie zwraca `false` .</span><span class="sxs-lookup"><span data-stu-id="f6424-106">[out] Returns `true` if the stepper is currently executing a step; otherwise, returns `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f6424-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="f6424-107">Remarks</span></span>  

 <span data-ttu-id="f6424-108">Każda akcja krok pozostaje aktywna, dopóki debuger nie otrzyma wywołania [ICorDebugManagedCallback:: StepComplete —](icordebugmanagedcallback-stepcomplete-method.md) , które automatycznie dezaktywuje stepper.</span><span class="sxs-lookup"><span data-stu-id="f6424-108">Any step action remains active until the debugger receives a [ICorDebugManagedCallback::StepComplete](icordebugmanagedcallback-stepcomplete-method.md) call, which automatically deactivates the stepper.</span></span> <span data-ttu-id="f6424-109">Stepper może również zostać zdezaktywowany przedwcześnie przez wywołanie [ICorDebugStepper::D eactivate](icordebugstepper-deactivate-method.md) przed osiągnięciem warunku wywołania zwrotnego.</span><span class="sxs-lookup"><span data-stu-id="f6424-109">A stepper may also be deactivated prematurely by calling [ICorDebugStepper::Deactivate](icordebugstepper-deactivate-method.md) before the callback condition is reached.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6424-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="f6424-110">Requirements</span></span>  

 <span data-ttu-id="f6424-111">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f6424-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6424-112">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="f6424-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f6424-113">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="f6424-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f6424-114">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6424-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
