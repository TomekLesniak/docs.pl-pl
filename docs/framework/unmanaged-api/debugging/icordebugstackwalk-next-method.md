---
title: ICorDebugStackWalk::Next — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk.Next Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk::Next
helpviewer_keywords:
- ICorDebugStackWalk::Next method [.NET Framework debugging]
- Next method, ICorDebugStackWalk interface [.NET Framework debugging]
ms.assetid: 189c36be-028c-4fba-a002-5edfb8fcd07f
topic_type:
- apiref
ms.openlocfilehash: 497dda473e6510cfa31405b2066c63b1a70dd5e9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677326"
---
# <a name="icordebugstackwalknext-method"></a><span data-ttu-id="259ea-102">ICorDebugStackWalk::Next — Metoda</span><span class="sxs-lookup"><span data-stu-id="259ea-102">ICorDebugStackWalk::Next Method</span></span>

<span data-ttu-id="259ea-103">Przenosi obiekt [ICorDebugStackWalk](icordebugstackwalk-interface.md) do następnej ramki.</span><span class="sxs-lookup"><span data-stu-id="259ea-103">Moves the [ICorDebugStackWalk](icordebugstackwalk-interface.md) object to the next frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="259ea-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="259ea-104">Syntax</span></span>  
  
```cpp  
HRESULT Next();  
```  
  
## <a name="return-value"></a><span data-ttu-id="259ea-105">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="259ea-105">Return Value</span></span>  

 <span data-ttu-id="259ea-106">Ta metoda zwraca następujące określone wartości HRESULT oraz błędy HRESULT wskazujące niepowodzenie metody.</span><span class="sxs-lookup"><span data-stu-id="259ea-106">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="259ea-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="259ea-107">HRESULT</span></span>|<span data-ttu-id="259ea-108">Opis</span><span class="sxs-lookup"><span data-stu-id="259ea-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="259ea-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="259ea-109">S_OK</span></span>|<span data-ttu-id="259ea-110">Środowisko wykonawcze zostało pomyślnie odwiązane z następną ramką (Zobacz uwagi).</span><span class="sxs-lookup"><span data-stu-id="259ea-110">The runtime successfully unwound to the next frame (see Remarks).</span></span>|  
|<span data-ttu-id="259ea-111">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="259ea-111">E_FAIL</span></span>|<span data-ttu-id="259ea-112">Nie można wykonać `ICorDebugStackWalk` zaawansowanego obiektu.</span><span class="sxs-lookup"><span data-stu-id="259ea-112">The `ICorDebugStackWalk` object could not be advanced.</span></span>|  
|<span data-ttu-id="259ea-113">CORDBG_S_AT_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="259ea-113">CORDBG_S_AT_END_OF_STACK</span></span>|<span data-ttu-id="259ea-114">Osiągnięto koniec stosu w wyniku tego elementu unwind.</span><span class="sxs-lookup"><span data-stu-id="259ea-114">The end of the stack was reached as a result of this unwind.</span></span>|  
|<span data-ttu-id="259ea-115">CORDBG_E_PAST_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="259ea-115">CORDBG_E_PAST_END_OF_STACK</span></span>|<span data-ttu-id="259ea-116">Wskaźnik ramki znajduje się już na końcu stosu; w związku z tym nie można uzyskać dostępu do dodatkowych ramek.</span><span class="sxs-lookup"><span data-stu-id="259ea-116">The frame pointer is already at the end of the stack; therefore, no additional frames can be accessed.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="259ea-117">Wyjątki</span><span class="sxs-lookup"><span data-stu-id="259ea-117">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="259ea-118">Uwagi</span><span class="sxs-lookup"><span data-stu-id="259ea-118">Remarks</span></span>  

 <span data-ttu-id="259ea-119">`Next`Metoda przesuwa `ICorDebugStackWalk` obiekt do ramki wywołującej tylko wtedy, gdy środowisko uruchomieniowe może odwinięcie bieżącej ramki.</span><span class="sxs-lookup"><span data-stu-id="259ea-119">The `Next` method advances the `ICorDebugStackWalk` object to the calling frame only if the runtime can unwind the current frame.</span></span> <span data-ttu-id="259ea-120">W przeciwnym razie obiekt przechodzi do następnej ramki, którą środowisko uruchomieniowe może przewinięcie.</span><span class="sxs-lookup"><span data-stu-id="259ea-120">Otherwise, the object advances to the next frame that the runtime is able to unwind.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="259ea-121">Wymagania</span><span class="sxs-lookup"><span data-stu-id="259ea-121">Requirements</span></span>  

 <span data-ttu-id="259ea-122">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="259ea-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="259ea-123">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="259ea-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="259ea-124">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="259ea-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="259ea-125">**.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="259ea-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="259ea-126">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="259ea-126">See also</span></span>

- [<span data-ttu-id="259ea-127">ICorDebugStackWalk — Interfejs</span><span class="sxs-lookup"><span data-stu-id="259ea-127">ICorDebugStackWalk Interface</span></span>](icordebugstackwalk-interface.md)
- [<span data-ttu-id="259ea-128">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="259ea-128">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="259ea-129">Debugowanie</span><span class="sxs-lookup"><span data-stu-id="259ea-129">Debugging</span></span>](index.md)
