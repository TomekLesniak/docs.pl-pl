---
title: IHostSecurityManager::GetSecurityContext — Metoda
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.GetSecurityContext
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::GetSecurityContext
helpviewer_keywords:
- GetSecurityContext method [.NET Framework hosting]
- IHostSecurityManager::GetSecurityContext method [.NET Framework hosting]
ms.assetid: 958970d6-f6a2-4b84-b32a-f555cbaf8f61
topic_type:
- apiref
ms.openlocfilehash: dfb96de02549e6d0f178c099793741f7fbd61d55
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724796"
---
# <a name="ihostsecuritymanagergetsecuritycontext-method"></a><span data-ttu-id="f834d-102">IHostSecurityManager::GetSecurityContext — Metoda</span><span class="sxs-lookup"><span data-stu-id="f834d-102">IHostSecurityManager::GetSecurityContext Method</span></span>

<span data-ttu-id="f834d-103">Pobiera żądany [IHostSecurityContext](ihostsecuritycontext-interface.md) z hosta.</span><span class="sxs-lookup"><span data-stu-id="f834d-103">Gets the requested [IHostSecurityContext](ihostsecuritycontext-interface.md) from the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f834d-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="f834d-104">Syntax</span></span>  
  
```cpp
HRESULT GetSecurityContext (  
    [in]  EContextType eContextType,
    [out] IHostSecurityContext** ppSecurityContext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f834d-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="f834d-105">Parameters</span></span>  

 `eContextType`  
 <span data-ttu-id="f834d-106">podczas Jedna z wartości [EContextType —](econtexttype-enumeration.md) , wskazująca typ kontekstu zabezpieczeń, który ma zostać zwrócony.</span><span class="sxs-lookup"><span data-stu-id="f834d-106">[in] One of the [EContextType](econtexttype-enumeration.md) values, indicating what type of security context to return.</span></span>  
  
 `ppSecurityContext`  
 <span data-ttu-id="f834d-107">określoną Adres wskaźnika interfejsu do `IHostSecurityContext` `eContextType` .</span><span class="sxs-lookup"><span data-stu-id="f834d-107">[out] The address of an interface pointer to the `IHostSecurityContext` of `eContextType`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f834d-108">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="f834d-108">Return Value</span></span>  
  
|<span data-ttu-id="f834d-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f834d-109">HRESULT</span></span>|<span data-ttu-id="f834d-110">Opis</span><span class="sxs-lookup"><span data-stu-id="f834d-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f834d-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="f834d-111">S_OK</span></span>|<span data-ttu-id="f834d-112">`GetSecurityContext` pomyślnie zwrócono.</span><span class="sxs-lookup"><span data-stu-id="f834d-112">`GetSecurityContext` returned successfully.</span></span>|  
|<span data-ttu-id="f834d-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f834d-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f834d-114">Środowisko uruchomieniowe języka wspólnego (CLR) nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="f834d-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f834d-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f834d-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f834d-116">Upłynął limit czasu połączenia.</span><span class="sxs-lookup"><span data-stu-id="f834d-116">The call timed out.</span></span>|  
|<span data-ttu-id="f834d-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f834d-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f834d-118">Obiekt wywołujący nie jest właocicielem blokady.</span><span class="sxs-lookup"><span data-stu-id="f834d-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f834d-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f834d-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f834d-120">Zdarzenie zostało anulowane podczas oczekiwania na niego zablokowanego wątku lub włókna.</span><span class="sxs-lookup"><span data-stu-id="f834d-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f834d-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f834d-121">E_FAIL</span></span>|<span data-ttu-id="f834d-122">Wystąpił nieznany błąd krytyczny.</span><span class="sxs-lookup"><span data-stu-id="f834d-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f834d-123">Gdy metoda zwraca E_FAIL, środowisko CLR nie będzie już można używać w procesie.</span><span class="sxs-lookup"><span data-stu-id="f834d-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f834d-124">Kolejne wywołania metod hostingu zwracają HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f834d-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f834d-125">Uwagi</span><span class="sxs-lookup"><span data-stu-id="f834d-125">Remarks</span></span>  

 <span data-ttu-id="f834d-126">Host może kontrolować cały dostęp kodu do tokenów wątków przez środowisko CLR i kod użytkownika.</span><span class="sxs-lookup"><span data-stu-id="f834d-126">A host can control all code access to thread tokens by both the CLR and user code.</span></span> <span data-ttu-id="f834d-127">Może także zapewnić, że pełne informacje kontekstu zabezpieczeń są przesyłane przez operacje asynchroniczne lub punkty kodowe z ograniczonym dostępem do kodu.</span><span class="sxs-lookup"><span data-stu-id="f834d-127">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="f834d-128">`IHostSecurityContext` hermetyzuje te informacje kontekstu zabezpieczeń, które nie są nieprzezroczyste dla środowiska CLR.</span><span class="sxs-lookup"><span data-stu-id="f834d-128">`IHostSecurityContext` encapsulates this security context information, which is opaque to the CLR.</span></span> <span data-ttu-id="f834d-129">Środowisko CLR przechwytuje te informacje i przenosi je między elementami procesu roboczego puli wątków, wykonywaniem finalizatora oraz konstruowaniem modułów i klas.</span><span class="sxs-lookup"><span data-stu-id="f834d-129">The CLR captures this information and moves it across thread pool worker item dispatch, finalizer execution, and module and class construction.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f834d-130">Wymagania</span><span class="sxs-lookup"><span data-stu-id="f834d-130">Requirements</span></span>  

 <span data-ttu-id="f834d-131">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f834d-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f834d-132">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f834d-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f834d-133">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f834d-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f834d-134">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f834d-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f834d-135">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="f834d-135">See also</span></span>

- [<span data-ttu-id="f834d-136">EContextType — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="f834d-136">EContextType Enumeration</span></span>](econtexttype-enumeration.md)
- [<span data-ttu-id="f834d-137">IHostSecurityContext — Interfejs</span><span class="sxs-lookup"><span data-stu-id="f834d-137">IHostSecurityContext Interface</span></span>](ihostsecuritycontext-interface.md)
- [<span data-ttu-id="f834d-138">IHostSecurityManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="f834d-138">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)
