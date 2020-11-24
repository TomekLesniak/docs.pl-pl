---
title: IHostSecurityManager — Interfejs
ms.date: 03/30/2017
api_name:
- IHostSecurityManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager
helpviewer_keywords:
- IHostSecurityManager interface [.NET Framework hosting]
ms.assetid: c3be2cbd-2d93-438b-9888-9a0251b63c03
topic_type:
- apiref
ms.openlocfilehash: 37f606a67bef79936c81b2a36f12a00d24bd82f1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680537"
---
# <a name="ihostsecuritymanager-interface"></a><span data-ttu-id="953d5-102">IHostSecurityManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="953d5-102">IHostSecurityManager Interface</span></span>

<span data-ttu-id="953d5-103">Zapewnia metody, które umożliwiają dostęp do i kontrolę nad kontekstem zabezpieczeń aktualnie wykonywanego wątku.</span><span class="sxs-lookup"><span data-stu-id="953d5-103">Provides methods that allow access to and control over the security context of the currently executing thread.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="953d5-104">Metody</span><span class="sxs-lookup"><span data-stu-id="953d5-104">Methods</span></span>  
  
|<span data-ttu-id="953d5-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="953d5-105">Method</span></span>|<span data-ttu-id="953d5-106">Opis</span><span class="sxs-lookup"><span data-stu-id="953d5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="953d5-107">GetSecurityContext, metoda</span><span class="sxs-lookup"><span data-stu-id="953d5-107">GetSecurityContext Method</span></span>](ihostsecuritymanager-getsecuritycontext-method.md)|<span data-ttu-id="953d5-108">Pobiera żądany [IHostSecurityContext](ihostsecuritycontext-interface.md) z hosta.</span><span class="sxs-lookup"><span data-stu-id="953d5-108">Gets the requested [IHostSecurityContext](ihostsecuritycontext-interface.md) from the host.</span></span>|  
|[<span data-ttu-id="953d5-109">ImpersonateLoggedOnUser, metoda</span><span class="sxs-lookup"><span data-stu-id="953d5-109">ImpersonateLoggedOnUser Method</span></span>](ihostsecuritymanager-impersonateloggedonuser-method.md)|<span data-ttu-id="953d5-110">Żąda wykonania kodu przy użyciu poświadczeń bieżącego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="953d5-110">Requests that code be executed using the credentials of the current user identity.</span></span>|  
|[<span data-ttu-id="953d5-111">OpenThreadToken, metoda</span><span class="sxs-lookup"><span data-stu-id="953d5-111">OpenThreadToken Method</span></span>](ihostsecuritymanager-openthreadtoken-method.md)|<span data-ttu-id="953d5-112">Otwiera token dostępu swobodnego skojarzony z bieżącym wątkiem.</span><span class="sxs-lookup"><span data-stu-id="953d5-112">Opens the discretionary access token associated with the current thread.</span></span>|  
|[<span data-ttu-id="953d5-113">RevertToSelf, metoda</span><span class="sxs-lookup"><span data-stu-id="953d5-113">RevertToSelf Method</span></span>](ihostsecuritymanager-reverttoself-method.md)|<span data-ttu-id="953d5-114">Kończy personifikację bieżącej tożsamości użytkownika i zwraca oryginalny token wątku.</span><span class="sxs-lookup"><span data-stu-id="953d5-114">Terminates impersonation of the current user identity and returns the original thread token.</span></span>|  
|[<span data-ttu-id="953d5-115">SetSecurityContext, metoda</span><span class="sxs-lookup"><span data-stu-id="953d5-115">SetSecurityContext Method</span></span>](ihostsecuritymanager-setsecuritycontext-method.md)|<span data-ttu-id="953d5-116">Ustawia kontekst zabezpieczeń aktualnie wykonywanego wątku.</span><span class="sxs-lookup"><span data-stu-id="953d5-116">Sets the security context for the currently executing thread.</span></span>|  
|[<span data-ttu-id="953d5-117">SetThreadToken, metoda</span><span class="sxs-lookup"><span data-stu-id="953d5-117">SetThreadToken Method</span></span>](ihostsecuritymanager-setthreadtoken-method.md)|<span data-ttu-id="953d5-118">Ustawia dojście dla aktualnie wykonywanego wątku.</span><span class="sxs-lookup"><span data-stu-id="953d5-118">Sets a handle for the currently executing thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="953d5-119">Uwagi</span><span class="sxs-lookup"><span data-stu-id="953d5-119">Remarks</span></span>  

 <span data-ttu-id="953d5-120">Host może kontrolować cały dostęp kodu do tokenów wątków przez środowisko uruchomieniowe języka wspólnego (CLR) i kod użytkownika.</span><span class="sxs-lookup"><span data-stu-id="953d5-120">A host can control all code access to thread tokens by both the common language runtime (CLR) and user code.</span></span> <span data-ttu-id="953d5-121">Może także zapewnić, że pełne informacje kontekstu zabezpieczeń są przesyłane przez operacje asynchroniczne lub punkty kodowe z ograniczonym dostępem do kodu.</span><span class="sxs-lookup"><span data-stu-id="953d5-121">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="953d5-122">`IHostSecurityContext` hermetyzuje te informacje kontekstu zabezpieczeń, które nie są nieprzezroczyste dla środowiska CLR.</span><span class="sxs-lookup"><span data-stu-id="953d5-122">`IHostSecurityContext` encapsulates this security context information, which is opaque to the CLR.</span></span>  
  
 <span data-ttu-id="953d5-123">Środowisko CLR obsługuje wewnętrznie zarządzane kontekstu wątku.</span><span class="sxs-lookup"><span data-stu-id="953d5-123">The CLR handles managed thread context internally.</span></span> <span data-ttu-id="953d5-124">Wysyła zapytanie do określonego procesu `IHostSecurityManager` w następujących sytuacjach:</span><span class="sxs-lookup"><span data-stu-id="953d5-124">It queries the process-specific `IHostSecurityManager` in the following situations:</span></span>  
  
