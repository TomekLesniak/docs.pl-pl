---
title: AssemblyRefFlags — Wyliczenie
ms.date: 03/30/2017
api_name:
- AssemblyRefFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- AssemblyRefFlags
helpviewer_keywords:
- AssemblyRefFlags enumeration [.NET Framework metadata]
ms.assetid: decd4f46-f3b2-466f-9501-e74f2b86b846
topic_type:
- apiref
ms.openlocfilehash: 0a99d2f79645bdc46ff4db86d7280614eeb1faf5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732765"
---
# <a name="assemblyrefflags-enumeration"></a><span data-ttu-id="d4093-102">AssemblyRefFlags — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="d4093-102">AssemblyRefFlags Enumeration</span></span>

<span data-ttu-id="d4093-103">Zawiera wartości opisujące funkcje odwołania do zestawu.</span><span class="sxs-lookup"><span data-stu-id="d4093-103">Contains values that describe features of an assembly reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4093-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="d4093-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    arfFullOriginator = 0x0001  
} AssemblyRefFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="d4093-105">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="d4093-105">Members</span></span>  
  
|<span data-ttu-id="d4093-106">Członek</span><span class="sxs-lookup"><span data-stu-id="d4093-106">Member</span></span>|<span data-ttu-id="d4093-107">Opis</span><span class="sxs-lookup"><span data-stu-id="d4093-107">Description</span></span>|  
|------------|-----------------|  
|`arfFullOriginator`|<span data-ttu-id="d4093-108">Określa, że odwołanie do zestawu zawiera pełne, niezmieszane informacje o wydawcy zestawu.</span><span class="sxs-lookup"><span data-stu-id="d4093-108">Specifies that the assembly reference contains full, unhashed information about the publisher of the assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d4093-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="d4093-109">Requirements</span></span>  

 <span data-ttu-id="d4093-110">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d4093-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4093-111">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="d4093-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d4093-112">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4093-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4093-113">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="d4093-113">See also</span></span>

- [<span data-ttu-id="d4093-114">Wyliczenia metadanych</span><span class="sxs-lookup"><span data-stu-id="d4093-114">Metadata Enumerations</span></span>](metadata-enumerations.md)
- [<span data-ttu-id="d4093-115">IMetaDataAssemblyEmit — Interfejs</span><span class="sxs-lookup"><span data-stu-id="d4093-115">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
- [<span data-ttu-id="d4093-116">DefineAssemblyRef, metoda</span><span class="sxs-lookup"><span data-stu-id="d4093-116">DefineAssemblyRef Method</span></span>](imetadataassemblyemit-defineassemblyref-method.md)
