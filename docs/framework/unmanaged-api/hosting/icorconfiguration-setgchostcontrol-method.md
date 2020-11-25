---
title: ICorConfiguration::SetGCHostControl — Metoda
ms.date: 03/30/2017
api_name:
- ICorConfiguration.SetGCHostControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetGCHostControl
helpviewer_keywords:
- ICorConfiguration::SetGCHostControl method [.NET Framework hosting]
- SetGCHostControl method [.NET Framework hosting]
ms.assetid: bca6bd79-e288-475a-aa46-6bf81541d966
topic_type:
- apiref
ms.openlocfilehash: 4824fcfc53bae6c81760a23f76e83fb8ae7efd79
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715815"
---
# <a name="icorconfigurationsetgchostcontrol-method"></a><span data-ttu-id="4bd77-102">ICorConfiguration::SetGCHostControl — Metoda</span><span class="sxs-lookup"><span data-stu-id="4bd77-102">ICorConfiguration::SetGCHostControl Method</span></span>

<span data-ttu-id="4bd77-103">Ustawia interfejs wywołania zwrotnego, który ma być używany przez moduł wyrzucania elementów bezużytecznych, aby zażądać od hosta zmiany limitów pamięci wirtualnej.</span><span class="sxs-lookup"><span data-stu-id="4bd77-103">Sets the callback interface to be used by the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4bd77-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="4bd77-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGCHostControl (  
    [in] IGCHostControl* pGCHostControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4bd77-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="4bd77-105">Parameters</span></span>  

 `pGCHostControl`  
 <span data-ttu-id="4bd77-106">podczas Wskaźnik do obiektu [IGCHostControl](igchostcontrol-interface.md) , który umożliwia modułowi wyrzucania elementów bezużytecznych żądanie zmiany limitów pamięci wirtualnej.</span><span class="sxs-lookup"><span data-stu-id="4bd77-106">[in] A pointer to an [IGCHostControl](igchostcontrol-interface.md) object that allows the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4bd77-107">Wymagania</span><span class="sxs-lookup"><span data-stu-id="4bd77-107">Requirements</span></span>  

 <span data-ttu-id="4bd77-108">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4bd77-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4bd77-109">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="4bd77-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4bd77-110">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4bd77-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4bd77-111">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4bd77-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bd77-112">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="4bd77-112">See also</span></span>

- [<span data-ttu-id="4bd77-113">ICorConfiguration — Interfejs</span><span class="sxs-lookup"><span data-stu-id="4bd77-113">ICorConfiguration Interface</span></span>](icorconfiguration-interface.md)
