---
title: IGCHost::SetGCStartupLimits — Metoda
ms.date: 03/30/2017
api_name:
- IGCHost.SetGCStartupLimits
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetGCStartupLimits
helpviewer_keywords:
- SetGCStartupLimits method, IGCHost interface [.NET Framework hosting]
- IGCHost::SetGCStartupLimits method [.NET Framework hosting]
ms.assetid: cae53926-82ac-4d1d-b297-0bde0bd1bebb
topic_type:
- apiref
ms.openlocfilehash: 0eea9dba57886edfef13c31948a9cff94c6c1bfd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687889"
---
# <a name="igchostsetgcstartuplimits-method"></a><span data-ttu-id="7d963-102">IGCHost::SetGCStartupLimits — Metoda</span><span class="sxs-lookup"><span data-stu-id="7d963-102">IGCHost::SetGCStartupLimits Method</span></span>

<span data-ttu-id="7d963-103">Ustawia rozmiar segmentu i maksymalny rozmiar generacji 0.</span><span class="sxs-lookup"><span data-stu-id="7d963-103">Sets the segment size and the maximum size for generation 0.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="7d963-104">Począwszy od .NET Framework 4,5, można ustawić rozmiar segmentu i rozmiar maksymalnej generacji 0 na wartości większe niż przy `DWORD` użyciu metody [IGCHost2:: SetGCStartupLimitsEx —](igchost2-setgcstartuplimitsex-method.md) .</span><span class="sxs-lookup"><span data-stu-id="7d963-104">Starting with the .NET Framework 4.5, you can set segment size and maximum generation 0 size to values greater than `DWORD` by using the [IGCHost2::SetGCStartupLimitsEx](igchost2-setgcstartuplimitsex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d963-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="7d963-105">Syntax</span></span>  
  
```cpp  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,  
    [in] DWORD MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d963-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="7d963-106">Parameters</span></span>  

 `SegmentSize`  
 <span data-ttu-id="7d963-107">podczas Rozmiar segmentu używany przez system odzyskiwania pamięci.</span><span class="sxs-lookup"><span data-stu-id="7d963-107">[in] The size of the segment used by the garbage collection system.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="7d963-108">podczas Maksymalny rozmiar generacji 0.</span><span class="sxs-lookup"><span data-stu-id="7d963-108">[in] The maximum size for generation 0.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7d963-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="7d963-109">Remarks</span></span>  

 <span data-ttu-id="7d963-110">`SetGCStartupLimits`Metoda może być wywoływana tylko raz.</span><span class="sxs-lookup"><span data-stu-id="7d963-110">The `SetGCStartupLimits` method may be called only once.</span></span> <span data-ttu-id="7d963-111">Tych wartości nie można później zmienić.</span><span class="sxs-lookup"><span data-stu-id="7d963-111">These values cannot be changed later.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d963-112">Wymagania</span><span class="sxs-lookup"><span data-stu-id="7d963-112">Requirements</span></span>  

 <span data-ttu-id="7d963-113">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7d963-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d963-114">**Nagłówek:** GCHost. idl, GCHost. h</span><span class="sxs-lookup"><span data-stu-id="7d963-114">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="7d963-115">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7d963-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7d963-116">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d963-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d963-117">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="7d963-117">See also</span></span>

- [<span data-ttu-id="7d963-118">IGCHost — Interfejs</span><span class="sxs-lookup"><span data-stu-id="7d963-118">IGCHost Interface</span></span>](igchost-interface.md)
