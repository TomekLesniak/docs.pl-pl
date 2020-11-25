---
title: CLSID_RESOLUTION_FLAGS — Wyliczenie
ms.date: 03/30/2017
api_name:
- CLSID_RESOLUTION_FLAGS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CLSID_RESOLUTION_FLAGS
helpviewer_keywords:
- CLSID_RESOLUTION_FLAGS enumeration [.NET Framework hosting]
ms.assetid: cd8b9879-962a-4811-aa46-2e2b6bae0d84
topic_type:
- apiref
ms.openlocfilehash: 19731f34d259757e6de62dd4b4f0d4735d1c2e61
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706167"
---
# <a name="clsid_resolution_flags-enumeration"></a><span data-ttu-id="602b1-102">CLSID_RESOLUTION_FLAGS — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="602b1-102">CLSID_RESOLUTION_FLAGS Enumeration</span></span>

<span data-ttu-id="602b1-103">Zawiera wartości wskazujące sposób, w jaki środowisko uruchomieniowe języka wspólnego (CLR) powinno rozwiązać problem `CLSID` .</span><span class="sxs-lookup"><span data-stu-id="602b1-103">Contains values that indicate how the common language runtime (CLR) should resolve a `CLSID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="602b1-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="602b1-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    CLSID_RESOLUTION_DEFAULT      = 0x0,  
    CLSID_RESOLUTION_REGISTERED   = 0x1  
} CLSID_RESOLUTION_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="602b1-105">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="602b1-105">Members</span></span>  
  
|<span data-ttu-id="602b1-106">Członek</span><span class="sxs-lookup"><span data-stu-id="602b1-106">Member</span></span>|<span data-ttu-id="602b1-107">Opis</span><span class="sxs-lookup"><span data-stu-id="602b1-107">Description</span></span>|  
|------------|-----------------|  
|`CLSID_RESOLUTION_DEFAULT`|<span data-ttu-id="602b1-108">Wskazuje zachowanie domyślne.</span><span class="sxs-lookup"><span data-stu-id="602b1-108">Indicates the default behavior.</span></span>|  
|`CLSID_RESOLUTION_REGISTERED`|<span data-ttu-id="602b1-109">Wskazuje, że środowisko uruchomieniowe przeszukuje rejestr i stosuje zasady dotyczące podkładek.</span><span class="sxs-lookup"><span data-stu-id="602b1-109">Indicates that the runtime searches the registry and applies shim policy.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="602b1-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="602b1-110">Requirements</span></span>  

 <span data-ttu-id="602b1-111">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="602b1-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="602b1-112">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="602b1-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="602b1-113">**.NET Framework wersje:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="602b1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="602b1-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="602b1-114">See also</span></span>

- [<span data-ttu-id="602b1-115">Hosting — Wyliczenia</span><span class="sxs-lookup"><span data-stu-id="602b1-115">Hosting Enumerations</span></span>](hosting-enumerations.md)
