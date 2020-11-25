---
title: IGCThreadControl::SuspensionStarting — Metoda
ms.date: 03/30/2017
api_name:
- IGCThreadControl.SuspensionStarting
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SuspensionStarting
helpviewer_keywords:
- IGCThreadControl::SuspensionStarting method [.NET Framework hosting]
- SuspensionStarting method, IGCThreadControl interface [.NET Framework hosting]
ms.assetid: 0af312af-98e9-415e-b182-42e80a1aee51
topic_type:
- apiref
ms.openlocfilehash: 9d39ee79f7734f7dd099a07640ecb06f4f8dcbb3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721663"
---
# <a name="igcthreadcontrolsuspensionstarting-method"></a><span data-ttu-id="39758-102">IGCThreadControl::SuspensionStarting — Metoda</span><span class="sxs-lookup"><span data-stu-id="39758-102">IGCThreadControl::SuspensionStarting Method</span></span>

<span data-ttu-id="39758-103">Powiadamia hosta, że środowisko uruchomieniowe rozpoczyna zawieszenie wątku na wyrzucanie elementów bezużytecznych lub inne zawieszenie.</span><span class="sxs-lookup"><span data-stu-id="39758-103">Notifies the host that the runtime is beginning a thread suspension for a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39758-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="39758-104">Syntax</span></span>  
  
```cpp  
HRESULT SuspensionStarting ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="39758-105">Uwagi</span><span class="sxs-lookup"><span data-stu-id="39758-105">Remarks</span></span>  

 <span data-ttu-id="39758-106">Nie należy ponownie planować żadnych wątków w trakcie `SuspensionStarting` wywołania zwrotnego.</span><span class="sxs-lookup"><span data-stu-id="39758-106">Do not reschedule any threads during the `SuspensionStarting` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39758-107">Wymagania</span><span class="sxs-lookup"><span data-stu-id="39758-107">Requirements</span></span>  

 <span data-ttu-id="39758-108">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="39758-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39758-109">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="39758-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="39758-110">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="39758-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="39758-111">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39758-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39758-112">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="39758-112">See also</span></span>

- [<span data-ttu-id="39758-113">IGCThreadControl — Interfejs</span><span class="sxs-lookup"><span data-stu-id="39758-113">IGCThreadControl Interface</span></span>](igcthreadcontrol-interface.md)
