---
title: CorRegFlags — Wyliczenie
ms.date: 03/30/2017
api_name:
- CorRegFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorRegFlags
helpviewer_keywords:
- CorRegFlags enumeration [.NET Framework metadata]
ms.assetid: 8d3080ee-39fe-4c57-8950-51323632d045
topic_type:
- apiref
ms.openlocfilehash: 5ea588194720394ad9f361fbba702f3fcdcbe110
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706102"
---
# <a name="corregflags-enumeration"></a><span data-ttu-id="ea7d5-102">CorRegFlags — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="ea7d5-102">CorRegFlags Enumeration</span></span>

<span data-ttu-id="ea7d5-103">Dostarcza wartości flag używanych do rejestracji podczas instalacji modułu lub obrazu złożonego.</span><span class="sxs-lookup"><span data-stu-id="ea7d5-103">Provides flag values used for registration when installing a module or composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea7d5-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="ea7d5-104">Syntax</span></span>  
  
```cpp  
typedef enum
{  
    regNoCopy  = 0x00000001,  
    regConfig  = 0x00000002,  
    regHasRefs = 0x00000004  
} CorRegFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="ea7d5-105">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="ea7d5-105">Members</span></span>  
  
|<span data-ttu-id="ea7d5-106">Członek</span><span class="sxs-lookup"><span data-stu-id="ea7d5-106">Member</span></span>|<span data-ttu-id="ea7d5-107">Opis</span><span class="sxs-lookup"><span data-stu-id="ea7d5-107">Description</span></span>|  
|------------|-----------------|  
|`regNoCopy`|<span data-ttu-id="ea7d5-108">Określa, że pliki nie powinny być kopiowane do lokalizacji docelowej.</span><span class="sxs-lookup"><span data-stu-id="ea7d5-108">Specifies that files should not be copied into the destination.</span></span>|  
|`regConfig`|<span data-ttu-id="ea7d5-109">Określa, że moduł lub kompozyt jest konfiguracją.</span><span class="sxs-lookup"><span data-stu-id="ea7d5-109">Specifies that the module or composite is a configuration.</span></span>|  
|`regHasRefs`|<span data-ttu-id="ea7d5-110">Określa, że moduł lub kompozyt zawiera odwołania do klas.</span><span class="sxs-lookup"><span data-stu-id="ea7d5-110">Specifies that the module or composite has class references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ea7d5-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="ea7d5-111">Requirements</span></span>  

 <span data-ttu-id="ea7d5-112">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ea7d5-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea7d5-113">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ea7d5-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ea7d5-114">**Biblioteka:** Uwzględnione jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ea7d5-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ea7d5-115">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea7d5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea7d5-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="ea7d5-116">See also</span></span>

- [<span data-ttu-id="ea7d5-117">Wyliczenia metadanych</span><span class="sxs-lookup"><span data-stu-id="ea7d5-117">Metadata Enumerations</span></span>](metadata-enumerations.md)
