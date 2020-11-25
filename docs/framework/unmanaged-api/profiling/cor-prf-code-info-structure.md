---
title: COR_PRF_CODE_INFO — Struktura
ms.date: 03/30/2017
api_name:
- COR_PRF_CODE_INFO
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_CODE_INFO
helpviewer_keywords:
- COR_PRF_CODE_INFO structure [.NET Framework profiling]
ms.assetid: cf30e27c-1f7e-43a2-ba1e-01e4137301db
topic_type:
- apiref
ms.openlocfilehash: b64e58a79f3dbe0c91b0c0cefc4a9d918c700cf9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718634"
---
# <a name="cor_prf_code_info-structure"></a><span data-ttu-id="14b4e-102">COR_PRF_CODE_INFO — Struktura</span><span class="sxs-lookup"><span data-stu-id="14b4e-102">COR_PRF_CODE_INFO Structure</span></span>

<span data-ttu-id="14b4e-103">Reprezentuje jeden ciągły blok kodu natywnego przechowywanego w pamięci.</span><span class="sxs-lookup"><span data-stu-id="14b4e-103">Represents one contiguous block of native code stored in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14b4e-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="14b4e-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_PRF_CODE_INFO {  
    UINT_PTR startAddress;  
    SIZE_T size;  
} COR_PRF_CODE_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="14b4e-105">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="14b4e-105">Members</span></span>  
  
|<span data-ttu-id="14b4e-106">Członek</span><span class="sxs-lookup"><span data-stu-id="14b4e-106">Member</span></span>|<span data-ttu-id="14b4e-107">Opis</span><span class="sxs-lookup"><span data-stu-id="14b4e-107">Description</span></span>|  
|------------|-----------------|  
|`startAddress`|<span data-ttu-id="14b4e-108">Adres początkowy ciągłego bloku kodu.</span><span class="sxs-lookup"><span data-stu-id="14b4e-108">The starting address of the contiguous block of code.</span></span>|  
|`size`|<span data-ttu-id="14b4e-109">Rozmiar bloku.</span><span class="sxs-lookup"><span data-stu-id="14b4e-109">The size of the block.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="14b4e-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="14b4e-110">Requirements</span></span>  

 <span data-ttu-id="14b4e-111">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="14b4e-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14b4e-112">**Nagłówek:** CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="14b4e-112">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="14b4e-113">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="14b4e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="14b4e-114">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14b4e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14b4e-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="14b4e-115">See also</span></span>

- [<span data-ttu-id="14b4e-116">Profiling — Struktury</span><span class="sxs-lookup"><span data-stu-id="14b4e-116">Profiling Structures</span></span>](profiling-structures.md)
