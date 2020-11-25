---
title: ICLRMetaHostPolicy — Interfejs
ms.date: 03/30/2017
api_name:
- ICLRMetaHostPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHostPolicy
helpviewer_keywords:
- ICLRMetaHostPolicy interface [.NET Framework hosting]
ms.assetid: 1bdeccb6-0698-4c97-ad69-eae2b69e59f1
topic_type:
- apiref
ms.openlocfilehash: 515b73b019c683bd3e5aa3b895ee5623e75e4ad0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707610"
---
# <a name="iclrmetahostpolicy-interface"></a><span data-ttu-id="5b61b-102">ICLRMetaHostPolicy — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5b61b-102">ICLRMetaHostPolicy Interface</span></span>

<span data-ttu-id="5b61b-103">Udostępnia metodę [GetRequestedRuntime —](iclrmetahostpolicy-getrequestedruntime-method.md) , która zwraca wskaźnik do interfejsu środowiska uruchomieniowego języka wspólnego (CLR) na podstawie kryteriów zasad, zestawu zarządzanego, wersji i pliku konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="5b61b-103">Provides the [GetRequestedRuntime](iclrmetahostpolicy-getrequestedruntime-method.md) method, which returns a pointer to a common language runtime (CLR) interface based on a policy criteria, managed assembly, version and configuration file.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5b61b-104">Metody</span><span class="sxs-lookup"><span data-stu-id="5b61b-104">Methods</span></span>  
  
|<span data-ttu-id="5b61b-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="5b61b-105">Method</span></span>|<span data-ttu-id="5b61b-106">Opis</span><span class="sxs-lookup"><span data-stu-id="5b61b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5b61b-107">GetRequestedRuntime, metoda</span><span class="sxs-lookup"><span data-stu-id="5b61b-107">GetRequestedRuntime Method</span></span>](iclrmetahostpolicy-getrequestedruntime-method.md)|<span data-ttu-id="5b61b-108">Udostępnia preferowany interfejs CLR na podstawie kryteriów zasad, zestawu zarządzanego, wersji i pliku konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="5b61b-108">Provides a preferred CLR interface based on a policy criteria, managed assembly, version, and configuration file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5b61b-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="5b61b-109">Remarks</span></span>  

 <span data-ttu-id="5b61b-110">Odwołanie do tego interfejsu można uzyskać, wywołując funkcję [CLRCreateInstance](clrcreateinstance-function.md) , jak pokazano w poniższym kodzie:</span><span class="sxs-lookup"><span data-stu-id="5b61b-110">You can get a reference to this interface by calling the [CLRCreateInstance](clrcreateinstance-function.md) function as shown in the following code:</span></span>  
  
```cpp  
ICLRMetaHostPolicy *pMetaHostPolicy = NULL;  
HRESULT hr = CLRCreateInstance(CLSID_CLRMetaHostPolicy,  
                   IID_ICLRMetaHostPolicy, (LPVOID*)&pMetaHostPolicy);  
```  
  
> [!NOTE]
> <span data-ttu-id="5b61b-111">Ten interfejs nie ładuje ani nie aktywuje środowiska CLR, ale po prostu zwraca preferowaną wersję środowiska CLR na podstawie dostępnych wersji zainstalowanych lub załadowanych.</span><span class="sxs-lookup"><span data-stu-id="5b61b-111">This interface does not actually load or activate the CLR, but simply returns the preferred CLR version based on the available versions that are installed or loaded.</span></span>  
  
 <span data-ttu-id="5b61b-112">Interfejs API hostingu .NET Framework 4 konsoliduje zasady tak, aby hosty z konkretnymi potrzebami mogły korzystać z podstawowych funkcji bez ponoszenia niezamierzonych kar.</span><span class="sxs-lookup"><span data-stu-id="5b61b-112">The .NET Framework 4 hosting API consolidates policies so that hosts with specific needs may use basic functionality without incurring unintended penalties.</span></span> <span data-ttu-id="5b61b-113">Na przykład wiele eksportów MSCorEE.dll zostanie powiązana z określonym środowiskiem CLR, chociaż Metoda może nie być logicznie wymagana.</span><span class="sxs-lookup"><span data-stu-id="5b61b-113">For example, many of the MSCorEE.dll exports will bind to a specific CLR, although a method might not logically require it.</span></span> <span data-ttu-id="5b61b-114">Wyliczenie [METAHOST_POLICY_FLAGS](metahost-policy-flags-enumeration.md) zawiera zasady powiązań, które są wspólne dla większości hostów.</span><span class="sxs-lookup"><span data-stu-id="5b61b-114">The [METAHOST_POLICY_FLAGS](metahost-policy-flags-enumeration.md) enumeration provides binding policies that are common to the majority of hosts.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b61b-115">Wymagania</span><span class="sxs-lookup"><span data-stu-id="5b61b-115">Requirements</span></span>  

 <span data-ttu-id="5b61b-116">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5b61b-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b61b-117">**Nagłówek:** Obiekt ServiceHost. h</span><span class="sxs-lookup"><span data-stu-id="5b61b-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="5b61b-118">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5b61b-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5b61b-119">**.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b61b-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b61b-120">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="5b61b-120">See also</span></span>

- [<span data-ttu-id="5b61b-121">Interfejsy hostingu środowiska CLR dodane w programie .NET Framework 4 i 4.5</span><span class="sxs-lookup"><span data-stu-id="5b61b-121">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [<span data-ttu-id="5b61b-122">Hosting — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="5b61b-122">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="5b61b-123">Hosting</span><span class="sxs-lookup"><span data-stu-id="5b61b-123">Hosting</span></span>](index.md)
