---
title: CorPropertyAttr — Wyliczenie
ms.date: 03/30/2017
api_name:
- CorPropertyAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorPropertyAttr
helpviewer_keywords:
- CorPropertyAttr enumeration [.NET Framework metadata]
ms.assetid: 58ac8202-854d-4efd-acfb-d2da8b446e12
topic_type:
- apiref
ms.openlocfilehash: d76de80f87a8e5a63eac9f6a413f2efb0e394b0a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706128"
---
# <a name="corpropertyattr-enumeration"></a><span data-ttu-id="59afb-102">CorPropertyAttr — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="59afb-102">CorPropertyAttr Enumeration</span></span>

<span data-ttu-id="59afb-103">Zawiera wartości opisujące metadane właściwości.</span><span class="sxs-lookup"><span data-stu-id="59afb-103">Contains values that describe the metadata of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59afb-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="59afb-104">Syntax</span></span>  
  
```cpp  
typedef enum CorPropertyAttr {  
  
    prSpecialName           =   0x0200,
    prReservedMask          =   0xf400,  
    prRTSpecialName         =   0x0400,  
    prHasDefault            =   0x1000,  
    prUnused                =   0xe9ff  
  
} CorPropertyAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="59afb-105">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="59afb-105">Members</span></span>  
  
|<span data-ttu-id="59afb-106">Członek</span><span class="sxs-lookup"><span data-stu-id="59afb-106">Member</span></span>|<span data-ttu-id="59afb-107">Opis</span><span class="sxs-lookup"><span data-stu-id="59afb-107">Description</span></span>|  
|------------|-----------------|  
|`prSpecialName`|<span data-ttu-id="59afb-108">Określa, że właściwość jest specjalna i że jej nazwa opisuje sposób.</span><span class="sxs-lookup"><span data-stu-id="59afb-108">Specifies that the property is special, and that its name describes how.</span></span>|  
|`prReservedMask`|<span data-ttu-id="59afb-109">Zarezerwowane do użytku wewnętrznego przez środowisko uruchomieniowe języka wspólnego.</span><span class="sxs-lookup"><span data-stu-id="59afb-109">Reserved for internal use by the common language runtime.</span></span>|  
|`prRTSpecialName`|<span data-ttu-id="59afb-110">Określa, że wewnętrzne interfejsy API środowiska uruchomieniowego języka wspólnego powinny sprawdzać kodowanie nazwy właściwości.</span><span class="sxs-lookup"><span data-stu-id="59afb-110">Specifies that the common language runtime metadata internal APIs should check the encoding of the property name.</span></span>|  
|`prHasDefault`|<span data-ttu-id="59afb-111">Określa, że właściwość ma wartość domyślną.</span><span class="sxs-lookup"><span data-stu-id="59afb-111">Specifies that the property has a default value.</span></span>|  
|`prUnused`|<span data-ttu-id="59afb-112">Nieużywany.</span><span class="sxs-lookup"><span data-stu-id="59afb-112">Unused.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="59afb-113">Wymagania</span><span class="sxs-lookup"><span data-stu-id="59afb-113">Requirements</span></span>  

 <span data-ttu-id="59afb-114">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="59afb-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59afb-115">**Nagłówek:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="59afb-115">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="59afb-116">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59afb-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59afb-117">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="59afb-117">See also</span></span>

- [<span data-ttu-id="59afb-118">Wyliczenia metadanych</span><span class="sxs-lookup"><span data-stu-id="59afb-118">Metadata Enumerations</span></span>](metadata-enumerations.md)
