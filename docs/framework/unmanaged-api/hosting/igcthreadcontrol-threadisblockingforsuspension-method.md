---
title: IGCThreadControl::ThreadIsBlockingForSuspension — Metoda
ms.date: 03/30/2017
api_name:
- IGCThreadControl.ThreadIsBlockingForSuspension
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ThreadIsBlockingForSuspension
helpviewer_keywords:
- IGCThreadControl::ThreadIsBlockingForSuspension method [.NET Framework hosting]
- ThreadIsBlockingForSuspension method [.NET Framework hosting]
ms.assetid: ed5b5b58-7db7-46b5-9e2c-278db7159cee
topic_type:
- apiref
ms.openlocfilehash: 39834ba868a21ead3113f2f0d9157cd210d9798c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721650"
---
# <a name="igcthreadcontrolthreadisblockingforsuspension-method"></a><span data-ttu-id="7d7df-102">IGCThreadControl::ThreadIsBlockingForSuspension — Metoda</span><span class="sxs-lookup"><span data-stu-id="7d7df-102">IGCThreadControl::ThreadIsBlockingForSuspension Method</span></span>

<span data-ttu-id="7d7df-103">Powiadamia hosta, że wątek, który wywołuje wywołanie, ma zablokować, prawdopodobnie na wyrzucanie elementów bezużytecznych lub w innym zawieszeniu.</span><span class="sxs-lookup"><span data-stu-id="7d7df-103">Notifies the host that the thread that is making the call is about to block, perhaps for a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d7df-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="7d7df-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadIsBlockingForSuspension ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="7d7df-105">Uwagi</span><span class="sxs-lookup"><span data-stu-id="7d7df-105">Remarks</span></span>  

 <span data-ttu-id="7d7df-106">Host może wybrać w `ThreadIsBlockingForSuspension` wywołaniu zwrotnym, czy ponownie zaplanować wątek.</span><span class="sxs-lookup"><span data-stu-id="7d7df-106">The host may choose within the `ThreadIsBlockingForSuspension` callback whether to reschedule a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d7df-107">Wymagania</span><span class="sxs-lookup"><span data-stu-id="7d7df-107">Requirements</span></span>  

 <span data-ttu-id="7d7df-108">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7d7df-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d7df-109">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="7d7df-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7d7df-110">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7d7df-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7d7df-111">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d7df-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d7df-112">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="7d7df-112">See also</span></span>

- [<span data-ttu-id="7d7df-113">IGCThreadControl — Interfejs</span><span class="sxs-lookup"><span data-stu-id="7d7df-113">IGCThreadControl Interface</span></span>](igcthreadcontrol-interface.md)
