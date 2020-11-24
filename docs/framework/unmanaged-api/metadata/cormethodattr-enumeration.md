---
title: CorMethodAttr — Wyliczenie
ms.date: 03/30/2017
api_name:
- CorMethodAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorMethodAttr
helpviewer_keywords:
- CorMethodAttr enumeration [.NET Framework metadata]
ms.assetid: 4e0c3521-e54d-43c1-9857-cc76b49b8ffc
topic_type:
- apiref
ms.openlocfilehash: 6c3e721c24da217eaf2e8857377359e1c51b7b59
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677027"
---
# <a name="cormethodattr-enumeration"></a><span data-ttu-id="6424b-102">CorMethodAttr — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="6424b-102">CorMethodAttr Enumeration</span></span>

<span data-ttu-id="6424b-103">Zawiera wartości opisujące funkcje metody.</span><span class="sxs-lookup"><span data-stu-id="6424b-103">Contains values that describe the features of a method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6424b-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="6424b-104">Syntax</span></span>  
  
```cpp  
typedef enum CorMethodAttr {  
  
    mdMemberAccessMask          =   0x0007,  
    mdPrivateScope              =   0x0000,  
    mdPrivate                   =   0x0001,  
    mdFamANDAssem               =   0x0002,  
    mdAssem                     =   0x0003,  
    mdFamily                    =   0x0004,  
    mdFamORAssem                =   0x0005,  
    mdPublic                    =   0x0006,  
  
    mdStatic                    =   0x0010,  
    mdFinal                     =   0x0020,  
    mdVirtual                   =   0x0040,  
    mdHideBySig                 =   0x0080,  
  
    mdVtableLayoutMask          =   0x0100,  
    mdReuseSlot                 =   0x0000,  
    mdNewSlot                   =   0x0100,  
  
    mdCheckAccessOnOverride     =   0x0200,  
    mdAbstract                  =   0x0400,  
    mdSpecialName               =   0x0800,  
  
    mdPinvokeImpl               =   0x2000,  
    mdUnmanagedExport           =   0x0008,  
  
    mdReservedMask              =   0xd000,  
    mdRTSpecialName             =   0x1000,  
    mdHasSecurity               =   0x4000,  
    mdRequireSecObject          =   0x8000,  
  
} CorMethodAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="6424b-105">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="6424b-105">Members</span></span>  
  
|<span data-ttu-id="6424b-106">Członek</span><span class="sxs-lookup"><span data-stu-id="6424b-106">Member</span></span>|<span data-ttu-id="6424b-107">Opis</span><span class="sxs-lookup"><span data-stu-id="6424b-107">Description</span></span>|  
|------------|-----------------|  
|`mdMemberAccessMask`|<span data-ttu-id="6424b-108">Określa dostęp do elementu członkowskiego.</span><span class="sxs-lookup"><span data-stu-id="6424b-108">Specifies member access.</span></span>|  
|`mdPrivateScope`|<span data-ttu-id="6424b-109">Określa, że nie można odwołać się do elementu członkowskiego.</span><span class="sxs-lookup"><span data-stu-id="6424b-109">Specifies that the member cannot be referenced.</span></span>|  
|`mdPrivate`|<span data-ttu-id="6424b-110">Określa, że element członkowski jest dostępny tylko dla typu nadrzędnego.</span><span class="sxs-lookup"><span data-stu-id="6424b-110">Specifies that the member is accessible only by the parent type.</span></span>|  
|`mdFamANDAssem`|<span data-ttu-id="6424b-111">Określa, że element członkowski jest dostępny tylko dla podtypów w tym zestawie.</span><span class="sxs-lookup"><span data-stu-id="6424b-111">Specifies that the member is accessible by subtypes only in this assembly.</span></span>|  
|`mdAssem`|<span data-ttu-id="6424b-112">Określa, że element członkowski jest Accessibly przez każdą z nich w zestawie.</span><span class="sxs-lookup"><span data-stu-id="6424b-112">Specifies that the member is accessibly by anyone in the assembly.</span></span>|  
|`mdFamily`|<span data-ttu-id="6424b-113">Określa, że element członkowski jest dostępny tylko dla typów i podtypów.</span><span class="sxs-lookup"><span data-stu-id="6424b-113">Specifies that the member is accessible only by type and subtypes.</span></span>|  
|`mdFamORAssem`|<span data-ttu-id="6424b-114">Określa, że element członkowski jest dostępny dla klas pochodnych i innych typów w zestawie.</span><span class="sxs-lookup"><span data-stu-id="6424b-114">Specifies that the member is accessible by derived classes and by other types in its assembly.</span></span>|  
|`mdPublic`|<span data-ttu-id="6424b-115">Określa, że element członkowski jest dostępny dla wszystkich typów z dostępem do zakresu.</span><span class="sxs-lookup"><span data-stu-id="6424b-115">Specifies that the member is accessible by all types with access to the scope.</span></span>|  
|`mdStatic`|<span data-ttu-id="6424b-116">Określa, że element członkowski jest zdefiniowany jako część typu, a nie jako element członkowski wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="6424b-116">Specifies that the member is defined as part of the type rather than as a member of an instance.</span></span>|  
|`mdFinal`|<span data-ttu-id="6424b-117">Określa, że nie można zastąpić metody.</span><span class="sxs-lookup"><span data-stu-id="6424b-117">Specifies that the method cannot be overridden.</span></span>|  
|`mdVirtual`|<span data-ttu-id="6424b-118">Określa, że metoda może zostać przesłonięta.</span><span class="sxs-lookup"><span data-stu-id="6424b-118">Specifies that the method can be overridden.</span></span>|  
|`mdHideBySig`|<span data-ttu-id="6424b-119">Określa, że Metoda ukrywa przez nazwę i podpis, a nie tylko według nazwy.</span><span class="sxs-lookup"><span data-stu-id="6424b-119">Specifies that the method hides by name and signature, rather than just by name.</span></span>|  
|`mdVtableLayoutMask`|<span data-ttu-id="6424b-120">Określa układ tabeli wirtualnej.</span><span class="sxs-lookup"><span data-stu-id="6424b-120">Specifies virtual table layout.</span></span>|  
|`mdReuseSlot`|<span data-ttu-id="6424b-121">Określa, że gniazdo używane dla tej metody w tabeli wirtualnej ma być ponownie używane.</span><span class="sxs-lookup"><span data-stu-id="6424b-121">Specifies that the slot used for this method in the virtual table be reused.</span></span> <span data-ttu-id="6424b-122">Jest to opcja domyślna.</span><span class="sxs-lookup"><span data-stu-id="6424b-122">This is the default.</span></span>|  
|`mdNewSlot`|<span data-ttu-id="6424b-123">Określa, że metoda zawsze pobiera nowe miejsce w tabeli wirtualnej.</span><span class="sxs-lookup"><span data-stu-id="6424b-123">Specifies that the method always gets a new slot in the virtual table.</span></span>|  
|`mdCheckAccessOnOverride`|<span data-ttu-id="6424b-124">Określa, że metoda może być zastąpiona przez te same typy, do których jest widoczna.</span><span class="sxs-lookup"><span data-stu-id="6424b-124">Specifies that the method can be overridden by the same types to which it is visible.</span></span>|  
|`mdAbstract`|<span data-ttu-id="6424b-125">Określa, że metoda nie jest zaimplementowana.</span><span class="sxs-lookup"><span data-stu-id="6424b-125">Specifies that the method is not implemented.</span></span>|  
|`mdSpecialName`|<span data-ttu-id="6424b-126">Określa, że metoda jest specjalna i że jej nazwa opisuje sposób.</span><span class="sxs-lookup"><span data-stu-id="6424b-126">Specifies that the method is special, and that its name describes how.</span></span>|  
|`mdPinvokeImpl`|<span data-ttu-id="6424b-127">Określa, że implementacja metody jest przekazywana za pomocą funkcji PInvoke.</span><span class="sxs-lookup"><span data-stu-id="6424b-127">Specifies that the method implementation is forwarded using PInvoke.</span></span>|  
|`mdUnmanagedExport`|<span data-ttu-id="6424b-128">Określa, że metoda jest metodą zarządzaną eksportowaną do kodu niezarządzanego.</span><span class="sxs-lookup"><span data-stu-id="6424b-128">Specifies that the method is a managed method exported to unmanaged code.</span></span>|  
|`mdReservedMask`|<span data-ttu-id="6424b-129">Zarezerwowane do użytku wewnętrznego przez środowisko uruchomieniowe języka wspólnego.</span><span class="sxs-lookup"><span data-stu-id="6424b-129">Reserved for internal use by the common language runtime.</span></span>|  
|`mdRTSpecialName`|<span data-ttu-id="6424b-130">Określa, że środowisko uruchomieniowe języka wspólnego powinno sprawdzać kodowanie nazwy metody.</span><span class="sxs-lookup"><span data-stu-id="6424b-130">Specifies that the common language runtime should check the encoding of the method name.</span></span>|  
|`mdHasSecurity`|<span data-ttu-id="6424b-131">Określa, że do metody są skojarzone zabezpieczenia.</span><span class="sxs-lookup"><span data-stu-id="6424b-131">Specifies that the method has security associated with it.</span></span>|  
|`mdRequireSecObject`|<span data-ttu-id="6424b-132">Określa, że metoda wywołuje inną metodę zawierającą kod zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="6424b-132">Specifies that the method calls another method containing security code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6424b-133">Wymagania</span><span class="sxs-lookup"><span data-stu-id="6424b-133">Requirements</span></span>  

 <span data-ttu-id="6424b-134">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6424b-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6424b-135">**Nagłówek:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="6424b-135">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="6424b-136">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6424b-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6424b-137">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="6424b-137">See also</span></span>

- [<span data-ttu-id="6424b-138">Wyliczenia metadanych</span><span class="sxs-lookup"><span data-stu-id="6424b-138">Metadata Enumerations</span></span>](metadata-enumerations.md)
