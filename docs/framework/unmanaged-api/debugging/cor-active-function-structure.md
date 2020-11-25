---
title: COR_ACTIVE_FUNCTION — Struktura
ms.date: 03/30/2017
api_name:
- COR_ACTIVE_FUNCTION
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_ACTIVE_FUNCTION
helpviewer_keywords:
- COR_ACTIVE_FUNCTION structure [.NET Framework debugging]
ms.assetid: ed86185f-2152-459c-961f-10c06d62e83f
topic_type:
- apiref
ms.openlocfilehash: c50ba530d78296ebb956329b2f34b4f1e5cae94c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727422"
---
# <a name="cor_active_function-structure"></a><span data-ttu-id="0c7f2-102">COR_ACTIVE_FUNCTION — Struktura</span><span class="sxs-lookup"><span data-stu-id="0c7f2-102">COR_ACTIVE_FUNCTION Structure</span></span>

<span data-ttu-id="0c7f2-103">Zawiera informacje o funkcjach, które są obecnie aktywne w ramkach wątku.</span><span class="sxs-lookup"><span data-stu-id="0c7f2-103">Contains information about the functions that are currently active in a thread's frames.</span></span> <span data-ttu-id="0c7f2-104">Ta struktura jest używana przez metodę [ICorDebugThread2:: GetActiveFunctions —](icordebugthread2-getactivefunctions-method.md) .</span><span class="sxs-lookup"><span data-stu-id="0c7f2-104">This structure is used by the [ICorDebugThread2::GetActiveFunctions](icordebugthread2-getactivefunctions-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c7f2-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="0c7f2-105">Syntax</span></span>  
  
```cpp  
typedef struct  _COR_ACTIVE_FUNCTION {  
    ICorDebugAppDomain   *pAppDomain;  
    ICorDebugModule      *pModule;  
    ICorDebugFunction2   *pFunction;  
    ULONG32              ilOffset;  
    ULONG32              flags;  
} COR_ACTIVE_FUNCTION;  
```  
  
## <a name="members"></a><span data-ttu-id="0c7f2-106">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="0c7f2-106">Members</span></span>  
  
|<span data-ttu-id="0c7f2-107">Członek</span><span class="sxs-lookup"><span data-stu-id="0c7f2-107">Member</span></span>|<span data-ttu-id="0c7f2-108">Opis</span><span class="sxs-lookup"><span data-stu-id="0c7f2-108">Description</span></span>|  
|------------|-----------------|  
|`pAppDomain`|<span data-ttu-id="0c7f2-109">Wskaźnik do właściciela domeny aplikacji `ilOffset` pola.</span><span class="sxs-lookup"><span data-stu-id="0c7f2-109">Pointer to the application domain owner of the `ilOffset` field.</span></span>|  
|`pModule`|<span data-ttu-id="0c7f2-110">Wskaźnik do właściciela modułu `ilOffset` pola.</span><span class="sxs-lookup"><span data-stu-id="0c7f2-110">Pointer to the module owner of the `ilOffset` field.</span></span>|  
|`pFunction`|<span data-ttu-id="0c7f2-111">Wskaźnik do właściciela funkcji `ilOffset` pola.</span><span class="sxs-lookup"><span data-stu-id="0c7f2-111">Pointer to the function owner of the `ilOffset` field.</span></span>|  
|`ilOffset`|<span data-ttu-id="0c7f2-112">Przesunięcie języka pośredniego (MSIL) firmy Microsoft dla ramki.</span><span class="sxs-lookup"><span data-stu-id="0c7f2-112">The Microsoft intermediate language (MSIL) offset of the frame.</span></span>|  
|`flags`|<span data-ttu-id="0c7f2-113">Zarezerwowane do użytku w przyszłości.</span><span class="sxs-lookup"><span data-stu-id="0c7f2-113">Reserved for future extensibility.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0c7f2-114">Wymagania</span><span class="sxs-lookup"><span data-stu-id="0c7f2-114">Requirements</span></span>  

 <span data-ttu-id="0c7f2-115">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c7f2-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c7f2-116">**Nagłówek:** CorDebug. idl</span><span class="sxs-lookup"><span data-stu-id="0c7f2-116">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="0c7f2-117">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="0c7f2-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0c7f2-118">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c7f2-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c7f2-119">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="0c7f2-119">See also</span></span>

- [<span data-ttu-id="0c7f2-120">Struktury debugowania</span><span class="sxs-lookup"><span data-stu-id="0c7f2-120">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="0c7f2-121">Debugowanie</span><span class="sxs-lookup"><span data-stu-id="0c7f2-121">Debugging</span></span>](index.md)
