---
title: IHostTask::Start — Metoda
ms.date: 03/30/2017
api_name:
- IHostTask.Start
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::Start
helpviewer_keywords:
- IHostTask::Start method [.NET Framework hosting]
- Start method, IHostTask interface [.NET Framework hosting]
ms.assetid: b18742b0-d8c4-401c-ae89-e6eccdaa81d0
topic_type:
- apiref
ms.openlocfilehash: 4143c3d25dd5262a10b53708a249910cc79f5314
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720441"
---
# <a name="ihosttaskstart-method"></a><span data-ttu-id="c16cc-102">IHostTask::Start — Metoda</span><span class="sxs-lookup"><span data-stu-id="c16cc-102">IHostTask::Start Method</span></span>

<span data-ttu-id="c16cc-103">Żąda, aby Host przeniesieł zadanie reprezentowane przez bieżące wystąpienie [IHostTask](ihosttask-interface.md) od zawieszenia do stanu na żywo, w którym można wykonać kod.</span><span class="sxs-lookup"><span data-stu-id="c16cc-103">Requests that the host move the task represented by the current [IHostTask](ihosttask-interface.md) instance from a suspended to a live state, in which code can be executed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c16cc-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="c16cc-104">Syntax</span></span>  
  
```cpp  
HRESULT Start ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="c16cc-105">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="c16cc-105">Return Value</span></span>  
  
|<span data-ttu-id="c16cc-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c16cc-106">HRESULT</span></span>|<span data-ttu-id="c16cc-107">Opis</span><span class="sxs-lookup"><span data-stu-id="c16cc-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c16cc-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="c16cc-108">S_OK</span></span>|<span data-ttu-id="c16cc-109">Pomyślnie zwrócono.</span><span class="sxs-lookup"><span data-stu-id="c16cc-109">Start returned successfully.</span></span>|  
|<span data-ttu-id="c16cc-110">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c16cc-110">E_FAIL</span></span>|<span data-ttu-id="c16cc-111">Wystąpił nieznany błąd krytyczny.</span><span class="sxs-lookup"><span data-stu-id="c16cc-111">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c16cc-112">Gdy metoda zwraca E_FAIL, środowisko uruchomieniowe języka wspólnego (CLR) nie jest już możliwe do użycia w procesie.</span><span class="sxs-lookup"><span data-stu-id="c16cc-112">When a method returns E_FAIL, the common language runtime (CLR) is no longer usable within the process.</span></span> <span data-ttu-id="c16cc-113">Kolejne wywołania metod hostingu zwracają HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c16cc-113">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c16cc-114">Uwagi</span><span class="sxs-lookup"><span data-stu-id="c16cc-114">Remarks</span></span>  

 <span data-ttu-id="c16cc-115">`Start` zawsze zwraca wartość HRESULT S_OK, z wyjątkiem przypadków, w których wystąpił błąd krytyczny.</span><span class="sxs-lookup"><span data-stu-id="c16cc-115">`Start` always returns an HRESULT value of S_OK, except in cases where a catastrophic failure has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c16cc-116">Wymagania</span><span class="sxs-lookup"><span data-stu-id="c16cc-116">Requirements</span></span>  

 <span data-ttu-id="c16cc-117">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c16cc-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c16cc-118">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c16cc-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c16cc-119">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c16cc-119">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c16cc-120">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c16cc-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c16cc-121">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="c16cc-121">See also</span></span>

- [<span data-ttu-id="c16cc-122">ICLRTask — Interfejs</span><span class="sxs-lookup"><span data-stu-id="c16cc-122">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="c16cc-123">ICLRTaskManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="c16cc-123">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="c16cc-124">IHostTask — Interfejs</span><span class="sxs-lookup"><span data-stu-id="c16cc-124">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="c16cc-125">IHostTaskManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="c16cc-125">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
