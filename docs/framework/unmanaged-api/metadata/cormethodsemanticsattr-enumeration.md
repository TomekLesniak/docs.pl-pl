---
title: CorMethodSemanticsAttr — Wyliczenie
ms.date: 03/30/2017
api_name:
- CorMethodSemanticsAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorMethodSemanticsAttr
helpviewer_keywords:
- CorMethodSemanticsAttr enumeration [.NET Framework metadata]
ms.assetid: ca2af325-eb9d-4a91-90e4-267e45b98611
topic_type:
- apiref
ms.openlocfilehash: 347b323951b0125ffa5f82626b2d9b235079492c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676949"
---
# <a name="cormethodsemanticsattr-enumeration"></a><span data-ttu-id="fae0a-102">CorMethodSemanticsAttr — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="fae0a-102">CorMethodSemanticsAttr Enumeration</span></span>

<span data-ttu-id="fae0a-103">Zawiera wartości opisujące relacje między metodą a skojarzoną właściwością lub zdarzeniem.</span><span class="sxs-lookup"><span data-stu-id="fae0a-103">Contains values that describe the relationship between a method and an associated property or event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fae0a-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="fae0a-104">Syntax</span></span>  
  
```cpp  
typedef enum CorMethodSemanticsAttr {  
  
    msSetter    =   0x0001,  
    msGetter    =   0x0002,  
    msOther     =   0x0004,  
    msAddOn     =   0x0008,  
    msRemoveOn  =   0x0010,  
    msFire      =   0x0020,  
  
} CorMethodSemanticsAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="fae0a-105">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="fae0a-105">Members</span></span>  
  
|<span data-ttu-id="fae0a-106">Członek</span><span class="sxs-lookup"><span data-stu-id="fae0a-106">Member</span></span>|<span data-ttu-id="fae0a-107">Opis</span><span class="sxs-lookup"><span data-stu-id="fae0a-107">Description</span></span>|  
|------------|-----------------|  
|`msSetter`|<span data-ttu-id="fae0a-108">Określa, że metoda jest `set` akcesorem dla właściwości.</span><span class="sxs-lookup"><span data-stu-id="fae0a-108">Specifies that the method is a `set` accessor for a property.</span></span>|  
|`msGetter`|<span data-ttu-id="fae0a-109">Określa, że metoda jest `get` akcesorem dla właściwości.</span><span class="sxs-lookup"><span data-stu-id="fae0a-109">Specifies that the method is a `get` accessor for a property.</span></span>|  
|`msOther`|<span data-ttu-id="fae0a-110">Określa, że metoda ma relację z właściwością lub zdarzeniem innym niż zdefiniowane w tym miejscu.</span><span class="sxs-lookup"><span data-stu-id="fae0a-110">Specifies that the method has a relationship to a property or an event other than those defined here.</span></span>|  
|`msAddOn`|<span data-ttu-id="fae0a-111">Określa, że Metoda dodaje metody obsługi dla zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="fae0a-111">Specifies that the method adds handler methods for an event.</span></span>|  
|`msRemoveOn`|<span data-ttu-id="fae0a-112">Określa, że metoda usuwa metody obsługi dla zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="fae0a-112">Specifies that the method removes handler methods for an event.</span></span>|  
|`msFire`|<span data-ttu-id="fae0a-113">Określa, że metoda wywołuje zdarzenie.</span><span class="sxs-lookup"><span data-stu-id="fae0a-113">Specifies that the method raises an event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fae0a-114">Wymagania</span><span class="sxs-lookup"><span data-stu-id="fae0a-114">Requirements</span></span>  

 <span data-ttu-id="fae0a-115">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fae0a-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fae0a-116">**Nagłówek:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="fae0a-116">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="fae0a-117">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fae0a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fae0a-118">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="fae0a-118">See also</span></span>

- [<span data-ttu-id="fae0a-119">Wyliczenia metadanych</span><span class="sxs-lookup"><span data-stu-id="fae0a-119">Metadata Enumerations</span></span>](metadata-enumerations.md)
