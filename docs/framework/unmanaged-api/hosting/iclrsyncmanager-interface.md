---
title: ICLRSyncManager — Interfejs
ms.date: 03/30/2017
api_name:
- ICLRSyncManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager
helpviewer_keywords:
- ICLRSyncManager interface [.NET Framework hosting]
ms.assetid: a49f9d80-1c76-4ddd-8c49-34f913a5c596
topic_type:
- apiref
ms.openlocfilehash: b0b9c0b7d178557806a9ab2893bff2d34dc408ff
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557739"
---
# <a name="iclrsyncmanager-interface"></a><span data-ttu-id="9b822-102">ICLRSyncManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="9b822-102">ICLRSyncManager Interface</span></span>
<span data-ttu-id="9b822-103">Definiuje metody, które pozwalają hostowi uzyskać informacje o żądanych zadaniach i wykryć zakleszczenie w swojej implementacji synchronizacji.</span><span class="sxs-lookup"><span data-stu-id="9b822-103">Defines methods that allow the host to get information about requested tasks and to detect deadlocks in its synchronization implementation.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9b822-104">Metody</span><span class="sxs-lookup"><span data-stu-id="9b822-104">Methods</span></span>  
  
|<span data-ttu-id="9b822-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="9b822-105">Method</span></span>|<span data-ttu-id="9b822-106">Opis</span><span class="sxs-lookup"><span data-stu-id="9b822-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9b822-107">CreateRWLockOwnerIterator, metoda</span><span class="sxs-lookup"><span data-stu-id="9b822-107">CreateRWLockOwnerIterator Method</span></span>](iclrsyncmanager-createrwlockowneriterator-method.md)|<span data-ttu-id="9b822-108">Żądania, które środowisko uruchomieniowe języka wspólnego (CLR) tworzy iterator dla hosta do użycia w celu określenia zestawu zadań oczekujących na blokadę modułu odczytującego.</span><span class="sxs-lookup"><span data-stu-id="9b822-108">Requests that the common language runtime (CLR) create an iterator for the host to use to determine the set of tasks waiting on a reader-writer lock.</span></span>|  
|[<span data-ttu-id="9b822-109">DeleteRWLockOwnerIterator, metoda</span><span class="sxs-lookup"><span data-stu-id="9b822-109">DeleteRWLockOwnerIterator Method</span></span>](iclrsyncmanager-deleterwlockowneriterator-method.md)|<span data-ttu-id="9b822-110">Żądania, aby środowisko CLR zniszczyć iterator, który został utworzony przez wywołanie metody `CreateRWLockOwnerIterator` .</span><span class="sxs-lookup"><span data-stu-id="9b822-110">Requests that the CLR destroy an iterator that was created by a call to `CreateRWLockOwnerIterator`.</span></span>|  
|[<span data-ttu-id="9b822-111">GetMonitorOwner, metoda</span><span class="sxs-lookup"><span data-stu-id="9b822-111">GetMonitorOwner Method</span></span>](iclrsyncmanager-getmonitorowner-method.md)|<span data-ttu-id="9b822-112">Pobiera zadanie, które jest właścicielem określonego monitora.</span><span class="sxs-lookup"><span data-stu-id="9b822-112">Gets the task that owns the specified monitor.</span></span>|  
|[<span data-ttu-id="9b822-113">GetRWLockOwnerNext, metoda</span><span class="sxs-lookup"><span data-stu-id="9b822-113">GetRWLockOwnerNext Method</span></span>](iclrsyncmanager-getrwlockownernext-method.md)|<span data-ttu-id="9b822-114">Pobiera następne zadanie czekające na bieżącą blokadę modułu odczytującego.</span><span class="sxs-lookup"><span data-stu-id="9b822-114">Gets the next task that is waiting on the current reader-writer lock.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9b822-115">Wymagania</span><span class="sxs-lookup"><span data-stu-id="9b822-115">Requirements</span></span>  
 <span data-ttu-id="9b822-116">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b822-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b822-117">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="9b822-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9b822-118">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9b822-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9b822-119">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b822-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b822-120">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="9b822-120">See also</span></span>

- <xref:System.Threading.Thread>
- [<span data-ttu-id="9b822-121">IHostSyncManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="9b822-121">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
- <span data-ttu-id="9b822-122">[Wątki zarządzane i niezarządzane](/previous-versions/dotnet/netframework-4.0/5s8ee185(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="9b822-122">[Managed and Unmanaged Threading](/previous-versions/dotnet/netframework-4.0/5s8ee185(v=vs.100))</span></span>
- [<span data-ttu-id="9b822-123">Hosting — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="9b822-123">Hosting Interfaces</span></span>](hosting-interfaces.md)
