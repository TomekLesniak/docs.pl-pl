---
title: IAssemblyCache — Interfejs
ms.date: 03/30/2017
api_name:
- IAssemblyCache
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCache
helpviewer_keywords:
- IAssemblyCache interface [.NET Framework fusion]
ms.assetid: 71ea170f-872d-4fc5-81b6-27da1dec9b19
topic_type:
- apiref
ms.openlocfilehash: df4f0ba018b55202c22cb90b22b927a9c426c4ed
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95696859"
---
# <a name="iassemblycache-interface"></a><span data-ttu-id="6fb99-102">IAssemblyCache — Interfejs</span><span class="sxs-lookup"><span data-stu-id="6fb99-102">IAssemblyCache Interface</span></span>

<span data-ttu-id="6fb99-103">Reprezentuje globalną pamięć podręczną zestawów do użycia przez technologię Fusion.</span><span class="sxs-lookup"><span data-stu-id="6fb99-103">Represents the global assembly cache for use by the fusion technology.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6fb99-104">Metody</span><span class="sxs-lookup"><span data-stu-id="6fb99-104">Methods</span></span>  
  
|<span data-ttu-id="6fb99-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="6fb99-105">Method</span></span>|<span data-ttu-id="6fb99-106">Opis</span><span class="sxs-lookup"><span data-stu-id="6fb99-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6fb99-107">CreateAssemblyCacheItem, metoda</span><span class="sxs-lookup"><span data-stu-id="6fb99-107">CreateAssemblyCacheItem Method</span></span>](iassemblycache-createassemblycacheitem-method.md)|<span data-ttu-id="6fb99-108">Pobiera odwołanie do nowego [IAssemblyCacheItem](iassemblycacheitem-interface.md).</span><span class="sxs-lookup"><span data-stu-id="6fb99-108">Gets a reference to a new [IAssemblyCacheItem](iassemblycacheitem-interface.md).</span></span>|  
|[<span data-ttu-id="6fb99-109">CreateAssemblyScavenger, metoda</span><span class="sxs-lookup"><span data-stu-id="6fb99-109">CreateAssemblyScavenger Method</span></span>](iassemblycache-createassemblyscavenger-method.md)|<span data-ttu-id="6fb99-110">Zarezerwowane do użytku wewnętrznego przez technologię Fusion.</span><span class="sxs-lookup"><span data-stu-id="6fb99-110">Reserved for internal use by the fusion technology.</span></span>|  
|[<span data-ttu-id="6fb99-111">InstallAssembly, metoda</span><span class="sxs-lookup"><span data-stu-id="6fb99-111">InstallAssembly Method</span></span>](iassemblycache-installassembly-method.md)|<span data-ttu-id="6fb99-112">Instaluje określony zestaw w globalnej pamięci podręcznej zestawów.</span><span class="sxs-lookup"><span data-stu-id="6fb99-112">Installs the specified assembly in the global assembly cache.</span></span>|  
|[<span data-ttu-id="6fb99-113">QueryAssemblyInfo, metoda</span><span class="sxs-lookup"><span data-stu-id="6fb99-113">QueryAssemblyInfo Method</span></span>](iassemblycache-queryassemblyinfo-method.md)|<span data-ttu-id="6fb99-114">Pobiera żądane dane dotyczące określonego zestawu.</span><span class="sxs-lookup"><span data-stu-id="6fb99-114">Gets the requested data about the specified assembly.</span></span>|  
|[<span data-ttu-id="6fb99-115">UninstallAssembly, metoda</span><span class="sxs-lookup"><span data-stu-id="6fb99-115">UninstallAssembly Method</span></span>](iassemblycache-uninstallassembly-method.md)|<span data-ttu-id="6fb99-116">Odinstalowuje określony zestaw z globalnej pamięci podręcznej zestawów.</span><span class="sxs-lookup"><span data-stu-id="6fb99-116">Uninstalls the specified assembly from the global assembly cache.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6fb99-117">Wymagania</span><span class="sxs-lookup"><span data-stu-id="6fb99-117">Requirements</span></span>  

 <span data-ttu-id="6fb99-118">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6fb99-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6fb99-119">**Nagłówek:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="6fb99-119">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="6fb99-120">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6fb99-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fb99-121">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="6fb99-121">See also</span></span>

- [<span data-ttu-id="6fb99-122">Interfejsy łączenia</span><span class="sxs-lookup"><span data-stu-id="6fb99-122">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="6fb99-123">Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="6fb99-123">Global Assembly Cache</span></span>](../../app-domains/gac.md)
