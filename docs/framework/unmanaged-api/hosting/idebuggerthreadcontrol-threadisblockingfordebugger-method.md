---
title: IDebuggerThreadControl::ThreadIsBlockingForDebugger — Metoda
ms.date: 03/30/2017
api_name:
- IDebuggerThreadControl.ThreadIsBlockingForDebugger
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ThreadIsBlockingForDebugger
helpviewer_keywords:
- ThreadIsBlockingForDebugger method [.NET Framework hosting]
- IDebuggerThreadControl::ThreadIsBlockingForDebugger method [.NET Framework hosting]
ms.assetid: d4d7cb2d-69da-48b3-879a-1a8a68c9bfa8
topic_type:
- apiref
ms.openlocfilehash: 8c2741d7db60781fef12293f3be0b515a55b7885
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705517"
---
# <a name="idebuggerthreadcontrolthreadisblockingfordebugger-method"></a><span data-ttu-id="07d16-102">IDebuggerThreadControl::ThreadIsBlockingForDebugger — Metoda</span><span class="sxs-lookup"><span data-stu-id="07d16-102">IDebuggerThreadControl::ThreadIsBlockingForDebugger Method</span></span>

<span data-ttu-id="07d16-103">Powiadamia hosta, że wątek wysyłający to wywołanie zwrotne ma zostać zablokowany w ramach usług debugowania.</span><span class="sxs-lookup"><span data-stu-id="07d16-103">Notifies the host that the thread that is sending this callback is about to block within the debugging services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07d16-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="07d16-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadIsBlockingForDebugger ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="07d16-105">Uwagi</span><span class="sxs-lookup"><span data-stu-id="07d16-105">Remarks</span></span>  

 <span data-ttu-id="07d16-106">`ThreadIsBlockingForDebugger`Metoda zostanie zawsze wywołana w wątku środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="07d16-106">The `ThreadIsBlockingForDebugger` method will always be called on a runtime thread.</span></span>  
  
 <span data-ttu-id="07d16-107">`ThreadIsBlockingForDebugger`Metoda zapewnia hostowi możliwość wykonywania innej akcji podczas bloków wątków.</span><span class="sxs-lookup"><span data-stu-id="07d16-107">The `ThreadIsBlockingForDebugger` method gives the host an opportunity to perform another action while the thread blocks.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07d16-108">Wymagania</span><span class="sxs-lookup"><span data-stu-id="07d16-108">Requirements</span></span>  

 <span data-ttu-id="07d16-109">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="07d16-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07d16-110">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="07d16-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="07d16-111">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="07d16-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="07d16-112">**Wersje programu .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07d16-112">**NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07d16-113">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="07d16-113">See also</span></span>

- [<span data-ttu-id="07d16-114">IDebuggerThreadControl — Interfejs</span><span class="sxs-lookup"><span data-stu-id="07d16-114">IDebuggerThreadControl Interface</span></span>](idebuggerthreadcontrol-interface.md)
