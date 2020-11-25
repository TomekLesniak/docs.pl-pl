---
title: CLR_DEBUGGING_VERSION — Struktura
ms.date: 03/30/2017
api_name:
- CLR_DEBUGGING_VERSION
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CLR_DEBUGGING_VERSION
helpviewer_keywords:
- CLR_DEBUGGING_VERSION structure [.NET Framework debugging]
ms.assetid: 4d821186-3ddf-405a-ac44-d79438a9f7f3
topic_type:
- apiref
ms.openlocfilehash: 8a2abe847728a2bb1f1345ef73e55b58e4704001
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729814"
---
# <a name="clr_debugging_version-structure"></a><span data-ttu-id="6d464-102">CLR_DEBUGGING_VERSION — Struktura</span><span class="sxs-lookup"><span data-stu-id="6d464-102">CLR_DEBUGGING_VERSION Structure</span></span>

<span data-ttu-id="6d464-103">Definiuje wersję produktu środowiska uruchomieniowego języka wspólnego (CLR) do celów debugowania.</span><span class="sxs-lookup"><span data-stu-id="6d464-103">Defines the product version of the common language runtime (CLR) for debugging purposes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d464-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="6d464-104">Syntax</span></span>  
  
```cpp  
typedef struct _CLR_DEBUGGING_VERSION  
{  
    WORD wStructVersion;
    WORD wMajor;
    WORD wMinor;
    WORD wBuild;
    WORD wRevision;
} CLR_DEBUGGING_VERSION;
```  
  
## <a name="members"></a><span data-ttu-id="6d464-105">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="6d464-105">Members</span></span>  
  
|<span data-ttu-id="6d464-106">Członek</span><span class="sxs-lookup"><span data-stu-id="6d464-106">Member</span></span>|<span data-ttu-id="6d464-107">Opis</span><span class="sxs-lookup"><span data-stu-id="6d464-107">Description</span></span>|  
|------------|-----------------|  
|`wStructVersion`|<span data-ttu-id="6d464-108">Numer wersji struktury</span><span class="sxs-lookup"><span data-stu-id="6d464-108">The structure version number</span></span>|  
|`wMajor`|<span data-ttu-id="6d464-109">Główny numer wersji.</span><span class="sxs-lookup"><span data-stu-id="6d464-109">The major version number.</span></span>|  
|`wMinor`|<span data-ttu-id="6d464-110">Pomocniczy numer wersji.</span><span class="sxs-lookup"><span data-stu-id="6d464-110">The minor version number.</span></span>|  
|`wBuild`|<span data-ttu-id="6d464-111">Numer kompilacji.</span><span class="sxs-lookup"><span data-stu-id="6d464-111">The build number.</span></span>|  
|`wRevision`|<span data-ttu-id="6d464-112">Numer poprawki.</span><span class="sxs-lookup"><span data-stu-id="6d464-112">The revision number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6d464-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="6d464-113">Remarks</span></span>  

 <span data-ttu-id="6d464-114">`CLR_DEBUGGING_VERSION`Struktura jest taka sama jak struktura COR_VERSION, jednak `CLR_DEBUGGING_VERSION` Struktura zawiera dodatkowe pole wersji struktury ( `wStructVersion` ).</span><span class="sxs-lookup"><span data-stu-id="6d464-114">The `CLR_DEBUGGING_VERSION` structure is the same as the COR_VERSION structure, however, the `CLR_DEBUGGING_VERSION` structure provides an additional structure version field (`wStructVersion`).</span></span> <span data-ttu-id="6d464-115">Obecnie to pole musi mieć wartość zero.</span><span class="sxs-lookup"><span data-stu-id="6d464-115">Currently, this field must be set to zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d464-116">Wymagania</span><span class="sxs-lookup"><span data-stu-id="6d464-116">Requirements</span></span>  

 <span data-ttu-id="6d464-117">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d464-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d464-118">**Nagłówek:** CorDebug. idl</span><span class="sxs-lookup"><span data-stu-id="6d464-118">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="6d464-119">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="6d464-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6d464-120">**.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d464-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d464-121">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="6d464-121">See also</span></span>

- [<span data-ttu-id="6d464-122">Struktury debugowania</span><span class="sxs-lookup"><span data-stu-id="6d464-122">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="6d464-123">Debugowanie</span><span class="sxs-lookup"><span data-stu-id="6d464-123">Debugging</span></span>](index.md)
