---
title: Metoda ICorDebugDebugEvent::GetThread
ms.date: 03/30/2017
ms.assetid: 4f2e9a2c-8369-4a07-a881-ad5422626353
ms.openlocfilehash: ca6aba7897d9e97743d29db49bd058e140f84e6e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713590"
---
# <a name="icordebugdebugeventgetthread-method"></a><span data-ttu-id="c6f50-102">Metoda ICorDebugDebugEvent::GetThread</span><span class="sxs-lookup"><span data-stu-id="c6f50-102">ICorDebugDebugEvent::GetThread Method</span></span>

<span data-ttu-id="c6f50-103">Pobiera wątek, w którym wystąpiło zdarzenie.</span><span class="sxs-lookup"><span data-stu-id="c6f50-103">Gets the thread on which the event occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6f50-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="c6f50-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThread(  
        [out]ICorDebugThread **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c6f50-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="c6f50-105">Parameters</span></span>  

 <span data-ttu-id="c6f50-106">ppThread</span><span class="sxs-lookup"><span data-stu-id="c6f50-106">ppThread</span></span>  
 <span data-ttu-id="c6f50-107">określoną Wskaźnik do adresu obiektu ICorDebugThread, który reprezentuje wątek, w którym wystąpiło zdarzenie.</span><span class="sxs-lookup"><span data-stu-id="c6f50-107">[out] A pointer to the address of an ICorDebugThread object that represents the thread on which the event occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c6f50-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="c6f50-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c6f50-109">Ta metoda jest dostępna tylko z .NET Native.</span><span class="sxs-lookup"><span data-stu-id="c6f50-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6f50-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="c6f50-110">Requirements</span></span>  

 <span data-ttu-id="c6f50-111">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6f50-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6f50-112">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="c6f50-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c6f50-113">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="c6f50-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c6f50-114">**.NET Framework wersje:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6f50-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6f50-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="c6f50-115">See also</span></span>

- [<span data-ttu-id="c6f50-116">Interfejs ICorDebugDebugEvent</span><span class="sxs-lookup"><span data-stu-id="c6f50-116">ICorDebugDebugEvent Interface</span></span>](icordebugdebugevent-interface.md)
- [<span data-ttu-id="c6f50-117">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="c6f50-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
