---
title: CorAttributeTargets — Wyliczenie
ms.date: 03/30/2017
api_name:
- CorAttributeTargets
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorAttributeTargets
helpviewer_keywords:
- CorAttributeTargets enumeration [.NET Framework metadata]
ms.assetid: 694c0fa0-7011-41a9-9dfd-f0e16ea574b5
topic_type:
- apiref
ms.openlocfilehash: fbe721bad56ec2be434039f00e741ad9a177815f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718972"
---
# <a name="corattributetargets-enumeration"></a><span data-ttu-id="be44c-102">CorAttributeTargets — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="be44c-102">CorAttributeTargets Enumeration</span></span>

<span data-ttu-id="be44c-103">Określa elementy aplikacji, na których jest prawidłowy, aby zastosować atrybut.</span><span class="sxs-lookup"><span data-stu-id="be44c-103">Specifies the application elements on which it is valid to apply an attribute.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be44c-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="be44c-104">Syntax</span></span>  
  
```cpp  
typedef enum CorAttributeTargets  
{  
    catAssembly            = 0x0001,  
    catModule              = 0x0002,  
    catClass               = 0x0004,  
    catStruct              = 0x0008,  
    catEnum                = 0x0010,  
    catConstructor         = 0x0020,  
    catMethod              = 0x0040,  
    catProperty            = 0x0080,  
    catField               = 0x0100,  
    catEvent               = 0x0200,  
    catInterface           = 0x0400,  
    catParameter           = 0x0800,  
    catDelegate            = 0x1000,  
    catGenericParameter    = 0x4000,  
  
    catAll                 =
        catAssembly | catModule | catClass | catStruct |
        catEnum | catConstructor | catMethod | catProperty |
        catField | catEvent | catInterface | catParameter |
        catDelegate | catGenericParameter,  
  
    catClassMembers        =
        catClass | catStruct | catEnum | catConstructor |
        catMethod | catProperty | catField | catEvent |
        catDelegate | catInterface  
  
} CorAttributeTargets;  
```  
  
## <a name="members"></a><span data-ttu-id="be44c-105">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="be44c-105">Members</span></span>  
  
|<span data-ttu-id="be44c-106">Członek</span><span class="sxs-lookup"><span data-stu-id="be44c-106">Member</span></span>|<span data-ttu-id="be44c-107">Opis</span><span class="sxs-lookup"><span data-stu-id="be44c-107">Description</span></span>|  
|------------|-----------------|  
|`catAssembly`|<span data-ttu-id="be44c-108">Atrybut może zostać zastosowany do zestawu.</span><span class="sxs-lookup"><span data-stu-id="be44c-108">Attribute can be applied to an assembly.</span></span>|  
|`catModule`|<span data-ttu-id="be44c-109">Atrybut można zastosować do przenośnego modułu pliku wykonywalnego (. dll lub. exe).</span><span class="sxs-lookup"><span data-stu-id="be44c-109">Attribute can be applied to a portable executable (.dll or .exe) module.</span></span>|  
|`catClass`|<span data-ttu-id="be44c-110">Atrybut może być stosowany do klasy.</span><span class="sxs-lookup"><span data-stu-id="be44c-110">Attribute can be applied to a class.</span></span>|  
|`catStruct`|<span data-ttu-id="be44c-111">Atrybut może być stosowany do struktury; oznacza to, że typ wartości.</span><span class="sxs-lookup"><span data-stu-id="be44c-111">Attribute can be applied to a structure; that is, a value type.</span></span>|  
|`catEnum`|<span data-ttu-id="be44c-112">Atrybut może być stosowany do wyliczenia.</span><span class="sxs-lookup"><span data-stu-id="be44c-112">Attribute can be applied to an enumeration.</span></span>|  
|`catConstructor`|<span data-ttu-id="be44c-113">Atrybut może być stosowany do konstruktora.</span><span class="sxs-lookup"><span data-stu-id="be44c-113">Attribute can be applied to a constructor.</span></span>|  
|`catMethod`|<span data-ttu-id="be44c-114">Atrybut można zastosować do metody.</span><span class="sxs-lookup"><span data-stu-id="be44c-114">Attribute can be applied to a method.</span></span>|  
|`catProperty`|<span data-ttu-id="be44c-115">Atrybut może być stosowany do właściwości.</span><span class="sxs-lookup"><span data-stu-id="be44c-115">Attribute can be applied to a property.</span></span>|  
|`catField`|<span data-ttu-id="be44c-116">Atrybut może być stosowany do pola.</span><span class="sxs-lookup"><span data-stu-id="be44c-116">Attribute can be applied to a field.</span></span>|  
|`catEvent`|<span data-ttu-id="be44c-117">Atrybut może być stosowany do zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="be44c-117">Attribute can be applied to an event.</span></span>|  
|`catInterface`|<span data-ttu-id="be44c-118">Atrybut może być stosowany do interfejsu.</span><span class="sxs-lookup"><span data-stu-id="be44c-118">Attribute can be applied to an interface.</span></span>|  
|`catParameter`|<span data-ttu-id="be44c-119">Atrybut może być stosowany do parametru.</span><span class="sxs-lookup"><span data-stu-id="be44c-119">Attribute can be applied to a parameter.</span></span>|  
|`catDelegate`|<span data-ttu-id="be44c-120">Atrybut można zastosować do obiektu delegowanego.</span><span class="sxs-lookup"><span data-stu-id="be44c-120">Attribute can be applied to a delegate.</span></span>|  
|`catGenericParameter`|<span data-ttu-id="be44c-121">Atrybut może być stosowany do parametru generycznego.</span><span class="sxs-lookup"><span data-stu-id="be44c-121">Attribute can be applied to a generic parameter.</span></span>|  
|`catAll`|<span data-ttu-id="be44c-122">Atrybut można zastosować do dowolnego elementu aplikacji.</span><span class="sxs-lookup"><span data-stu-id="be44c-122">Attribute can be applied to any application element.</span></span>|  
|`catClassMembers`|<span data-ttu-id="be44c-123">Atrybut można zastosować do składowej klasy.</span><span class="sxs-lookup"><span data-stu-id="be44c-123">Attribute can be applied to a member of a class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="be44c-124">Uwagi</span><span class="sxs-lookup"><span data-stu-id="be44c-124">Remarks</span></span>  

 <span data-ttu-id="be44c-125">`CorAttributeTargets`Wartości wyliczenia można łączyć z wartością bitową lub operacją w celu uzyskania preferowanej kombinacji.</span><span class="sxs-lookup"><span data-stu-id="be44c-125">The `CorAttributeTargets` enumeration values can be combined with a bitwise OR operation to get the preferred combination.</span></span>  
  
 <span data-ttu-id="be44c-126">`CorAttributeTargets`Równolegle zarządzanym <xref:System.AttributeTargets?displayProperty=nameWithType> wyliczeniem.</span><span class="sxs-lookup"><span data-stu-id="be44c-126">The `CorAttributeTargets` parallels the managed <xref:System.AttributeTargets?displayProperty=nameWithType> enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be44c-127">Wymagania</span><span class="sxs-lookup"><span data-stu-id="be44c-127">Requirements</span></span>  

 <span data-ttu-id="be44c-128">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="be44c-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be44c-129">**Nagłówek:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="be44c-129">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="be44c-130">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be44c-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be44c-131">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="be44c-131">See also</span></span>

- [<span data-ttu-id="be44c-132">Wyliczenia metadanych</span><span class="sxs-lookup"><span data-stu-id="be44c-132">Metadata Enumerations</span></span>](metadata-enumerations.md)
