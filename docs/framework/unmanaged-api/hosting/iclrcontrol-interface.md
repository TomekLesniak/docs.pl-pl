---
title: ICLRControl — Interfejs
ms.date: 03/30/2017
api_name:
- ICLRControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRControl
helpviewer_keywords:
- ICLRControl interface [.NET Framework hosting]
ms.assetid: a24fd905-1fa6-45a0-ad65-e9e2ee58861e
topic_type:
- apiref
ms.openlocfilehash: acf449014f5bf5683d5488f8ed2ead963676fe6b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728345"
---
# <a name="iclrcontrol-interface"></a><span data-ttu-id="79af7-102">ICLRControl — Interfejs</span><span class="sxs-lookup"><span data-stu-id="79af7-102">ICLRControl Interface</span></span>

<span data-ttu-id="79af7-103">Dostarcza metody, które umożliwiają hostowi uzyskanie odwołań do i Konfigurowanie aspektów środowiska uruchomieniowego języka wspólnego (CLR).</span><span class="sxs-lookup"><span data-stu-id="79af7-103">Provides methods that allow a host to get references to, and configure aspects of, the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="79af7-104">Metody</span><span class="sxs-lookup"><span data-stu-id="79af7-104">Methods</span></span>  
  
|<span data-ttu-id="79af7-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="79af7-105">Method</span></span>|<span data-ttu-id="79af7-106">Opis</span><span class="sxs-lookup"><span data-stu-id="79af7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="79af7-107">GetCLRManager, metoda</span><span class="sxs-lookup"><span data-stu-id="79af7-107">GetCLRManager Method</span></span>](iclrcontrol-getclrmanager-method.md)|<span data-ttu-id="79af7-108">Pobiera wskaźnik interfejsu do wystąpienia dowolnego typu Menedżera, którego host może użyć do skonfigurowania środowiska CLR.</span><span class="sxs-lookup"><span data-stu-id="79af7-108">Gets an interface pointer to an instance of any of the manager types the host can use to configure the CLR.</span></span>|  
|[<span data-ttu-id="79af7-109">SetAppDomainManagerType — Metoda</span><span class="sxs-lookup"><span data-stu-id="79af7-109">SetAppDomainManagerType Method</span></span>](iclrcontrol-setappdomainmanagertype-method.md)|<span data-ttu-id="79af7-110">Ustawia typ pochodzący od <xref:System.AppDomainManager> typu dla menedżerów domeny aplikacji.</span><span class="sxs-lookup"><span data-stu-id="79af7-110">Sets a type derived from <xref:System.AppDomainManager> as the type for application domain managers.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="79af7-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="79af7-111">Requirements</span></span>  

 <span data-ttu-id="79af7-112">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="79af7-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79af7-113">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="79af7-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="79af7-114">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="79af7-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="79af7-115">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="79af7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79af7-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="79af7-116">See also</span></span>

- [<span data-ttu-id="79af7-117">ICLRAssemblyIdentityManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="79af7-117">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="79af7-118">ICLRDebugManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="79af7-118">ICLRDebugManager Interface</span></span>](iclrdebugmanager-interface.md)
- [<span data-ttu-id="79af7-119">ICLRGCManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="79af7-119">ICLRGCManager Interface</span></span>](iclrgcmanager-interface.md)
- [<span data-ttu-id="79af7-120">ICLRHostBindingPolicyManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="79af7-120">ICLRHostBindingPolicyManager Interface</span></span>](iclrhostbindingpolicymanager-interface.md)
- [<span data-ttu-id="79af7-121">ICLRHostProtectionManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="79af7-121">ICLRHostProtectionManager Interface</span></span>](iclrhostprotectionmanager-interface.md)
- [<span data-ttu-id="79af7-122">ICLROnEventManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="79af7-122">ICLROnEventManager Interface</span></span>](iclroneventmanager-interface.md)
- [<span data-ttu-id="79af7-123">ICLRPolicyManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="79af7-123">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="79af7-124">IHostControl — Interfejs</span><span class="sxs-lookup"><span data-stu-id="79af7-124">IHostControl Interface</span></span>](ihostcontrol-interface.md)
- [<span data-ttu-id="79af7-125">Hosting — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="79af7-125">Hosting Interfaces</span></span>](hosting-interfaces.md)
