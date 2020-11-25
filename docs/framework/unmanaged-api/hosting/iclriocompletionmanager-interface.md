---
title: ICLRIoCompletionManager — Interfejs
ms.date: 03/30/2017
api_name:
- ICLRIoCompletionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRIoCompletionManager
helpviewer_keywords:
- ICLRIoCompletionManager interface [.NET Framework hosting]
ms.assetid: c6c3ace6-e5e7-4450-8cc5-a9a48208c493
topic_type:
- apiref
ms.openlocfilehash: e23675351e1fd0de510243c9ee8b3a6dd6f29cec
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714123"
---
# <a name="iclriocompletionmanager-interface"></a><span data-ttu-id="13a9d-102">ICLRIoCompletionManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="13a9d-102">ICLRIoCompletionManager Interface</span></span>

<span data-ttu-id="13a9d-103">Implementuje metodę wywołania zwrotnego, która umożliwia hostowi powiadamianie środowiska uruchomieniowego języka wspólnego (CLR) o stanie określonych żądań we/wy.</span><span class="sxs-lookup"><span data-stu-id="13a9d-103">Implements a callback method that allows the host to notify the common language runtime (CLR) of the status of specified I/O requests.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="13a9d-104">Metody</span><span class="sxs-lookup"><span data-stu-id="13a9d-104">Methods</span></span>  
  
|<span data-ttu-id="13a9d-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="13a9d-105">Method</span></span>|<span data-ttu-id="13a9d-106">Opis</span><span class="sxs-lookup"><span data-stu-id="13a9d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="13a9d-107">OnComplete, metoda</span><span class="sxs-lookup"><span data-stu-id="13a9d-107">OnComplete Method</span></span>](iclriocompletionmanager-oncomplete-method.md)|<span data-ttu-id="13a9d-108">Powiadamia CLR o stanie żądania we/wy, które zostało wykonane przy użyciu wywołania metody [IHostIoCompletionManager:: bind](ihostiocompletionmanager-bind-method.md) .</span><span class="sxs-lookup"><span data-stu-id="13a9d-108">Notifies the CLR of the status of an I/O request that was made by using a call to the [IHostIoCompletionManager::Bind](ihostiocompletionmanager-bind-method.md) method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="13a9d-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="13a9d-109">Remarks</span></span>  

 <span data-ttu-id="13a9d-110">Host implementuje abstrakcję ukończenia we/wy przy użyciu interfejsu [IHostIoCompletionManager](ihostiocompletionmanager-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="13a9d-110">The host implements the I/O completion abstraction by using the [IHostIoCompletionManager](ihostiocompletionmanager-interface.md) interface.</span></span> <span data-ttu-id="13a9d-111">Środowisko CLR wykonuje żądania we/wy za pośrednictwem tego interfejsu, a host powiadamia środowisko uruchomieniowe o wyniku takich żądań za pomocą `ICLRIoCompletionManager` interfejsu.</span><span class="sxs-lookup"><span data-stu-id="13a9d-111">The CLR makes I/O requests through this interface, and the host notifies the runtime of the outcome of such requests by using the `ICLRIoCompletionManager` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13a9d-112">Wymagania</span><span class="sxs-lookup"><span data-stu-id="13a9d-112">Requirements</span></span>  

 <span data-ttu-id="13a9d-113">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="13a9d-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13a9d-114">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="13a9d-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="13a9d-115">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="13a9d-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="13a9d-116">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13a9d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13a9d-117">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="13a9d-117">See also</span></span>

- [<span data-ttu-id="13a9d-118">IHostIoCompletionManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="13a9d-118">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
- [<span data-ttu-id="13a9d-119">IHostThreadPoolManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="13a9d-119">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)
- [<span data-ttu-id="13a9d-120">Hosting — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="13a9d-120">Hosting Interfaces</span></span>](hosting-interfaces.md)
