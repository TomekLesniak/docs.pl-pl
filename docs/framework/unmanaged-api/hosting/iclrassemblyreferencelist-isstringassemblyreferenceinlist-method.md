---
title: ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList — Metoda
ms.date: 03/30/2017
api_name:
- ICLRAssemblyReferenceList.IsStringAssemblyReferenceInList
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList
helpviewer_keywords:
- ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList method [.NET Framework hosting]
- IsStringAssemblyReferenceInList method [.NET Framework hosting]
ms.assetid: e6121cc3-2f11-42c7-bdae-47808581ff71
topic_type:
- apiref
ms.openlocfilehash: 74d47b3f55c10f65d47f726a2b96ba5e0b18b749
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679146"
---
# <a name="iclrassemblyreferencelistisstringassemblyreferenceinlist-method"></a><span data-ttu-id="66629-102">ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList — Metoda</span><span class="sxs-lookup"><span data-stu-id="66629-102">ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList Method</span></span>

<span data-ttu-id="66629-103">Pobiera wartość wskazującą, czy podana nazwa jest zgodna z nazwą zestawu znajdującego się na liście.</span><span class="sxs-lookup"><span data-stu-id="66629-103">Gets a value that indicates whether the supplied name matches the name of an assembly in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66629-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="66629-104">Syntax</span></span>  
  
```cpp  
HRESULT IsStringAssemblyReferenceInList (  
    [in] LPCWSTR pwzAssemblyName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="66629-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="66629-105">Parameters</span></span>  

 `pwzAssemblyName`  
 <span data-ttu-id="66629-106">podczas Nazwa zestawu, który ma zostać wyszukany.</span><span class="sxs-lookup"><span data-stu-id="66629-106">[in] The name of the assembly for which to search.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="66629-107">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="66629-107">Return Value</span></span>  
  
|<span data-ttu-id="66629-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="66629-108">HRESULT</span></span>|<span data-ttu-id="66629-109">Opis</span><span class="sxs-lookup"><span data-stu-id="66629-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="66629-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="66629-110">S_OK</span></span>|<span data-ttu-id="66629-111">Ciąg zostanie wyświetlony na liście.</span><span class="sxs-lookup"><span data-stu-id="66629-111">The string appears in the list.</span></span>|  
|<span data-ttu-id="66629-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="66629-112">S_FALSE</span></span>|<span data-ttu-id="66629-113">Ciąg nie pojawia się na liście.</span><span class="sxs-lookup"><span data-stu-id="66629-113">The string does not appear in the list.</span></span>|  
|<span data-ttu-id="66629-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="66629-114">E_FAIL</span></span>|<span data-ttu-id="66629-115">Wystąpił nieznany błąd krytyczny.</span><span class="sxs-lookup"><span data-stu-id="66629-115">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="66629-116">Po powrocie metody E_FAIL, środowisko uruchomieniowe języka wspólnego nie będzie już można używać w procesie.</span><span class="sxs-lookup"><span data-stu-id="66629-116">After a method returns E_FAIL, the common language runtime is no longer usable within the process.</span></span> <span data-ttu-id="66629-117">Kolejne wywołania metod hostingu zwracają HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="66629-117">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="66629-118">Wymagania</span><span class="sxs-lookup"><span data-stu-id="66629-118">Requirements</span></span>  

 <span data-ttu-id="66629-119">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="66629-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66629-120">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="66629-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="66629-121">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="66629-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="66629-122">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66629-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66629-123">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="66629-123">See also</span></span>

- [<span data-ttu-id="66629-124">ICLRAssemblyIdentityManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="66629-124">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="66629-125">ICLRAssemblyReferenceList — Interfejs</span><span class="sxs-lookup"><span data-stu-id="66629-125">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="66629-126">IHostAssemblyManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="66629-126">IHostAssemblyManager Interface</span></span>](ihostassemblymanager-interface.md)
- [<span data-ttu-id="66629-127">IHostAssemblyStore — Interfejs</span><span class="sxs-lookup"><span data-stu-id="66629-127">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
