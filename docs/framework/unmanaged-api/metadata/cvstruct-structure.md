---
title: Struktura CVStruct
ms.date: 03/30/2017
api_name:
- CVStruct
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CVStruct
helpviewer_keywords:
- CVStruct structure [.NET Framework metadata]
ms.assetid: e9e4e497-d5fb-464b-991c-3bdd824664fd
topic_type:
- apiref
ms.openlocfilehash: db36b94fafe20b58b9bcbb886b8d285326960f67
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715579"
---
# <a name="cvstruct-structure"></a><span data-ttu-id="995f2-102">Struktura CVStruct</span><span class="sxs-lookup"><span data-stu-id="995f2-102">CVStruct Structure</span></span>

<span data-ttu-id="995f2-103">Zawiera informacje, które są używane podczas instalowania modułu lub obrazu złożonego.</span><span class="sxs-lookup"><span data-stu-id="995f2-103">Contains information that is used when installing a module or a composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="995f2-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="995f2-104">Syntax</span></span>  
  
```cpp  
typedef struct {  
    short Major;  
    short Minor;  
    short Sub;  
    short Build;  
} CVStruct;  
```  
  
## <a name="members"></a><span data-ttu-id="995f2-105">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="995f2-105">Members</span></span>  
  
|<span data-ttu-id="995f2-106">Członek</span><span class="sxs-lookup"><span data-stu-id="995f2-106">Member</span></span>|<span data-ttu-id="995f2-107">Opis</span><span class="sxs-lookup"><span data-stu-id="995f2-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="995f2-108">Duży</span><span class="sxs-lookup"><span data-stu-id="995f2-108">Major</span></span>|<span data-ttu-id="995f2-109">Numer kompilacji wersji głównej.</span><span class="sxs-lookup"><span data-stu-id="995f2-109">Major version build number.</span></span>|  
|<span data-ttu-id="995f2-110">Mały</span><span class="sxs-lookup"><span data-stu-id="995f2-110">Minor</span></span>|<span data-ttu-id="995f2-111">Numer kompilacji wersji pomocniczej.</span><span class="sxs-lookup"><span data-stu-id="995f2-111">Minor version build number.</span></span>|  
|<span data-ttu-id="995f2-112">Sub</span><span class="sxs-lookup"><span data-stu-id="995f2-112">Sub</span></span>|<span data-ttu-id="995f2-113">Numer kompilacji podrzędnej.</span><span class="sxs-lookup"><span data-stu-id="995f2-113">Sub-build number.</span></span>|  
|<span data-ttu-id="995f2-114">Kompilacja</span><span class="sxs-lookup"><span data-stu-id="995f2-114">Build</span></span>|<span data-ttu-id="995f2-115">Numer kompilacji.</span><span class="sxs-lookup"><span data-stu-id="995f2-115">Build number.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="995f2-116">Wymagania</span><span class="sxs-lookup"><span data-stu-id="995f2-116">Requirements</span></span>  

 <span data-ttu-id="995f2-117">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="995f2-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="995f2-118">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="995f2-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="995f2-119">**Biblioteka:** Używane jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="995f2-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="995f2-120">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="995f2-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="995f2-121">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="995f2-121">See also</span></span>

- [<span data-ttu-id="995f2-122">Metadane — Struktury</span><span class="sxs-lookup"><span data-stu-id="995f2-122">Metadata Structures</span></span>](metadata-structures.md)
