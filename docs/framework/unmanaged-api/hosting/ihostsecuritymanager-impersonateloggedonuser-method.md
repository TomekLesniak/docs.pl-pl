---
title: IHostSecurityManager::ImpersonateLoggedOnUser — Metoda
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.ImpersonateLoggedOnUser
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::ImpersonateLoggedOnUser
helpviewer_keywords:
- ImpersonateLoggedOnUser method [.NET Framework hosting]
- IHostSecurityManager::ImpersonateLoggedOnUser method [.NET Framework hosting]
ms.assetid: acc49ba0-f1d9-45ad-871f-9d053a89dcbe
topic_type:
- apiref
ms.openlocfilehash: dd1d1af8072ac11e37bd2eb1a47d76b12685cb31
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724783"
---
# <a name="ihostsecuritymanagerimpersonateloggedonuser-method"></a><span data-ttu-id="4b7b0-102">IHostSecurityManager::ImpersonateLoggedOnUser — Metoda</span><span class="sxs-lookup"><span data-stu-id="4b7b0-102">IHostSecurityManager::ImpersonateLoggedOnUser Method</span></span>

<span data-ttu-id="4b7b0-103">Żąda wykonania kodu przy użyciu poświadczeń bieżącego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="4b7b0-103">Requests that code be executed using the credentials of the current user identity.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b7b0-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="4b7b0-104">Syntax</span></span>  
  
```cpp  
HRESULT ImpersonateLoggedOnUser (  
    [in] HANDLE hToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4b7b0-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="4b7b0-105">Parameters</span></span>  

 `hToken`  
 <span data-ttu-id="4b7b0-106">podczas Token reprezentujący poświadczenia użytkownika do personifikacji.</span><span class="sxs-lookup"><span data-stu-id="4b7b0-106">[in] A token representing the credentials of the user to be impersonated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4b7b0-107">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="4b7b0-107">Return Value</span></span>  
  
|<span data-ttu-id="4b7b0-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4b7b0-108">HRESULT</span></span>|<span data-ttu-id="4b7b0-109">Opis</span><span class="sxs-lookup"><span data-stu-id="4b7b0-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4b7b0-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="4b7b0-110">S_OK</span></span>|<span data-ttu-id="4b7b0-111">`ImpersonateLoggedOnUser` pomyślnie zwrócono.</span><span class="sxs-lookup"><span data-stu-id="4b7b0-111">`ImpersonateLoggedOnUser` returned successfully.</span></span>|  
|<span data-ttu-id="4b7b0-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4b7b0-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4b7b0-113">Środowisko uruchomieniowe języka wspólnego (CLR) nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="4b7b0-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4b7b0-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4b7b0-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4b7b0-115">Upłynął limit czasu połączenia.</span><span class="sxs-lookup"><span data-stu-id="4b7b0-115">The call timed out.</span></span>|  
|<span data-ttu-id="4b7b0-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4b7b0-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4b7b0-117">Obiekt wywołujący nie jest właocicielem blokady.</span><span class="sxs-lookup"><span data-stu-id="4b7b0-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4b7b0-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4b7b0-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4b7b0-119">Zdarzenie zostało anulowane podczas oczekiwania na niego zablokowanego wątku lub włókna.</span><span class="sxs-lookup"><span data-stu-id="4b7b0-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4b7b0-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4b7b0-120">E_FAIL</span></span>|<span data-ttu-id="4b7b0-121">Wystąpił nieznany błąd krytyczny.</span><span class="sxs-lookup"><span data-stu-id="4b7b0-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4b7b0-122">Gdy metoda zwraca E_FAIL, środowisko CLR nie będzie już można używać w procesie.</span><span class="sxs-lookup"><span data-stu-id="4b7b0-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4b7b0-123">Kolejne wywołania metod hostingu zwracają HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="4b7b0-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4b7b0-124">Uwagi</span><span class="sxs-lookup"><span data-stu-id="4b7b0-124">Remarks</span></span>  

 <span data-ttu-id="4b7b0-125">Wywołanie `LogonUser` lub powiązana funkcja Win32 w celu uzyskania dojścia do poświadczeń bieżącej tożsamości użytkownika.</span><span class="sxs-lookup"><span data-stu-id="4b7b0-125">Call `LogonUser` or a related Win32 function to get a handle to the credentials of the current user identity.</span></span>  
  
 <span data-ttu-id="4b7b0-126">`HANDLE`Typ nie jest zgodny z modelem COM, oznacza to, że jego rozmiar jest specyficzny dla systemu operacyjnego i wymaga organizowania niestandardowego.</span><span class="sxs-lookup"><span data-stu-id="4b7b0-126">The `HANDLE` type is not COM-compliant, that is, its size is specific to an operating system, and it requires custom marshaling.</span></span> <span data-ttu-id="4b7b0-127">W ten sposób token jest używany tylko w ramach procesu, między środowiskiem CLR a hostem.</span><span class="sxs-lookup"><span data-stu-id="4b7b0-127">Thus, this token is for use only within the process, between the CLR and the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b7b0-128">Wymagania</span><span class="sxs-lookup"><span data-stu-id="4b7b0-128">Requirements</span></span>  

 <span data-ttu-id="4b7b0-129">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b7b0-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b7b0-130">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="4b7b0-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4b7b0-131">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4b7b0-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4b7b0-132">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b7b0-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b7b0-133">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="4b7b0-133">See also</span></span>

- [<span data-ttu-id="4b7b0-134">IHostSecurityContext — Interfejs</span><span class="sxs-lookup"><span data-stu-id="4b7b0-134">IHostSecurityContext Interface</span></span>](ihostsecuritycontext-interface.md)
- [<span data-ttu-id="4b7b0-135">IHostSecurityManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="4b7b0-135">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)
- [<span data-ttu-id="4b7b0-136">RevertToSelf, metoda</span><span class="sxs-lookup"><span data-stu-id="4b7b0-136">RevertToSelf Method</span></span>](ihostsecuritymanager-reverttoself-method.md)
