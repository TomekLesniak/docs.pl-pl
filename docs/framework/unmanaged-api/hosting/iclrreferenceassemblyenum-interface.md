---
title: ICLRReferenceAssemblyEnum — Interfejs
ms.date: 03/30/2017
api_name:
- ICLRReferenceAssemblyEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRReferenceAssemblyEnum
helpviewer_keywords:
- ICLRReferenceAssemblyEnum interface [.NET Framework hosting]
ms.assetid: 8adbf092-c3ba-4bee-b25b-0de6e43a4ce5
topic_type:
- apiref
ms.openlocfilehash: 189fbb1943d049dc4f52ea6cb626c02e9e25b3c7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95686147"
---
# <a name="iclrreferenceassemblyenum-interface"></a><span data-ttu-id="5174f-102">ICLRReferenceAssemblyEnum — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5174f-102">ICLRReferenceAssemblyEnum Interface</span></span>

<span data-ttu-id="5174f-103">Dostarcza metody, które umożliwiają hostowi manipulowanie zestawem zestawów, do których odwołuje się plik lub strumień przy użyciu danych tożsamości zestawu, które są wewnętrzne dla środowiska uruchomieniowego języka wspólnego (CLR), bez konieczności tworzenia lub zrozumienia tych tożsamości.</span><span class="sxs-lookup"><span data-stu-id="5174f-103">Provides methods that allow the host to manipulate the set of assemblies referenced by a file or stream using assembly identity data that is internal to the common language runtime (CLR), without needing to create or understand those identities.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5174f-104">Metody</span><span class="sxs-lookup"><span data-stu-id="5174f-104">Methods</span></span>  
  
|<span data-ttu-id="5174f-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="5174f-105">Method</span></span>|<span data-ttu-id="5174f-106">Opis</span><span class="sxs-lookup"><span data-stu-id="5174f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5174f-107">Get — Metoda</span><span class="sxs-lookup"><span data-stu-id="5174f-107">Get Method</span></span>](iclrreferenceassemblyenum-get-method.md)|<span data-ttu-id="5174f-108">Pobiera tożsamość zestawu przy użyciu podanego indeksu.</span><span class="sxs-lookup"><span data-stu-id="5174f-108">Gets the assembly identity at the supplied index.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5174f-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="5174f-109">Requirements</span></span>  

 <span data-ttu-id="5174f-110">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5174f-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5174f-111">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="5174f-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5174f-112">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5174f-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5174f-113">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5174f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5174f-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="5174f-114">See also</span></span>

- [<span data-ttu-id="5174f-115">ICLRAssemblyIdentityManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5174f-115">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="5174f-116">ICLRAssemblyReferenceList — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5174f-116">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="5174f-117">Hosting — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="5174f-117">Hosting Interfaces</span></span>](hosting-interfaces.md)
