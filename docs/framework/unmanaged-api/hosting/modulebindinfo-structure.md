---
title: ModuleBindInfo — Struktura
ms.date: 03/30/2017
api_name:
- ModuleBindInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ModuleBindInfo
helpviewer_keywords:
- ModuleBindInfo structure [.NET Framework hosting]
ms.assetid: 632d4adc-dbc9-4ce8-9397-abc3285c1c69
topic_type:
- apiref
ms.openlocfilehash: 505015877985492edab4b761b379f33f1e5c6660
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729983"
---
# <a name="modulebindinfo-structure"></a><span data-ttu-id="b0f1f-102">ModuleBindInfo — Struktura</span><span class="sxs-lookup"><span data-stu-id="b0f1f-102">ModuleBindInfo Structure</span></span>

<span data-ttu-id="b0f1f-103">Zawiera szczegółowe informacje dotyczące modułu, do którego istnieje odwołanie, i zestawu, który go zawiera.</span><span class="sxs-lookup"><span data-stu-id="b0f1f-103">Provides detailed information about the referenced module and the assembly that contains it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0f1f-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="b0f1f-104">Syntax</span></span>  
  
```cpp  
typedef struct _ModuleBindInfo {  
    DWORD    dwAppDomainId;  
    LPCWSTR  lpAssemblyIdentity;  
    LPCWSTR  lpModuleName  
} ModuleBindInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="b0f1f-105">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="b0f1f-105">Members</span></span>  
  
|<span data-ttu-id="b0f1f-106">Członek</span><span class="sxs-lookup"><span data-stu-id="b0f1f-106">Member</span></span>|<span data-ttu-id="b0f1f-107">Opis</span><span class="sxs-lookup"><span data-stu-id="b0f1f-107">Description</span></span>|  
|------------|-----------------|  
|`dwAppDomainId`|<span data-ttu-id="b0f1f-108">Unikatowy identyfikator `IStream` , który jest zwracany przez wywołanie metody [IHostAssemblyStore::P rovidemodule](ihostassemblystore-providemodule-method.md) , z której ma zostać załadowany moduł, do którego istnieje odwołanie.</span><span class="sxs-lookup"><span data-stu-id="b0f1f-108">A unique identifier for the `IStream` that is returned by a call to the [IHostAssemblyStore::ProvideModule](ihostassemblystore-providemodule-method.md) method from which the referenced module is to be loaded.</span></span>|  
|`lpAssemblyIdentity`|<span data-ttu-id="b0f1f-109">Unikatowy identyfikator zestawu, który zawiera moduł, do którego się odwoływano.</span><span class="sxs-lookup"><span data-stu-id="b0f1f-109">A unique identifier for the assembly that contains the referenced module.</span></span>|  
|`lpModuleName`|<span data-ttu-id="b0f1f-110">Nazwa modułu, do którego się odwoływano.</span><span class="sxs-lookup"><span data-stu-id="b0f1f-110">The name of the referenced module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b0f1f-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="b0f1f-111">Remarks</span></span>  

 <span data-ttu-id="b0f1f-112">`ModuleBindInfo` jest przenoszona jako parametr do `IHostAssemblyStore::ProvideModule` .</span><span class="sxs-lookup"><span data-stu-id="b0f1f-112">`ModuleBindInfo` is passed as a parameter to `IHostAssemblyStore::ProvideModule`.</span></span> <span data-ttu-id="b0f1f-113">Host dostarcza unikatowy identyfikator `dwAppDomainId` do środowiska uruchomieniowego języka wspólnego (CLR).</span><span class="sxs-lookup"><span data-stu-id="b0f1f-113">The host supplies the unique identifier `dwAppDomainId` to the common language runtime (CLR).</span></span> <span data-ttu-id="b0f1f-114">Po wywołaniu metody [IHostAssemblyStore::P rovideassembly](ihostassemblystore-provideassembly-method.md) , środowisko uruchomieniowe użyje identyfikatora, aby określić, czy zawartość `IStream` została zamapowana.</span><span class="sxs-lookup"><span data-stu-id="b0f1f-114">After a call to the [IHostAssemblyStore::ProvideAssembly](ihostassemblystore-provideassembly-method.md) method returns, the runtime uses the identifier to determine whether the contents of the `IStream` have been mapped.</span></span> <span data-ttu-id="b0f1f-115">Jeśli tak, środowisko uruchomieniowe ładuje istniejącą kopię zamiast ponownego mapowania strumienia.</span><span class="sxs-lookup"><span data-stu-id="b0f1f-115">If so, the runtime loads the existing copy rather than remapping the stream.</span></span> <span data-ttu-id="b0f1f-116">Środowisko uruchomieniowe używa również tego identyfikatora jako klucza wyszukiwania dla strumieni, które są zwracane z wywołań `IHostAssemblyStore::ProvideAssembly` metody.</span><span class="sxs-lookup"><span data-stu-id="b0f1f-116">The runtime also uses this identifier as a lookup key for streams that are returned from calls to the `IHostAssemblyStore::ProvideAssembly` method.</span></span> <span data-ttu-id="b0f1f-117">W związku z tym identyfikator musi być unikatowy w przypadku żądań modułu, a także dla żądań zestawu.</span><span class="sxs-lookup"><span data-stu-id="b0f1f-117">Therefore, the identifier must be unique for module requests as well as for assembly requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0f1f-118">Wymagania</span><span class="sxs-lookup"><span data-stu-id="b0f1f-118">Requirements</span></span>  

 <span data-ttu-id="b0f1f-119">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0f1f-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0f1f-120">**Nagłówek:** MSCorEE. idl</span><span class="sxs-lookup"><span data-stu-id="b0f1f-120">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="b0f1f-121">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b0f1f-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b0f1f-122">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0f1f-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0f1f-123">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="b0f1f-123">See also</span></span>

- [<span data-ttu-id="b0f1f-124">Hosting — Struktury</span><span class="sxs-lookup"><span data-stu-id="b0f1f-124">Hosting Structures</span></span>](hosting-structures.md)
- [<span data-ttu-id="b0f1f-125">AssemblyBindInfo — Struktura</span><span class="sxs-lookup"><span data-stu-id="b0f1f-125">AssemblyBindInfo Structure</span></span>](assemblybindinfo-structure.md)
- [<span data-ttu-id="b0f1f-126">ICLRAssemblyIdentityManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="b0f1f-126">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="b0f1f-127">ICLRAssemblyReferenceList — Interfejs</span><span class="sxs-lookup"><span data-stu-id="b0f1f-127">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="b0f1f-128">IHostAssemblyManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="b0f1f-128">IHostAssemblyManager Interface</span></span>](ihostassemblymanager-interface.md)
