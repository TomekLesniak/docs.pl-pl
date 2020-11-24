---
title: IHostAssemblyManager — Interfejs
ms.date: 03/30/2017
api_name:
- IHostAssemblyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyManager
helpviewer_keywords:
- IHostAssemblyManager interface [.NET Framework hosting]
ms.assetid: dfec05bb-3cd7-4bd5-b396-a4f097c3a636
topic_type:
- apiref
ms.openlocfilehash: a06e7f13b6de9450aa2a81f28f591c0a3ce8db0f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95681005"
---
# <a name="ihostassemblymanager-interface"></a><span data-ttu-id="9671e-102">IHostAssemblyManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="9671e-102">IHostAssemblyManager Interface</span></span>

<span data-ttu-id="9671e-103">Dostarcza metody, które umożliwiają hostowi określenie zestawów zestawów, które powinny być ładowane przez środowisko uruchomieniowe języka wspólnego (CLR) lub hosta.</span><span class="sxs-lookup"><span data-stu-id="9671e-103">Provides methods that allow a host to specify sets of assemblies that should be loaded by the common language runtime (CLR) or by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9671e-104">Metody</span><span class="sxs-lookup"><span data-stu-id="9671e-104">Methods</span></span>  
  
|<span data-ttu-id="9671e-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="9671e-105">Method</span></span>|<span data-ttu-id="9671e-106">Opis</span><span class="sxs-lookup"><span data-stu-id="9671e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9671e-107">GetAssemblyStore, metoda</span><span class="sxs-lookup"><span data-stu-id="9671e-107">GetAssemblyStore Method</span></span>](ihostassemblymanager-getassemblystore-method.md)|<span data-ttu-id="9671e-108">Pobiera wskaźnik interfejsu do [IHostAssemblyStore](ihostassemblystore-interface.md) , który reprezentuje listę zestawów załadowanych przez hosta.</span><span class="sxs-lookup"><span data-stu-id="9671e-108">Gets an interface pointer to an [IHostAssemblyStore](ihostassemblystore-interface.md) that represents the list of assemblies loaded by the host.</span></span>|  
|[<span data-ttu-id="9671e-109">GetNonHostStoreAssemblies, metoda</span><span class="sxs-lookup"><span data-stu-id="9671e-109">GetNonHostStoreAssemblies Method</span></span>](ihostassemblymanager-getnonhoststoreassemblies-method.md)|<span data-ttu-id="9671e-110">Pobiera wskaźnik interfejsu do [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) , który reprezentuje listę zestawów, które host oczekuje na załadowanie środowiska CLR.</span><span class="sxs-lookup"><span data-stu-id="9671e-110">Gets an interface pointer to an [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) that represents the list of assemblies that the host expects the CLR to load.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9671e-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="9671e-111">Remarks</span></span>  

 <span data-ttu-id="9671e-112">Host nie jest wymagany do implementowania `IHostAssemblyManager` ani `IHostAssemblyStore` .</span><span class="sxs-lookup"><span data-stu-id="9671e-112">The host is not required to implement `IHostAssemblyManager` or `IHostAssemblyStore`.</span></span> <span data-ttu-id="9671e-113">Jeśli host jest zaimplementowany `IHostAssemblyManager` , musi również implementować `IHostAssemblyStore` .</span><span class="sxs-lookup"><span data-stu-id="9671e-113">If the host does implement `IHostAssemblyManager`, it must also implement `IHostAssemblyStore`.</span></span>  
  
 <span data-ttu-id="9671e-114">Zapytania środowiska uruchomieniowego dla obiektu `IHostAssemblyManager` przez wywołanie [IHostControl:: GetHostManager](ihostcontrol-gethostmanager-method.md) po zainicjowaniu z `IID` IID_IHostAssemblyManager.</span><span class="sxs-lookup"><span data-stu-id="9671e-114">The runtime queries for an `IHostAssemblyManager` by calling [IHostControl::GetHostManager](ihostcontrol-gethostmanager-method.md) upon initialization with an `IID` of IID_IHostAssemblyManager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9671e-115">Wymagania</span><span class="sxs-lookup"><span data-stu-id="9671e-115">Requirements</span></span>  

 <span data-ttu-id="9671e-116">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9671e-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9671e-117">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="9671e-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9671e-118">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9671e-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9671e-119">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9671e-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9671e-120">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="9671e-120">See also</span></span>

- [<span data-ttu-id="9671e-121">ICLRAssemblyReferenceList — Interfejs</span><span class="sxs-lookup"><span data-stu-id="9671e-121">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="9671e-122">IHostAssemblyStore — Interfejs</span><span class="sxs-lookup"><span data-stu-id="9671e-122">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
- [<span data-ttu-id="9671e-123">IHostControl — Interfejs</span><span class="sxs-lookup"><span data-stu-id="9671e-123">IHostControl Interface</span></span>](ihostcontrol-interface.md)
- [<span data-ttu-id="9671e-124">Hosting — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="9671e-124">Hosting Interfaces</span></span>](hosting-interfaces.md)
