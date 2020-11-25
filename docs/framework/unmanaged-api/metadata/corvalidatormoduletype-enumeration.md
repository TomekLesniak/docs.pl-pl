---
title: CorValidatorModuleType — Wyliczenie
ms.date: 03/30/2017
api_name:
- CorValidatorModuleType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorValidatorModuleType
helpviewer_keywords:
- CorValidatorModuleType enumeration [.NET Framework metadata]
ms.assetid: 748f1ab2-fbcb-4f55-89ec-8d23d81ebc80
topic_type:
- apiref
ms.openlocfilehash: 2fb7f11677870f7d53439f1867f167fabe70b22a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723860"
---
# <a name="corvalidatormoduletype-enumeration"></a><span data-ttu-id="d75f7-102">CorValidatorModuleType — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="d75f7-102">CorValidatorModuleType Enumeration</span></span>

<span data-ttu-id="d75f7-103">Określa typ modułu.</span><span class="sxs-lookup"><span data-stu-id="d75f7-103">Specifies the type of a module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d75f7-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="d75f7-104">Syntax</span></span>  
  
```cpp  
typedef enum  
{  
    ValidatorModuleTypeInvalid  = 0x0,  
    ValidatorModuleTypeMin      = 0x00000001,  
    ValidatorModuleTypePE       = 0x00000001,  
    ValidatorModuleTypeObj      = 0x00000002,  
    ValidatorModuleTypeEnc      = 0x00000003,  
    ValidatorModuleTypeIncr     = 0x00000004,  
    ValidatorModuleTypeMax      = 0x00000004  
} CorValidatorModuleType;  
```  
  
## <a name="members"></a><span data-ttu-id="d75f7-105">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="d75f7-105">Members</span></span>  
  
|<span data-ttu-id="d75f7-106">Członek</span><span class="sxs-lookup"><span data-stu-id="d75f7-106">Member</span></span>|<span data-ttu-id="d75f7-107">Opis</span><span class="sxs-lookup"><span data-stu-id="d75f7-107">Description</span></span>|  
|------------|-----------------|  
|`ValidatorModuleTypeInvalid`|<span data-ttu-id="d75f7-108">Moduł jest nieprawidłowym typem.</span><span class="sxs-lookup"><span data-stu-id="d75f7-108">The module is an invalid type.</span></span>|  
|`ValidatorModuleTypeMin`|<span data-ttu-id="d75f7-109">Minimalna wartość `CorValidatorModuleType` wyliczenia.</span><span class="sxs-lookup"><span data-stu-id="d75f7-109">The minimum value of the `CorValidatorModuleType` enum.</span></span>|  
|`ValidatorModuleTypePE`|<span data-ttu-id="d75f7-110">Moduł jest przenośnym plikiem wykonywalnym (PE).</span><span class="sxs-lookup"><span data-stu-id="d75f7-110">The module is a portable executable (PE) file.</span></span>|  
|`ValidatorModuleTypeObj`|<span data-ttu-id="d75f7-111">Moduł jest plikiem. obj.</span><span class="sxs-lookup"><span data-stu-id="d75f7-111">The module is a .obj file.</span></span>|  
|`ValidatorModuleTypeEnc`|<span data-ttu-id="d75f7-112">Moduł to sesja debugera Edit-and-Continue.</span><span class="sxs-lookup"><span data-stu-id="d75f7-112">The module is an edit-and-continue debugger session.</span></span>|  
|`ValidatorModuleTypeIncr`|<span data-ttu-id="d75f7-113">Moduł jest tym, który został utworzony przyrostowo.</span><span class="sxs-lookup"><span data-stu-id="d75f7-113">The module is one that has been incrementally built.</span></span>|  
|`ValidatorModuleTypeMax`|<span data-ttu-id="d75f7-114">Maksymalna wartość `CorValidatorModuleType` wyliczenia.</span><span class="sxs-lookup"><span data-stu-id="d75f7-114">The maximum value of the `CorValidatorModuleType` enum.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d75f7-115">Wymagania</span><span class="sxs-lookup"><span data-stu-id="d75f7-115">Requirements</span></span>  

 <span data-ttu-id="d75f7-116">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d75f7-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d75f7-117">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="d75f7-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d75f7-118">**Biblioteka:** Uwzględnione jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d75f7-118">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d75f7-119">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d75f7-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d75f7-120">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="d75f7-120">See also</span></span>

- [<span data-ttu-id="d75f7-121">Wyliczenia metadanych</span><span class="sxs-lookup"><span data-stu-id="d75f7-121">Metadata Enumerations</span></span>](metadata-enumerations.md)
