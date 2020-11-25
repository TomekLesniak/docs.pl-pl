---
title: COR_GC_THREAD_STATS — Struktura
ms.date: 03/30/2017
api_name:
- COR_GC_THREAD_STATS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_GC_THREAD_STATS
helpviewer_keywords:
- COR_GC_THREAD_STATS structure [.NET Framework hosting]
ms.assetid: 01f9a59b-7679-4d42-9ced-4a8981625c3d
topic_type:
- apiref
ms.openlocfilehash: 25a90965dc5466b7cf1a07140705424cf2ba4cd9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699238"
---
# <a name="cor_gc_thread_stats-structure"></a><span data-ttu-id="6880b-102">COR_GC_THREAD_STATS — Struktura</span><span class="sxs-lookup"><span data-stu-id="6880b-102">COR_GC_THREAD_STATS Structure</span></span>

<span data-ttu-id="6880b-103">Zawiera statystyki poszczególnych wątków dotyczące wyrzucania elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="6880b-103">Contains per-thread statistics pertaining to garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6880b-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="6880b-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_GC_THREAD_STATS {  
    ULONGLONG  PerThreadAllocation;
    ULONG      Flags;
} COR_GC_THREAD_STATS;  
```  
  
## <a name="members"></a><span data-ttu-id="6880b-105">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="6880b-105">Members</span></span>  
  
|<span data-ttu-id="6880b-106">Członek</span><span class="sxs-lookup"><span data-stu-id="6880b-106">Member</span></span>|<span data-ttu-id="6880b-107">Opis</span><span class="sxs-lookup"><span data-stu-id="6880b-107">Description</span></span>|  
|------------|-----------------|  
|`PerThreadAllocation`|<span data-ttu-id="6880b-108">Liczba bajtów pamięci przydzieloną w wątku, który jest skojarzony z bieżącym `COR_GC_THREAD_STATS` wystąpieniem.</span><span class="sxs-lookup"><span data-stu-id="6880b-108">The number of bytes of memory allocated on the thread that is associated with the current `COR_GC_THREAD_STATS` instance.</span></span> <span data-ttu-id="6880b-109">Ta liczba jest wyczyszczona do zera za każdym razem, gdy wystąpi wyrzucanie elementów bezużytecznych generacji.</span><span class="sxs-lookup"><span data-stu-id="6880b-109">This number is cleared to zero each time a generation-zero garbage collection occurs.</span></span>|  
|`Flags`|<span data-ttu-id="6880b-110">Liczba bajtów, które mają zostać podwyższone do wyższej generacji przy ostatnim wyrzucaniu elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="6880b-110">The number of bytes promoted to a higher generation at the most recent garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6880b-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="6880b-111">Remarks</span></span>  

 <span data-ttu-id="6880b-112">[ICLRTask:: GetMemStats —](iclrtask-getmemstats-method.md) pobiera parametr wyjściowy typu `COR_GC_THREAD_STATS` .</span><span class="sxs-lookup"><span data-stu-id="6880b-112">[ICLRTask::GetMemStats](iclrtask-getmemstats-method.md) takes an output parameter of type `COR_GC_THREAD_STATS`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6880b-113">Wymagania</span><span class="sxs-lookup"><span data-stu-id="6880b-113">Requirements</span></span>  

 <span data-ttu-id="6880b-114">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6880b-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6880b-115">**Nagłówek:** GCHost. idl</span><span class="sxs-lookup"><span data-stu-id="6880b-115">**Header:** GCHost.idl</span></span>  
  
 <span data-ttu-id="6880b-116">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6880b-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6880b-117">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6880b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6880b-118">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="6880b-118">See also</span></span>

- [<span data-ttu-id="6880b-119">Hosting — Struktury</span><span class="sxs-lookup"><span data-stu-id="6880b-119">Hosting Structures</span></span>](hosting-structures.md)
- [<span data-ttu-id="6880b-120">IHostTask — Interfejs</span><span class="sxs-lookup"><span data-stu-id="6880b-120">IHostTask Interface</span></span>](ihosttask-interface.md)
