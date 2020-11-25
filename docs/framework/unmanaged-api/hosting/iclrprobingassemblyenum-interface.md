---
title: ICLRProbingAssemblyEnum — Interfejs
ms.date: 03/30/2017
api_name:
- ICLRProbingAssemblyEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRProbingAssemblyEnum
helpviewer_keywords:
- ICLRProbingAssemblyEnum interface [.NET Framework hosting]
ms.assetid: e7d3ccab-b0f0-4872-8935-0ed72920171b
topic_type:
- apiref
ms.openlocfilehash: 6df08889af30542af5a128cbffc38a57ce640fde
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728930"
---
# <a name="iclrprobingassemblyenum-interface"></a><span data-ttu-id="55027-102">ICLRProbingAssemblyEnum — Interfejs</span><span class="sxs-lookup"><span data-stu-id="55027-102">ICLRProbingAssemblyEnum Interface</span></span>

<span data-ttu-id="55027-103">Dostarcza metody, które umożliwiają hostowi pobieranie tożsamości dla zestawu przy użyciu informacji o tożsamości zestawu, które są wewnętrzne dla środowiska uruchomieniowego języka wspólnego (CLR), bez konieczności tworzenia lub zrozumienia tożsamości.</span><span class="sxs-lookup"><span data-stu-id="55027-103">Provides methods that enable the host to get the probing identities of an assembly by using the assembly's identity information that is internal to the common language runtime (CLR), without needing to create or understand that identity.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="55027-104">Metody</span><span class="sxs-lookup"><span data-stu-id="55027-104">Methods</span></span>  
  
|<span data-ttu-id="55027-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="55027-105">Method</span></span>|<span data-ttu-id="55027-106">Opis</span><span class="sxs-lookup"><span data-stu-id="55027-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="55027-107">Get — Metoda</span><span class="sxs-lookup"><span data-stu-id="55027-107">Get Method</span></span>](iclrprobingassemblyenum-get-method.md)|<span data-ttu-id="55027-108">Pobiera tożsamość zestawu o określonym indeksie.</span><span class="sxs-lookup"><span data-stu-id="55027-108">Gets the assembly identity at the specified index.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="55027-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="55027-109">Remarks</span></span>  

 <span data-ttu-id="55027-110">Metody, takie jak [ICLRAssemblyIdentityManager:: GetProbingAssembliesFromReference —](iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) , zwracają `ICLRProbingAssemblyEnum` wystąpienie.</span><span class="sxs-lookup"><span data-stu-id="55027-110">Methods such as [ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference](iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) return an `ICLRProbingAssemblyEnum` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55027-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="55027-111">Requirements</span></span>  

 <span data-ttu-id="55027-112">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="55027-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55027-113">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="55027-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="55027-114">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="55027-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="55027-115">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55027-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55027-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="55027-116">See also</span></span>

- [<span data-ttu-id="55027-117">ICLRAssemblyIdentityManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="55027-117">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="55027-118">ICLRAssemblyReferenceList — Interfejs</span><span class="sxs-lookup"><span data-stu-id="55027-118">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="55027-119">Hosting — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="55027-119">Hosting Interfaces</span></span>](hosting-interfaces.md)
