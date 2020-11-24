---
title: COR_PRF_JIT_CACHE — Wyliczenie
ms.date: 03/30/2017
api_name:
- COR_PRF_JIT_CACHE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_JIT_CACHE
helpviewer_keywords:
- COR_PRF_JIT_CACHE enumeration [.NET Framework profiling]
ms.assetid: e7b8f6b4-95bc-4ba5-b9eb-f5590a7326a4
topic_type:
- apiref
ms.openlocfilehash: 0bf17e7c9d8ff16dc8f07e4a386f599284828f40
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95682253"
---
# <a name="cor_prf_jit_cache-enumeration"></a><span data-ttu-id="111a9-102">COR_PRF_JIT_CACHE — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="111a9-102">COR_PRF_JIT_CACHE Enumeration</span></span>

<span data-ttu-id="111a9-103">Wskazuje wynik funkcji wyszukiwania w pamięci podręcznej.</span><span class="sxs-lookup"><span data-stu-id="111a9-103">Indicates the result of a cached function search.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="111a9-104">`COR_PRF_CACHED_FUNCTION_FOUND` ma wartość zero, więc `COR_PRF_JIT_CACHE` nie może być używana jako surogat wartości logicznej.</span><span class="sxs-lookup"><span data-stu-id="111a9-104">`COR_PRF_CACHED_FUNCTION_FOUND` has a value of zero, so `COR_PRF_JIT_CACHE` cannot be used as a Boolean surrogate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="111a9-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="111a9-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_CACHED_FUNCTION_FOUND,  
    COR_PRF_CACHED_FUNCTION_NOT_FOUND  
} COR_PRF_JIT_CACHE;  
```  
  
## <a name="members"></a><span data-ttu-id="111a9-106">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="111a9-106">Members</span></span>  
  
|<span data-ttu-id="111a9-107">Członek</span><span class="sxs-lookup"><span data-stu-id="111a9-107">Member</span></span>|<span data-ttu-id="111a9-108">Opis</span><span class="sxs-lookup"><span data-stu-id="111a9-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FUNCTION_FOUND`|<span data-ttu-id="111a9-109">Wyszukiwanie odnalazło funkcję.</span><span class="sxs-lookup"><span data-stu-id="111a9-109">The search found the function.</span></span>|  
|`COR_PRF_FUNCTION_NOT_FOUND`|<span data-ttu-id="111a9-110">Wyszukiwanie nie znalazło funkcji.</span><span class="sxs-lookup"><span data-stu-id="111a9-110">The search did not find the function.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="111a9-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="111a9-111">Requirements</span></span>  

 <span data-ttu-id="111a9-112">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="111a9-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="111a9-113">**Nagłówek:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="111a9-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="111a9-114">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="111a9-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="111a9-115">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="111a9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="111a9-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="111a9-116">See also</span></span>

- [<span data-ttu-id="111a9-117">Profilowanie — Wyliczenia</span><span class="sxs-lookup"><span data-stu-id="111a9-117">Profiling Enumerations</span></span>](profiling-enumerations.md)
