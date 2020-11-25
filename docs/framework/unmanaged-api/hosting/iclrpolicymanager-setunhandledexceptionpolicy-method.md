---
title: ICLRPolicyManager::SetUnhandledExceptionPolicy — Metoda
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetUnhandledExceptionPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetUnhandledExceptionPolicy
helpviewer_keywords:
- ICLRPolicyManager::SetUnhandledExceptionPolicy method [.NET Framework hosting]
- SetUnhandledExceptionPolicy method [.NET Framework hosting]
ms.assetid: 5268480e-280a-4931-b7a3-dc3ffdf7f78f
topic_type:
- apiref
ms.openlocfilehash: 1088374c9df18ded38b44384be44de245f0bd403
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728956"
---
# <a name="iclrpolicymanagersetunhandledexceptionpolicy-method"></a><span data-ttu-id="afdc6-102">ICLRPolicyManager::SetUnhandledExceptionPolicy — Metoda</span><span class="sxs-lookup"><span data-stu-id="afdc6-102">ICLRPolicyManager::SetUnhandledExceptionPolicy Method</span></span>

<span data-ttu-id="afdc6-103">Określa zachowanie środowiska uruchomieniowego języka wspólnego (CLR) w przypadku wystąpienia nieobsługiwanego wyjątku.</span><span class="sxs-lookup"><span data-stu-id="afdc6-103">Specifies the behavior of the common language runtime (CLR) when an unhandled exception occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="afdc6-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="afdc6-104">Syntax</span></span>  
  
```cpp  
HRESULT SetUnhandledExceptionPolicy (  
    [in] EClrUnhandledExceptionPolicy policy  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="afdc6-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="afdc6-105">Parameters</span></span>  

 `policy`  
 <span data-ttu-id="afdc6-106">podczas Jedna z wartości [EClrUnhandledException —](eclrunhandledexception-enumeration.md) , wskazująca, czy zachowanie jest ustawione przez środowisko CLR czy hosta.</span><span class="sxs-lookup"><span data-stu-id="afdc6-106">[in] One of the [EClrUnhandledException](eclrunhandledexception-enumeration.md) values, indicating whether the behavior is set by the CLR or the host.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="afdc6-107">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="afdc6-107">Return Value</span></span>  
  
|<span data-ttu-id="afdc6-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="afdc6-108">HRESULT</span></span>|<span data-ttu-id="afdc6-109">Opis</span><span class="sxs-lookup"><span data-stu-id="afdc6-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="afdc6-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="afdc6-110">S_OK</span></span>|<span data-ttu-id="afdc6-111">`SetUnhandledExceptionPolicy` pomyślnie zwrócono.</span><span class="sxs-lookup"><span data-stu-id="afdc6-111">`SetUnhandledExceptionPolicy` returned successfully.</span></span>|  
|<span data-ttu-id="afdc6-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="afdc6-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="afdc6-113">Środowisko CLR nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="afdc6-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="afdc6-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="afdc6-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="afdc6-115">Upłynął limit czasu połączenia.</span><span class="sxs-lookup"><span data-stu-id="afdc6-115">The call timed out.</span></span>|  
|<span data-ttu-id="afdc6-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="afdc6-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="afdc6-117">Obiekt wywołujący nie jest właocicielem blokady.</span><span class="sxs-lookup"><span data-stu-id="afdc6-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="afdc6-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="afdc6-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="afdc6-119">Zdarzenie zostało anulowane podczas oczekiwania na niego zablokowanego wątku lub włókna.</span><span class="sxs-lookup"><span data-stu-id="afdc6-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="afdc6-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="afdc6-120">E_FAIL</span></span>|<span data-ttu-id="afdc6-121">Wystąpił nieznany błąd krytyczny.</span><span class="sxs-lookup"><span data-stu-id="afdc6-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="afdc6-122">Po powrocie metody E_FAIL nie będzie można używać środowiska CLR w procesie.</span><span class="sxs-lookup"><span data-stu-id="afdc6-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="afdc6-123">Kolejne wywołania metod hostingu zwracają HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="afdc6-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="afdc6-124">Uwagi</span><span class="sxs-lookup"><span data-stu-id="afdc6-124">Remarks</span></span>  

 <span data-ttu-id="afdc6-125">Domyślnie środowisko CLR jest ostatnim programem obsługi dla wszystkich nieobsłużonych wyjątków, a jego domyślne zachowanie polega na rozdzieleniu tego procesu.</span><span class="sxs-lookup"><span data-stu-id="afdc6-125">By default, the CLR is the final handler for all unhandled exceptions, and its default behavior is to tear down the process.</span></span> <span data-ttu-id="afdc6-126">Na hoście można zmienić to zachowanie, ustawiając `policy` wartość na eHostDeterminedPolicy.</span><span class="sxs-lookup"><span data-stu-id="afdc6-126">The host can change this behavior by setting the `policy` value to eHostDeterminedPolicy.</span></span> <span data-ttu-id="afdc6-127">Ta wartość umożliwia hostowi wdrożenie własnego zachowania domyślnego, tak jak w przypadku wcześniejszych wersji środowiska CLR.</span><span class="sxs-lookup"><span data-stu-id="afdc6-127">This value allows the host to implement its own default behavior, as with earlier versions of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="afdc6-128">Wymagania</span><span class="sxs-lookup"><span data-stu-id="afdc6-128">Requirements</span></span>  

 <span data-ttu-id="afdc6-129">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="afdc6-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="afdc6-130">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="afdc6-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="afdc6-131">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="afdc6-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="afdc6-132">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="afdc6-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afdc6-133">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="afdc6-133">See also</span></span>

- [<span data-ttu-id="afdc6-134">EClrUnhandledException — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="afdc6-134">EClrUnhandledException Enumeration</span></span>](eclrunhandledexception-enumeration.md)
- [<span data-ttu-id="afdc6-135">ICLRControl — Interfejs</span><span class="sxs-lookup"><span data-stu-id="afdc6-135">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="afdc6-136">ICLRPolicyManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="afdc6-136">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="afdc6-137">IHostPolicyManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="afdc6-137">IHostPolicyManager Interface</span></span>](ihostpolicymanager-interface.md)
