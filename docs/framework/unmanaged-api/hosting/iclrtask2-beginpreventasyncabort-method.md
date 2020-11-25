---
title: ICLRTask2::BeginPreventAsyncAbort — Metoda
ms.date: 03/30/2017
api_name:
- ICLRTask2.BeginPreventAsyncAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask2::BeginPreventAsyncAbort
helpviewer_keywords:
- ICLRTask2::BeginPreventAsyncAbort method [.NET Framework hosting]
- BeginPreventAsyncAbort method [.NET Framework hosting]
ms.assetid: 75754c2f-38c7-4707-85fe-559db4542729
topic_type:
- apiref
ms.openlocfilehash: daf211fcc496f63ef71575abf6a28655004db264
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720246"
---
# <a name="iclrtask2beginpreventasyncabort-method"></a><span data-ttu-id="790aa-102">ICLRTask2::BeginPreventAsyncAbort — Metoda</span><span class="sxs-lookup"><span data-stu-id="790aa-102">ICLRTask2::BeginPreventAsyncAbort Method</span></span>

<span data-ttu-id="790aa-103">Opóźnia nowe żądania przerwania wątku z wyniku przerwania wątku w bieżącym wątku.</span><span class="sxs-lookup"><span data-stu-id="790aa-103">Delays new thread abort requests from resulting in thread aborts on the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="790aa-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="790aa-104">Syntax</span></span>  
  
```cpp  
HRESULT BeginPreventAsyncAbort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="790aa-105">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="790aa-105">Return Value</span></span>  

 <span data-ttu-id="790aa-106">Ta metoda zwraca następujące określone wartości HRESULT oraz błędy HRESULT wskazujące niepowodzenie metody.</span><span class="sxs-lookup"><span data-stu-id="790aa-106">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="790aa-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="790aa-107">HRESULT</span></span>|<span data-ttu-id="790aa-108">Opis</span><span class="sxs-lookup"><span data-stu-id="790aa-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="790aa-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="790aa-109">S_OK</span></span>|<span data-ttu-id="790aa-110">Metoda została ukończona pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="790aa-110">The method completed successfully.</span></span>|  
|<span data-ttu-id="790aa-111">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="790aa-111">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="790aa-112">Metoda została wywołana w wątku, który nie jest bieżącym wątkiem.</span><span class="sxs-lookup"><span data-stu-id="790aa-112">The method was called on a thread which is not the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="790aa-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="790aa-113">Remarks</span></span>  

 <span data-ttu-id="790aa-114">Wywołanie tej metody zwiększa licznik Opóźnij wątek wątku dla bieżącego wątku o jeden.</span><span class="sxs-lookup"><span data-stu-id="790aa-114">Calling this method increments the delay-thread-abort counter for the current thread by one.</span></span>  
  
 <span data-ttu-id="790aa-115">Wywołania `BeginPreventAsyncAbort` i [ICLRTask2:: EndPreventAsyncAbort —](iclrtask2-endpreventasyncabort-method.md) mogą być zagnieżdżane.</span><span class="sxs-lookup"><span data-stu-id="790aa-115">Calls to `BeginPreventAsyncAbort` and [ICLRTask2::EndPreventAsyncAbort](iclrtask2-endpreventasyncabort-method.md) can be nested.</span></span> <span data-ttu-id="790aa-116">Tak długo, jak licznik jest większy od zera, przerwania wątku dla bieżącego wątku są opóźnione.</span><span class="sxs-lookup"><span data-stu-id="790aa-116">As long as the counter is greater than zero, thread aborts for the current thread are delayed.</span></span> <span data-ttu-id="790aa-117">Jeśli to wywołanie nie jest sparowane z wywołaniem `EndPreventAsyncAbort` metody, można dotrzeć do stanu, w którym przerwania wątku nie można dostarczyć do bieżącego wątku.</span><span class="sxs-lookup"><span data-stu-id="790aa-117">If this call is not paired with a call to the `EndPreventAsyncAbort` method, it is possible to reach a state in which thread aborts cannot be delivered to the current thread.</span></span>  
  
 <span data-ttu-id="790aa-118">Opóźnienie nie jest uznawane za wątek, który przerywa siebie.</span><span class="sxs-lookup"><span data-stu-id="790aa-118">The delay is not honored for a thread that aborts itself.</span></span>  
  
 <span data-ttu-id="790aa-119">Funkcja, która jest udostępniona przez tę funkcję, jest używana wewnętrznie przez maszynę wirtualną (VM).</span><span class="sxs-lookup"><span data-stu-id="790aa-119">The functionality that is exposed by this feature is used internally by the virtual machine (VM).</span></span> <span data-ttu-id="790aa-120">Użycie tych metod może spowodować nieokreślone zachowanie maszyny wirtualnej.</span><span class="sxs-lookup"><span data-stu-id="790aa-120">Misuse of these methods may cause unspecified behavior in the VM.</span></span> <span data-ttu-id="790aa-121">Na przykład wywołanie `EndPreventAsyncAbort` bez pierwszego wywołania `BeginPreventAsyncAbort` może spowodować ustawienie wartości zero dla licznika, gdy maszyna wirtualna została wcześniej zwiększona.</span><span class="sxs-lookup"><span data-stu-id="790aa-121">For example, calling `EndPreventAsyncAbort` without first calling `BeginPreventAsyncAbort` could set the counter to zero when the VM has previously incremented it.</span></span> <span data-ttu-id="790aa-122">Podobnie licznik wewnętrzny nie jest sprawdzany pod kątem przepełnienia.</span><span class="sxs-lookup"><span data-stu-id="790aa-122">Similarly, the internal counter is not checked for overflow.</span></span> <span data-ttu-id="790aa-123">W przypadku przekroczenia limitu całkowitego, ponieważ jest zwiększana przez zarówno hosta, jak i maszynę wirtualną, zachowanie nie zostanie określone.</span><span class="sxs-lookup"><span data-stu-id="790aa-123">If it exceeds its integral limit because it is incremented by both the host and the VM, the resulting behavior is unspecified.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="790aa-124">Wymagania</span><span class="sxs-lookup"><span data-stu-id="790aa-124">Requirements</span></span>  

 <span data-ttu-id="790aa-125">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="790aa-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="790aa-126">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="790aa-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="790aa-127">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="790aa-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="790aa-128">**.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="790aa-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="790aa-129">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="790aa-129">See also</span></span>

- [<span data-ttu-id="790aa-130">EndPreventAsyncAbort, metoda</span><span class="sxs-lookup"><span data-stu-id="790aa-130">EndPreventAsyncAbort Method</span></span>](iclrtask2-endpreventasyncabort-method.md)
- [<span data-ttu-id="790aa-131">ICLRTask2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="790aa-131">ICLRTask2 Interface</span></span>](iclrtask2-interface.md)
- [<span data-ttu-id="790aa-132">ICLRTaskManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="790aa-132">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="790aa-133">IHostTask — Interfejs</span><span class="sxs-lookup"><span data-stu-id="790aa-133">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="790aa-134">IHostTaskManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="790aa-134">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="790aa-135">Hosting — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="790aa-135">Hosting Interfaces</span></span>](hosting-interfaces.md)
