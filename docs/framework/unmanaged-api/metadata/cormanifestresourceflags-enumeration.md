---
title: CorManifestResourceFlags — Wyliczenie
ms.date: 03/30/2017
api_name:
- CorManifestResourceFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorManifestResourceFlags
helpviewer_keywords:
- CorManifestResourceFlags enumeration [.NET Framework metadata]
ms.assetid: 1b0306b7-622b-4b57-8edc-3c713bb147ae
topic_type:
- apiref
ms.openlocfilehash: f8334cb44042e21c086bc05c723e99b0c079fa2c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677066"
---
# <a name="cormanifestresourceflags-enumeration"></a><span data-ttu-id="8e42c-102">CorManifestResourceFlags — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="8e42c-102">CorManifestResourceFlags Enumeration</span></span>

<span data-ttu-id="8e42c-103">Wskazuje widoczność zasobów zakodowanych w manifeście zestawu.</span><span class="sxs-lookup"><span data-stu-id="8e42c-103">Indicates the visibility of resources encoded in an assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e42c-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="8e42c-104">Syntax</span></span>  
  
```cpp  
typedef enum CorManifestResourceFlags {  
  
    mrVisibilityMask        =   0x0007,  
    mrPublic                =   0x0001,  
    mrPrivate               =   0x0002  
  
} CorManifestResourceFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="8e42c-105">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="8e42c-105">Members</span></span>  
  
|<span data-ttu-id="8e42c-106">Członek</span><span class="sxs-lookup"><span data-stu-id="8e42c-106">Member</span></span>|<span data-ttu-id="8e42c-107">Opis</span><span class="sxs-lookup"><span data-stu-id="8e42c-107">Description</span></span>|  
|------------|-----------------|  
|`mrVisibilityMask`|<span data-ttu-id="8e42c-108">Zarezerwowany.</span><span class="sxs-lookup"><span data-stu-id="8e42c-108">Reserved.</span></span>|  
|`mrPublic`|<span data-ttu-id="8e42c-109">Zasoby są publiczne.</span><span class="sxs-lookup"><span data-stu-id="8e42c-109">The resources are public.</span></span>|  
|`mrPrivate`|<span data-ttu-id="8e42c-110">Zasoby są prywatne.</span><span class="sxs-lookup"><span data-stu-id="8e42c-110">The resources are private.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8e42c-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="8e42c-111">Requirements</span></span>  

 <span data-ttu-id="8e42c-112">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8e42c-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e42c-113">**Nagłówek:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="8e42c-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="8e42c-114">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e42c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e42c-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="8e42c-115">See also</span></span>

- [<span data-ttu-id="8e42c-116">Wyliczenia metadanych</span><span class="sxs-lookup"><span data-stu-id="8e42c-116">Metadata Enumerations</span></span>](metadata-enumerations.md)
