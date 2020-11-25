---
title: CorRefToDefCheck — Wyliczenie
ms.date: 03/30/2017
api_name:
- CorRefToDefCheck
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorRefToDefCheck
helpviewer_keywords:
- CorRefToDefCheck enumeration [.NET Framework metadata]
ms.assetid: f9a80f1a-55af-4459-b095-8441aae16119
topic_type:
- apiref
ms.openlocfilehash: e7ce604acddb88d5a15844cbce2622b21e364cc1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706115"
---
# <a name="correftodefcheck-enumeration"></a><span data-ttu-id="8fabf-102">CorRefToDefCheck — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="8fabf-102">CorRefToDefCheck Enumeration</span></span>

<span data-ttu-id="8fabf-103">Określa flagi do kontrolowania, które elementy, do których istnieją odwołania, są konwertowane na ich definicje, aby zoptymalizować kod.</span><span class="sxs-lookup"><span data-stu-id="8fabf-103">Specifies flags to control which referenced items are converted to their definitions in order to optimize the code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8fabf-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="8fabf-104">Syntax</span></span>  
  
```cpp  
typedef enum CorRefToDefCheck {  
    MDRefToDefDefault           = 0x00000003,  
    MDRefToDefAll               = 0xffffffff,  
    MDRefToDefNone              = 0x00000000,  
    MDTypeRefToDef              = 0x00000001,  
    MDMemberRefToDef            = 0x00000002  
} CorRefToDefCheck;  
```  
  
## <a name="members"></a><span data-ttu-id="8fabf-105">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="8fabf-105">Members</span></span>  
  
|<span data-ttu-id="8fabf-106">Członek</span><span class="sxs-lookup"><span data-stu-id="8fabf-106">Member</span></span>|<span data-ttu-id="8fabf-107">Opis</span><span class="sxs-lookup"><span data-stu-id="8fabf-107">Description</span></span>|  
|------------|-----------------|  
|`MDRefToDefDefault`|<span data-ttu-id="8fabf-108">Określa, że odwołania do typu i odwołania do elementów członkowskich powinny być konwertowane na definicje.</span><span class="sxs-lookup"><span data-stu-id="8fabf-108">Specifies that type references and member references should be converted to definitions.</span></span> <span data-ttu-id="8fabf-109">Jest to wartość domyślna ( `MDTypeRefToDef` &#124; `MDMemberRefToDef` ).</span><span class="sxs-lookup"><span data-stu-id="8fabf-109">This is the default value (`MDTypeRefToDef` &#124; `MDMemberRefToDef`).</span></span>|  
|`MDRefToDefAll`|<span data-ttu-id="8fabf-110">Określa, że wszystkie elementy, do których istnieją odwołania, powinny być konwertowane na definicje.</span><span class="sxs-lookup"><span data-stu-id="8fabf-110">Specifies that all referenced items should be converted to definitions.</span></span>|  
|`MDRefToDefNone`|<span data-ttu-id="8fabf-111">Określa, że żadne elementy, do których istnieją odwołania, nie powinny być konwertowane na definicje.</span><span class="sxs-lookup"><span data-stu-id="8fabf-111">Specifies that no referenced items should be converted to definitions.</span></span>|  
|`MDTypeRefToDef`|<span data-ttu-id="8fabf-112">Określa, że odwołania do typu mają być konwertowane do definicji typu.</span><span class="sxs-lookup"><span data-stu-id="8fabf-112">Specifies that only type references should be converted to type definitions.</span></span>|  
|`MDMemberRefToDef`|<span data-ttu-id="8fabf-113">Określa, że tylko odwołania składowe powinny być konwertowane na definicje.</span><span class="sxs-lookup"><span data-stu-id="8fabf-113">Specifies that only member references should be converted to definitions.</span></span> <span data-ttu-id="8fabf-114">Oznacza to, że odwołania do elementów członkowskich powinny być konwertowane na definicje metod lub definicje pól.</span><span class="sxs-lookup"><span data-stu-id="8fabf-114">That is, member references should be converted to either method definitions or field definitions.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8fabf-115">Wymagania</span><span class="sxs-lookup"><span data-stu-id="8fabf-115">Requirements</span></span>  

 <span data-ttu-id="8fabf-116">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8fabf-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8fabf-117">**Nagłówek:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="8fabf-117">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="8fabf-118">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8fabf-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fabf-119">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="8fabf-119">See also</span></span>

- [<span data-ttu-id="8fabf-120">Wyliczenia metadanych</span><span class="sxs-lookup"><span data-stu-id="8fabf-120">Metadata Enumerations</span></span>](metadata-enumerations.md)
