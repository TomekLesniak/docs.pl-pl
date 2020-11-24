---
title: ICLRMemoryNotificationCallback — Interfejs
ms.date: 03/30/2017
api_name:
- ICLRMemoryNotificationCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMemoryNotificationCallback
helpviewer_keywords:
- ICLRMemoryNotificationCallback interface [.NET Framework hosting]
ms.assetid: 873639e2-4837-4568-83b3-4493e67e4174
topic_type:
- apiref
ms.openlocfilehash: 5762a354bec485cb382b5460dfd2a337f79bee1a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689540"
---
# <a name="iclrmemorynotificationcallback-interface"></a><span data-ttu-id="474d4-102">ICLRMemoryNotificationCallback — Interfejs</span><span class="sxs-lookup"><span data-stu-id="474d4-102">ICLRMemoryNotificationCallback Interface</span></span>

<span data-ttu-id="474d4-103">Umożliwia hostowi zgłaszanie warunków ciśnienia pamięci przy użyciu podejścia podobnego do `CreateMemoryResourceNotification` funkcji Win32.</span><span class="sxs-lookup"><span data-stu-id="474d4-103">Allows the host to report memory pressure conditions using an approach similar to that of the Win32 `CreateMemoryResourceNotification` function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="474d4-104">Metody</span><span class="sxs-lookup"><span data-stu-id="474d4-104">Methods</span></span>  
  
|<span data-ttu-id="474d4-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="474d4-105">Method</span></span>|<span data-ttu-id="474d4-106">Opis</span><span class="sxs-lookup"><span data-stu-id="474d4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="474d4-107">OnMemoryNotification, metoda</span><span class="sxs-lookup"><span data-stu-id="474d4-107">OnMemoryNotification Method</span></span>](iclrmemorynotificationcallback-onmemorynotification-method.md)|<span data-ttu-id="474d4-108">Powiadamia środowisko uruchomieniowe języka wspólnego (CLR) o załadowaniu pamięci na komputerze.</span><span class="sxs-lookup"><span data-stu-id="474d4-108">Notifies the common language runtime (CLR) of the memory load on the computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="474d4-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="474d4-109">Remarks</span></span>  

 <span data-ttu-id="474d4-110">Host używa `ICLRMemoryNotificationCallback` interfejsu do żądania zasobów wolnej pamięci środowiska CLR.</span><span class="sxs-lookup"><span data-stu-id="474d4-110">The host uses the `ICLRMemoryNotificationCallback` interface to request that the CLR free memory resources.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="474d4-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="474d4-111">Requirements</span></span>  

 <span data-ttu-id="474d4-112">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="474d4-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="474d4-113">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="474d4-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="474d4-114">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="474d4-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="474d4-115">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="474d4-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="474d4-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="474d4-116">See also</span></span>

- [<span data-ttu-id="474d4-117">IHostMemoryManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="474d4-117">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
- [<span data-ttu-id="474d4-118">Hosting — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="474d4-118">Hosting Interfaces</span></span>](hosting-interfaces.md)
