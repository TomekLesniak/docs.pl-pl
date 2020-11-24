---
title: IGCHost::SetVirtualMemLimit — Metoda
ms.date: 03/30/2017
api_name:
- IGCHost.SetVirtualMemLimit
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetVirtualMemLimit
helpviewer_keywords:
- IGCHost::SetVirtualMemLimit method [.NET Framework hosting]
- SetVirtualMemLimit method [.NET Framework hosting]
ms.assetid: c7e7c2d0-e58c-4650-b40c-47b2be2cda45
topic_type:
- apiref
ms.openlocfilehash: 9898b760edbb149afcd6bf957a30d0a47287485b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687824"
---
# <a name="igchostsetvirtualmemlimit-method"></a><span data-ttu-id="71e7d-102">IGCHost::SetVirtualMemLimit — Metoda</span><span class="sxs-lookup"><span data-stu-id="71e7d-102">IGCHost::SetVirtualMemLimit Method</span></span>

<span data-ttu-id="71e7d-103">Ustawia maksymalny rozmiar pamięci wirtualnej środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="71e7d-103">Sets the maximum size of the runtime's virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71e7d-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="71e7d-104">Syntax</span></span>  
  
```cpp  
HRESULT SetVirtualMemLimit (  
    [in] SIZE_T sztMaxVirtualMemMB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="71e7d-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="71e7d-105">Parameters</span></span>  

 `sztMaxVirtualMemMB`  
 <span data-ttu-id="71e7d-106">podczas Maksymalny rozmiar pamięci wirtualnej środowiska uruchomieniowego (w megabajtach).</span><span class="sxs-lookup"><span data-stu-id="71e7d-106">[in] The maximum size, in megabytes, of the runtime's virtual memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="71e7d-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="71e7d-107">Remarks</span></span>  

 <span data-ttu-id="71e7d-108">Maksymalny rozmiar pamięci wirtualnej środowiska uruchomieniowego można zmienić dynamicznie.</span><span class="sxs-lookup"><span data-stu-id="71e7d-108">The maximum size of the runtime's virtual memory can be changed dynamically.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71e7d-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="71e7d-109">Requirements</span></span>  

 <span data-ttu-id="71e7d-110">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71e7d-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71e7d-111">**Nagłówek:** GCHost. idl, GCHost. h</span><span class="sxs-lookup"><span data-stu-id="71e7d-111">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="71e7d-112">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="71e7d-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="71e7d-113">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71e7d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71e7d-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="71e7d-114">See also</span></span>

- [<span data-ttu-id="71e7d-115">IGCHost — Interfejs</span><span class="sxs-lookup"><span data-stu-id="71e7d-115">IGCHost Interface</span></span>](igchost-interface.md)
