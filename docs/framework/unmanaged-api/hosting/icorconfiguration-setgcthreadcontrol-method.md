---
title: ICorConfiguration::SetGCThreadControl — Metoda
ms.date: 03/30/2017
api_name:
- ICorConfiguration.SetGCThreadControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetGCThreadControl
helpviewer_keywords:
- ICorConfiguration::SetGCThreadControl method [.NET Framework hosting]
- SetGCThreadControl method [.NET Framework hosting]
ms.assetid: 72e38e61-3d56-4ae3-b8f6-0ab7922aaf11
topic_type:
- apiref
ms.openlocfilehash: 28b012bbe3f8c11ecd0afb8b5905336bd99c349c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724029"
---
# <a name="icorconfigurationsetgcthreadcontrol-method"></a><span data-ttu-id="73afc-102">ICorConfiguration::SetGCThreadControl — Metoda</span><span class="sxs-lookup"><span data-stu-id="73afc-102">ICorConfiguration::SetGCThreadControl Method</span></span>

<span data-ttu-id="73afc-103">Ustawia interfejs wywołania zwrotnego dla wątków planowania dla zadań innych niż środowisko uruchomieniowe, które w przeciwnym razie byłyby blokowane dla wyrzucania elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="73afc-103">Sets the callback interface for scheduling threads for non-runtime tasks that would otherwise be blocked for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73afc-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="73afc-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGCThreadControl (  
    [in] IGCThreadControl* pGCThreadControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="73afc-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="73afc-105">Parameters</span></span>  

 `pGCThreadControl`  
 <span data-ttu-id="73afc-106">podczas Wskaźnik do obiektu [IGCThreadControl](igcthreadcontrol-interface.md) , który powiadamia hosta o zawieszeniu wątków dla zadań innych niż środowisko uruchomieniowe.</span><span class="sxs-lookup"><span data-stu-id="73afc-106">[in] A pointer to an [IGCThreadControl](igcthreadcontrol-interface.md) object that notifies the host about the suspension of threads for non-runtime tasks.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="73afc-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="73afc-107">Remarks</span></span>  

 <span data-ttu-id="73afc-108">Host może wybrać w ramach wywołania zwrotnego [IGCThreadControl:: ThreadIsBlockingForSuspension —](igcthreadcontrol-threadisblockingforsuspension-method.md) , czy ponownie zaplanować wątek.</span><span class="sxs-lookup"><span data-stu-id="73afc-108">The host may choose within the [IGCThreadControl::ThreadIsBlockingForSuspension](igcthreadcontrol-threadisblockingforsuspension-method.md) callback whether to reschedule a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73afc-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="73afc-109">Requirements</span></span>  

 <span data-ttu-id="73afc-110">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="73afc-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73afc-111">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="73afc-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="73afc-112">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="73afc-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="73afc-113">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73afc-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73afc-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="73afc-114">See also</span></span>

- [<span data-ttu-id="73afc-115">ICorConfiguration — Interfejs</span><span class="sxs-lookup"><span data-stu-id="73afc-115">ICorConfiguration Interface</span></span>](icorconfiguration-interface.md)
