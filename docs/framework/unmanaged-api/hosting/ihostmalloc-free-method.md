---
title: IHostMAlloc::Free — Metoda
ms.date: 03/30/2017
api_name:
- IHostMAlloc.Free
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMAlloc::Free
helpviewer_keywords:
- IHostMAlloc::Free method [.NET Framework hosting]
- Free method, IHostMAlloc interface [.NET Framework hosting]
ms.assetid: c89abf5b-1120-4437-8b57-4a99fb3ae7f9
topic_type:
- apiref
ms.openlocfilehash: d4c9048c89d55ed048a55a771572823905a056df
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687141"
---
# <a name="ihostmallocfree-method"></a><span data-ttu-id="cd8d2-102">IHostMAlloc::Free — Metoda</span><span class="sxs-lookup"><span data-stu-id="cd8d2-102">IHostMAlloc::Free Method</span></span>

<span data-ttu-id="cd8d2-103">Zwalnia pamięć przydzieloną przy użyciu funkcji [Alloc](ihostmalloc-alloc-method.md) .</span><span class="sxs-lookup"><span data-stu-id="cd8d2-103">Frees memory that was allocated by using the [Alloc](ihostmalloc-alloc-method.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd8d2-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="cd8d2-104">Syntax</span></span>  
  
```cpp  
HRESULT Free (  
    [in] void* pMem  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cd8d2-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="cd8d2-105">Parameters</span></span>  

 `pMem`  
 <span data-ttu-id="cd8d2-106">podczas Wskaźnik do pamięci, która ma zostać zwolniona.</span><span class="sxs-lookup"><span data-stu-id="cd8d2-106">[in] A pointer to the memory to be freed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cd8d2-107">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="cd8d2-107">Return Value</span></span>  
  
|<span data-ttu-id="cd8d2-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cd8d2-108">HRESULT</span></span>|<span data-ttu-id="cd8d2-109">Opis</span><span class="sxs-lookup"><span data-stu-id="cd8d2-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cd8d2-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="cd8d2-110">S_OK</span></span>|<span data-ttu-id="cd8d2-111">`Free` pomyślnie zwrócono.</span><span class="sxs-lookup"><span data-stu-id="cd8d2-111">`Free` returned successfully.</span></span>|  
|<span data-ttu-id="cd8d2-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="cd8d2-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="cd8d2-113">Środowisko uruchomieniowe języka wspólnego (CLR) nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="cd8d2-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="cd8d2-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="cd8d2-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="cd8d2-115">Upłynął limit czasu połączenia.</span><span class="sxs-lookup"><span data-stu-id="cd8d2-115">The call timed out.</span></span>|  
|<span data-ttu-id="cd8d2-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="cd8d2-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="cd8d2-117">Obiekt wywołujący nie jest właocicielem blokady.</span><span class="sxs-lookup"><span data-stu-id="cd8d2-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="cd8d2-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="cd8d2-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="cd8d2-119">Zdarzenie zostało anulowane podczas oczekiwania na niego zablokowanego wątku lub włókna.</span><span class="sxs-lookup"><span data-stu-id="cd8d2-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="cd8d2-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="cd8d2-120">E_FAIL</span></span>|<span data-ttu-id="cd8d2-121">Wystąpił nieznany błąd krytyczny.</span><span class="sxs-lookup"><span data-stu-id="cd8d2-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="cd8d2-122">Gdy metoda zwraca E_FAIL, środowisko CLR nie będzie już można używać w procesie.</span><span class="sxs-lookup"><span data-stu-id="cd8d2-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="cd8d2-123">Kolejne wywołania metod hostingu zwracają HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="cd8d2-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="cd8d2-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="cd8d2-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="cd8d2-125">Podjęto próbę zwolnienia pamięci, która nie została przyalokowana przez hosta.</span><span class="sxs-lookup"><span data-stu-id="cd8d2-125">An attempt was made to free memory that was not allocated through the host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cd8d2-126">Uwagi</span><span class="sxs-lookup"><span data-stu-id="cd8d2-126">Remarks</span></span>  

 <span data-ttu-id="cd8d2-127">Jeśli `pMem` parametr odnosi się do regionu pamięci, który nie został przydzielony przy użyciu wywołania do `Alloc` , host powinien zwrócić HOST_E_INVALIDOPERATION.</span><span class="sxs-lookup"><span data-stu-id="cd8d2-127">If the `pMem` parameter refers to a region of memory that was not allocated by using a call to `Alloc`, the host should return HOST_E_INVALIDOPERATION.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd8d2-128">Wymagania</span><span class="sxs-lookup"><span data-stu-id="cd8d2-128">Requirements</span></span>  

 <span data-ttu-id="cd8d2-129">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cd8d2-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd8d2-130">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="cd8d2-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cd8d2-131">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cd8d2-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cd8d2-132">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd8d2-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd8d2-133">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="cd8d2-133">See also</span></span>

- [<span data-ttu-id="cd8d2-134">IHostMemoryManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="cd8d2-134">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
- [<span data-ttu-id="cd8d2-135">IHostMalloc — Interfejs</span><span class="sxs-lookup"><span data-stu-id="cd8d2-135">IHostMalloc Interface</span></span>](ihostmalloc-interface.md)
