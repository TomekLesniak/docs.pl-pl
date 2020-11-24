---
title: ICLRAssemblyReferenceList::IsAssemblyReferenceInList — Metoda
ms.date: 03/30/2017
api_name:
- ICLRAssemblyReferenceList.IsAssemblyReferenceInList
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyReferenceList::IsAssemblyReferenceInList
helpviewer_keywords:
- ICLRAssemblyReferenceList::IsAssemblyReferenceInList method [.NET Framework hosting]
- IsAssemblyReferenceInList method [.NET Framework hosting]
ms.assetid: 8a570813-21be-407e-92a6-7ae8de3bc728
topic_type:
- apiref
ms.openlocfilehash: f74e0f111ff7869d0bfed61d420f3788f65876dc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679159"
---
# <a name="iclrassemblyreferencelistisassemblyreferenceinlist-method"></a><span data-ttu-id="427a7-102">ICLRAssemblyReferenceList::IsAssemblyReferenceInList — Metoda</span><span class="sxs-lookup"><span data-stu-id="427a7-102">ICLRAssemblyReferenceList::IsAssemblyReferenceInList Method</span></span>

<span data-ttu-id="427a7-103">Pobiera wartość wskazującą, czy dostarczony wskaźnik odwołuje się do zestawu na liście.</span><span class="sxs-lookup"><span data-stu-id="427a7-103">Gets a value that indicates whether the supplied pointer refers to an assembly in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="427a7-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="427a7-104">Syntax</span></span>  
  
```cpp  
HRESULT IsAssemblyReferenceInList (  
    [in] IUnknown *pName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="427a7-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="427a7-105">Parameters</span></span>  

 `pName`  
 <span data-ttu-id="427a7-106">podczas Wskaźnik interfejsu do zestawu, który ma zostać wyszukany.</span><span class="sxs-lookup"><span data-stu-id="427a7-106">[in] An interface pointer to the assembly for which to search.</span></span> <span data-ttu-id="427a7-107">Prawidłowe wartości to typu `IAssemblyName` lub `IReferenceIdentity` .</span><span class="sxs-lookup"><span data-stu-id="427a7-107">Valid values are of type `IAssemblyName` or `IReferenceIdentity`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="427a7-108">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="427a7-108">Return Value</span></span>  
  
|<span data-ttu-id="427a7-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="427a7-109">HRESULT</span></span>|<span data-ttu-id="427a7-110">Opis</span><span class="sxs-lookup"><span data-stu-id="427a7-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="427a7-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="427a7-111">S_OK</span></span>|<span data-ttu-id="427a7-112">Ciąg zostanie wyświetlony na liście.</span><span class="sxs-lookup"><span data-stu-id="427a7-112">The string appears in the list.</span></span>|  
|<span data-ttu-id="427a7-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="427a7-113">S_FALSE</span></span>|<span data-ttu-id="427a7-114">Ciąg nie pojawia się na liście.</span><span class="sxs-lookup"><span data-stu-id="427a7-114">The string does not appear in the list.</span></span>|  
|<span data-ttu-id="427a7-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="427a7-115">E_FAIL</span></span>|<span data-ttu-id="427a7-116">Wystąpił nieznany błąd krytyczny.</span><span class="sxs-lookup"><span data-stu-id="427a7-116">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="427a7-117">Po powrocie metody E_FAIL, środowisko uruchomieniowe języka wspólnego nie będzie już można używać w procesie.</span><span class="sxs-lookup"><span data-stu-id="427a7-117">After a method returns E_FAIL, the common language runtime is no longer usable within the process.</span></span> <span data-ttu-id="427a7-118">Kolejne wywołania metod hostingu zwracają HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="427a7-118">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="427a7-119">Wymagania</span><span class="sxs-lookup"><span data-stu-id="427a7-119">Requirements</span></span>  

 <span data-ttu-id="427a7-120">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="427a7-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="427a7-121">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="427a7-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="427a7-122">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="427a7-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="427a7-123">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="427a7-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="427a7-124">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="427a7-124">See also</span></span>

- [<span data-ttu-id="427a7-125">ICLRAssemblyIdentityManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="427a7-125">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="427a7-126">ICLRAssemblyReferenceList — Interfejs</span><span class="sxs-lookup"><span data-stu-id="427a7-126">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="427a7-127">IHostAssemblyManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="427a7-127">IHostAssemblyManager Interface</span></span>](ihostassemblymanager-interface.md)
- [<span data-ttu-id="427a7-128">IHostAssemblyStore — Interfejs</span><span class="sxs-lookup"><span data-stu-id="427a7-128">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
