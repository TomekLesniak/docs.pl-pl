---
title: CorDebugGuidToTypeMapping — Struktura
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CorDebugGuidToTypeMapping
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugGuidToTypeMapping
helpviewer_keywords:
- CorDebugGuidToTypeMapping structure [.NET Framework debugging]
ms.assetid: 57dbccd9-b16d-4da3-ae25-7a2cf9adf679
topic_type:
- apiref
ms.openlocfilehash: 859853521b741f42f1de7921de813941d2501173
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729099"
---
# <a name="cordebugguidtotypemapping-structure"></a><span data-ttu-id="83132-102">CorDebugGuidToTypeMapping — Struktura</span><span class="sxs-lookup"><span data-stu-id="83132-102">CorDebugGuidToTypeMapping Structure</span></span>

<span data-ttu-id="83132-103">Mapuje identyfikator GUID środowisko wykonawcze systemu Windows na odpowiedni obiekt ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="83132-103">Maps a Windows Runtime GUID to its corresponding ICorDebugType object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83132-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="83132-104">Syntax</span></span>  
  
```cpp
typedef struct CorDebugGuidToTypeMapping {  
    GUID iid;  
    ICorDebugType *pType;  
} CorDebugGuidToTypeMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="83132-105">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="83132-105">Members</span></span>  
  
|<span data-ttu-id="83132-106">Członek</span><span class="sxs-lookup"><span data-stu-id="83132-106">Member</span></span>|<span data-ttu-id="83132-107">Opis</span><span class="sxs-lookup"><span data-stu-id="83132-107">Description</span></span>|  
|------------|-----------------|  
|`iid`|<span data-ttu-id="83132-108">Identyfikator GUID typu środowisko wykonawcze systemu Windows w pamięci podręcznej.</span><span class="sxs-lookup"><span data-stu-id="83132-108">The GUID of the cached Windows Runtime type.</span></span>|  
|`pType`|<span data-ttu-id="83132-109">Wskaźnik do obiektu ICorDebugType, który zawiera informacje o typie pamięci podręcznej.</span><span class="sxs-lookup"><span data-stu-id="83132-109">A pointer to an ICorDebugType object that provides information about the cached type.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="83132-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="83132-110">Requirements</span></span>  

 <span data-ttu-id="83132-111">**Platformy:** środowisko wykonawcze systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="83132-111">**Platforms:** Windows Runtime.</span></span>  
  
 <span data-ttu-id="83132-112">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="83132-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="83132-113">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="83132-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="83132-114">**.NET Framework wersje:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83132-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83132-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="83132-115">See also</span></span>

- [<span data-ttu-id="83132-116">Struktury debugowania</span><span class="sxs-lookup"><span data-stu-id="83132-116">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="83132-117">Debugowanie</span><span class="sxs-lookup"><span data-stu-id="83132-117">Debugging</span></span>](index.md)
