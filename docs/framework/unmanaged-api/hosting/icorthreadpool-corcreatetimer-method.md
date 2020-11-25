---
title: ICorThreadpool::CorCreateTimer — Metoda
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorCreateTimer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorCreateTimer
helpviewer_keywords:
- CorCreateTimer method [.NET Framework hosting]
- ICorThreadpool::CorCreateTimer method [.NET Framework hosting]
ms.assetid: 0d56ef25-30f1-4499-8a1f-76e7654ec614
topic_type:
- apiref
ms.openlocfilehash: 3eac575e18c7371754401da6498d85ba7ed6c8cf
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717621"
---
# <a name="icorthreadpoolcorcreatetimer-method"></a><span data-ttu-id="dd51f-102">ICorThreadpool::CorCreateTimer — Metoda</span><span class="sxs-lookup"><span data-stu-id="dd51f-102">ICorThreadpool::CorCreateTimer Method</span></span>

<span data-ttu-id="dd51f-103">Ta metoda obsługuje infrastrukturę .NET Framework i nie jest przeznaczona do użycia bezpośrednio w kodzie.</span><span class="sxs-lookup"><span data-stu-id="dd51f-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd51f-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="dd51f-104">Syntax</span></span>  
  
```cpp  
HRESULT CorCreateTimer (  
    [in]  HANDLE*             phNewTimer,  
    [in]  WAITORTIMERCALLBACK Callback,  
    [in]  PVOID               Parameter,  
    [in]  DWORD               DueTime,  
    [in]  DWORD               Period,  
    [out] BOOL*               result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="dd51f-105">Wymagania</span><span class="sxs-lookup"><span data-stu-id="dd51f-105">Requirements</span></span>  

 <span data-ttu-id="dd51f-106">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dd51f-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd51f-107">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="dd51f-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dd51f-108">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="dd51f-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dd51f-109">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd51f-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd51f-110">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="dd51f-110">See also</span></span>

- [<span data-ttu-id="dd51f-111">ICorThreadpool — Interfejs</span><span class="sxs-lookup"><span data-stu-id="dd51f-111">ICorThreadpool Interface</span></span>](icorthreadpool-interface.md)
