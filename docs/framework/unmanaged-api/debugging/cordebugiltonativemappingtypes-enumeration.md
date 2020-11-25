---
title: CorDebugIlToNativeMappingTypes — Wyliczenie
ms.date: 03/30/2017
api_name:
- CorDebugIlToNativeMappingTypes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugIlToNativeMappingTypes
helpviewer_keywords:
- CorDebugIIToNativeMappingTypes enumeration [.NET Framework debugging]
ms.assetid: c35e2919-42c3-4ba0-ae28-443c35f66f93
topic_type:
- apiref
ms.openlocfilehash: ecb88195e3ecc7c540679a683005798247afe57f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712433"
---
# <a name="cordebugiltonativemappingtypes-enumeration"></a><span data-ttu-id="931c5-102">CorDebugIlToNativeMappingTypes — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="931c5-102">CorDebugIlToNativeMappingTypes Enumeration</span></span>

<span data-ttu-id="931c5-103">Wskazuje, czy konkretny zakres instrukcji macierzystych, reprezentowany przez wystąpienie struktury COR_DEBUG_IL_TO_NATIVE_MAP, odpowiada specjalnemu regionowi kodu.</span><span class="sxs-lookup"><span data-stu-id="931c5-103">Indicates whether a particular range of native instructions, represented by an instance of the COR_DEBUG_IL_TO_NATIVE_MAP structure, corresponds to a special code region.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="931c5-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="931c5-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugIlToNativeMappingTypes {  
    NO_MAPPING = -1,  
    PROLOG     = -2,  
    EPILOG     = -3  
} CorDebugIlToNativeMappingTypes;  
```  
  
## <a name="members"></a><span data-ttu-id="931c5-105">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="931c5-105">Members</span></span>  
  
|<span data-ttu-id="931c5-106">Członek</span><span class="sxs-lookup"><span data-stu-id="931c5-106">Member</span></span>|<span data-ttu-id="931c5-107">Opis</span><span class="sxs-lookup"><span data-stu-id="931c5-107">Description</span></span>|  
|------------|-----------------|  
|`NO_MAPPING`|<span data-ttu-id="931c5-108">Zakres instrukcji natywnych nie odpowiada żadnemu specjalnemu regionowi kodu.</span><span class="sxs-lookup"><span data-stu-id="931c5-108">The range of native instructions does not correspond to any special code region.</span></span>|  
|`PROLOG`|<span data-ttu-id="931c5-109">Zakres natywnych instrukcji odpowiada prologu.</span><span class="sxs-lookup"><span data-stu-id="931c5-109">The range of native instructions corresponds to the prolog.</span></span>|  
|`EPILOG`|<span data-ttu-id="931c5-110">Zakres instrukcji natywnych odpowiada epilogu.</span><span class="sxs-lookup"><span data-stu-id="931c5-110">The range of native instructions corresponds to the epilog.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="931c5-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="931c5-111">Requirements</span></span>  

 <span data-ttu-id="931c5-112">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="931c5-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="931c5-113">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="931c5-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="931c5-114">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="931c5-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="931c5-115">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="931c5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="931c5-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="931c5-116">See also</span></span>

- [<span data-ttu-id="931c5-117">GetILToNativeMapping, metoda</span><span class="sxs-lookup"><span data-stu-id="931c5-117">GetILToNativeMapping Method</span></span>](icordebugcode-getiltonativemapping-method.md)
- [<span data-ttu-id="931c5-118">Debugowanie — wyliczenia</span><span class="sxs-lookup"><span data-stu-id="931c5-118">Debugging Enumerations</span></span>](debugging-enumerations.md)
