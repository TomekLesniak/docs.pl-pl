---
title: IHostMalloc — Interfejs
ms.date: 03/30/2017
api_name:
- IHostMAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMAlloc
helpviewer_keywords:
- IHostMAlloc interface [.NET Framework hosting]
ms.assetid: e3c6643b-6fc7-4a99-959d-4b7b4e63fdee
topic_type:
- apiref
ms.openlocfilehash: 2530c7fcd63f81b566d6623a533bd8e2af084047
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702163"
---
# <a name="ihostmalloc-interface"></a><span data-ttu-id="76552-102">IHostMalloc — Interfejs</span><span class="sxs-lookup"><span data-stu-id="76552-102">IHostMalloc Interface</span></span>

<span data-ttu-id="76552-103">Zapewnia metody, które umożliwiają środowisko uruchomieniowe języka wspólnego (CLR) żądania bardziej szczegółowych alokacji ze sterty za pośrednictwem hosta.</span><span class="sxs-lookup"><span data-stu-id="76552-103">Provides methods that allow the common language runtime (CLR) to request fine-grained allocations from the heap through the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="76552-104">Metody</span><span class="sxs-lookup"><span data-stu-id="76552-104">Methods</span></span>  
  
|<span data-ttu-id="76552-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="76552-105">Method</span></span>|<span data-ttu-id="76552-106">Opis</span><span class="sxs-lookup"><span data-stu-id="76552-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="76552-107">Alloc, metoda</span><span class="sxs-lookup"><span data-stu-id="76552-107">Alloc Method</span></span>](ihostmalloc-alloc-method.md)|<span data-ttu-id="76552-108">Żąda od sterty przydzielenia przez hosta żądaną ilość pamięci.</span><span class="sxs-lookup"><span data-stu-id="76552-108">Requests that the host allocate the requested amount of memory from the heap.</span></span>|  
|[<span data-ttu-id="76552-109">DebugAlloc, metoda</span><span class="sxs-lookup"><span data-stu-id="76552-109">DebugAlloc Method</span></span>](ihostmalloc-debugalloc-method.md)|<span data-ttu-id="76552-110">Żąda, aby Host przydzielił żądaną ilość pamięci ze sterty, a także śledzić miejsce przydzielenia pamięci.</span><span class="sxs-lookup"><span data-stu-id="76552-110">Requests that the host allocate the requested amount of memory from the heap, and additionally track where the memory was allocated.</span></span>|  
|[<span data-ttu-id="76552-111">Free, metoda</span><span class="sxs-lookup"><span data-stu-id="76552-111">Free Method</span></span>](ihostmalloc-free-method.md)|<span data-ttu-id="76552-112">Zwalnia pamięć przydzieloną przy użyciu `Alloc` metody.</span><span class="sxs-lookup"><span data-stu-id="76552-112">Frees memory that was allocated by using the `Alloc` method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="76552-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="76552-113">Remarks</span></span>  

 <span data-ttu-id="76552-114">Środowisko CLR Pobiera wskaźnik interfejsu do `IHostMalloc` wystąpienia, wywołując metodę [IHostMemoryManager::](ihostmemorymanager-createmalloc-method.md) CreateInstance.</span><span class="sxs-lookup"><span data-stu-id="76552-114">The CLR gets an interface pointer to an `IHostMalloc` instance by calling the [IHostMemoryManager::CreateMalloc](ihostmemorymanager-createmalloc-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76552-115">Wymagania</span><span class="sxs-lookup"><span data-stu-id="76552-115">Requirements</span></span>  

 <span data-ttu-id="76552-116">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="76552-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76552-117">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="76552-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="76552-118">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="76552-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="76552-119">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76552-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76552-120">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="76552-120">See also</span></span>

- [<span data-ttu-id="76552-121">IHostMemoryManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="76552-121">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
- [<span data-ttu-id="76552-122">Hosting — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="76552-122">Hosting Interfaces</span></span>](hosting-interfaces.md)
