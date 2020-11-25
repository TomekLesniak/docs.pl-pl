---
title: CorDebugHandleType — Wyliczenie
ms.date: 03/30/2017
api_name:
- CorDebugHandleType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugHandleType
helpviewer_keywords:
- CorDebugHandleType enumeration [.NET Framework debugging]
ms.assetid: 84296b55-c2c5-424c-ac9c-8e28e2895945
topic_type:
- apiref
ms.openlocfilehash: a0ec83a5590e184b9ff60449a8147d1a3c90a6a9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712459"
---
# <a name="cordebughandletype-enumeration"></a><span data-ttu-id="5f24f-102">CorDebugHandleType — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="5f24f-102">CorDebugHandleType Enumeration</span></span>

<span data-ttu-id="5f24f-103">Wskazuje typ dojścia.</span><span class="sxs-lookup"><span data-stu-id="5f24f-103">Indicates the handle type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f24f-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="5f24f-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugHandleType {  
    HANDLE_STRONG                  = 1,  
    HANDLE_WEAK_TRACK_RESURRECTION = 2  
} CorDebugHandleType;  
```  
  
## <a name="members"></a><span data-ttu-id="5f24f-105">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="5f24f-105">Members</span></span>  
  
|<span data-ttu-id="5f24f-106">Członek</span><span class="sxs-lookup"><span data-stu-id="5f24f-106">Member</span></span>|<span data-ttu-id="5f24f-107">Opis</span><span class="sxs-lookup"><span data-stu-id="5f24f-107">Description</span></span>|  
|------------|-----------------|  
|`HANDLE_STRONG`|<span data-ttu-id="5f24f-108">Dojście jest silnie, co uniemożliwia odjęcie obiektu przez wyrzucanie elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="5f24f-108">The handle is strong, which prevents an object from being reclaimed by garbage collection.</span></span>|  
|`HANDLE_WEAK_TRACK_RESURRECTION`|<span data-ttu-id="5f24f-109">Dojście jest słabe, co nie zapobiega odzyskiwaniu obiektu przez wyrzucanie elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="5f24f-109">The handle is weak, which does not prevent an object from being reclaimed by garbage collection.</span></span><br /><br /> <span data-ttu-id="5f24f-110">Uchwyt jest nieprawidłowy, gdy zbierany jest obiekt.</span><span class="sxs-lookup"><span data-stu-id="5f24f-110">The handle becomes invalid when the object is collected.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5f24f-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="5f24f-111">Requirements</span></span>  

 <span data-ttu-id="5f24f-112">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f24f-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f24f-113">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="5f24f-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5f24f-114">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="5f24f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5f24f-115">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f24f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f24f-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="5f24f-116">See also</span></span>

- [<span data-ttu-id="5f24f-117">Debugowanie — wyliczenia</span><span class="sxs-lookup"><span data-stu-id="5f24f-117">Debugging Enumerations</span></span>](debugging-enumerations.md)
