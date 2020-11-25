---
title: ICLRRuntimeInfo::BindAsLegacyV2Runtime — Metoda
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.BindAsLegacyV2Runtime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::BindAsLegacyV2Runtime
helpviewer_keywords:
- ICLRRuntimeInfo::BindAsLegacyV2Runtime method [.NET Framework hosting]
- BindAsLegacyV2Runtime method [.NET Framework hosting]
ms.assetid: 65fd55ac-4a24-4479-9384-a2e8013bfb2b
topic_type:
- apiref
ms.openlocfilehash: f0a03ecce49bbc3c1c03d037c9be31a8e994259d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732099"
---
# <a name="iclrruntimeinfobindaslegacyv2runtime-method"></a><span data-ttu-id="c7f60-102">ICLRRuntimeInfo::BindAsLegacyV2Runtime — Metoda</span><span class="sxs-lookup"><span data-stu-id="c7f60-102">ICLRRuntimeInfo::BindAsLegacyV2Runtime Method</span></span>

<span data-ttu-id="c7f60-103">Wiąże bieżące środowisko uruchomieniowe dla wszystkich starszych decyzji zasad aktywacji środowiska uruchomieniowego języka wspólnego (CLR) w wersji 2.</span><span class="sxs-lookup"><span data-stu-id="c7f60-103">Binds the current runtime for all legacy common language runtime (CLR) version 2 activation policy decisions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7f60-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="c7f60-104">Syntax</span></span>  
  
```cpp  
HRESULT BindAsLegacyV2Runtime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="c7f60-105">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="c7f60-105">Return Value</span></span>  

 <span data-ttu-id="c7f60-106">Ta metoda zwraca następujące określone wartości HRESULT:</span><span class="sxs-lookup"><span data-stu-id="c7f60-106">This method returns the following specific HRESULTs:</span></span>  
  
|<span data-ttu-id="c7f60-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c7f60-107">HRESULT</span></span>|<span data-ttu-id="c7f60-108">Opis</span><span class="sxs-lookup"><span data-stu-id="c7f60-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c7f60-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="c7f60-109">S_OK</span></span>|<span data-ttu-id="c7f60-110">Powiązanie zakończyło się pomyślnie lub to środowisko uruchomieniowe zostało już powiązane jako starsze środowisko uruchomieniowe zasad aktywacji środowiska CLR w wersji 2.</span><span class="sxs-lookup"><span data-stu-id="c7f60-110">Either binding succeeded, or this runtime was already bound as the legacy CLR version 2 activation policy runtime.</span></span>|  
|<span data-ttu-id="c7f60-111">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span><span class="sxs-lookup"><span data-stu-id="c7f60-111">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span></span>|<span data-ttu-id="c7f60-112">Inne środowisko uruchomieniowe zostało już powiązane ze starszymi zasadami aktywacji środowiska CLR w wersji 2.</span><span class="sxs-lookup"><span data-stu-id="c7f60-112">A different runtime was already bound to the legacy CLR version 2 activation policy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c7f60-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="c7f60-113">Remarks</span></span>  

 <span data-ttu-id="c7f60-114">Jeśli bieżące środowisko uruchomieniowe jest już powiązane ze wszystkimi decyzjami dotyczącymi starszych zasad aktywacji środowiska CLR w wersji 2 (na przykład przy użyciu `useLegacyV2RuntimeActivationPolicy` atrybutu dla [ \<startup> elementu](../../configure-apps/file-schema/startup/startup-element.md) w pliku konfiguracji), ta metoda nie zwraca wyniku błędu; zamiast tego wynik jest S_OK, tak jak gdyby metoda pomyślnie powiązana z starszą zasadą aktywacji.</span><span class="sxs-lookup"><span data-stu-id="c7f60-114">If the current runtime is already bound for all legacy CLR version 2 activation policy decisions (for example, by using the `useLegacyV2RuntimeActivationPolicy` attribute on the [\<startup> element](../../configure-apps/file-schema/startup/startup-element.md) in the configuration file), this method does not return an error result; instead, the result is S_OK, just as it would be if the method had successfully bound legacy activation policy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7f60-115">Wymagania</span><span class="sxs-lookup"><span data-stu-id="c7f60-115">Requirements</span></span>  

 <span data-ttu-id="c7f60-116">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7f60-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7f60-117">**Nagłówek:** Obiekt ServiceHost. h</span><span class="sxs-lookup"><span data-stu-id="c7f60-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="c7f60-118">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c7f60-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c7f60-119">**.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7f60-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7f60-120">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="c7f60-120">See also</span></span>

- [<span data-ttu-id="c7f60-121">ICLRRuntimeInfo — Interfejs</span><span class="sxs-lookup"><span data-stu-id="c7f60-121">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="c7f60-122">Hosting — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="c7f60-122">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="c7f60-123">Hosting</span><span class="sxs-lookup"><span data-stu-id="c7f60-123">Hosting</span></span>](index.md)
- [<span data-ttu-id="c7f60-124">\<startup> Postaci</span><span class="sxs-lookup"><span data-stu-id="c7f60-124">\<startup> Element</span></span>](../../configure-apps/file-schema/startup/startup-element.md)
