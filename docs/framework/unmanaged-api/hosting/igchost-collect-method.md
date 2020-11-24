---
title: IGCHost::Collect — Metoda
ms.date: 03/30/2017
api_name:
- IGCHost.Collect
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- Collect
helpviewer_keywords:
- Collect method, IGCHost interface [.NET Framework hosting]
- IGCHost::Collect method [.NET Framework hosting]
ms.assetid: fc7d9448-3186-494d-9f0d-ea39717e9a82
topic_type:
- apiref
ms.openlocfilehash: f32b91f0d47449f80c38542162035999d616813b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95670147"
---
# <a name="igchostcollect-method"></a><span data-ttu-id="72b8f-102">IGCHost::Collect — Metoda</span><span class="sxs-lookup"><span data-stu-id="72b8f-102">IGCHost::Collect Method</span></span>

<span data-ttu-id="72b8f-103">Wymusza, aby kolekcja była wykonywana dla danej generacji, niezależnie od stanu bieżącej wyrzucania elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="72b8f-103">Forces a collection to occur for the given generation, regardless of the state of the current garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72b8f-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="72b8f-104">Syntax</span></span>  
  
```cpp  
HRESULT Collect (  
    [in] LONG Generation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="72b8f-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="72b8f-105">Parameters</span></span>  

 `Generation`  
 <span data-ttu-id="72b8f-106">podczas Generacja, na której ma zostać wykonane odzyskiwanie pamięci.</span><span class="sxs-lookup"><span data-stu-id="72b8f-106">[in] The generation on which to perform the garbage collection.</span></span> <span data-ttu-id="72b8f-107">Wartość-1 oznacza, że wszystkie generacji zostaną poddane wyrzucania elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="72b8f-107">A value of -1 indicates that all generations will undergo a garbage collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72b8f-108">Wymagania</span><span class="sxs-lookup"><span data-stu-id="72b8f-108">Requirements</span></span>  

 <span data-ttu-id="72b8f-109">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="72b8f-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72b8f-110">**Nagłówek:** GCHost. idl, GCHost. h</span><span class="sxs-lookup"><span data-stu-id="72b8f-110">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="72b8f-111">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="72b8f-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="72b8f-112">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72b8f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72b8f-113">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="72b8f-113">See also</span></span>

- [<span data-ttu-id="72b8f-114">IGCHost — Interfejs</span><span class="sxs-lookup"><span data-stu-id="72b8f-114">IGCHost Interface</span></span>](igchost-interface.md)
