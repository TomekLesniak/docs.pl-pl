---
title: CorLocalRefPreservation — Wyliczenie
ms.date: 03/30/2017
api_name:
- CorLocalRefPreservation
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorLocalRefPreservation
helpviewer_keywords:
- CorLocalRefPreservation enumeration [.NET Framework metadata]
ms.assetid: 44757163-1228-4213-a4c4-d4de503cc75d
topic_type:
- apiref
ms.openlocfilehash: 49b0298f4fa776c93f89ac380ce65568b493379b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677118"
---
# <a name="corlocalrefpreservation-enumeration"></a><span data-ttu-id="d4559-102">CorLocalRefPreservation — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="d4559-102">CorLocalRefPreservation Enumeration</span></span>

<span data-ttu-id="d4559-103">Zawiera wartości flag dla traktowania odwołań lokalnych.</span><span class="sxs-lookup"><span data-stu-id="d4559-103">Contains flag values for the treatment of local references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4559-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="d4559-104">Syntax</span></span>  
  
```cpp  
typedef enum CorLocalRefPreservation  
{  
    MDPreserveLocalRefsNone     =   0x00000000,  
    MDPreserveLocalTypeRef      =   0x00000001,  
    MDPreserveLocalMemberRef    =   0x00000002  
} CorLocalRefPreservation;  
```  
  
## <a name="members"></a><span data-ttu-id="d4559-105">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="d4559-105">Members</span></span>  
  
|<span data-ttu-id="d4559-106">Członek</span><span class="sxs-lookup"><span data-stu-id="d4559-106">Member</span></span>|<span data-ttu-id="d4559-107">Opis</span><span class="sxs-lookup"><span data-stu-id="d4559-107">Description</span></span>|  
|------------|-----------------|  
|`MDPreserveLocalRefsNone`|<span data-ttu-id="d4559-108">Nie zachowuj żadnych odwołań lokalnych.</span><span class="sxs-lookup"><span data-stu-id="d4559-108">Preserve no local references.</span></span>|  
|`MDPreserveLocalTypeRef`|<span data-ttu-id="d4559-109">Zachowaj odwołania do typu lokalnego.</span><span class="sxs-lookup"><span data-stu-id="d4559-109">Preserve local type references.</span></span>|  
|`MDPreserveLocalMemberRef`|<span data-ttu-id="d4559-110">Zachowaj odwołania do lokalnych członków.</span><span class="sxs-lookup"><span data-stu-id="d4559-110">Preserve local member references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d4559-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="d4559-111">Requirements</span></span>  

 <span data-ttu-id="d4559-112">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d4559-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4559-113">**Nagłówek:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="d4559-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="d4559-114">**.NET Framework wersje:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4559-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4559-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="d4559-115">See also</span></span>

- [<span data-ttu-id="d4559-116">Wyliczenia metadanych</span><span class="sxs-lookup"><span data-stu-id="d4559-116">Metadata Enumerations</span></span>](metadata-enumerations.md)
