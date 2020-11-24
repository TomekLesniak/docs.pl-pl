---
title: ICLRGCManager — Interfejs
ms.date: 03/30/2017
api_name:
- ICLRGCManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager
helpviewer_keywords:
- ICLRGCManager interface [.NET Framework hosting]
ms.assetid: fb511c9b-3fe4-41b0-822a-6ba4a079d1f5
topic_type:
- apiref
ms.openlocfilehash: dbe3df6bb20e5ad8f9eb534a366405eb9c33984f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678249"
---
# <a name="iclrgcmanager-interface"></a><span data-ttu-id="70b16-102">ICLRGCManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="70b16-102">ICLRGCManager Interface</span></span>

<span data-ttu-id="70b16-103">Dostarcza metody, które umożliwiają hostowi współdziałanie z systemem odzyskiwania pamięci środowiska uruchomieniowego języka wspólnego.</span><span class="sxs-lookup"><span data-stu-id="70b16-103">Provides methods that allow a host to interact with the common language runtime's garbage collection system.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="70b16-104">Począwszy od .NET Framework 4,5, można użyć metody [ICLRGCManager2:: SetGCStartupLimitsEx —](iclrgcmanager2-setgcstartuplimitsex-method.md) , aby ustawić rozmiar segmentu wyrzucania elementów bezużytecznych i maksymalny rozmiar generacji systemu wyrzucania elementów bezużytecznych z wartości większej niż `DWORD` Limit narzucony przez metodę [SetGCStartupLimits —](iclrgcmanager-setgcstartuplimits-method.md) .</span><span class="sxs-lookup"><span data-stu-id="70b16-104">Starting with the .NET Framework 4.5, you can use the [ICLRGCManager2::SetGCStartupLimitsEx](iclrgcmanager2-setgcstartuplimitsex-method.md) method to set the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0 to values greater than the `DWORD` limit that is imposed by the [SetGCStartupLimits](iclrgcmanager-setgcstartuplimits-method.md) method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="70b16-105">Metody</span><span class="sxs-lookup"><span data-stu-id="70b16-105">Methods</span></span>  
  
|<span data-ttu-id="70b16-106">Metoda</span><span class="sxs-lookup"><span data-stu-id="70b16-106">Method</span></span>|<span data-ttu-id="70b16-107">Opis</span><span class="sxs-lookup"><span data-stu-id="70b16-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="70b16-108">Collect, metoda</span><span class="sxs-lookup"><span data-stu-id="70b16-108">Collect Method</span></span>](iclrgcmanager-collect-method.md)|<span data-ttu-id="70b16-109">Wymusza wyrzucanie elementów bezużytecznych dla określonej generacji.</span><span class="sxs-lookup"><span data-stu-id="70b16-109">Forces a garbage collection for the specified generation.</span></span>|  
|[<span data-ttu-id="70b16-110">GetStats — Metoda</span><span class="sxs-lookup"><span data-stu-id="70b16-110">GetStats Method</span></span>](iclrgcmanager-getstats-method.md)|<span data-ttu-id="70b16-111">Pobiera zestaw bieżących statystyk dotyczących systemu odzyskiwania pamięci.</span><span class="sxs-lookup"><span data-stu-id="70b16-111">Gets a set of current statistics about the garbage collection system.</span></span>|  
|[<span data-ttu-id="70b16-112">SetGCStartupLimits, metoda</span><span class="sxs-lookup"><span data-stu-id="70b16-112">SetGCStartupLimits Method</span></span>](iclrgcmanager-setgcstartuplimits-method.md)|<span data-ttu-id="70b16-113">Ustawia rozmiar segmentu wyrzucania elementów bezużytecznych i maksymalny rozmiar generacji 0 systemu odzyskiwania pamięci.</span><span class="sxs-lookup"><span data-stu-id="70b16-113">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="70b16-114">Uwagi</span><span class="sxs-lookup"><span data-stu-id="70b16-114">Remarks</span></span>  

 <span data-ttu-id="70b16-115">Środowisko uruchomieniowe języka wspólnego (CLR) implementuje mechanizm wyrzucania elementów bezużytecznych z typem zarządzanym <xref:System.GC> .</span><span class="sxs-lookup"><span data-stu-id="70b16-115">The common language runtime (CLR) implements its garbage collection mechanism with the managed <xref:System.GC> type.</span></span> <span data-ttu-id="70b16-116">Aby uzyskać więcej informacji na temat systemu wyrzucania elementów bezużytecznych, zobacz [odzyskiwanie pamięci](../../../standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="70b16-116">For more information about the garbage collection system, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70b16-117">Wymagania</span><span class="sxs-lookup"><span data-stu-id="70b16-117">Requirements</span></span>  

 <span data-ttu-id="70b16-118">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="70b16-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70b16-119">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="70b16-119">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="70b16-120">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="70b16-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="70b16-121">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70b16-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70b16-122">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="70b16-122">See also</span></span>

- [<span data-ttu-id="70b16-123">Automatyczne zarządzanie pamięcią</span><span class="sxs-lookup"><span data-stu-id="70b16-123">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="70b16-124">COR_GC_STATS — Struktura</span><span class="sxs-lookup"><span data-stu-id="70b16-124">COR_GC_STATS Structure</span></span>](cor-gc-stats-structure.md)
- [<span data-ttu-id="70b16-125">ICLRControl — Interfejs</span><span class="sxs-lookup"><span data-stu-id="70b16-125">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="70b16-126">Interfejsy hostingu środowiska CLR</span><span class="sxs-lookup"><span data-stu-id="70b16-126">CLR Hosting Interfaces</span></span>](clr-hosting-interfaces.md)
- [<span data-ttu-id="70b16-127">Hosting — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="70b16-127">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="70b16-128">Hosting</span><span class="sxs-lookup"><span data-stu-id="70b16-128">Hosting</span></span>](index.md)
