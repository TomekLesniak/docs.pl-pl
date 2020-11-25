---
title: ICorThreadpool::CorSetMaxThreads — Metoda
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorSetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSetMaxThreads
helpviewer_keywords:
- ICorThreadpool::CorSetMaxThreads method [.NET Framework hosting]
- CorSetMaxThreads method [.NET Framework hosting]
ms.assetid: 4a846238-df4e-4060-ba3b-5173f6a51e85
topic_type:
- apiref
ms.openlocfilehash: f7d9d3d059abcf58fe0f4b35ce41046efb9c2400
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733987"
---
# <a name="icorthreadpoolcorsetmaxthreads-method"></a><span data-ttu-id="5c66c-102">ICorThreadpool::CorSetMaxThreads — Metoda</span><span class="sxs-lookup"><span data-stu-id="5c66c-102">ICorThreadpool::CorSetMaxThreads Method</span></span>

<span data-ttu-id="5c66c-103">Ta metoda obsługuje infrastrukturę .NET Framework i nie jest przeznaczona do użycia bezpośrednio w kodzie.</span><span class="sxs-lookup"><span data-stu-id="5c66c-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c66c-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="5c66c-104">Syntax</span></span>  
  
```cpp  
HRESULT CorSetMaxThreads (  
    [in] DWORD MaxWorkerThreads,  
    [in] DWORD MaxIOCompletionThreads  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="5c66c-105">Wymagania</span><span class="sxs-lookup"><span data-stu-id="5c66c-105">Requirements</span></span>  

 <span data-ttu-id="5c66c-106">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c66c-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c66c-107">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="5c66c-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5c66c-108">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5c66c-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5c66c-109">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c66c-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c66c-110">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="5c66c-110">See also</span></span>

- [<span data-ttu-id="5c66c-111">ICorThreadpool — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5c66c-111">ICorThreadpool Interface</span></span>](icorthreadpool-interface.md)
