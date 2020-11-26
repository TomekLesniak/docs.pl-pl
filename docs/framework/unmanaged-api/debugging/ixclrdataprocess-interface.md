---
title: IXCLRDataProcess, interfejs
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess Interface
helpviewer.keywords:
- IXCLRDataProcess Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 376ec2b840bc17c79ed1f27c17a8ddd22c37a0f4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96245357"
---
# <a name="ixclrdataprocess-interface"></a><span data-ttu-id="4ff23-102">IXCLRDataProcess, interfejs</span><span class="sxs-lookup"><span data-stu-id="4ff23-102">IXCLRDataProcess Interface</span></span>

<span data-ttu-id="4ff23-103">Dostarcza metody do wykonywania zapytań dotyczących informacji o procesie.</span><span class="sxs-lookup"><span data-stu-id="4ff23-103">Provides methods for querying information about a process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="4ff23-104">Metody</span><span class="sxs-lookup"><span data-stu-id="4ff23-104">Methods</span></span>

| <span data-ttu-id="4ff23-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="4ff23-105">Method</span></span>                                                                                                                                               | <span data-ttu-id="4ff23-106">Opis</span><span class="sxs-lookup"><span data-stu-id="4ff23-106">Description</span></span>                                                                                     |
| ---------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="4ff23-107">GetRuntimeNameByAddress</span><span class="sxs-lookup"><span data-stu-id="4ff23-107">GetRuntimeNameByAddress</span></span>](ixclrdataprocess-getruntimenamebyaddress-method.md)                     | <span data-ttu-id="4ff23-108">Pobiera nazwę dla danego adresu.</span><span class="sxs-lookup"><span data-stu-id="4ff23-108">Gets a name for the given address.</span></span>                                                               |
| [<span data-ttu-id="4ff23-109">GetAppDomainByUniqueId</span><span class="sxs-lookup"><span data-stu-id="4ff23-109">GetAppDomainByUniqueId</span></span>](ixclrdataprocess-getappdomainbyuniqueid-method.md)                       | <span data-ttu-id="4ff23-110">Pobiera `AppDomain` w procesie według jego unikatowego identyfikatora.</span><span class="sxs-lookup"><span data-stu-id="4ff23-110">Gets an `AppDomain` in a process by its unique id.</span></span>                                              |
| [<span data-ttu-id="4ff23-111">StartEnumModules</span><span class="sxs-lookup"><span data-stu-id="4ff23-111">StartEnumModules</span></span>](ixclrdataprocess-startenummodules-method.md)                                   | <span data-ttu-id="4ff23-112">Udostępnia dojście do wyliczenia modułów procesu.</span><span class="sxs-lookup"><span data-stu-id="4ff23-112">Provides a handle to enumerate the modules of a process.</span></span>                                        |
| [<span data-ttu-id="4ff23-113">EnumModule</span><span class="sxs-lookup"><span data-stu-id="4ff23-113">EnumModule</span></span>](ixclrdataprocess-enummodule-method.md)                                               | <span data-ttu-id="4ff23-114">Wylicza moduły tego procesu.</span><span class="sxs-lookup"><span data-stu-id="4ff23-114">Enumerates the modules of this process.</span></span>                                                         |
| [<span data-ttu-id="4ff23-115">EndEnumModules</span><span class="sxs-lookup"><span data-stu-id="4ff23-115">EndEnumModules</span></span>](ixclrdataprocess-endenummodules-method.md)                                       | <span data-ttu-id="4ff23-116">Zwalnia zasoby używane przez Iteratory wewnętrzne używane podczas wyliczania modułu.</span><span class="sxs-lookup"><span data-stu-id="4ff23-116">Releases the resources used by internal iterators used during module enumeration.</span></span>               |
| [<span data-ttu-id="4ff23-117">StartEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="4ff23-117">StartEnumMethodInstancesByAddress</span></span>](ixclrdataprocess-startenummethodinstancesbyaddress-method.md) | <span data-ttu-id="4ff23-118">Udostępnia dojście do wyliczenia wystąpień metod, `AppDomain` Zaczynając od danego adresu.</span><span class="sxs-lookup"><span data-stu-id="4ff23-118">Provides a handle to enumerate the method instances of `AppDomain` starting at a given address.</span></span> |
| [<span data-ttu-id="4ff23-119">EnumMethodInstanceByAddress</span><span class="sxs-lookup"><span data-stu-id="4ff23-119">EnumMethodInstanceByAddress</span></span>](ixclrdataprocess-enummethodinstancebyaddress-method.md)             | <span data-ttu-id="4ff23-120">Wylicza wystąpienia metody tego procesu, rozpoczynając od przesunięcia adresu.</span><span class="sxs-lookup"><span data-stu-id="4ff23-120">Enumerates the method instances of this process starting at an address offset.</span></span>                  |
| [<span data-ttu-id="4ff23-121">EndEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="4ff23-121">EndEnumMethodInstancesByAddress</span></span>](ixclrdataprocess-endenummethodinstancesbyaddress-method.md)     | <span data-ttu-id="4ff23-122">Zwalnia zasoby używane przez Iteratory wewnętrzne używane podczas wyliczania wystąpień.</span><span class="sxs-lookup"><span data-stu-id="4ff23-122">Releases the resources used by internal iterators used during instance enumeration.</span></span>             |

## <a name="remarks"></a><span data-ttu-id="4ff23-123">Uwagi</span><span class="sxs-lookup"><span data-stu-id="4ff23-123">Remarks</span></span>

<span data-ttu-id="4ff23-124">Ten interfejs jest wewnątrz środowiska uruchomieniowego i nie jest udostępniany przez żadne nagłówki lub pliki bibliotek.</span><span class="sxs-lookup"><span data-stu-id="4ff23-124">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="4ff23-125">Jest to jednak interfejs COM pochodzący z `IUnknown` identyfikatora GUID `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` , który można uzyskać za pomocą zwykłych mechanizmów com.</span><span class="sxs-lookup"><span data-stu-id="4ff23-125">However, it's a COM interface that derives from `IUnknown` with GUID `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="4ff23-126">Wymagania</span><span class="sxs-lookup"><span data-stu-id="4ff23-126">Requirements</span></span>

<span data-ttu-id="4ff23-127">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4ff23-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>
<span data-ttu-id="4ff23-128">**Nagłówek:** Dawaj</span><span class="sxs-lookup"><span data-stu-id="4ff23-128">**Header:** None</span></span>  
<span data-ttu-id="4ff23-129">**Biblioteka:** Dawaj</span><span class="sxs-lookup"><span data-stu-id="4ff23-129">**Library:** None</span></span>  
<span data-ttu-id="4ff23-130">**.NET Framework wersje:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="4ff23-130">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="4ff23-131">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="4ff23-131">See also</span></span>

- [<span data-ttu-id="4ff23-132">Debugowanie</span><span class="sxs-lookup"><span data-stu-id="4ff23-132">Debugging</span></span>](index.md)
- [<span data-ttu-id="4ff23-133">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="4ff23-133">Debugging Interfaces</span></span>](debugging-interfaces.md)
