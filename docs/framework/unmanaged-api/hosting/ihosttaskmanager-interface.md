---
title: IHostTaskManager — Interfejs
ms.date: 03/30/2017
api_name:
- IHostTaskManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager
helpviewer_keywords:
- IHostTaskManager interface [.NET Framework hosting]
ms.assetid: 4a0b05b9-3ef1-4607-b7c8-bd4dd43647a0
topic_type:
- apiref
ms.openlocfilehash: deb14d291bfd511e8f3534f3c5e32787c259c5e8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673114"
---
# <a name="ihosttaskmanager-interface"></a><span data-ttu-id="8a17d-102">IHostTaskManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="8a17d-102">IHostTaskManager Interface</span></span>

<span data-ttu-id="8a17d-103">Zapewnia metody, które umożliwiają środowisko uruchomieniowe języka wspólnego (CLR) do pracy z zadaniami za pośrednictwem hosta zamiast korzystania ze standardowego wątku lub funkcji światłowodowych systemu operacyjnego.</span><span class="sxs-lookup"><span data-stu-id="8a17d-103">Provides methods that allow the common language runtime (CLR) to work with tasks through the host instead of using the standard operating system threading or fiber functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8a17d-104">Metody</span><span class="sxs-lookup"><span data-stu-id="8a17d-104">Methods</span></span>  
  
