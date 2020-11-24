---
title: IHostAssemblyStore — Interfejs
ms.date: 03/30/2017
api_name:
- IHostAssemblyStore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyStore
helpviewer_keywords:
- IHostAssemblyStore interface [.NET Framework hosting]
ms.assetid: cccb650f-abe0-41e2-9fd1-b383788eb1f6
topic_type:
- apiref
ms.openlocfilehash: 4b2fed963d2d0ebec54e5f7a4d95cba26c1bac1f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680956"
---
# <a name="ihostassemblystore-interface"></a><span data-ttu-id="16da5-102">IHostAssemblyStore — Interfejs</span><span class="sxs-lookup"><span data-stu-id="16da5-102">IHostAssemblyStore Interface</span></span>

<span data-ttu-id="16da5-103">Zapewnia metody, które pozwalają hostowi ładować zestawy i moduły niezależnie od środowiska uruchomieniowego języka wspólnego (CLR).</span><span class="sxs-lookup"><span data-stu-id="16da5-103">Provides methods that allow a host to load assemblies and modules independently of the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="16da5-104">Metody</span><span class="sxs-lookup"><span data-stu-id="16da5-104">Methods</span></span>  
  
|<span data-ttu-id="16da5-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="16da5-105">Method</span></span>|<span data-ttu-id="16da5-106">Opis</span><span class="sxs-lookup"><span data-stu-id="16da5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="16da5-107">ProvideAssembly, metoda</span><span class="sxs-lookup"><span data-stu-id="16da5-107">ProvideAssembly Method</span></span>](ihostassemblystore-provideassembly-method.md)|<span data-ttu-id="16da5-108">Pobiera odwołanie do zestawu, do którego nie odwołuje się [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) zwrócone z wywołania [IHostAssemblyManager:: GetNonHostStoreAssemblies —](ihostassemblymanager-getnonhoststoreassemblies-method.md).</span><span class="sxs-lookup"><span data-stu-id="16da5-108">Gets a reference to an assembly that is not referenced by the [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) returned from a call to [IHostAssemblyManager::GetNonHostStoreAssemblies](ihostassemblymanager-getnonhoststoreassemblies-method.md).</span></span>|  
|[<span data-ttu-id="16da5-109">ProvideModule, metoda</span><span class="sxs-lookup"><span data-stu-id="16da5-109">ProvideModule Method</span></span>](ihostassemblystore-providemodule-method.md)|<span data-ttu-id="16da5-110">Rozwiązuje moduł w zestawie lub połączonym (nieosadzonym) pliku zasobów.</span><span class="sxs-lookup"><span data-stu-id="16da5-110">Resolves a module within an assembly or a linked (not embedded) resource file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="16da5-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="16da5-111">Remarks</span></span>  

 <span data-ttu-id="16da5-112">`IHostAssemblyStore` umożliwia hostowi wydajne ładowanie zestawów w oparciu o tożsamość zestawu.</span><span class="sxs-lookup"><span data-stu-id="16da5-112">`IHostAssemblyStore` provides a way for a host to load assemblies efficiently based on assembly identity.</span></span> <span data-ttu-id="16da5-113">Host ładuje zestawy, zwracając `IStream` wystąpienia bezpośrednio w bajtach.</span><span class="sxs-lookup"><span data-stu-id="16da5-113">The host loads assemblies by returning `IStream` instances that point directly at the bytes.</span></span>  
  
 <span data-ttu-id="16da5-114">Środowisko CLR określa, czy host został zaimplementowany `IHostAssemblyStore` przez wywołanie przy `IHostAssemblyManager::GetNonHostAssemblyStores` inicjacji.</span><span class="sxs-lookup"><span data-stu-id="16da5-114">The CLR determines whether a host has implemented `IHostAssemblyStore` by calling `IHostAssemblyManager::GetNonHostAssemblyStores` upon initialization.</span></span> <span data-ttu-id="16da5-115">Dzięki temu host może na przykład kontrolować powiązania z zestawami użytkowników, ale w celu utworzenia powiązania z zestawami .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="16da5-115">This allows the host, for example, to control binding to user assemblies, but to rely on the runtime to bind to .NET Framework assemblies.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="16da5-116">W przypadku wdrażania programu `IHostAssemblyStore` host określa jego zamiar, aby rozpoznać wszystkie zestawy, do których nie odwołują się `ICLRAssemblyReferenceList` zwrócone z `IHostAssemblyManager::GetNonHostStoreAssemblies` .</span><span class="sxs-lookup"><span data-stu-id="16da5-116">In providing an implementation of `IHostAssemblyStore`, the host specifies its intent to resolve all assemblies that are not referenced by the `ICLRAssemblyReferenceList` returned from `IHostAssemblyManager::GetNonHostStoreAssemblies`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="16da5-117">.NET Framework wersja 2,0 nie umożliwia hostowi załadowania obrazu natywnego zestawu, zgodnie z opisem w narzędziu [generatora obrazów natywnych (Ngen.exe)](../../tools/ngen-exe-native-image-generator.md) .</span><span class="sxs-lookup"><span data-stu-id="16da5-117">The .NET Framework version 2.0 does not provide a way for the host to load the native image of an assembly, as provided by the [Native Image Generator (Ngen.exe)](../../tools/ngen-exe-native-image-generator.md) utility.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16da5-118">Wymagania</span><span class="sxs-lookup"><span data-stu-id="16da5-118">Requirements</span></span>  

 <span data-ttu-id="16da5-119">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="16da5-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16da5-120">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="16da5-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="16da5-121">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="16da5-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="16da5-122">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16da5-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16da5-123">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="16da5-123">See also</span></span>

- [<span data-ttu-id="16da5-124">ICLRAssemblyReferenceList — Interfejs</span><span class="sxs-lookup"><span data-stu-id="16da5-124">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="16da5-125">IHostAssemblyManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="16da5-125">IHostAssemblyManager Interface</span></span>](ihostassemblymanager-interface.md)
- [<span data-ttu-id="16da5-126">Hosting — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="16da5-126">Hosting Interfaces</span></span>](hosting-interfaces.md)
