---
title: ICLRHostBindingPolicyManager — Interfejs
ms.date: 03/30/2017
api_name:
- ICLRHostBindingPolicyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostBindingPolicyManager
helpviewer_keywords:
- ICLRHostBindingPolicyManager interface [.NET Framework hosting]
ms.assetid: f9da168b-366b-4b2b-bdb9-330b6bad5a6b
topic_type:
- apiref
ms.openlocfilehash: 49d1ee4dd0965d4ae5b54b53208809cfbdf7e718
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725636"
---
# <a name="iclrhostbindingpolicymanager-interface"></a><span data-ttu-id="6c0c1-102">ICLRHostBindingPolicyManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="6c0c1-102">ICLRHostBindingPolicyManager Interface</span></span>

<span data-ttu-id="6c0c1-103">Dostarcza metody dla hosta do szacowania bieżących zasad powiązań i przekazywania zmian zasad dla określonego zestawu.</span><span class="sxs-lookup"><span data-stu-id="6c0c1-103">Provides methods for the host to evaluate current binding policy and communicate policy changes for a specified assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6c0c1-104">Metody</span><span class="sxs-lookup"><span data-stu-id="6c0c1-104">Methods</span></span>  
  
|<span data-ttu-id="6c0c1-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="6c0c1-105">Method</span></span>|<span data-ttu-id="6c0c1-106">Opis</span><span class="sxs-lookup"><span data-stu-id="6c0c1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6c0c1-107">EvaluatePolicy, metoda</span><span class="sxs-lookup"><span data-stu-id="6c0c1-107">EvaluatePolicy Method</span></span>](iclrhostbindingpolicymanager-evaluatepolicy-method.md)|<span data-ttu-id="6c0c1-108">Oblicza zasady powiązań w imieniu hosta.</span><span class="sxs-lookup"><span data-stu-id="6c0c1-108">Evaluates binding policy on behalf of the host.</span></span>|  
|[<span data-ttu-id="6c0c1-109">ModifyApplicationPolicy, metoda</span><span class="sxs-lookup"><span data-stu-id="6c0c1-109">ModifyApplicationPolicy Method</span></span>](iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md)|<span data-ttu-id="6c0c1-110">Modyfikuje zasady powiązań dla określonego zestawu i tworzy nową wersję zasad.</span><span class="sxs-lookup"><span data-stu-id="6c0c1-110">Modifies the binding policy for the specified assembly, and creates a new version of the policy.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6c0c1-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="6c0c1-111">Requirements</span></span>  

 <span data-ttu-id="6c0c1-112">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6c0c1-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c0c1-113">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="6c0c1-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6c0c1-114">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6c0c1-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6c0c1-115">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c0c1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c0c1-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="6c0c1-116">See also</span></span>

- [<span data-ttu-id="6c0c1-117">ICLRAssemblyIdentityManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="6c0c1-117">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="6c0c1-118">IHostAssemblyStore — Interfejs</span><span class="sxs-lookup"><span data-stu-id="6c0c1-118">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
- [<span data-ttu-id="6c0c1-119">Hosting — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="6c0c1-119">Hosting Interfaces</span></span>](hosting-interfaces.md)
