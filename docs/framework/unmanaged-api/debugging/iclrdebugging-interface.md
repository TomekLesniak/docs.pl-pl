---
title: ICLRDebugging — Interfejs
ms.date: 03/30/2017
api_name:
- ICLRDebugging
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebugging
helpviewer_keywords:
- ICLRDebugging interface [.NET Framework debugging]
ms.assetid: 429d8fce-b1b1-49d7-895c-28c1c1aa2dbd
topic_type:
- apiref
ms.openlocfilehash: 6eea7f6c222b8e30376ec72ee0c193a68c23f0d0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723561"
---
# <a name="iclrdebugging-interface"></a><span data-ttu-id="fc37d-102">ICLRDebugging — Interfejs</span><span class="sxs-lookup"><span data-stu-id="fc37d-102">ICLRDebugging Interface</span></span>

<span data-ttu-id="fc37d-103">Zapewnia metody obsługujące ładowanie i wyładowanie modułów do debugowania.</span><span class="sxs-lookup"><span data-stu-id="fc37d-103">Provides methods that handle loading and unloading modules for debugging.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fc37d-104">Metody</span><span class="sxs-lookup"><span data-stu-id="fc37d-104">Methods</span></span>  
  
|<span data-ttu-id="fc37d-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="fc37d-105">Method</span></span>|<span data-ttu-id="fc37d-106">Opis</span><span class="sxs-lookup"><span data-stu-id="fc37d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fc37d-107">OpenVirtualProcess, metoda</span><span class="sxs-lookup"><span data-stu-id="fc37d-107">OpenVirtualProcess Method</span></span>](iclrdebugging-openvirtualprocess-method.md)|<span data-ttu-id="fc37d-108">Pobiera interfejs "ICorDebugProcess", który odnosi się do modułu środowiska uruchomieniowego języka wspólnego (CLR), który jest ładowany w procesie.</span><span class="sxs-lookup"><span data-stu-id="fc37d-108">Gets the "ICorDebugProcess" interface that corresponds to a common language runtime (CLR) module loaded in the process.</span></span>|  
|[<span data-ttu-id="fc37d-109">CanUnloadNow, metoda</span><span class="sxs-lookup"><span data-stu-id="fc37d-109">CanUnloadNow Method</span></span>](iclrdebugging-canunloadnow-method.md)|<span data-ttu-id="fc37d-110">Określa, czy biblioteka, która została dostarczona przez interfejs [ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md) , jest nadal używana, czy może zostać zwolniona.</span><span class="sxs-lookup"><span data-stu-id="fc37d-110">Determines whether a library that was provided by an [ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md) interface is still in use or can be unloaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fc37d-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="fc37d-111">Remarks</span></span>  

 <span data-ttu-id="fc37d-112">Wystąpienie interfejsu można uzyskać przy `ICLRDebugging` użyciu funkcji [CLRCreateInstance](../hosting/clrcreateinstance-function.md) .</span><span class="sxs-lookup"><span data-stu-id="fc37d-112">You can obtain an instance of the `ICLRDebugging` interface by using the [CLRCreateInstance](../hosting/clrcreateinstance-function.md) function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc37d-113">Wymagania</span><span class="sxs-lookup"><span data-stu-id="fc37d-113">Requirements</span></span>  

 <span data-ttu-id="fc37d-114">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc37d-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc37d-115">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="fc37d-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fc37d-116">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="fc37d-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fc37d-117">**.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc37d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc37d-118">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="fc37d-118">See also</span></span>

- [<span data-ttu-id="fc37d-119">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="fc37d-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="fc37d-120">Debugowanie</span><span class="sxs-lookup"><span data-stu-id="fc37d-120">Debugging</span></span>](index.md)
