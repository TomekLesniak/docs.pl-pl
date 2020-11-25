---
title: CorDebugExceptionFlags — Wyliczenie
ms.date: 03/30/2017
api_name:
- CorDebugExceptionFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugExceptionFlags
helpviewer_keywords:
- CorDebugExceptionFlags enumeration [.NET Framework debugging]
ms.assetid: b22687a8-e9cf-4e65-a1b0-f92a81bc524e
topic_type:
- apiref
ms.openlocfilehash: a50272bce2e27963a1d684fef40bac30cf44e1f0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712719"
---
# <a name="cordebugexceptionflags-enumeration"></a><span data-ttu-id="d5d1c-102">CorDebugExceptionFlags — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="d5d1c-102">CorDebugExceptionFlags Enumeration</span></span>

<span data-ttu-id="d5d1c-103">Zawiera dodatkowe informacje o wyjątku.</span><span class="sxs-lookup"><span data-stu-id="d5d1c-103">Provides additional information about an exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5d1c-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="d5d1c-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugExceptionFlags {  
    DEBUG_EXCEPTION_NONE = 0,  
    DEBUG_EXCEPTION_CAN_BE_INTERCEPTED = 0x0001  
} CorDebugExceptionFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="d5d1c-105">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="d5d1c-105">Members</span></span>  
  
|<span data-ttu-id="d5d1c-106">Członek</span><span class="sxs-lookup"><span data-stu-id="d5d1c-106">Member</span></span>|<span data-ttu-id="d5d1c-107">Opis</span><span class="sxs-lookup"><span data-stu-id="d5d1c-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_NONE`|<span data-ttu-id="d5d1c-108">Nie istnieje żaden wyjątek.</span><span class="sxs-lookup"><span data-stu-id="d5d1c-108">There is no exception.</span></span>|  
|`DEBUG_EXCEPTION_CAN_BE_INTERCEPTED`|<span data-ttu-id="d5d1c-109">Wyjątek jest przechwytywany.</span><span class="sxs-lookup"><span data-stu-id="d5d1c-109">The exception is interceptable.</span></span><br /><br /> <span data-ttu-id="d5d1c-110">Czas wyjątku może być nadal taki, aby debuger nie mógł go przechwycić.</span><span class="sxs-lookup"><span data-stu-id="d5d1c-110">The timing of the exception may still be such that the debugger cannot intercept it.</span></span> <span data-ttu-id="d5d1c-111">Na przykład, jeśli nie istnieje kod zarządzany poniżej bieżącego wywołania zwrotnego lub zdarzenie wyjątku spowodowało z załącznika just-in-Time (JIT), nie można przechwycić wyjątku.</span><span class="sxs-lookup"><span data-stu-id="d5d1c-111">For example, if there is no managed code below the current callback or the exception event resulted from a just-in-time (JIT) attachment, the exception cannot be intercepted.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d5d1c-112">Uwagi</span><span class="sxs-lookup"><span data-stu-id="d5d1c-112">Remarks</span></span>  

 <span data-ttu-id="d5d1c-113">Nowe wartości można dodać do tego wyliczenia w nowszych wersjach, dlatego należy przygotować kod, który używa `CorDebugExceptionFlags` dla nieoczekiwanych wartości.</span><span class="sxs-lookup"><span data-stu-id="d5d1c-113">New values may be added to this enumeration in later versions, so you should prepare code that uses `CorDebugExceptionFlags` for unexpected values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5d1c-114">Wymagania</span><span class="sxs-lookup"><span data-stu-id="d5d1c-114">Requirements</span></span>  

 <span data-ttu-id="d5d1c-115">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d5d1c-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5d1c-116">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="d5d1c-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d5d1c-117">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="d5d1c-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d5d1c-118">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5d1c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5d1c-119">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="d5d1c-119">See also</span></span>

- [<span data-ttu-id="d5d1c-120">Debugowanie — wyliczenia</span><span class="sxs-lookup"><span data-stu-id="d5d1c-120">Debugging Enumerations</span></span>](debugging-enumerations.md)
