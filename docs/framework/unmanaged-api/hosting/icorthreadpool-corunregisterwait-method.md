---
title: ICorThreadpool::CorUnregisterWait — Metoda
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorUnregisterWait
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorUnregisterWait
helpviewer_keywords:
- CorUnregisterWait method [.NET Framework hosting]
- ICorThreadpool::CorUnregisterWait method [.NET Framework hosting]
ms.assetid: 42c933f1-30a8-4011-bdea-e117f3c3265e
topic_type:
- apiref
ms.openlocfilehash: 38b3655da75750ffc3ea1c7983ce3b549d76f087
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733974"
---
# <a name="icorthreadpoolcorunregisterwait-method"></a><span data-ttu-id="766ac-102">ICorThreadpool::CorUnregisterWait — Metoda</span><span class="sxs-lookup"><span data-stu-id="766ac-102">ICorThreadpool::CorUnregisterWait Method</span></span>

<span data-ttu-id="766ac-103">Ta metoda obsługuje infrastrukturę .NET Framework i nie jest przeznaczona do użycia bezpośrednio w kodzie.</span><span class="sxs-lookup"><span data-stu-id="766ac-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="766ac-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="766ac-104">Syntax</span></span>  
  
```cpp  
HRESULT CorUnregisterWait (  
    [in] HANDLE hWaitObject,  
    [in] HANDLE CompletionEvent,  
    [out] BOOL* result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="766ac-105">Wymagania</span><span class="sxs-lookup"><span data-stu-id="766ac-105">Requirements</span></span>  

 <span data-ttu-id="766ac-106">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="766ac-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="766ac-107">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="766ac-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="766ac-108">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="766ac-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="766ac-109">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="766ac-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="766ac-110">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="766ac-110">See also</span></span>

- [<span data-ttu-id="766ac-111">ICorThreadpool — Interfejs</span><span class="sxs-lookup"><span data-stu-id="766ac-111">ICorThreadpool Interface</span></span>](icorthreadpool-interface.md)
