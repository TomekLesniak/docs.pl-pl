---
title: IHostIoCompletionManager::InitializeHostOverlapped — Metoda
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.InitializeHostOverlapped
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::InitializeHostOverlapped
helpviewer_keywords:
- IHostIoCompletionManager::InitializeHostOverlapped method [.NET Framework hosting]
- InitializeHostOverlapped method [.NET Framework hosting]
ms.assetid: c35199bf-bc47-4901-b467-4e8a37644bbb
topic_type:
- apiref
ms.openlocfilehash: 397dbbeb0b85cb549a8b5917f977ecb13b3d6539
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720220"
---
# <a name="ihostiocompletionmanagerinitializehostoverlapped-method"></a><span data-ttu-id="142b4-102">IHostIoCompletionManager::InitializeHostOverlapped — Metoda</span><span class="sxs-lookup"><span data-stu-id="142b4-102">IHostIoCompletionManager::InitializeHostOverlapped Method</span></span>

<span data-ttu-id="142b4-103">Udostępnia hostowi możliwość zainicjowania dowolnych danych niestandardowych w celu dołączenia do `OVERLAPPED` struktury Win32, która jest używana na potrzeby asynchronicznych żądań we/wy.</span><span class="sxs-lookup"><span data-stu-id="142b4-103">Provides the host with an opportunity to initialize any custom data to append to a Win32 `OVERLAPPED` structure that is used for asynchronous I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="142b4-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="142b4-104">Syntax</span></span>  
  
```cpp  
HRESULT InitializeHostOverlapped (  
    [in] void* pvOverlapped  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="142b4-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="142b4-105">Parameters</span></span>  

 `pvOverlapped`  
 <span data-ttu-id="142b4-106">podczas Wskaźnik do struktury Win32, `OVERLAPPED` który ma zostać dołączony do żądania we/wy.</span><span class="sxs-lookup"><span data-stu-id="142b4-106">[in] A pointer to the Win32 `OVERLAPPED` structure to be included with the I/O request.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="142b4-107">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="142b4-107">Return Value</span></span>  
  
|<span data-ttu-id="142b4-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="142b4-108">HRESULT</span></span>|<span data-ttu-id="142b4-109">Opis</span><span class="sxs-lookup"><span data-stu-id="142b4-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="142b4-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="142b4-110">S_OK</span></span>|<span data-ttu-id="142b4-111">`InitializeHostOverlapped` pomyślnie zwrócono.</span><span class="sxs-lookup"><span data-stu-id="142b4-111">`InitializeHostOverlapped` returned successfully.</span></span>|  
|<span data-ttu-id="142b4-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="142b4-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="142b4-113">Środowisko uruchomieniowe języka wspólnego (CLR) nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="142b4-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="142b4-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="142b4-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="142b4-115">Upłynął limit czasu połączenia.</span><span class="sxs-lookup"><span data-stu-id="142b4-115">The call timed out.</span></span>|  
|<span data-ttu-id="142b4-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="142b4-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="142b4-117">Obiekt wywołujący nie jest właocicielem blokady.</span><span class="sxs-lookup"><span data-stu-id="142b4-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="142b4-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="142b4-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="142b4-119">Zdarzenie zostało anulowane podczas oczekiwania na niego zablokowanego wątku lub włókna.</span><span class="sxs-lookup"><span data-stu-id="142b4-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="142b4-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="142b4-120">E_FAIL</span></span>|<span data-ttu-id="142b4-121">Wystąpił nieznany błąd krytyczny.</span><span class="sxs-lookup"><span data-stu-id="142b4-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="142b4-122">Gdy metoda zwraca E_FAIL, środowisko CLR nie będzie już można używać w procesie.</span><span class="sxs-lookup"><span data-stu-id="142b4-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="142b4-123">Kolejne wywołania metod hostingu zwracają HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="142b4-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="142b4-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="142b4-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="142b4-125">Za mało dostępnej pamięci, aby przydzielić żądany zasób.</span><span class="sxs-lookup"><span data-stu-id="142b4-125">Not enough memory was available to allocate the requested resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="142b4-126">Uwagi</span><span class="sxs-lookup"><span data-stu-id="142b4-126">Remarks</span></span>  

 <span data-ttu-id="142b4-127">Funkcje platformy systemu Windows używają `OVERLAPPED` struktury do przechowywania stanu asynchronicznych żądań we/wy.</span><span class="sxs-lookup"><span data-stu-id="142b4-127">The Windows Platform functions use the `OVERLAPPED` structure to store state for asynchronous I/O requests.</span></span> <span data-ttu-id="142b4-128">Środowisko CLR wywołuje `InitializeHostOverlapped` metodę, aby umożliwić hostowi dołączenie danych niestandardowych do `OVERLAPPED` wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="142b4-128">The CLR calls the `InitializeHostOverlapped` method to give the host the opportunity to append custom data to an `OVERLAPPED` instance.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="142b4-129">Aby przejść do początku swojego niestandardowego bloku danych, hosty muszą ustawić przesunięcie na rozmiar `OVERLAPPED` struktury ( `sizeof(OVERLAPPED)` ).</span><span class="sxs-lookup"><span data-stu-id="142b4-129">To get to the beginning of their custom data block, hosts must set the offset to the size of the `OVERLAPPED` structure (`sizeof(OVERLAPPED)`).</span></span>  
  
 <span data-ttu-id="142b4-130">Wartość zwracana E_OUTOFMEMORY wskazuje, że host nie zainicjuje swoich niestandardowych danych.</span><span class="sxs-lookup"><span data-stu-id="142b4-130">A return value of E_OUTOFMEMORY indicates that the host has failed to initialize its custom data.</span></span> <span data-ttu-id="142b4-131">W takim przypadku środowisko CLR zgłasza błąd i nie wywołuje wywołania.</span><span class="sxs-lookup"><span data-stu-id="142b4-131">In this case, the CLR reports an error and fails the call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="142b4-132">Wymagania</span><span class="sxs-lookup"><span data-stu-id="142b4-132">Requirements</span></span>  

 <span data-ttu-id="142b4-133">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="142b4-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="142b4-134">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="142b4-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="142b4-135">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="142b4-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="142b4-136">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="142b4-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="142b4-137">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="142b4-137">See also</span></span>

- [<span data-ttu-id="142b4-138">ICLRIoCompletionManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="142b4-138">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="142b4-139">GetHostOverlappedSize, metoda</span><span class="sxs-lookup"><span data-stu-id="142b4-139">GetHostOverlappedSize Method</span></span>](ihostiocompletionmanager-gethostoverlappedsize-method.md)
- [<span data-ttu-id="142b4-140">IHostIoCompletionManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="142b4-140">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
