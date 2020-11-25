---
title: IHostCrst::TryEnter — Metoda
ms.date: 03/30/2017
api_name:
- IHostCrst.TryEnter
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst::TryEnter
helpviewer_keywords:
- IHostCrst::TryEnter method [.NET Framework hosting]
- TryEnter method [.NET Framework hosting]
ms.assetid: a922fa98-beab-4f09-a342-cc94fc65687f
topic_type:
- apiref
ms.openlocfilehash: 02f36068f12bf0a40e5f0ac477803abfb84c72a9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729541"
---
# <a name="ihostcrsttryenter-method"></a><span data-ttu-id="0ace2-102">IHostCrst::TryEnter — Metoda</span><span class="sxs-lookup"><span data-stu-id="0ace2-102">IHostCrst::TryEnter Method</span></span>

<span data-ttu-id="0ace2-103">Próbuje wprowadzić sekcję krytyczną reprezentowaną przez bieżące wystąpienie [IHostCrst](ihostcrst-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="0ace2-103">Attempts to enter the critical section represented by the current [IHostCrst](ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ace2-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="0ace2-104">Syntax</span></span>  
  
```cpp  
HRESULT TryEnter (  
    [in]  DWORD  option,  
    [out] BOOL   *pbSucceeded  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0ace2-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="0ace2-105">Parameters</span></span>  

 `option`  
 <span data-ttu-id="0ace2-106">podczas Jeden z wartości [WAIT_OPTION](wait-option-enumeration.md) , wskazujący, jaka akcja powinna zostać podjęta przez hosta, jeśli operacja jest blokowana.</span><span class="sxs-lookup"><span data-stu-id="0ace2-106">[in] One of the [WAIT_OPTION](wait-option-enumeration.md) values, indicating what action the host should take if the operation blocks.</span></span>  
  
 `pbSucceeded`  
 <span data-ttu-id="0ace2-107">[out] `true` Jeśli można wprowadzić sekcję krytyczną; w przeciwnym razie `false` .</span><span class="sxs-lookup"><span data-stu-id="0ace2-107">[out] `true` if the critical section can be entered; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0ace2-108">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="0ace2-108">Return Value</span></span>  
  
|<span data-ttu-id="0ace2-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0ace2-109">HRESULT</span></span>|<span data-ttu-id="0ace2-110">Opis</span><span class="sxs-lookup"><span data-stu-id="0ace2-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0ace2-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="0ace2-111">S_OK</span></span>|<span data-ttu-id="0ace2-112">`TryEnter` pomyślnie zwrócono.</span><span class="sxs-lookup"><span data-stu-id="0ace2-112">`TryEnter` returned successfully.</span></span>|  
|<span data-ttu-id="0ace2-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0ace2-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0ace2-114">Środowisko uruchomieniowe języka wspólnego (CLR) nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="0ace2-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0ace2-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0ace2-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0ace2-116">Upłynął limit czasu połączenia.</span><span class="sxs-lookup"><span data-stu-id="0ace2-116">The call timed out.</span></span>|  
|<span data-ttu-id="0ace2-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0ace2-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0ace2-118">Obiekt wywołujący nie jest właocicielem blokady.</span><span class="sxs-lookup"><span data-stu-id="0ace2-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0ace2-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0ace2-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0ace2-120">Zdarzenie zostało anulowane podczas oczekiwania na niego zablokowanego wątku lub włókna.</span><span class="sxs-lookup"><span data-stu-id="0ace2-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0ace2-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0ace2-121">E_FAIL</span></span>|<span data-ttu-id="0ace2-122">Wystąpił nieznany błąd krytyczny.</span><span class="sxs-lookup"><span data-stu-id="0ace2-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0ace2-123">Gdy metoda zwraca E_FAIL, środowisko CLR nie będzie już można używać w procesie.</span><span class="sxs-lookup"><span data-stu-id="0ace2-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0ace2-124">Kolejne wywołania metod hostingu zwracają HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="0ace2-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0ace2-125">Uwagi</span><span class="sxs-lookup"><span data-stu-id="0ace2-125">Remarks</span></span>  

 <span data-ttu-id="0ace2-126">`TryEnter` zwraca natychmiast i wskazuje, czy wywołujący wątek wszedł do sekcji krytycznej.</span><span class="sxs-lookup"><span data-stu-id="0ace2-126">`TryEnter` returns immediately and indicates whether the calling thread entered the critical section.</span></span> <span data-ttu-id="0ace2-127">Ta metoda odzwierciedla funkcję Wind32 `TryEnterCriticalSection` .</span><span class="sxs-lookup"><span data-stu-id="0ace2-127">This method mirrors the Wind32 `TryEnterCriticalSection` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ace2-128">Wymagania</span><span class="sxs-lookup"><span data-stu-id="0ace2-128">Requirements</span></span>  

 <span data-ttu-id="0ace2-129">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ace2-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ace2-130">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="0ace2-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0ace2-131">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0ace2-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0ace2-132">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ace2-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ace2-133">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="0ace2-133">See also</span></span>

- [<span data-ttu-id="0ace2-134">ICLRSyncManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="0ace2-134">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="0ace2-135">IHostCrst — Interfejs</span><span class="sxs-lookup"><span data-stu-id="0ace2-135">IHostCrst Interface</span></span>](ihostcrst-interface.md)
- [<span data-ttu-id="0ace2-136">IHostSyncManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="0ace2-136">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