|<span data-ttu-id="8a17d-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="8a17d-105">Method</span></span>|<span data-ttu-id="8a17d-106">Opis</span><span class="sxs-lookup"><span data-stu-id="8a17d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8a17d-107">BeginDelayAbort, metoda</span><span class="sxs-lookup"><span data-stu-id="8a17d-107">BeginDelayAbort Method</span></span>](ihosttaskmanager-begindelayabort-method.md)|<span data-ttu-id="8a17d-108">Powiadamia hosta, że kod zarządzany wprowadza okres, w którym bieżące zadanie nie może zostać przerwane.</span><span class="sxs-lookup"><span data-stu-id="8a17d-108">Notifies the host that managed code is entering a period in which the current task must not be aborted.</span></span>|  
|[<span data-ttu-id="8a17d-109">BeginThreadAffinity, metoda</span><span class="sxs-lookup"><span data-stu-id="8a17d-109">BeginThreadAffinity Method</span></span>](ihosttaskmanager-beginthreadaffinity-method.md)|<span data-ttu-id="8a17d-110">Powiadamia hosta, że kod zarządzany wprowadza okres, w którym bieżące zadanie nie może zostać przeniesione do innego wątku systemu operacyjnego.</span><span class="sxs-lookup"><span data-stu-id="8a17d-110">Notifies the host that managed code is entering a period in which the current task must not be moved to another operating system thread.</span></span>|  
|[<span data-ttu-id="8a17d-111">CallNeedsHostHook, metoda</span><span class="sxs-lookup"><span data-stu-id="8a17d-111">CallNeedsHostHook Method</span></span>](ihosttaskmanager-callneedshosthook-method.md)|<span data-ttu-id="8a17d-112">Umożliwia hostowi określenie, czy środowisko uruchomieniowe języka wspólnego może być wbudowane w określone wywołanie do niezarządzanej funkcji.</span><span class="sxs-lookup"><span data-stu-id="8a17d-112">Enables the host to specify whether the common language runtime can inline the specified call to an unmanaged function.</span></span>|  
|[<span data-ttu-id="8a17d-113">CreateTask — Metoda</span><span class="sxs-lookup"><span data-stu-id="8a17d-113">CreateTask Method</span></span>](ihosttaskmanager-createtask-method.md)|<span data-ttu-id="8a17d-114">Żąda utworzenia nowego zadania przez hosta.</span><span class="sxs-lookup"><span data-stu-id="8a17d-114">Requests that the host create a new task.</span></span>|  
|[<span data-ttu-id="8a17d-115">EndDelayAbort, metoda</span><span class="sxs-lookup"><span data-stu-id="8a17d-115">EndDelayAbort Method</span></span>](ihosttaskmanager-enddelayabort-method.md)|<span data-ttu-id="8a17d-116">Powiadamia hosta, że kod zarządzany kończy okres, w którym bieżące zadanie nie może zostać przerwane, po wcześniejszym wywołaniu `BeginDelayAbort` .</span><span class="sxs-lookup"><span data-stu-id="8a17d-116">Notifies the host that managed code is exiting the period in which the current task must not be aborted, following an earlier call to `BeginDelayAbort`.</span></span>|  
|[<span data-ttu-id="8a17d-117">EndThreadAffinity, metoda</span><span class="sxs-lookup"><span data-stu-id="8a17d-117">EndThreadAffinity Method</span></span>](ihosttaskmanager-endthreadaffinity-method.md)|<span data-ttu-id="8a17d-118">Powiadamia hosta, że kod zarządzany kończy okres, w którym bieżące zadanie nie może zostać przeniesione do innego wątku systemu operacyjnego, po wcześniejszym wywołaniu `BeginThreadAffinity` .</span><span class="sxs-lookup"><span data-stu-id="8a17d-118">Notifies the host that managed code is exiting the period in which the current task must not be moved to another operating system thread, following an earlier call to `BeginThreadAffinity`.</span></span>|  
|[<span data-ttu-id="8a17d-119">EnterRuntime, metoda</span><span class="sxs-lookup"><span data-stu-id="8a17d-119">EnterRuntime Method</span></span>](ihosttaskmanager-enterruntime-method.md)|<span data-ttu-id="8a17d-120">Powiadamia hosta, że wywołanie metody niezarządzanej, takie jak metoda Invoke platformy, zwraca sterowanie wykonywaniem do środowiska CLR.</span><span class="sxs-lookup"><span data-stu-id="8a17d-120">Notifies the host that a call to an unmanaged method, such as a platform invoke method, is returning execution control to the CLR.</span></span>|  
|[<span data-ttu-id="8a17d-121">GetCurrentTask, metoda</span><span class="sxs-lookup"><span data-stu-id="8a17d-121">GetCurrentTask Method</span></span>](ihosttaskmanager-getcurrenttask-method.md)|<span data-ttu-id="8a17d-122">Pobiera wskaźnik interfejsu do zadania, które jest aktualnie wykonywane w wątku systemu operacyjnego, z którego wykonano to wywołanie.</span><span class="sxs-lookup"><span data-stu-id="8a17d-122">Gets an interface pointer to the task that is currently executing on the operating system thread from which this call is made.</span></span>|  
|[<span data-ttu-id="8a17d-123">GetStackGuarantee, metoda</span><span class="sxs-lookup"><span data-stu-id="8a17d-123">GetStackGuarantee Method</span></span>](ihosttaskmanager-getstackguarantee-method.md)|<span data-ttu-id="8a17d-124">Pobiera ilość miejsca na stosie, która ma być dostępna po zakończeniu operacji stosu, ale przed zamknięciem procesu.</span><span class="sxs-lookup"><span data-stu-id="8a17d-124">Gets the amount of stack space that is guaranteed to be available after a stack operation completes, but before the closing of a process.</span></span>|  
|[<span data-ttu-id="8a17d-125">LeaveRuntime, metoda</span><span class="sxs-lookup"><span data-stu-id="8a17d-125">LeaveRuntime Method</span></span>](ihosttaskmanager-leaveruntime-method.md)|<span data-ttu-id="8a17d-126">Powiadamia hosta, że kod zarządzany ma nawiązać wywołanie funkcji niezarządzanej.</span><span class="sxs-lookup"><span data-stu-id="8a17d-126">Notifies the host that managed code is about to make a call to an unmanaged function.</span></span>|  
|[<span data-ttu-id="8a17d-127">ReverseEnterRuntime, metoda</span><span class="sxs-lookup"><span data-stu-id="8a17d-127">ReverseEnterRuntime Method</span></span>](ihosttaskmanager-reverseenterruntime-method.md)|<span data-ttu-id="8a17d-128">Powiadamia hosta, że wywołanie jest nawiązywane w środowisku uruchomieniowym języka wspólnego (CLR) z kodu niezarządzanego.</span><span class="sxs-lookup"><span data-stu-id="8a17d-128">Notifies the host that a call is being made into the common language runtime (CLR) from unmanaged code.</span></span>|  
|[<span data-ttu-id="8a17d-129">ReverseLeaveRuntime, metoda</span><span class="sxs-lookup"><span data-stu-id="8a17d-129">ReverseLeaveRuntime Method</span></span>](ihosttaskmanager-reverseleaveruntime-method.md)|<span data-ttu-id="8a17d-130">Powiadamia hosta, że kontrola opuszcza środowisko CLR i wprowadza niezarządzaną funkcję, która była z kolei wywoływana z kodu zarządzanego.</span><span class="sxs-lookup"><span data-stu-id="8a17d-130">Notifies the host that control is leaving the CLR and entering an unmanaged function that was, in turn, called from managed code.</span></span>|  
|[<span data-ttu-id="8a17d-131">SetCLRTaskManager, metoda</span><span class="sxs-lookup"><span data-stu-id="8a17d-131">SetCLRTaskManager Method</span></span>](ihosttaskmanager-setclrtaskmanager-method.md)|<span data-ttu-id="8a17d-132">Dostarcza host ze wskaźnikiem interfejsu do wystąpienia [ICLRTaskManager](iclrtaskmanager-interface.md) zaimplementowanego przez środowisko CLR.</span><span class="sxs-lookup"><span data-stu-id="8a17d-132">Provides the host with an interface pointer to an [ICLRTaskManager](iclrtaskmanager-interface.md) instance implemented by the CLR.</span></span>|  
|[<span data-ttu-id="8a17d-133">SetLocale, metoda</span><span class="sxs-lookup"><span data-stu-id="8a17d-133">SetLocale Method</span></span>](ihosttaskmanager-setlocale-method.md)|<span data-ttu-id="8a17d-134">Powiadamia hosta o zmianie ustawień regionalnych przez środowisko CLR w bieżącym zadaniu.</span><span class="sxs-lookup"><span data-stu-id="8a17d-134">Notifies the host that the CLR has changed the locale on the current task.</span></span>|  
|[<span data-ttu-id="8a17d-135">SetStackGuarantee, metoda</span><span class="sxs-lookup"><span data-stu-id="8a17d-135">SetStackGuarantee Method</span></span>](ihosttaskmanager-setstackguarantee-method.md)|<span data-ttu-id="8a17d-136">Zarezerwowane wyłącznie do użytku wewnętrznego.</span><span class="sxs-lookup"><span data-stu-id="8a17d-136">Reserved for internal use only.</span></span>|  
|[<span data-ttu-id="8a17d-137">SetUILocale, metoda</span><span class="sxs-lookup"><span data-stu-id="8a17d-137">SetUILocale Method</span></span>](ihosttaskmanager-setuilocale-method.md)|<span data-ttu-id="8a17d-138">Powiadamia hosta, że ustawienia regionalne interfejsu użytkownika zostały zmienione w bieżącym zadaniu.</span><span class="sxs-lookup"><span data-stu-id="8a17d-138">Notifies the host that the user interface locale has been changed on the current task.</span></span>|  
|[<span data-ttu-id="8a17d-139">Sleep, metoda</span><span class="sxs-lookup"><span data-stu-id="8a17d-139">Sleep Method</span></span>](ihosttaskmanager-sleep-method.md)|<span data-ttu-id="8a17d-140">Powiadamia hosta, że bieżące zadanie przechodzi w stan uśpienia.</span><span class="sxs-lookup"><span data-stu-id="8a17d-140">Notifies the host that the current task is going to sleep.</span></span>|  
|[<span data-ttu-id="8a17d-141">SwitchToTask, metoda</span><span class="sxs-lookup"><span data-stu-id="8a17d-141">SwitchToTask Method</span></span>](ihosttaskmanager-switchtotask-method.md)|<span data-ttu-id="8a17d-142">Powiadamia hosta o konieczności przełączenia bieżącego zadania.</span><span class="sxs-lookup"><span data-stu-id="8a17d-142">Notifies the host that it should switch out the current task.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8a17d-143">Uwagi</span><span class="sxs-lookup"><span data-stu-id="8a17d-143">Remarks</span></span>  

 <span data-ttu-id="8a17d-144">`IHostTaskManager` umożliwia środowisku CLR tworzenie zadań i zarządzanie nimi, w celu zapewnienia podpunktów dla hosta do podjęcia działania podczas kontroli transferu z zarządzanego do kodu niezarządzanego i na odwrót oraz do określania pewnych akcji, które host może i nie może wykonać podczas wykonywania kodu.</span><span class="sxs-lookup"><span data-stu-id="8a17d-144">`IHostTaskManager` allows the CLR to create and manage tasks, to provide hooks for the host to take action when control transfers from managed to unmanaged code and vice versa, and to specify certain actions the host can and cannot take during code execution.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a17d-145">Wymagania</span><span class="sxs-lookup"><span data-stu-id="8a17d-145">Requirements</span></span>  

 <span data-ttu-id="8a17d-146">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a17d-146">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a17d-147">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="8a17d-147">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8a17d-148">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8a17d-148">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8a17d-149">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a17d-149">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a17d-150">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="8a17d-150">See also</span></span>

- [<span data-ttu-id="8a17d-151">ICLRTask — Interfejs</span><span class="sxs-lookup"><span data-stu-id="8a17d-151">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="8a17d-152">ICLRTaskManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="8a17d-152">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="8a17d-153">IHostTask — Interfejs</span><span class="sxs-lookup"><span data-stu-id="8a17d-153">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="8a17d-154">Hosting — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="8a17d-154">Hosting Interfaces</span></span>](hosting-interfaces.md)
