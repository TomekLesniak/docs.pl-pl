---
title: ICorDebugController::Stop — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugController.Stop
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Stop
helpviewer_keywords:
- Stop method, ICorDebugController interface [.NET Framework debugging]
- ICorDebugController::Stop method [.NET Framework debugging]
ms.assetid: c34e79be-a7fb-479e-8dec-d126a4c330e5
topic_type:
- apiref
ms.openlocfilehash: 11cc6e4108a2064a8a9fcefa760bf3c3411d63fb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679861"
---
# <a name="icordebugcontrollerstop-method"></a><span data-ttu-id="da13a-102">ICorDebugController::Stop — Metoda</span><span class="sxs-lookup"><span data-stu-id="da13a-102">ICorDebugController::Stop Method</span></span>

<span data-ttu-id="da13a-103">Wykonuje przerwanie w ramach wszystkich wątków, które uruchamiają kod zarządzany w procesie.</span><span class="sxs-lookup"><span data-stu-id="da13a-103">Performs a cooperative stop on all threads that are running managed code in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da13a-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="da13a-104">Syntax</span></span>  
  
```cpp  
HRESULT Stop (  
    [in] DWORD dwTimeoutIgnored  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="da13a-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="da13a-105">Parameters</span></span>  

 `dwTimeoutIgnored`  
 <span data-ttu-id="da13a-106">Nie używany.</span><span class="sxs-lookup"><span data-stu-id="da13a-106">Not used.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="da13a-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="da13a-107">Remarks</span></span>  

 <span data-ttu-id="da13a-108">`Stop` wykonuje przerwanie w ramach wszystkich wątków uruchamiających kod zarządzany w procesie.</span><span class="sxs-lookup"><span data-stu-id="da13a-108">`Stop` performs a cooperative stop on all threads running managed code in the process.</span></span> <span data-ttu-id="da13a-109">W trakcie sesji debugowania tylko zarządzanej wątki niezarządzane mogą nadal działać (ale będą blokowane podczas próby wywołania kodu zarządzanego).</span><span class="sxs-lookup"><span data-stu-id="da13a-109">During a managed-only debugging session, unmanaged threads may continue to run (but will be blocked when trying to call managed code).</span></span> <span data-ttu-id="da13a-110">W trakcie sesji debugowania międzyoperacyjności wątki niezarządzane również zostaną zatrzymane.</span><span class="sxs-lookup"><span data-stu-id="da13a-110">During an interop debugging session, unmanaged threads will also be stopped.</span></span> <span data-ttu-id="da13a-111">`dwTimeoutIgnored`Wartość jest obecnie ignorowana i traktowana jako nieskończona (-1).</span><span class="sxs-lookup"><span data-stu-id="da13a-111">The `dwTimeoutIgnored` value is currently ignored and treated as INFINITE (-1).</span></span> <span data-ttu-id="da13a-112">Jeśli z powodu zakleszczenia nie powiedzie się, wszystkie wątki są zawieszone, a E_TIMEOUT jest zwracana.</span><span class="sxs-lookup"><span data-stu-id="da13a-112">If the cooperative stop fails due to a deadlock, all threads are suspended and E_TIMEOUT is returned.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="da13a-113">`Stop` jest jedyną metodą synchroniczną w interfejsie API debugowania.</span><span class="sxs-lookup"><span data-stu-id="da13a-113">`Stop` is the only synchronous method in the debugging API.</span></span> <span data-ttu-id="da13a-114">Gdy `Stop` zwraca S_OK, proces jest zatrzymany.</span><span class="sxs-lookup"><span data-stu-id="da13a-114">When `Stop` returns S_OK, the process is stopped.</span></span> <span data-ttu-id="da13a-115">Nie podano wywołania zwrotnego, aby powiadomić detektory zatrzymania.</span><span class="sxs-lookup"><span data-stu-id="da13a-115">No callback is given to notify listeners of the stop.</span></span> <span data-ttu-id="da13a-116">Debuger musi wywołać [ICorDebugController:: Kontynuuj](icordebugcontroller-continue-method.md) , aby umożliwić wznowienie procesu.</span><span class="sxs-lookup"><span data-stu-id="da13a-116">The debugger must call [ICorDebugController::Continue](icordebugcontroller-continue-method.md) to allow the process to resume.</span></span>  
  
 <span data-ttu-id="da13a-117">Debuger zachowuje licznik zatrzymania.</span><span class="sxs-lookup"><span data-stu-id="da13a-117">The debugger maintains a stop counter.</span></span> <span data-ttu-id="da13a-118">Gdy licznik spadnie do zera, kontroler zostanie wznowiony.</span><span class="sxs-lookup"><span data-stu-id="da13a-118">When the counter goes to zero, the controller is resumed.</span></span> <span data-ttu-id="da13a-119">Każde wywołanie `Stop` lub każde wywoływane wywołanie zwrotne zwiększa licznik.</span><span class="sxs-lookup"><span data-stu-id="da13a-119">Each call to `Stop` or each dispatched callback increments the counter.</span></span> <span data-ttu-id="da13a-120">Każde wywołanie `ICorDebugController::Continue` zmniejsza licznik.</span><span class="sxs-lookup"><span data-stu-id="da13a-120">Each call to `ICorDebugController::Continue` decrements the counter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da13a-121">Wymagania</span><span class="sxs-lookup"><span data-stu-id="da13a-121">Requirements</span></span>  

 <span data-ttu-id="da13a-122">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da13a-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da13a-123">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="da13a-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="da13a-124">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="da13a-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="da13a-125">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da13a-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da13a-126">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="da13a-126">See also</span></span>
