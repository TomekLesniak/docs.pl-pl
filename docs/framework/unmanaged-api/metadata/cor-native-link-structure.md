---
title: COR_NATIVE_LINK — Struktura
ms.date: 03/30/2017
api_name:
- COR_NATIVE_LINK
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_NATIVE_LINK
helpviewer_keywords:
- COR_NATIVE_LINK structure [.NET Framework metadata]
ms.assetid: 6ef78d3c-1c69-4141-b687-dcb065b7a74d
topic_type:
- apiref
ms.openlocfilehash: 15f573ebc07bcf08a1ab8f5a5bbb88e940c5c8dc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724172"
---
# <a name="cor_native_link-structure"></a><span data-ttu-id="9f0bb-102">COR_NATIVE_LINK — Struktura</span><span class="sxs-lookup"><span data-stu-id="9f0bb-102">COR_NATIVE_LINK Structure</span></span>

<span data-ttu-id="9f0bb-103">Zawiera informacje, które są używane do łączenia kodu natywnego.</span><span class="sxs-lookup"><span data-stu-id="9f0bb-103">Contains information that is used to link native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f0bb-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="9f0bb-104">Syntax</span></span>  
  
```cpp  
typedef struct
{  
    BYTE        m_linkType;  
    BYTE        m_flags;  
    mdMemberRef m_entryPoint;  
} COR_NATIVE_LINK;  
```  
  
## <a name="members"></a><span data-ttu-id="9f0bb-105">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="9f0bb-105">Members</span></span>  
  
|<span data-ttu-id="9f0bb-106">Członek</span><span class="sxs-lookup"><span data-stu-id="9f0bb-106">Member</span></span>|<span data-ttu-id="9f0bb-107">Opis</span><span class="sxs-lookup"><span data-stu-id="9f0bb-107">Description</span></span>|  
|------------|-----------------|  
|`m_linkType`|<span data-ttu-id="9f0bb-108">Typ, który ma być połączony w kodzie natywnym.</span><span class="sxs-lookup"><span data-stu-id="9f0bb-108">The type to be linked in native code.</span></span> <span data-ttu-id="9f0bb-109">Ta wartość jest jedną z wartości [CorNativeLinkType —](cornativelinktype-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="9f0bb-109">This value is one of the [CorNativeLinkType](cornativelinktype-enumeration.md) values.</span></span>|  
|`m_flags`|<span data-ttu-id="9f0bb-110">Flagi używane przez konsolidator podczas łączenia kodu natywnego.</span><span class="sxs-lookup"><span data-stu-id="9f0bb-110">Flags used by the linker when linking native code.</span></span> <span data-ttu-id="9f0bb-111">Ta wartość jest jedną z wartości [CorNativeLinkFlags —](cornativelinkflags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="9f0bb-111">This value is one of the [CorNativeLinkFlags](cornativelinkflags-enumeration.md) values.</span></span>|  
|`m_entryPoint`|<span data-ttu-id="9f0bb-112">Token metadanych elementu MemberRef reprezentujący punkt wejścia.</span><span class="sxs-lookup"><span data-stu-id="9f0bb-112">The MemberRef metadata token that represents the entry point.</span></span> <span data-ttu-id="9f0bb-113">Format to `lib:entrypoint` .</span><span class="sxs-lookup"><span data-stu-id="9f0bb-113">The format is `lib:entrypoint`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9f0bb-114">Wymagania</span><span class="sxs-lookup"><span data-stu-id="9f0bb-114">Requirements</span></span>  

 <span data-ttu-id="9f0bb-115">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9f0bb-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f0bb-116">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="9f0bb-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9f0bb-117">**Biblioteka:** Używane jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9f0bb-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9f0bb-118">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f0bb-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f0bb-119">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="9f0bb-119">See also</span></span>

- [<span data-ttu-id="9f0bb-120">Metadane — Struktury</span><span class="sxs-lookup"><span data-stu-id="9f0bb-120">Metadata Structures</span></span>](metadata-structures.md)
- [<span data-ttu-id="9f0bb-121">CorNativeLinkType — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="9f0bb-121">CorNativeLinkType Enumeration</span></span>](cornativelinktype-enumeration.md)
- [<span data-ttu-id="9f0bb-122">CorNativeLinkFlags — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="9f0bb-122">CorNativeLinkFlags Enumeration</span></span>](cornativelinkflags-enumeration.md)
