---
title: COR_PUB_ENUMPROCESS — Wyliczenie
ms.date: 03/30/2017
api_name:
- COR_PUB_ENUMPROCESS
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_PUB_ENUMPROCESS
helpviewer_keywords:
- COR_PUB_ENUMPROCESS enumeration [.NET Framework debugging]
ms.assetid: 5d3ada6e-feea-47da-a7ed-b664107c137f
topic_type:
- apiref
ms.openlocfilehash: 30a522fbf96aebaa96f33f4a1dc381683f183871
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726421"
---
# <a name="cor_pub_enumprocess-enumeration"></a><span data-ttu-id="24163-102">COR_PUB_ENUMPROCESS — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="24163-102">COR_PUB_ENUMPROCESS Enumeration</span></span>

<span data-ttu-id="24163-103">Identyfikuje typ procesu do wyliczenia.</span><span class="sxs-lookup"><span data-stu-id="24163-103">Identifies the type of process to be enumerated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24163-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="24163-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PUB_MANAGEDONLY    = 0x00000001  
} COR_PUB_ENUMPROCESS;  
```  
  
## <a name="members"></a><span data-ttu-id="24163-105">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="24163-105">Members</span></span>  
  
|<span data-ttu-id="24163-106">Nazwa elementu członkowskiego</span><span class="sxs-lookup"><span data-stu-id="24163-106">Member name</span></span>|<span data-ttu-id="24163-107">Opis</span><span class="sxs-lookup"><span data-stu-id="24163-107">Description</span></span>|  
|-----------------|-----------------|  
|`COR_PUB_MANAGEDONLY`|<span data-ttu-id="24163-108">Proces zarządzany.</span><span class="sxs-lookup"><span data-stu-id="24163-108">A managed process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="24163-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="24163-109">Remarks</span></span>  

 <span data-ttu-id="24163-110">Bieżąca wersja niezarządzanego interfejsu API debugowania wylicza tylko procesy zarządzane.</span><span class="sxs-lookup"><span data-stu-id="24163-110">The current version of the unmanaged debugging API enumerates only managed processes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24163-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="24163-111">Requirements</span></span>  

 <span data-ttu-id="24163-112">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="24163-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24163-113">**Nagłówek:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="24163-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="24163-114">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="24163-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="24163-115">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24163-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24163-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="24163-116">See also</span></span>

- [<span data-ttu-id="24163-117">Debugowanie — wyliczenia</span><span class="sxs-lookup"><span data-stu-id="24163-117">Debugging Enumerations</span></span>](debugging-enumerations.md)