- <span data-ttu-id="953d5-125">W wątku finalizatora podczas wykonywania finalizatora.</span><span class="sxs-lookup"><span data-stu-id="953d5-125">On the finalizer thread, during finalizer execution.</span></span>  
  
- <span data-ttu-id="953d5-126">Podczas wykonywania konstruktora klasy i modułu.</span><span class="sxs-lookup"><span data-stu-id="953d5-126">During class and module constructor execution.</span></span>  
  
- <span data-ttu-id="953d5-127">W przypadku asynchronicznych punktów w wątku roboczym w wywołaniach metody [IHostThreadPoolManager:: QueueUserWorkItem](ihostthreadpoolmanager-queueuserworkitem-method.md) .</span><span class="sxs-lookup"><span data-stu-id="953d5-127">At asynchronous points on the worker thread, in calls to the [IHostThreadPoolManager::QueueUserWorkItem](ihostthreadpoolmanager-queueuserworkitem-method.md) method.</span></span>  
  
- <span data-ttu-id="953d5-128">W trakcie obsługi portów zakończenia we/wy.</span><span class="sxs-lookup"><span data-stu-id="953d5-128">In servicing of I/O completion ports.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="953d5-129">Wymagania</span><span class="sxs-lookup"><span data-stu-id="953d5-129">Requirements</span></span>  

 <span data-ttu-id="953d5-130">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="953d5-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="953d5-131">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="953d5-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="953d5-132">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="953d5-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="953d5-133">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="953d5-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="953d5-134">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="953d5-134">See also</span></span>

- [<span data-ttu-id="953d5-135">IHostSecurityContext — Interfejs</span><span class="sxs-lookup"><span data-stu-id="953d5-135">IHostSecurityContext Interface</span></span>](ihostsecuritycontext-interface.md)
- [<span data-ttu-id="953d5-136">Hosting — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="953d5-136">Hosting Interfaces</span></span>](hosting-interfaces.md)
