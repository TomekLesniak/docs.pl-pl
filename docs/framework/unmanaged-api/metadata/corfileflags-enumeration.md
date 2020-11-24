---
title: CorFileFlags — Wyliczenie
ms.date: 03/30/2017
api_name:
- CorFileFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorFileFlags
helpviewer_keywords:
- CorFileFlags enumeration [.NET Framework metadata]
ms.assetid: d16703fd-518f-412e-92cb-74433d11032e
topic_type:
- apiref
ms.openlocfilehash: 70d789f417700734b546cac6ff527ed5aa84fcf9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688630"
---
# <a name="corfileflags-enumeration"></a><span data-ttu-id="7a68b-102">CorFileFlags — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="7a68b-102">CorFileFlags Enumeration</span></span>

<span data-ttu-id="7a68b-103">Zawiera wartości opisujące typ pliku zdefiniowanego w wywołaniu [IMetaDataAssemblyEmit::D efinefile](imetadataassemblyemit-definefile-method.md).</span><span class="sxs-lookup"><span data-stu-id="7a68b-103">Contains values that describe the type of file defined in a call to [IMetaDataAssemblyEmit::DefineFile](imetadataassemblyemit-definefile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a68b-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="7a68b-104">Syntax</span></span>  
  
```cpp  
typedef enum CorFileFlags {  
  
    ffContainsMetaData      =   0x0000,  
    ffContainsNoMetaData    =   0x0001  
  
} CorFileFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="7a68b-105">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="7a68b-105">Members</span></span>  
  
|<span data-ttu-id="7a68b-106">Członek</span><span class="sxs-lookup"><span data-stu-id="7a68b-106">Member</span></span>|<span data-ttu-id="7a68b-107">Opis</span><span class="sxs-lookup"><span data-stu-id="7a68b-107">Description</span></span>|  
|------------|-----------------|  
|`ffContainsMetaData`|<span data-ttu-id="7a68b-108">Wskazuje, że plik nie jest plikiem zasobów.</span><span class="sxs-lookup"><span data-stu-id="7a68b-108">Indicates that the file is not a resource file.</span></span>|  
|`ffContainsNoMetaData`|<span data-ttu-id="7a68b-109">Wskazuje, że plik, prawdopodobnie plik zasobów, nie zawiera metadanych.</span><span class="sxs-lookup"><span data-stu-id="7a68b-109">Indicates that the file, possibly a resource file, does not contain metadata.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7a68b-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="7a68b-110">Requirements</span></span>  

 <span data-ttu-id="7a68b-111">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7a68b-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a68b-112">**Nagłówek:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="7a68b-112">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="7a68b-113">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a68b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a68b-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="7a68b-114">See also</span></span>

- [<span data-ttu-id="7a68b-115">Wyliczenia metadanych</span><span class="sxs-lookup"><span data-stu-id="7a68b-115">Metadata Enumerations</span></span>](metadata-enumerations.md)
