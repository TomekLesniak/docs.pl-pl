---
title: ICLRAssemblyIdentityManager — Interfejs
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager
helpviewer_keywords:
- ICLRAssemblyIdentityManager interface [.NET Framework hosting]
ms.assetid: 6a81c6fe-cc22-4062-ae27-d6eeee03a7b9
topic_type:
- apiref
ms.openlocfilehash: 41d049c931091d2cc0b41bd1e9d74b3c15d7878d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679263"
---
# <a name="iclrassemblyidentitymanager-interface"></a><span data-ttu-id="3e74b-102">ICLRAssemblyIdentityManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="3e74b-102">ICLRAssemblyIdentityManager Interface</span></span>

<span data-ttu-id="3e74b-103">Zapewnia metody obsługujące komunikację między hostem i środowiskiem uruchomieniowym języka wspólnego (CLR) dotyczące zestawów.</span><span class="sxs-lookup"><span data-stu-id="3e74b-103">Provides methods that support communication between the host and the common language runtime (CLR) about assemblies.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3e74b-104">Metody</span><span class="sxs-lookup"><span data-stu-id="3e74b-104">Methods</span></span>  
  
|<span data-ttu-id="3e74b-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="3e74b-105">Method</span></span>|<span data-ttu-id="3e74b-106">Opis</span><span class="sxs-lookup"><span data-stu-id="3e74b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3e74b-107">GetBindingIdentityFromFile, metoda</span><span class="sxs-lookup"><span data-stu-id="3e74b-107">GetBindingIdentityFromFile Method</span></span>](iclrassemblyidentitymanager-getbindingidentityfromfile-method.md)|<span data-ttu-id="3e74b-108">Pobiera dane powiązania tożsamości zestawu z określoną ścieżką do pliku.</span><span class="sxs-lookup"><span data-stu-id="3e74b-108">Gets the assembly identity binding data for the assembly at the specified file path.</span></span>|  
|[<span data-ttu-id="3e74b-109">GetBindingIdentityFromStream, metoda</span><span class="sxs-lookup"><span data-stu-id="3e74b-109">GetBindingIdentityFromStream Method</span></span>](iclrassemblyidentitymanager-getbindingidentityfromstream-method.md)|<span data-ttu-id="3e74b-110">Pobiera dane tożsamości zestawu kanonicznego dla zestawu w określonym strumieniu.</span><span class="sxs-lookup"><span data-stu-id="3e74b-110">Gets the canonical assembly identity data for the assembly in the specified stream.</span></span>|  
|[<span data-ttu-id="3e74b-111">GetCLRAssemblyReferenceList, metoda</span><span class="sxs-lookup"><span data-stu-id="3e74b-111">GetCLRAssemblyReferenceList Method</span></span>](iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md)|<span data-ttu-id="3e74b-112">Pobiera wystąpienie [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) z podanej listy tożsamości zestawów częściowych.</span><span class="sxs-lookup"><span data-stu-id="3e74b-112">Gets an [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) instance from the supplied list of partial assembly identities.</span></span>|  
|[<span data-ttu-id="3e74b-113">GetProbingAssembliesFromReference, metoda</span><span class="sxs-lookup"><span data-stu-id="3e74b-113">GetProbingAssembliesFromReference Method</span></span>](iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md)|<span data-ttu-id="3e74b-114">Pobiera moduł wyliczający [ICLRProbingAssemblyEnum](iclrprobingassemblyenum-interface.md) dla tożsamości zestawu, do których odwołuje się zestaw z określoną tożsamością.</span><span class="sxs-lookup"><span data-stu-id="3e74b-114">Gets an [ICLRProbingAssemblyEnum](iclrprobingassemblyenum-interface.md) enumerator for the assembly identities referenced by the assembly with the specified identity.</span></span>|  
|[<span data-ttu-id="3e74b-115">GetReferencedAssembliesFromFile, metoda</span><span class="sxs-lookup"><span data-stu-id="3e74b-115">GetReferencedAssembliesFromFile Method</span></span>](iclrassemblyidentitymanager-getreferencedassembliesfromfile-method.md)|<span data-ttu-id="3e74b-116">Pobiera wystąpienie [ICLRReferenceAssemblyEnum](iclrreferenceassemblyenum-interface.md) , które zawiera listę zestawów, do których odwołuje się zestaw w określonej ścieżce pliku.</span><span class="sxs-lookup"><span data-stu-id="3e74b-116">Gets an [ICLRReferenceAssemblyEnum](iclrreferenceassemblyenum-interface.md) instance that contains a list of assemblies referenced by the assembly at the specified file path.</span></span>|  
|[<span data-ttu-id="3e74b-117">GetReferencedAssembliesFromStream, metoda</span><span class="sxs-lookup"><span data-stu-id="3e74b-117">GetReferencedAssembliesFromStream Method</span></span>](iclrassemblyidentitymanager-getreferencedassembliesfromstream-method.md)|<span data-ttu-id="3e74b-118">Pobiera wskaźnik do `ICLRReferenceAssemblyEnum` obiektu, który zawiera dane tożsamości zestawu dla zestawów, do których odwołuje się zestaw w określonym strumieniu.</span><span class="sxs-lookup"><span data-stu-id="3e74b-118">Gets a pointer to an `ICLRReferenceAssemblyEnum` object that contains assembly identity data for the assemblies referenced by the assembly in the specified stream.</span></span>|  
|[<span data-ttu-id="3e74b-119">IsStronglyNamed, metoda</span><span class="sxs-lookup"><span data-stu-id="3e74b-119">IsStronglyNamed Method</span></span>](iclrassemblyidentitymanager-isstronglynamed-method.md)|<span data-ttu-id="3e74b-120">Pobiera wartość wskazującą, czy określony zestaw ma silną nazwę.</span><span class="sxs-lookup"><span data-stu-id="3e74b-120">Gets a value that indicates whether the specified assembly is strongly named.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3e74b-121">Uwagi</span><span class="sxs-lookup"><span data-stu-id="3e74b-121">Remarks</span></span>  

 <span data-ttu-id="3e74b-122">Służy `ICLRAssemblyIdentityManager` do pobierania wystąpień `ICLRAssemblyReferenceList` i wyliczania tożsamości zestawu.</span><span class="sxs-lookup"><span data-stu-id="3e74b-122">Use `ICLRAssemblyIdentityManager` to get instances of `ICLRAssemblyReferenceList` and to enumerate assembly identities.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e74b-123">Wymagania</span><span class="sxs-lookup"><span data-stu-id="3e74b-123">Requirements</span></span>  

 <span data-ttu-id="3e74b-124">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3e74b-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e74b-125">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="3e74b-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3e74b-126">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3e74b-126">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3e74b-127">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e74b-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e74b-128">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="3e74b-128">See also</span></span>

- [<span data-ttu-id="3e74b-129">ICLRAssemblyReferenceList — Interfejs</span><span class="sxs-lookup"><span data-stu-id="3e74b-129">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="3e74b-130">ICLRProbingAssemblyEnum — Interfejs</span><span class="sxs-lookup"><span data-stu-id="3e74b-130">ICLRProbingAssemblyEnum Interface</span></span>](iclrprobingassemblyenum-interface.md)
- [<span data-ttu-id="3e74b-131">Hosting — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="3e74b-131">Hosting Interfaces</span></span>](hosting-interfaces.md)
