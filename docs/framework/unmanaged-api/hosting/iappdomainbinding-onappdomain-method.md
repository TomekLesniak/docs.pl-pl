---
title: IAppDomainBinding::OnAppDomain — Metoda
ms.date: 03/30/2017
api_name:
- IAppDomainBinding.OnAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- OnAppDomain
helpviewer_keywords:
- IAppDomainBinding::OnAppDomain method [.NET Framework hosting]
- OnAppDomain method [.NET Framework hosting]
ms.assetid: b419dcc9-e8aa-484b-af0d-0f40358edb99
topic_type:
- apiref
ms.openlocfilehash: 65f6be8c12ce057422ad178c759affed170e44ba
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721717"
---
# <a name="iappdomainbindingonappdomain-method"></a><span data-ttu-id="e78c3-102">IAppDomainBinding::OnAppDomain — Metoda</span><span class="sxs-lookup"><span data-stu-id="e78c3-102">IAppDomainBinding::OnAppDomain Method</span></span>

<span data-ttu-id="e78c3-103">Wywoływane przez środowisko uruchomieniowe języka wspólnego (CLR) do powiadamiania hosta o utworzeniu domeny aplikacji.</span><span class="sxs-lookup"><span data-stu-id="e78c3-103">Called by the common language runtime (CLR) to notify the host that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e78c3-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="e78c3-104">Syntax</span></span>  
  
```cpp  
HRESULT OnAppDomain (  
    [in] IUnknown* pAppdomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e78c3-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="e78c3-105">Parameters</span></span>  

 `pAppdomain`  
 <span data-ttu-id="e78c3-106">podczas Wskaźnik do obiektu interfejsu [IUnknown](/cpp/atl/iunknown) , który reprezentuje nową domenę aplikacji.</span><span class="sxs-lookup"><span data-stu-id="e78c3-106">[in] A pointer to an [IUnknown](/cpp/atl/iunknown) interface object that represents the new application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e78c3-107">Wymagania</span><span class="sxs-lookup"><span data-stu-id="e78c3-107">Requirements</span></span>  

 <span data-ttu-id="e78c3-108">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e78c3-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e78c3-109">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e78c3-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e78c3-110">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e78c3-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e78c3-111">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e78c3-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e78c3-112">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="e78c3-112">See also</span></span>

- [<span data-ttu-id="e78c3-113">IAppDomainBinding — Interfejs</span><span class="sxs-lookup"><span data-stu-id="e78c3-113">IAppDomainBinding Interface</span></span>](iappdomainbinding-interface.md)
