---
title: COR_PRF_STATIC_TYPE — Wyliczenie
ms.date: 03/30/2017
api_name:
- COR_PRF_STATIC_TYPE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_STATIC_TYPE
helpviewer_keywords:
- COR_PRF_STATIC_TYPE enumeration [.NET Framework profiling]
ms.assetid: 441d7809-5b65-41a5-ba64-2910a8008315
topic_type:
- apiref
ms.openlocfilehash: 2fbcbb6f6115ec48085b533dbf5611054a8235c5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95696742"
---
# <a name="cor_prf_static_type-enumeration"></a><span data-ttu-id="5f768-102">COR_PRF_STATIC_TYPE — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="5f768-102">COR_PRF_STATIC_TYPE Enumeration</span></span>

<span data-ttu-id="5f768-103">Wskazuje, czy pole jest statyczne i, jeśli tak, statyczna jakość stosowana do pola.</span><span class="sxs-lookup"><span data-stu-id="5f768-103">Indicates whether a field is static and, if so, the static quality that applies to the field.</span></span> <span data-ttu-id="5f768-104">Te wartości można łączyć za pomocą bitowego lub operacji, aby wskazać, że pole ma wiele różnych klas statycznych.</span><span class="sxs-lookup"><span data-stu-id="5f768-104">These values can be combined using the bitwise OR operation to indicate that the field has multiple, different static qualities.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f768-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="5f768-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_FIELD_NOT_A_STATIC = 0x0,  
    COR_PRF_FIELD_APP_DOMAIN_STATIC = 0x1,  
    COR_PRF_FIELD_THREAD_STATIC = 0x2,  
    COR_PRF_FIELD_CONTEXT_STATIC = 0x4,  
    COR_PRF_FIELD_RVA_STATIC = 0x8  
} COR_PRF_STATIC_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="5f768-106">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="5f768-106">Members</span></span>  
  
|<span data-ttu-id="5f768-107">Członek</span><span class="sxs-lookup"><span data-stu-id="5f768-107">Member</span></span>|<span data-ttu-id="5f768-108">Opis</span><span class="sxs-lookup"><span data-stu-id="5f768-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FIELD_NOT_A_STATIC`|<span data-ttu-id="5f768-109">Pole nie jest statyczne.</span><span class="sxs-lookup"><span data-stu-id="5f768-109">The field is not static.</span></span>|  
|`COR_PRF_FIELD_APP_DOMAIN_STATIC`|<span data-ttu-id="5f768-110">Pole jest domeną aplikacji — static.</span><span class="sxs-lookup"><span data-stu-id="5f768-110">The field is application domain-static.</span></span>|  
|`COR_PRF_FIELD_THREAD_STATIC`|<span data-ttu-id="5f768-111">Pole jest statyczne wątku.</span><span class="sxs-lookup"><span data-stu-id="5f768-111">The field is thread-static.</span></span>|  
|`COR_PRF_FIELD_CONTEXT_STATIC`|<span data-ttu-id="5f768-112">Pole jest kontekst-static.</span><span class="sxs-lookup"><span data-stu-id="5f768-112">The field is context-static.</span></span>|  
|`COR_PRF_FIELD_RVA_STATIC`|<span data-ttu-id="5f768-113">Pole jest względnym adresem wirtualnym (RVA) — static.</span><span class="sxs-lookup"><span data-stu-id="5f768-113">The field is relative virtual address (RVA)-static.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5f768-114">Wymagania</span><span class="sxs-lookup"><span data-stu-id="5f768-114">Requirements</span></span>  

 <span data-ttu-id="5f768-115">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f768-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f768-116">**Nagłówek:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="5f768-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5f768-117">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="5f768-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5f768-118">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f768-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f768-119">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="5f768-119">See also</span></span>

- [<span data-ttu-id="5f768-120">Profilowanie — Wyliczenia</span><span class="sxs-lookup"><span data-stu-id="5f768-120">Profiling Enumerations</span></span>](profiling-enumerations.md)
