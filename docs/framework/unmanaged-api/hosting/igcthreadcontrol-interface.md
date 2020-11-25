---
title: IGCThreadControl — Interfejs
ms.date: 03/30/2017
api_name:
- IGCThreadControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IGCThreadControl
helpviewer_keywords:
- IGCThreadControl interface [.NET Framework hosting]
ms.assetid: 3ff04d75-85ac-4df9-886d-dbaa037c0552
topic_type:
- apiref
ms.openlocfilehash: 02facbb0ff1c0f8978d4f4f720ab370f70f07fe2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721689"
---
# <a name="igcthreadcontrol-interface"></a><span data-ttu-id="edab0-102">IGCThreadControl — Interfejs</span><span class="sxs-lookup"><span data-stu-id="edab0-102">IGCThreadControl Interface</span></span>

<span data-ttu-id="edab0-103">Zapewnia metody uczestnictwa w planowaniu wątków, które w przeciwnym razie byłyby blokowane na wyrzucanie elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="edab0-103">Provides methods for participating in the scheduling of threads that would otherwise be blocked for a garbage collection.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="edab0-104">Metody</span><span class="sxs-lookup"><span data-stu-id="edab0-104">Methods</span></span>  
  
|<span data-ttu-id="edab0-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="edab0-105">Method</span></span>|<span data-ttu-id="edab0-106">Opis</span><span class="sxs-lookup"><span data-stu-id="edab0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="edab0-107">SuspensionEnding, metoda</span><span class="sxs-lookup"><span data-stu-id="edab0-107">SuspensionEnding Method</span></span>](igcthreadcontrol-suspensionending-method.md)|<span data-ttu-id="edab0-108">Powiadamia hosta, że środowisko uruchomieniowe wznawia wątki po wyrzucaniu elementów bezużytecznych lub innym zawieszeniu.</span><span class="sxs-lookup"><span data-stu-id="edab0-108">Notifies the host that the runtime is resuming threads after a garbage collection or other suspension.</span></span>|  
|[<span data-ttu-id="edab0-109">SuspensionStarting, metoda</span><span class="sxs-lookup"><span data-stu-id="edab0-109">SuspensionStarting Method</span></span>](igcthreadcontrol-suspensionstarting-method.md)|<span data-ttu-id="edab0-110">Powiadamia hosta, że środowisko uruchomieniowe rozpoczyna zawieszenie wątku na wyrzucanie elementów bezużytecznych lub inne zawieszenie.</span><span class="sxs-lookup"><span data-stu-id="edab0-110">Notifies the host that the runtime is beginning a thread suspension for a garbage collection or other suspension.</span></span>|  
|[<span data-ttu-id="edab0-111">ThreadIsBlockingForSuspension, metoda</span><span class="sxs-lookup"><span data-stu-id="edab0-111">ThreadIsBlockingForSuspension Method</span></span>](igcthreadcontrol-threadisblockingforsuspension-method.md)|<span data-ttu-id="edab0-112">Powiadamia hosta, że wątek wywołujący wywołanie ma być blokowany, prawdopodobnie na wyrzucanie elementów bezużytecznych lub innym zawieszeniu.</span><span class="sxs-lookup"><span data-stu-id="edab0-112">Notifies the host that the thread making the call is about to block, perhaps for a garbage collection or other suspension.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="edab0-113">Wymagania</span><span class="sxs-lookup"><span data-stu-id="edab0-113">Requirements</span></span>  

 <span data-ttu-id="edab0-114">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="edab0-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="edab0-115">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="edab0-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="edab0-116">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="edab0-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="edab0-117">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="edab0-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edab0-118">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="edab0-118">See also</span></span>

- [<span data-ttu-id="edab0-119">Hosting — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="edab0-119">Hosting Interfaces</span></span>](hosting-interfaces.md)
