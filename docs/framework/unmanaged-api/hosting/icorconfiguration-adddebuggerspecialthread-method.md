---
title: ICorConfiguration::AddDebuggerSpecialThread — Metoda
ms.date: 03/30/2017
api_name:
- ICorConfiguration.AddDebuggerSpecialThread
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- AddDebuggerSpecialThread
helpviewer_keywords:
- AddDebuggerSpecialThread method [.NET Framework hosting]
- ICorConfiguration::AddDebuggerSpecialThread method [.NET Framework hosting]
ms.assetid: 1f1e3239-438e-4be9-a3bb-7d0722d3a76d
topic_type:
- apiref
ms.openlocfilehash: bd89db3fa0b1814a98b016fcf9d1aeeabfff718b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715852"
---
# <a name="icorconfigurationadddebuggerspecialthread-method"></a><span data-ttu-id="9d667-102">ICorConfiguration::AddDebuggerSpecialThread — Metoda</span><span class="sxs-lookup"><span data-stu-id="9d667-102">ICorConfiguration::AddDebuggerSpecialThread Method</span></span>

<span data-ttu-id="9d667-103">Wskazuje usługi debugowania, które mogą kontynuować wykonywanie określonego wątku, podczas gdy debuger ma aplikację zatrzymaną w scenariuszach debugowania zarządzanego lub niezarządzanego.</span><span class="sxs-lookup"><span data-stu-id="9d667-103">Indicates to the debugging services that a particular thread should be allowed to continue executing while the debugger has an application stopped during managed or unmanaged debugging scenarios.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d667-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="9d667-104">Syntax</span></span>  
  
```cpp  
HRESULT AddDebuggerSpecialThread (  
    [in] DWORD dwSpecialThreadId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9d667-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="9d667-105">Parameters</span></span>  

 `dwSpecialThreadId`  
 <span data-ttu-id="9d667-106">podczas Identyfikator wątku, który powinien być dozwolony do dalszego wykonywania.</span><span class="sxs-lookup"><span data-stu-id="9d667-106">[in] The ID of the thread that should be allowed to continue executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9d667-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="9d667-107">Remarks</span></span>  

 <span data-ttu-id="9d667-108">Określony wątek nie będzie mógł uruchamiać kodu zarządzanego lub wprowadzać środowiska uruchomieniowego w jakikolwiek sposób.</span><span class="sxs-lookup"><span data-stu-id="9d667-108">The specified thread will not be allowed to run managed code or enter the runtime in any way.</span></span> <span data-ttu-id="9d667-109">Przykładem takiego wątku będzie wątek w procesie do obsługi starszych debugerów skryptów.</span><span class="sxs-lookup"><span data-stu-id="9d667-109">An example of such a thread would be an in-process thread to support legacy script debuggers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d667-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="9d667-110">Requirements</span></span>  

 <span data-ttu-id="9d667-111">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9d667-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d667-112">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="9d667-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9d667-113">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9d667-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9d667-114">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d667-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d667-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="9d667-115">See also</span></span>

- [<span data-ttu-id="9d667-116">ICorConfiguration — Interfejs</span><span class="sxs-lookup"><span data-stu-id="9d667-116">ICorConfiguration Interface</span></span>](icorconfiguration-interface.md)
