---
title: IHostPolicyManager::OnTimeout — Metoda
ms.date: 03/30/2017
api_name:
- IHostPolicyManager.OnTimeout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostPolicyManager::OnTimeout
helpviewer_keywords:
- IHostPolicyManager::OnTimeout method [.NET Framework hosting]
- OnTimeout method [.NET Framework hosting]
ms.assetid: 0a313b51-5e4d-4714-a86b-af75cf3902e6
topic_type:
- apiref
ms.openlocfilehash: e3f2dc7ff9beaf417184f3d09db76e611982118a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690671"
---
# <a name="ihostpolicymanagerontimeout-method"></a><span data-ttu-id="cc2c2-102">IHostPolicyManager::OnTimeout — Metoda</span><span class="sxs-lookup"><span data-stu-id="cc2c2-102">IHostPolicyManager::OnTimeout Method</span></span>

<span data-ttu-id="cc2c2-103">Powiadamia hosta, że środowisko uruchomieniowe języka wspólnego (CLR) ma wykonać akcję określoną przez wywołanie metody [ICLRPolicyManager:: SetActionOnTimeout —](iclrpolicymanager-setactionontimeout-method.md) w odpowiedzi na limit czasu.</span><span class="sxs-lookup"><span data-stu-id="cc2c2-103">Notifies the host that the common language runtime (CLR) is about to take the action specified by a call to the [ICLRPolicyManager::SetActionOnTimeout](iclrpolicymanager-setactionontimeout-method.md) method in response to a timeout.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc2c2-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="cc2c2-104">Syntax</span></span>  
  
```cpp  
HRESULT OnTimeout (  
    [in] EClrOperation  operation,
    [in] EPolicyAction  action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cc2c2-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="cc2c2-105">Parameters</span></span>  

 `operation`  
 <span data-ttu-id="cc2c2-106">podczas Jedna z wartości [EClrOperation —](eclroperation-enumeration.md) , wskazująca rodzaj operacji, która przekroczyła limit czasu.</span><span class="sxs-lookup"><span data-stu-id="cc2c2-106">[in] One of the [EClrOperation](eclroperation-enumeration.md) values, indicating the kind of operation that timed out.</span></span>  
  
 `action`  
 <span data-ttu-id="cc2c2-107">podczas Jedna z wartości [EPolicyAction —](epolicyaction-enumeration.md) , wskazująca na akcję, którą wykonuje środowisko CLR w odpowiedzi na limit czasu.</span><span class="sxs-lookup"><span data-stu-id="cc2c2-107">[in] One of the [EPolicyAction](epolicyaction-enumeration.md) values, indicating the action the CLR is taking in response to the timeout.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cc2c2-108">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="cc2c2-108">Return Value</span></span>  
  
|<span data-ttu-id="cc2c2-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cc2c2-109">HRESULT</span></span>|<span data-ttu-id="cc2c2-110">Opis</span><span class="sxs-lookup"><span data-stu-id="cc2c2-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cc2c2-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="cc2c2-111">S_OK</span></span>|<span data-ttu-id="cc2c2-112">`OnTimeout` pomyślnie zwrócono.</span><span class="sxs-lookup"><span data-stu-id="cc2c2-112">`OnTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="cc2c2-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="cc2c2-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="cc2c2-114">Środowisko CLR nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="cc2c2-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="cc2c2-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="cc2c2-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="cc2c2-116">Upłynął limit czasu połączenia.</span><span class="sxs-lookup"><span data-stu-id="cc2c2-116">The call timed out.</span></span>|  
|<span data-ttu-id="cc2c2-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="cc2c2-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="cc2c2-118">Obiekt wywołujący nie jest właocicielem blokady.</span><span class="sxs-lookup"><span data-stu-id="cc2c2-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="cc2c2-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="cc2c2-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="cc2c2-120">Zdarzenie zostało anulowane podczas oczekiwania na niego zablokowanego wątku lub włókna.</span><span class="sxs-lookup"><span data-stu-id="cc2c2-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="cc2c2-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="cc2c2-121">E_FAIL</span></span>|<span data-ttu-id="cc2c2-122">Wystąpił nieznany błąd krytyczny.</span><span class="sxs-lookup"><span data-stu-id="cc2c2-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="cc2c2-123">Gdy metoda zwraca E_FAIL, środowisko CLR nie będzie już można używać w procesie.</span><span class="sxs-lookup"><span data-stu-id="cc2c2-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="cc2c2-124">Kolejne wywołania metod hostingu zwracają HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="cc2c2-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cc2c2-125">Wymagania</span><span class="sxs-lookup"><span data-stu-id="cc2c2-125">Requirements</span></span>  

 <span data-ttu-id="cc2c2-126">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cc2c2-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc2c2-127">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="cc2c2-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cc2c2-128">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cc2c2-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cc2c2-129">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc2c2-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc2c2-130">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="cc2c2-130">See also</span></span>

- [<span data-ttu-id="cc2c2-131">EClrOperation — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="cc2c2-131">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="cc2c2-132">EPolicyAction — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="cc2c2-132">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="cc2c2-133">ICLRPolicyManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="cc2c2-133">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="cc2c2-134">IHostPolicyManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="cc2c2-134">IHostPolicyManager Interface</span></span>](ihostpolicymanager-interface.md)
