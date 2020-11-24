---
title: ICLRAssemblyReferenceList — Interfejs
ms.date: 03/30/2017
api_name:
- ICLRAssemblyReferenceList
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyReferenceList
helpviewer_keywords:
- ICLRAssemblyReferenceList interface [.NET Framework hosting]
ms.assetid: 5f890fdf-d22a-429e-a35f-135273d1a636
topic_type:
- apiref
ms.openlocfilehash: a75235cd0ac0e55412f0ba58881796e3ebc801f1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679242"
---
# <a name="iclrassemblyreferencelist-interface"></a><span data-ttu-id="3d37b-102">ICLRAssemblyReferenceList — Interfejs</span><span class="sxs-lookup"><span data-stu-id="3d37b-102">ICLRAssemblyReferenceList Interface</span></span>

<span data-ttu-id="3d37b-103">Zarządza listą zestawów, które są ładowane przez środowisko uruchomieniowe języka wspólnego (CLR), a nie przez hosta.</span><span class="sxs-lookup"><span data-stu-id="3d37b-103">Manages a list of assemblies that are loaded by the common language runtime (CLR) and not by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3d37b-104">Metody</span><span class="sxs-lookup"><span data-stu-id="3d37b-104">Methods</span></span>  
  
|<span data-ttu-id="3d37b-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="3d37b-105">Method</span></span>|<span data-ttu-id="3d37b-106">Opis</span><span class="sxs-lookup"><span data-stu-id="3d37b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3d37b-107">IsAssemblyReferenceInList, metoda</span><span class="sxs-lookup"><span data-stu-id="3d37b-107">IsAssemblyReferenceInList Method</span></span>](iclrassemblyreferencelist-isassemblyreferenceinlist-method.md)|<span data-ttu-id="3d37b-108">Pobiera wartość wskazującą, czy dostarczony wskaźnik odwołuje się do zestawu na liście.</span><span class="sxs-lookup"><span data-stu-id="3d37b-108">Gets a value that indicates whether the supplied pointer references an assembly in the list.</span></span>|  
|[<span data-ttu-id="3d37b-109">IsStringAssemblyReferenceInList, metoda</span><span class="sxs-lookup"><span data-stu-id="3d37b-109">IsStringAssemblyReferenceInList Method</span></span>](iclrassemblyreferencelist-isstringassemblyreferenceinlist-method.md)|<span data-ttu-id="3d37b-110">Pobiera wartość wskazującą, czy podana nazwa jest zgodna z nazwą zestawu znajdującego się na liście.</span><span class="sxs-lookup"><span data-stu-id="3d37b-110">Gets a value that indicates whether the supplied name matches the name of an assembly in the list.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3d37b-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="3d37b-111">Remarks</span></span>  

 <span data-ttu-id="3d37b-112">Wywołaj metodę [ICLRAssemblyIdentityManager:: GetCLRAssemblyReferenceList —](iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md) , aby uzyskać wskaźnik do wystąpienia `ICLRAssemblyReferenceList` .</span><span class="sxs-lookup"><span data-stu-id="3d37b-112">Call the [ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList](iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md) method to get a pointer to an instance of `ICLRAssemblyReferenceList`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d37b-113">Wymagania</span><span class="sxs-lookup"><span data-stu-id="3d37b-113">Requirements</span></span>  

 <span data-ttu-id="3d37b-114">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d37b-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d37b-115">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="3d37b-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3d37b-116">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3d37b-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3d37b-117">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d37b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d37b-118">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="3d37b-118">See also</span></span>

- [<span data-ttu-id="3d37b-119">ICLRAssemblyIdentityManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="3d37b-119">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="3d37b-120">IHostAssemblyStore — Interfejs</span><span class="sxs-lookup"><span data-stu-id="3d37b-120">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
- [<span data-ttu-id="3d37b-121">Hosting — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="3d37b-121">Hosting Interfaces</span></span>](hosting-interfaces.md)
