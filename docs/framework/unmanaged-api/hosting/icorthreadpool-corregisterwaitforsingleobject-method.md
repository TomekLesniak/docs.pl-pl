---
title: ICorThreadpool::CorRegisterWaitForSingleObject — Metoda
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorRegisterWaitForSingleObject
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorRegisterWaitForSingleObject
helpviewer_keywords:
- ICorThreadpool::CorRegisterWaitForSingleObject method [.NET Framework hosting]
- CorRegisterWaitForSingleObject method [.NET Framework hosting]
ms.assetid: cade1feb-71d2-43ed-85ca-7b2e9da12994
topic_type:
- apiref
ms.openlocfilehash: 9f555d3119ede5eabe61467aa81d35aa5c354751
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727851"
---
# <a name="icorthreadpoolcorregisterwaitforsingleobject-method"></a><span data-ttu-id="e243a-102">ICorThreadpool::CorRegisterWaitForSingleObject — Metoda</span><span class="sxs-lookup"><span data-stu-id="e243a-102">ICorThreadpool::CorRegisterWaitForSingleObject Method</span></span>

<span data-ttu-id="e243a-103">Ta metoda obsługuje infrastrukturę .NET Framework i nie jest przeznaczona do użycia bezpośrednio w kodzie.</span><span class="sxs-lookup"><span data-stu-id="e243a-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e243a-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="e243a-104">Syntax</span></span>  
  
```cpp  
HRESULT CorRegisterWaitForSingleObject (  
    [in]  HANDLE*             phNewWaitObject,  
    [in]  HANDLE              hWaitObject,  
    [in]  WAITORTIMERCALLBACK Callback,  
    [in]  PVOID               Context,  
    [in]  ULONG               timeout,  
    [in]  BOOL                executeOnlyOnce,  
    [out] BOOL*               result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="e243a-105">Wymagania</span><span class="sxs-lookup"><span data-stu-id="e243a-105">Requirements</span></span>  

 <span data-ttu-id="e243a-106">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e243a-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e243a-107">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e243a-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e243a-108">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e243a-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e243a-109">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e243a-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e243a-110">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="e243a-110">See also</span></span>

- [<span data-ttu-id="e243a-111">ICorThreadpool — Interfejs</span><span class="sxs-lookup"><span data-stu-id="e243a-111">ICorThreadpool Interface</span></span>](icorthreadpool-interface.md)
