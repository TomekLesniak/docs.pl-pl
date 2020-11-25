---
title: ICorConfiguration::SetDebuggerThreadControl — Metoda
ms.date: 03/30/2017
api_name:
- ICorConfiguration.SetDebuggerThreadControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetDebuggerThreadControl
helpviewer_keywords:
- SetDebuggerThreadControl method [.NET Framework hosting]
- ICorConfiguration::SetDebuggerThreadControl method [.NET Framework hosting]
ms.assetid: 1ded7639-dacb-4db1-961c-d1ceaec01959
topic_type:
- apiref
ms.openlocfilehash: 05df50d80c6b8962b3bdfe2708d5f9d30c58aaea
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723925"
---
# <a name="icorconfigurationsetdebuggerthreadcontrol-method"></a><span data-ttu-id="33257-102">ICorConfiguration::SetDebuggerThreadControl — Metoda</span><span class="sxs-lookup"><span data-stu-id="33257-102">ICorConfiguration::SetDebuggerThreadControl Method</span></span>

<span data-ttu-id="33257-103">Ustawia interfejs wywołania zwrotnego, który będzie wywoływany przez usługi debugowania jako wątki środowiska uruchomieniowego języka wspólnego (CLR), które są blokowane i odblokowywane na potrzeby debugowania.</span><span class="sxs-lookup"><span data-stu-id="33257-103">Sets the callback interface that the debugging services will call as common language runtime (CLR) threads are blocked and unblocked for debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33257-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="33257-104">Syntax</span></span>  
  
```cpp  
HRESULT SetDebuggerThreadControl (  
    [in] IDebuggerThreadControl* pDebuggerThreadControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="33257-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="33257-105">Parameters</span></span>  

 `pDebuggerThreadControl`  
 <span data-ttu-id="33257-106">podczas Wskaźnik do obiektu [IDebuggerThreadControl](idebuggerthreadcontrol-interface.md) , który powiadamia hosta o blokowaniu i odblokowywaniu wątków przez usługi debugowania.</span><span class="sxs-lookup"><span data-stu-id="33257-106">[in] A pointer to an [IDebuggerThreadControl](idebuggerthreadcontrol-interface.md) object that notifies the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33257-107">Wymagania</span><span class="sxs-lookup"><span data-stu-id="33257-107">Requirements</span></span>  

 <span data-ttu-id="33257-108">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33257-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33257-109">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="33257-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="33257-110">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="33257-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="33257-111">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33257-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33257-112">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="33257-112">See also</span></span>

- [<span data-ttu-id="33257-113">ICorConfiguration — Interfejs</span><span class="sxs-lookup"><span data-stu-id="33257-113">ICorConfiguration Interface</span></span>](icorconfiguration-interface.md)
