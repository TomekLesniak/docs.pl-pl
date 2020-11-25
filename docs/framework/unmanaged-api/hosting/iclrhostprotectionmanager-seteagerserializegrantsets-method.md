---
title: ICLRHostProtectionManager::SetEagerSerializeGrantSets — Metoda
ms.date: 03/30/2017
api_name:
- ICLRHostProtectionManager.SetEagerSerializeGrantSets
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostProtectionManager::SetEagerSerializeGrantSets
helpviewer_keywords:
- SetEagerSerializeGrantSets method [.NET Framework hosting]
- ICLRHostProtectionManager::SetEagerSerializeGrantSets method [.NET Framework hosting]
ms.assetid: d6158360-22b1-4ace-ad85-d830b9964783
topic_type:
- apiref
ms.openlocfilehash: 9ce4a5e042e838da8e9eba614f26e35b38af56c5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714136"
---
# <a name="iclrhostprotectionmanagerseteagerserializegrantsets-method"></a><span data-ttu-id="f3a8d-102">ICLRHostProtectionManager::SetEagerSerializeGrantSets — Metoda</span><span class="sxs-lookup"><span data-stu-id="f3a8d-102">ICLRHostProtectionManager::SetEagerSerializeGrantSets Method</span></span>

<span data-ttu-id="f3a8d-103">Ta metoda obsługuje infrastrukturę .NET Framework i nie jest przeznaczona do użycia bezpośrednio w kodzie.</span><span class="sxs-lookup"><span data-stu-id="f3a8d-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3a8d-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="f3a8d-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEagerSerializeGrantSets ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="f3a8d-105">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="f3a8d-105">Return Value</span></span>  
  
|<span data-ttu-id="f3a8d-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f3a8d-106">HRESULT</span></span>|<span data-ttu-id="f3a8d-107">Opis</span><span class="sxs-lookup"><span data-stu-id="f3a8d-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f3a8d-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="f3a8d-108">S_OK</span></span>|<span data-ttu-id="f3a8d-109">`SetEagerSerializeGrantSets` pomyślnie zwrócono.</span><span class="sxs-lookup"><span data-stu-id="f3a8d-109">`SetEagerSerializeGrantSets` returned successfully.</span></span>|  
|<span data-ttu-id="f3a8d-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f3a8d-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f3a8d-111">Środowisko CLR nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="f3a8d-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f3a8d-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f3a8d-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f3a8d-113">Upłynął limit czasu połączenia.</span><span class="sxs-lookup"><span data-stu-id="f3a8d-113">The call timed out.</span></span>|  
|<span data-ttu-id="f3a8d-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f3a8d-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f3a8d-115">Obiekt wywołujący nie jest właocicielem blokady.</span><span class="sxs-lookup"><span data-stu-id="f3a8d-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f3a8d-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f3a8d-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f3a8d-117">Zdarzenie zostało anulowane podczas oczekiwania na niego zablokowanego wątku lub włókna.</span><span class="sxs-lookup"><span data-stu-id="f3a8d-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f3a8d-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f3a8d-118">E_FAIL</span></span>|<span data-ttu-id="f3a8d-119">Wystąpił nieznany błąd krytyczny.</span><span class="sxs-lookup"><span data-stu-id="f3a8d-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f3a8d-120">Po powrocie metody E_FAIL nie będzie można używać środowiska CLR w procesie.</span><span class="sxs-lookup"><span data-stu-id="f3a8d-120">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f3a8d-121">Kolejne wywołania metod hostingu zwracają HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f3a8d-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f3a8d-122">Wymagania</span><span class="sxs-lookup"><span data-stu-id="f3a8d-122">Requirements</span></span>  

 <span data-ttu-id="f3a8d-123">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f3a8d-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3a8d-124">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f3a8d-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f3a8d-125">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f3a8d-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f3a8d-126">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3a8d-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3a8d-127">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="f3a8d-127">See also</span></span>

- [<span data-ttu-id="f3a8d-128">ICLRControl — Interfejs</span><span class="sxs-lookup"><span data-stu-id="f3a8d-128">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="f3a8d-129">ICLRHostProtectionManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="f3a8d-129">ICLRHostProtectionManager Interface</span></span>](iclrhostprotectionmanager-interface.md)
