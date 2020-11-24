---
title: CorNativeLinkType — Wyliczenie
ms.date: 03/30/2017
api_name:
- CorNativeLinkType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorNativeLinkType
helpviewer_keywords:
- CorNativeLinkType enumeration [.NET Framework metadata]
ms.assetid: 4f86ff37-2dab-4e64-819a-76b3bfe828ff
topic_type:
- apiref
ms.openlocfilehash: c155373f7da47e904c94a44efa2fba42309d4218
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95671359"
---
# <a name="cornativelinktype-enumeration"></a><span data-ttu-id="adbde-102">CorNativeLinkType — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="adbde-102">CorNativeLinkType Enumeration</span></span>

<span data-ttu-id="adbde-103">Dostarcza wartości, które wskazują typ połączony w kodzie natywnym.</span><span class="sxs-lookup"><span data-stu-id="adbde-103">Provides values that indicate the type linked in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="adbde-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="adbde-104">Syntax</span></span>  
  
```cpp  
typedef enum
{  
    nltNone       = 1,  
    nltAnsi       = 2,  
    nltUnicode    = 3,  
    nltAuto       = 4,  
    nltOle        = 5,  
    nltMaxValue   = 7  
} CorNativeLinkType;  
```  
  
## <a name="members"></a><span data-ttu-id="adbde-105">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="adbde-105">Members</span></span>  
  
|<span data-ttu-id="adbde-106">Członek</span><span class="sxs-lookup"><span data-stu-id="adbde-106">Member</span></span>|<span data-ttu-id="adbde-107">Opis</span><span class="sxs-lookup"><span data-stu-id="adbde-107">Description</span></span>|  
|------------|-----------------|  
|`nltNone`|<span data-ttu-id="adbde-108">Wskazuje, że nie określono żadnego ze słów kluczowych.</span><span class="sxs-lookup"><span data-stu-id="adbde-108">Indicates that none of the keywords are specified.</span></span>|  
|`nltAnsi`|<span data-ttu-id="adbde-109">Wskazuje, że jest określone słowo kluczowe ANSI.</span><span class="sxs-lookup"><span data-stu-id="adbde-109">Indicates that an ANSI keyword is specified.</span></span>|  
|`nltUnicode`|<span data-ttu-id="adbde-110">Wskazuje, że określono słowo kluczowe Unicode</span><span class="sxs-lookup"><span data-stu-id="adbde-110">Indicates that a Unicode keyword is specified</span></span>|  
|`nltAuto`|<span data-ttu-id="adbde-111">Wskazuje, że jest określone słowo kluczowe New.</span><span class="sxs-lookup"><span data-stu-id="adbde-111">Indicates that an auto keyword is specified.</span></span>|  
|`nltOle`|<span data-ttu-id="adbde-112">Wskazuje, że określono słowo kluczowe OLE.</span><span class="sxs-lookup"><span data-stu-id="adbde-112">Indicates that an OLE keyword is specified.</span></span>|  
|`nltMaxValue`|<span data-ttu-id="adbde-113">Nie używany.</span><span class="sxs-lookup"><span data-stu-id="adbde-113">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="adbde-114">Wymagania</span><span class="sxs-lookup"><span data-stu-id="adbde-114">Requirements</span></span>  

 <span data-ttu-id="adbde-115">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="adbde-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="adbde-116">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="adbde-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="adbde-117">**Biblioteka:** Uwzględnione jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="adbde-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="adbde-118">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="adbde-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adbde-119">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="adbde-119">See also</span></span>

- [<span data-ttu-id="adbde-120">Wyliczenia metadanych</span><span class="sxs-lookup"><span data-stu-id="adbde-120">Metadata Enumerations</span></span>](metadata-enumerations.md)
