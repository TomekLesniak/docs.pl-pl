---
title: IHostCrst::Enter — Metoda
ms.date: 03/30/2017
api_name:
- IHostCrst.Enter
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst::Enter
helpviewer_keywords:
- Enter method [.NET Framework hosting]
- IHostCrst::Enter method [.NET Framework hosting]
ms.assetid: 100dd7eb-7053-4295-9bb3-32ba47f6ec79
topic_type:
- apiref
ms.openlocfilehash: a5c2646d7c9dbf8a7aea4a7fb9bd0a6b8c1d5d66
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680555"
---
# <a name="ihostcrstenter-method"></a><span data-ttu-id="5ecb5-102">IHostCrst::Enter — Metoda</span><span class="sxs-lookup"><span data-stu-id="5ecb5-102">IHostCrst::Enter Method</span></span>

<span data-ttu-id="5ecb5-103">Wprowadza sekcję krytyczną, która jest reprezentowana przez bieżące wystąpienie [IHostCrst](ihostcrst-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="5ecb5-103">Enters the critical section that is represented by the current [IHostCrst](ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ecb5-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="5ecb5-104">Syntax</span></span>  
  
```cpp  
HRESULT Enter (  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5ecb5-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="5ecb5-105">Parameters</span></span>  

 `option`  
 <span data-ttu-id="5ecb5-106">podczas Jeden z wartości [WAIT_OPTION](wait-option-enumeration.md) , wskazujący, jaka akcja powinna zostać podjęta przez hosta, jeśli operacja jest blokowana.</span><span class="sxs-lookup"><span data-stu-id="5ecb5-106">[in] One of the [WAIT_OPTION](wait-option-enumeration.md) values, indicating what action the host should take if the operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5ecb5-107">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="5ecb5-107">Return Value</span></span>  
  
|<span data-ttu-id="5ecb5-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5ecb5-108">HRESULT</span></span>|<span data-ttu-id="5ecb5-109">Opis</span><span class="sxs-lookup"><span data-stu-id="5ecb5-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5ecb5-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="5ecb5-110">S_OK</span></span>|<span data-ttu-id="5ecb5-111">`Enter` pomyślnie zwrócono.</span><span class="sxs-lookup"><span data-stu-id="5ecb5-111">`Enter` returned successfully.</span></span>|  
|<span data-ttu-id="5ecb5-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5ecb5-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5ecb5-113">Środowisko uruchomieniowe języka wspólnego (CLR) nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="5ecb5-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5ecb5-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5ecb5-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5ecb5-115">Upłynął limit czasu połączenia.</span><span class="sxs-lookup"><span data-stu-id="5ecb5-115">The call timed out.</span></span>|  
|<span data-ttu-id="5ecb5-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5ecb5-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5ecb5-117">Obiekt wywołujący nie jest właocicielem blokady.</span><span class="sxs-lookup"><span data-stu-id="5ecb5-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5ecb5-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5ecb5-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5ecb5-119">Zdarzenie zostało anulowane podczas oczekiwania na niego zablokowanego wątku lub włókna.</span><span class="sxs-lookup"><span data-stu-id="5ecb5-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5ecb5-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5ecb5-120">E_FAIL</span></span>|<span data-ttu-id="5ecb5-121">Wystąpił nieznany błąd krytyczny.</span><span class="sxs-lookup"><span data-stu-id="5ecb5-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5ecb5-122">Gdy metoda zwraca E_FAIL, środowisko CLR nie będzie już można używać w procesie.</span><span class="sxs-lookup"><span data-stu-id="5ecb5-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5ecb5-123">Kolejne wywołania metod hostingu zwracają HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="5ecb5-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5ecb5-124">Uwagi</span><span class="sxs-lookup"><span data-stu-id="5ecb5-124">Remarks</span></span>  

 <span data-ttu-id="5ecb5-125">`Enter` odzwierciedla funkcję Win32 `EnterCriticalSection` .</span><span class="sxs-lookup"><span data-stu-id="5ecb5-125">`Enter` mirrors the Win32 `EnterCriticalSection` function.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5ecb5-126">Ta metoda nie jest zwracana do momentu wprowadzenia sekcji krytycznej.</span><span class="sxs-lookup"><span data-stu-id="5ecb5-126">This method does not return until the critical section is entered.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ecb5-127">Wymagania</span><span class="sxs-lookup"><span data-stu-id="5ecb5-127">Requirements</span></span>  

 <span data-ttu-id="5ecb5-128">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ecb5-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ecb5-129">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="5ecb5-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5ecb5-130">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5ecb5-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5ecb5-131">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ecb5-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ecb5-132">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="5ecb5-132">See also</span></span>

- [<span data-ttu-id="5ecb5-133">ICLRSyncManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5ecb5-133">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="5ecb5-134">IHostCrst — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5ecb5-134">IHostCrst Interface</span></span>](ihostcrst-interface.md)
- [<span data-ttu-id="5ecb5-135">IHostSyncManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5ecb5-135">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
