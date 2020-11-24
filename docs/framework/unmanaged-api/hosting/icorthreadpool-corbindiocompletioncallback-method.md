---
title: ICorThreadpool::CorBindIoCompletionCallback — Metoda
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorBindIoCompletionCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorBindIoCompletionCallback
helpviewer_keywords:
- CorBindIoCompletionCallback method [.NET Framework hosting]
- ICorThreadpool::CorBindIoCompletionCallback method [.NET Framework hosting]
ms.assetid: 2b159225-f09c-42f1-aa7c-44087e121249
topic_type:
- apiref
ms.openlocfilehash: 7baf144f5d14a8757101bdb29a8bc81ff3a05231
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690060"
---
# <a name="icorthreadpoolcorbindiocompletioncallback-method"></a><span data-ttu-id="49b44-102">ICorThreadpool::CorBindIoCompletionCallback — Metoda</span><span class="sxs-lookup"><span data-stu-id="49b44-102">ICorThreadpool::CorBindIoCompletionCallback Method</span></span>

<span data-ttu-id="49b44-103">Ta metoda obsługuje infrastrukturę .NET Framework i nie jest przeznaczona do użycia bezpośrednio w kodzie.</span><span class="sxs-lookup"><span data-stu-id="49b44-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49b44-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="49b44-104">Syntax</span></span>  
  
```cpp  
HRESULT CorBindIoCompletionCallback (  
    [in] HANDLE                          fileHandle,  
    [in] LPOVERLAPPED_COMPLETION_ROUTINE callback  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="49b44-105">Wymagania</span><span class="sxs-lookup"><span data-stu-id="49b44-105">Requirements</span></span>  

 <span data-ttu-id="49b44-106">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49b44-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49b44-107">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="49b44-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="49b44-108">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="49b44-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="49b44-109">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49b44-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49b44-110">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="49b44-110">See also</span></span>

- [<span data-ttu-id="49b44-111">ICorThreadpool — Interfejs</span><span class="sxs-lookup"><span data-stu-id="49b44-111">ICorThreadpool Interface</span></span>](icorthreadpool-interface.md)
