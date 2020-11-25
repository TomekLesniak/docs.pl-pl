---
title: ICorThreadpool::CorQueueUserWorkItem — Metoda
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorQueueUserWorkItem
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorQueueUserWorkItem
helpviewer_keywords:
- ICorThreadpool::CorQueueUserWorkItem method [.NET Framework hosting]
- CorQueueUserWorkItem method [.NET Framework hosting]
ms.assetid: 29ac7898-a7c7-433e-8f79-cd5237e0bab8
topic_type:
- apiref
ms.openlocfilehash: 42de7cd566db53e43985088851fd01fb66feabd9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720506"
---
# <a name="icorthreadpoolcorqueueuserworkitem-method"></a><span data-ttu-id="6d6be-102">ICorThreadpool::CorQueueUserWorkItem — Metoda</span><span class="sxs-lookup"><span data-stu-id="6d6be-102">ICorThreadpool::CorQueueUserWorkItem Method</span></span>

<span data-ttu-id="6d6be-103">Ta metoda obsługuje infrastrukturę .NET Framework i nie jest przeznaczona do użycia bezpośrednio w kodzie.</span><span class="sxs-lookup"><span data-stu-id="6d6be-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d6be-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="6d6be-104">Syntax</span></span>  
  
```cpp  
HRESULT CorQueueUserWorkItem (  
    [in] LPTHREAD_START_ROUTINE Function,  
    [in] PVOID                  Context,  
    [in] BOOL                   executeOnlyOnce,  
    [out] BOOL*                 result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="6d6be-105">Wymagania</span><span class="sxs-lookup"><span data-stu-id="6d6be-105">Requirements</span></span>  

 <span data-ttu-id="6d6be-106">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d6be-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d6be-107">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="6d6be-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6d6be-108">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6d6be-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6d6be-109">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d6be-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d6be-110">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="6d6be-110">See also</span></span>

- [<span data-ttu-id="6d6be-111">ICorThreadpool — Interfejs</span><span class="sxs-lookup"><span data-stu-id="6d6be-111">ICorThreadpool Interface</span></span>](icorthreadpool-interface.md)
