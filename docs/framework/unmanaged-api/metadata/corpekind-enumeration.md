---
title: CorPEKind — Wyliczenie
ms.date: 03/30/2017
api_name:
- CorPEKind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorPEKind
helpviewer_keywords:
- CorPEKind enumeration [.NET Framework metadata]
ms.assetid: 22dc6dea-b1b9-4982-a730-a022d586b117
topic_type:
- apiref
ms.openlocfilehash: 001be0c5e8897bacf76d2a044fb9400768473052
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673536"
---
# <a name="corpekind-enumeration"></a><span data-ttu-id="77a36-102">CorPEKind — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="77a36-102">CorPEKind Enumeration</span></span>

<span data-ttu-id="77a36-103">Zawiera wartości opisujące przenośny plik wykonywalny (PE), który jest zwracany przez wywołanie [IMetaDataImport2:: GetPEKind —](imetadataimport2-getpekind-method.md).</span><span class="sxs-lookup"><span data-stu-id="77a36-103">Contains values that describe a portable executable (PE) file, as returned from a call to [IMetaDataImport2::GetPEKind](imetadataimport2-getpekind-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77a36-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="77a36-104">Syntax</span></span>  
  
```cpp  
typedef enum CorPEKind {  
  
    peNot           = 0x00000000,  
    peILonly        = 0x00000001,  
    pe32BitRequired = 0x00000002,  
    pe32Plus        = 0x00000004,  
    pe32Unmanaged   = 0x00000008,  
    pe32BitPreferred= 0x00000010  
  
} CorPEKind;  
```  
  
## <a name="members"></a><span data-ttu-id="77a36-105">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="77a36-105">Members</span></span>  
  
|<span data-ttu-id="77a36-106">Członek</span><span class="sxs-lookup"><span data-stu-id="77a36-106">Member</span></span>|<span data-ttu-id="77a36-107">Opis</span><span class="sxs-lookup"><span data-stu-id="77a36-107">Description</span></span>|  
|------------|-----------------|  
|`peNot`|<span data-ttu-id="77a36-108">Wskazuje, że nie jest to plik PE.</span><span class="sxs-lookup"><span data-stu-id="77a36-108">Indicates that this is not a PE file.</span></span>|  
|`peILOnly`|<span data-ttu-id="77a36-109">Wskazuje, że ten plik PE zawiera tylko kod zarządzany.</span><span class="sxs-lookup"><span data-stu-id="77a36-109">Indicates that this PE file contains only managed code.</span></span>|  
|`pe32BitRequired`|<span data-ttu-id="77a36-110">Wskazuje, że ten plik PE wykonuje wywołania Win32.</span><span class="sxs-lookup"><span data-stu-id="77a36-110">Indicates that this PE file makes Win32 calls.</span></span>|  
|`pe32Plus`|<span data-ttu-id="77a36-111">Wskazuje, że ten plik PE działa na platformie 64-bitowej.</span><span class="sxs-lookup"><span data-stu-id="77a36-111">Indicates that this PE file runs on a 64-bit platform.</span></span>|  
|`pe32Unmanaged`|<span data-ttu-id="77a36-112">Wskazuje, że ten plik PE jest kodem natywnym.</span><span class="sxs-lookup"><span data-stu-id="77a36-112">Indicates that this PE file is native code.</span></span>|  
|<span data-ttu-id="77a36-113">pe32BitPreferred</span><span class="sxs-lookup"><span data-stu-id="77a36-113">pe32BitPreferred</span></span>|<span data-ttu-id="77a36-114">Wskazuje, że ten plik PE jest niezależny od platformy i preferowany do załadowania w środowisku 32-bitowym.</span><span class="sxs-lookup"><span data-stu-id="77a36-114">Indicates that this PE file is platform-neutral and prefers to be loaded in a 32-bit environment.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="77a36-115">Uwagi</span><span class="sxs-lookup"><span data-stu-id="77a36-115">Remarks</span></span>  

 <span data-ttu-id="77a36-116">Te wartości mogą być używane w kombinacjach bitowych.</span><span class="sxs-lookup"><span data-stu-id="77a36-116">These values can be used in bitwise combinations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77a36-117">Wymagania</span><span class="sxs-lookup"><span data-stu-id="77a36-117">Requirements</span></span>  

 <span data-ttu-id="77a36-118">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="77a36-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77a36-119">**Nagłówek:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="77a36-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="77a36-120">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77a36-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77a36-121">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="77a36-121">See also</span></span>

- [<span data-ttu-id="77a36-122">Wyliczenia metadanych</span><span class="sxs-lookup"><span data-stu-id="77a36-122">Metadata Enumerations</span></span>](metadata-enumerations.md)
