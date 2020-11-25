---
title: IGCThreadControl::SuspensionEnding — Metoda
ms.date: 03/30/2017
api_name:
- IGCThreadControl.SuspensionEnding
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SuspensionEnding
helpviewer_keywords:
- IGCThreadControl::SuspensionEnding method [.NET Framework hosting]
- SuspensionEnding method, IGCThreadControl interface [.NET Framework hosting]
ms.assetid: 70814265-c734-4ddc-9502-fe8b28d2b414
topic_type:
- apiref
ms.openlocfilehash: 4638672b1d64a9ea07618212cc514d00996470eb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721676"
---
# <a name="igcthreadcontrolsuspensionending-method"></a><span data-ttu-id="d325b-102">IGCThreadControl::SuspensionEnding — Metoda</span><span class="sxs-lookup"><span data-stu-id="d325b-102">IGCThreadControl::SuspensionEnding Method</span></span>

<span data-ttu-id="d325b-103">Powiadamia hosta, że środowisko uruchomieniowe wznawia wątki po wyrzucaniu elementów bezużytecznych lub innym zawieszeniu.</span><span class="sxs-lookup"><span data-stu-id="d325b-103">Notifies the host that the runtime is resuming threads after a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d325b-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="d325b-104">Syntax</span></span>  
  
```cpp  
HRESULT SuspensionEnding (  
    [in] DWORD Generation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d325b-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="d325b-105">Parameters</span></span>  

 `Generation`  
 <span data-ttu-id="d325b-106">podczas Generacja, na której wykonano odzyskiwanie pamięci.</span><span class="sxs-lookup"><span data-stu-id="d325b-106">[in] The generation on which a garbage collection has been performed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d325b-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="d325b-107">Remarks</span></span>  

 <span data-ttu-id="d325b-108">Nie należy ponownie planować żadnych wątków w trakcie `SuspensionEnding` wywołania zwrotnego.</span><span class="sxs-lookup"><span data-stu-id="d325b-108">Do not reschedule any threads during the `SuspensionEnding` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d325b-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="d325b-109">Requirements</span></span>  

 <span data-ttu-id="d325b-110">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d325b-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d325b-111">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="d325b-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d325b-112">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d325b-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d325b-113">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d325b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d325b-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="d325b-114">See also</span></span>

- [<span data-ttu-id="d325b-115">IGCThreadControl — Interfejs</span><span class="sxs-lookup"><span data-stu-id="d325b-115">IGCThreadControl Interface</span></span>](igcthreadcontrol-interface.md)
