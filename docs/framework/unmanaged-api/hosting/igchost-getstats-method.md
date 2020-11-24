---
title: IGCHost::GetStats — Metoda
ms.date: 03/30/2017
api_name:
- IGCHost.GetStats
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetStats
helpviewer_keywords:
- GetStats method, IGCHost interface [.NET Framework hosting]
- IGCHost::GetStats method [.NET Framework hosting]
ms.assetid: c4ae022c-46ac-4f19-9ddd-09b955f19412
topic_type:
- apiref
ms.openlocfilehash: 7e664d88bf9f67e936e693b663f27ca490da13ed
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95670111"
---
# <a name="igchostgetstats-method"></a><span data-ttu-id="a59e6-102">IGCHost::GetStats — Metoda</span><span class="sxs-lookup"><span data-stu-id="a59e6-102">IGCHost::GetStats Method</span></span>

<span data-ttu-id="a59e6-103">Pobiera statystyki bieżącego stanu systemu odzyskiwania pamięci.</span><span class="sxs-lookup"><span data-stu-id="a59e6-103">Gets the statistics for the current state of the garbage collection system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a59e6-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="a59e6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStats (  
    [in, out] COR_GC_STATS *pStats  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a59e6-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="a59e6-105">Parameters</span></span>  

 `pStats`  
 <span data-ttu-id="a59e6-106">[in. out] Wskaźnik do struktury [COR_GC_STATS](cor-gc-stats-structure.md) , która zawiera statystyki dotyczące bieżącego stanu systemu odzyskiwania pamięci.</span><span class="sxs-lookup"><span data-stu-id="a59e6-106">[in, out] A pointer to a [COR_GC_STATS](cor-gc-stats-structure.md) structure that contains the statistics for the current state of the garbage collection system.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a59e6-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="a59e6-107">Remarks</span></span>  

 <span data-ttu-id="a59e6-108">Dane statystyczne mogą być używane przez system alokacji inteligentnej, aby ułatwić działanie systemu wyrzucania elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="a59e6-108">The statistics can be used by a smart allocation system to help the garbage collection system operate.</span></span> <span data-ttu-id="a59e6-109">Na przykład system alokacji może określić, po przejrzeniu statystyk, że należy dodać więcej pamięci lub wymusić zbieranie danych.</span><span class="sxs-lookup"><span data-stu-id="a59e6-109">For example, the allocation system may determine, after reviewing the statistics, that it needs to add more memory or force a collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a59e6-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="a59e6-110">Requirements</span></span>  

 <span data-ttu-id="a59e6-111">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a59e6-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a59e6-112">**Nagłówek:** GCHost. idl, GCHost. h</span><span class="sxs-lookup"><span data-stu-id="a59e6-112">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="a59e6-113">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a59e6-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a59e6-114">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a59e6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a59e6-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="a59e6-115">See also</span></span>

- [<span data-ttu-id="a59e6-116">IGCHost — Interfejs</span><span class="sxs-lookup"><span data-stu-id="a59e6-116">IGCHost Interface</span></span>](igchost-interface.md)
