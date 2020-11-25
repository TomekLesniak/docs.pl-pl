---
title: ICLRRuntimeHost::GetCurrentAppDomainId — Metoda
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.GetCurrentAppDomainId
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::GetCurrentAppDomainId
helpviewer_keywords:
- ICLRRuntimeHost::GetCurrentAppDomainId method [.NET Framework hosting]
- GetCurrentAppDomainId method [.NET Framework hosting]
ms.assetid: 33800475-7815-4976-8aca-a1038761a2ef
topic_type:
- apiref
ms.openlocfilehash: 2b1c9e99604664c99960a0741de6eae6b38fe963
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728852"
---
# <a name="iclrruntimehostgetcurrentappdomainid-method"></a><span data-ttu-id="7f8c3-102">ICLRRuntimeHost::GetCurrentAppDomainId — Metoda</span><span class="sxs-lookup"><span data-stu-id="7f8c3-102">ICLRRuntimeHost::GetCurrentAppDomainId Method</span></span>

<span data-ttu-id="7f8c3-103">Pobiera liczbowy identyfikator <xref:System.AppDomain> , który jest aktualnie wykonywany.</span><span class="sxs-lookup"><span data-stu-id="7f8c3-103">Gets the numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f8c3-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="7f8c3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentAppDomainId(  
    [out] DWORD* pdwAppDomainId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7f8c3-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="7f8c3-105">Parameters</span></span>  

 `pdwAppDomainId`  
 <span data-ttu-id="7f8c3-106">określoną Liczbowy identyfikator <xref:System.AppDomain> , który jest aktualnie wykonywany.</span><span class="sxs-lookup"><span data-stu-id="7f8c3-106">[out] The numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7f8c3-107">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="7f8c3-107">Return Value</span></span>  
  
|<span data-ttu-id="7f8c3-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7f8c3-108">HRESULT</span></span>|<span data-ttu-id="7f8c3-109">Opis</span><span class="sxs-lookup"><span data-stu-id="7f8c3-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7f8c3-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="7f8c3-110">S_OK</span></span>|<span data-ttu-id="7f8c3-111">`GetCurrentAppDomainId` pomyślnie zwrócono.</span><span class="sxs-lookup"><span data-stu-id="7f8c3-111">`GetCurrentAppDomainId` returned successfully.</span></span>|  
|<span data-ttu-id="7f8c3-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7f8c3-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7f8c3-113">Środowisko uruchomieniowe języka wspólnego (CLR) nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="7f8c3-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7f8c3-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7f8c3-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7f8c3-115">Upłynął limit czasu połączenia.</span><span class="sxs-lookup"><span data-stu-id="7f8c3-115">The call timed out.</span></span>|  
|<span data-ttu-id="7f8c3-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7f8c3-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7f8c3-117">Obiekt wywołujący nie jest właocicielem blokady.</span><span class="sxs-lookup"><span data-stu-id="7f8c3-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7f8c3-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7f8c3-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7f8c3-119">Zdarzenie zostało anulowane podczas oczekiwania na niego zablokowanego wątku lub włókna.</span><span class="sxs-lookup"><span data-stu-id="7f8c3-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7f8c3-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7f8c3-120">E_FAIL</span></span>|<span data-ttu-id="7f8c3-121">Wystąpił nieznany błąd krytyczny.</span><span class="sxs-lookup"><span data-stu-id="7f8c3-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7f8c3-122">Jeśli metoda zwraca E_FAIL, środowisko CLR nie będzie już można używać w procesie.</span><span class="sxs-lookup"><span data-stu-id="7f8c3-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7f8c3-123">Kolejne wywołania metod hostingu zwracają HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="7f8c3-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7f8c3-124">Uwagi</span><span class="sxs-lookup"><span data-stu-id="7f8c3-124">Remarks</span></span>  

 <span data-ttu-id="7f8c3-125">`pdwAppDomainId`Parametr jest ustawiony na wartość <xref:System.AppDomain.Id%2A> właściwości, <xref:System.AppDomain> w której jest wykonywany bieżący wątek.</span><span class="sxs-lookup"><span data-stu-id="7f8c3-125">The `pdwAppDomainId` parameter is set to the value of the <xref:System.AppDomain.Id%2A> property of the <xref:System.AppDomain> in which the current thread is executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f8c3-126">Wymagania</span><span class="sxs-lookup"><span data-stu-id="7f8c3-126">Requirements</span></span>  

 <span data-ttu-id="7f8c3-127">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7f8c3-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f8c3-128">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="7f8c3-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7f8c3-129">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7f8c3-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7f8c3-130">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f8c3-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f8c3-131">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="7f8c3-131">See also</span></span>

- <xref:System.AppDomain>
- <xref:System.AppDomainManager>
- [<span data-ttu-id="7f8c3-132">ICLRRuntimeHost — Interfejs</span><span class="sxs-lookup"><span data-stu-id="7f8c3-132">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
