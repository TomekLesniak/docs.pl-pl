---
title: IHostTaskManager::GetStackGuarantee — Metoda
ms.date: 03/30/2017
api_name:
- IHostTaskManager.GetStackGuarantee
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::GetStackGuarantee
helpviewer_keywords:
- GetStackGuarantee method [.NET Framework hosting]
- IHostTaskManager::GetStackGuarantee method [.NET Framework hosting]
ms.assetid: 8176d732-c25c-4520-811d-e3310f339947
topic_type:
- apiref
ms.openlocfilehash: 718e6f3f19a5c368091c8a8aad3bd1f6598228df
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727283"
---
# <a name="ihosttaskmanagergetstackguarantee-method"></a><span data-ttu-id="93485-102">IHostTaskManager::GetStackGuarantee — Metoda</span><span class="sxs-lookup"><span data-stu-id="93485-102">IHostTaskManager::GetStackGuarantee Method</span></span>

<span data-ttu-id="93485-103">Pobiera ilość miejsca na stosie, która ma być dostępna po zakończeniu operacji stosu, ale przed zamknięciem procesu.</span><span class="sxs-lookup"><span data-stu-id="93485-103">Gets the amount of stack space that is guaranteed to be available after a stack operation completes, but before the closing of a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93485-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="93485-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackGuarantee(  
    [out] ULONG *pGuarantee  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="93485-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="93485-105">Parameters</span></span>  

 `pGuarantee`  
 <span data-ttu-id="93485-106">określoną Wskaźnik do liczby dostępnych bajtów.</span><span class="sxs-lookup"><span data-stu-id="93485-106">[out] A pointer to the number of bytes that are available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="93485-107">Wymagania</span><span class="sxs-lookup"><span data-stu-id="93485-107">Requirements</span></span>  

 <span data-ttu-id="93485-108">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="93485-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93485-109">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="93485-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="93485-110">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="93485-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="93485-111">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93485-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93485-112">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="93485-112">See also</span></span>

- [<span data-ttu-id="93485-113">IHostTaskManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="93485-113">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
