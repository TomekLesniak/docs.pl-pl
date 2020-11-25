---
title: COR_PRF_RUNTIME_TYPE — Wyliczenie
ms.date: 03/30/2017
api_name:
- COR_PRF_RUNTIME_TYPE Enumeration
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_RUNTIME_TYPE
helpviewer_keywords:
- COR_PRF_RUNTIME_TYPE enumeration [.NET Framework profiling]
ms.assetid: 35449514-333f-4918-9c60-7aa198d655d2
topic_type:
- apiref
ms.openlocfilehash: b599a97f414491ff80000f99551a727b86ae13de
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95696755"
---
# <a name="cor_prf_runtime_type-enumeration"></a><span data-ttu-id="c14fb-102">COR_PRF_RUNTIME_TYPE — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="c14fb-102">COR_PRF_RUNTIME_TYPE Enumeration</span></span>

<span data-ttu-id="c14fb-103">Zawiera wartości wskazujące wersję środowiska uruchomieniowego języka wspólnego (CLR): Desktop lub CoreCLR, która jest używana w programie Silverlight.</span><span class="sxs-lookup"><span data-stu-id="c14fb-103">Contains values that indicate the version of the common language runtime (CLR): desktop or CoreCLR, which is used in Silverlight.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c14fb-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="c14fb-104">Syntax</span></span>  
  
```cpp  
typedef enum  
{  
    COR_PRF_DESKTOP_CLR = 0x1,  
    COR_PRF_CORE_CLR    = 0x2,  
} COR_PRF_RUNTIME_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="c14fb-105">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="c14fb-105">Members</span></span>  
  
|<span data-ttu-id="c14fb-106">Członek</span><span class="sxs-lookup"><span data-stu-id="c14fb-106">Member</span></span>|<span data-ttu-id="c14fb-107">Opis</span><span class="sxs-lookup"><span data-stu-id="c14fb-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_DESKTOP_CLR`|<span data-ttu-id="c14fb-108">Wersja klasyczna środowiska CLR.</span><span class="sxs-lookup"><span data-stu-id="c14fb-108">The desktop version of the CLR.</span></span>|  
|`COR_PRF_CORE_CLR`|<span data-ttu-id="c14fb-109">Wersja podstawowa środowiska CLR używana w programie Silverlight.</span><span class="sxs-lookup"><span data-stu-id="c14fb-109">The core version of the CLR, used in Silverlight.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c14fb-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="c14fb-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c14fb-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="c14fb-111">Requirements</span></span>  

 <span data-ttu-id="c14fb-112">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c14fb-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c14fb-113">**Nagłówek:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="c14fb-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c14fb-114">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="c14fb-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c14fb-115">**.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c14fb-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c14fb-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="c14fb-116">See also</span></span>

- [<span data-ttu-id="c14fb-117">Profilowanie — Wyliczenia</span><span class="sxs-lookup"><span data-stu-id="c14fb-117">Profiling Enumerations</span></span>](profiling-enumerations.md)
