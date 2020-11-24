---
title: IHostSecurityManager::RevertToSelf — Metoda
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.RevertToSelf
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::RevertToSelf
helpviewer_keywords:
- RevertToSelf method [.NET Framework hosting]
- IHostSecurityManager::RevertToSelf method [.NET Framework hosting]
ms.assetid: 189f28f8-f9a1-4192-aedc-91084e4f8b99
topic_type:
- apiref
ms.openlocfilehash: a54c25cb0cae906dc2d030900b9a1e1dbbbb2f1e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680524"
---
# <a name="ihostsecuritymanagerreverttoself-method"></a><span data-ttu-id="a6785-102">IHostSecurityManager::RevertToSelf — Metoda</span><span class="sxs-lookup"><span data-stu-id="a6785-102">IHostSecurityManager::RevertToSelf Method</span></span>

<span data-ttu-id="a6785-103">Kończy personifikację bieżącej tożsamości użytkownika i zwraca oryginalny token wątku.</span><span class="sxs-lookup"><span data-stu-id="a6785-103">Terminates impersonation of the current user identity and returns the original thread token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6785-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="a6785-104">Syntax</span></span>  
  
```cpp  
HRESULT RevertToSelf ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="a6785-105">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="a6785-105">Return Value</span></span>  
  
|<span data-ttu-id="a6785-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a6785-106">HRESULT</span></span>|<span data-ttu-id="a6785-107">Opis</span><span class="sxs-lookup"><span data-stu-id="a6785-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a6785-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="a6785-108">S_OK</span></span>|<span data-ttu-id="a6785-109">`RevertToSelf` pomyślnie zwrócono.</span><span class="sxs-lookup"><span data-stu-id="a6785-109">`RevertToSelf` returned successfully.</span></span>|  
|<span data-ttu-id="a6785-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a6785-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a6785-111">Środowisko uruchomieniowe języka wspólnego (CLR) nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="a6785-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a6785-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a6785-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a6785-113">Upłynął limit czasu połączenia.</span><span class="sxs-lookup"><span data-stu-id="a6785-113">The call timed out.</span></span>|  
|<span data-ttu-id="a6785-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a6785-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a6785-115">Obiekt wywołujący nie jest właocicielem blokady.</span><span class="sxs-lookup"><span data-stu-id="a6785-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a6785-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a6785-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a6785-117">Zdarzenie zostało anulowane podczas oczekiwania na niego zablokowanego wątku lub włókna.</span><span class="sxs-lookup"><span data-stu-id="a6785-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a6785-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a6785-118">E_FAIL</span></span>|<span data-ttu-id="a6785-119">Wystąpił nieznany błąd krytyczny.</span><span class="sxs-lookup"><span data-stu-id="a6785-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a6785-120">Gdy metoda zwraca E_FAIL, środowisko CLR nie będzie już można używać w procesie.</span><span class="sxs-lookup"><span data-stu-id="a6785-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a6785-121">Kolejne wywołania metod hostingu zwracają HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a6785-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a6785-122">Uwagi</span><span class="sxs-lookup"><span data-stu-id="a6785-122">Remarks</span></span>  

 <span data-ttu-id="a6785-123">`RevertToSelf` jest wywoływana, aby powrócić do oryginalnego tokenu wątku po wcześniejszym wywołaniu metody [ImpersonateLoggedOnUser —](ihostsecuritymanager-impersonateloggedonuser-method.md) .</span><span class="sxs-lookup"><span data-stu-id="a6785-123">`RevertToSelf` is called to return to the original thread token, after an earlier call to the [ImpersonateLoggedOnUser](ihostsecuritymanager-impersonateloggedonuser-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6785-124">Wymagania</span><span class="sxs-lookup"><span data-stu-id="a6785-124">Requirements</span></span>  

 <span data-ttu-id="a6785-125">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6785-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6785-126">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="a6785-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a6785-127">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a6785-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a6785-128">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6785-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6785-129">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="a6785-129">See also</span></span>

- [<span data-ttu-id="a6785-130">IHostSecurityContext — Interfejs</span><span class="sxs-lookup"><span data-stu-id="a6785-130">IHostSecurityContext Interface</span></span>](ihostsecuritycontext-interface.md)
- [<span data-ttu-id="a6785-131">IHostSecurityManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="a6785-131">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)
- [<span data-ttu-id="a6785-132">ImpersonateLoggedOnUser, metoda</span><span class="sxs-lookup"><span data-stu-id="a6785-132">ImpersonateLoggedOnUser Method</span></span>](ihostsecuritymanager-impersonateloggedonuser-method.md)
