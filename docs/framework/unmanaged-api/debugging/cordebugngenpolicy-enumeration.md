---
title: CorDebugNGenPolicy — Wyliczenie
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CorDebugNGenPolicy
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugNGenPolicy
helpviewer_keywords:
- CorDebugNgenPolicy enumeration [.NET Framework debugging]
ms.assetid: edb4e4d2-3166-44d4-8b17-bf302f7ea093
topic_type:
- apiref
ms.openlocfilehash: b64de0fa2ecbddd2decf69a4099d9897ec42a563
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95696430"
---
# <a name="cordebugngenpolicy-enumeration"></a><span data-ttu-id="8dbc3-102">CorDebugNGenPolicy — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="8dbc3-102">CorDebugNGenPolicy Enumeration</span></span>

<span data-ttu-id="8dbc3-103">Zapewnia wartość określającą, czy debuger ładuje obrazy natywne (NGen) z pamięci podręcznej obrazów natywnych.</span><span class="sxs-lookup"><span data-stu-id="8dbc3-103">Provides a value that determines whether a debugger loads native (NGen) images from the native image cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8dbc3-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="8dbc3-104">Syntax</span></span>  
  
```cpp
enum CorDebugNGENPolicy {  
    DISABLE_LOCAL_NIC = 1  
} CorDebugNGENPolicy;  
```  
  
## <a name="members"></a><span data-ttu-id="8dbc3-105">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="8dbc3-105">Members</span></span>  
  
|<span data-ttu-id="8dbc3-106">Nazwa elementu członkowskiego</span><span class="sxs-lookup"><span data-stu-id="8dbc3-106">Member name</span></span>|<span data-ttu-id="8dbc3-107">Opis</span><span class="sxs-lookup"><span data-stu-id="8dbc3-107">Description</span></span>|  
|-----------------|-----------------|  
|`DISABLE_LOCAL_NIC`|<span data-ttu-id="8dbc3-108">W aplikacji ze sklepu Windows 8. x korzystanie z obrazów z lokalnej pamięci podręcznej obrazów natywnych jest wyłączone.</span><span class="sxs-lookup"><span data-stu-id="8dbc3-108">In a Windows 8.x Store app, the use of images from the local native image cache is disabled.</span></span> <span data-ttu-id="8dbc3-109">W aplikacji klasycznej to ustawienie nie ma żadnego wpływu.</span><span class="sxs-lookup"><span data-stu-id="8dbc3-109">In a desktop app, this setting has no effect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8dbc3-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="8dbc3-110">Remarks</span></span>  

 <span data-ttu-id="8dbc3-111">`CorDebugNGENPolicy`Wyliczenie jest używane przez metodę [ICorDebugProcess5:: EnableNGENPolicy —](icordebugprocess5-enablengenpolicy-method.md) .</span><span class="sxs-lookup"><span data-stu-id="8dbc3-111">The `CorDebugNGENPolicy` enumeration is used by the [ICorDebugProcess5::EnableNGENPolicy](icordebugprocess5-enablengenpolicy-method.md) method.</span></span> <span data-ttu-id="8dbc3-112">Wyłączenie używania obrazów z lokalnej pamięci podręcznej obrazów natywnych zapewnia spójne środowisko debugowania przez zagwarantowanie, że debuger ładuje obrazy skompilowane JIT możliwością debugowania zamiast zoptymalizowanych obrazów natywnych.</span><span class="sxs-lookup"><span data-stu-id="8dbc3-112">Disabling the use of images from the local native image cache provides for a consistent debugging experience by ensuring that the debugger loads debuggable JIT-compiled images instead of optimized native images.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8dbc3-113">Wymagania</span><span class="sxs-lookup"><span data-stu-id="8dbc3-113">Requirements</span></span>  

 <span data-ttu-id="8dbc3-114">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8dbc3-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8dbc3-115">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="8dbc3-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8dbc3-116">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="8dbc3-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8dbc3-117">**.NET Framework wersje:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8dbc3-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8dbc3-118">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="8dbc3-118">See also</span></span>

- [<span data-ttu-id="8dbc3-119">Debugowanie — wyliczenia</span><span class="sxs-lookup"><span data-stu-id="8dbc3-119">Debugging Enumerations</span></span>](debugging-enumerations.md)
