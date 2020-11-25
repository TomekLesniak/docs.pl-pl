---
title: ICorDebugProcess5::EnableNGENPolicy — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5::EnableNGenPolicy
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnableNGENPolicy
helpviewer_keywords:
- ICorDebugProcess5::EnableNGENPolicy method [.NET Framework debugging]
- EnableNGENPolicy method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 3b8e15ca-3c72-4685-a937-da4c739cb9e9
topic_type:
- apiref
ms.openlocfilehash: e3dfd3cae83c7891d246ff3a81427c161cc0e2d1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731392"
---
# <a name="icordebugprocess5enablengenpolicy-method"></a><span data-ttu-id="b391a-102">ICorDebugProcess5::EnableNGENPolicy — Metoda</span><span class="sxs-lookup"><span data-stu-id="b391a-102">ICorDebugProcess5::EnableNGENPolicy Method</span></span>

<span data-ttu-id="b391a-103">Ustawia wartość określającą sposób ładowania obrazów natywnych przez aplikację podczas działania w ramach zarządzanego debugera.</span><span class="sxs-lookup"><span data-stu-id="b391a-103">Sets a value that determines how an application loads native images while running under a managed debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b391a-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="b391a-104">Syntax</span></span>  
  
```cpp  
HRESULT EnableNGENPolicy(  
    [in] CorDebugNGENPolicy ePolicy  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b391a-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="b391a-105">Parameters</span></span>  

 `ePolicy`  
 <span data-ttu-id="b391a-106">podczas Stała [CorDebugNGenPolicy —](cordebugngenpolicy-enumeration.md) , która określa, w jaki sposób aplikacja ładuje obrazy natywne podczas działania w zarządzanym debugerze.</span><span class="sxs-lookup"><span data-stu-id="b391a-106">[in] A [CorDebugNGenPolicy](cordebugngenpolicy-enumeration.md) constant that determines how an application loads native images while running under a managed debugger.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b391a-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="b391a-107">Remarks</span></span>  

 <span data-ttu-id="b391a-108">Jeśli zasady zostały ustawione pomyślnie, metoda zwraca `S_OK` .</span><span class="sxs-lookup"><span data-stu-id="b391a-108">If the policy is set successfully, the method returns `S_OK`.</span></span> <span data-ttu-id="b391a-109">Jeśli `ePolicy` znajduje się poza zakresem wartości wyliczanych zdefiniowanych przez [CorDebugNGenPolicy —](cordebugngenpolicy-enumeration.md), metoda zwraca `E_INVALIDARG` i wywołanie metody nie ma żadnego wpływu.</span><span class="sxs-lookup"><span data-stu-id="b391a-109">If `ePolicy` is outside the range of the enumerated values defined by [CorDebugNGenPolicy](cordebugngenpolicy-enumeration.md), the method returns `E_INVALIDARG` and the method call has no effect.</span></span> <span data-ttu-id="b391a-110">Jeśli nie można zaktualizować zasad generatora obrazów natywnych (Ngen.exe), metoda zwraca `E_FAIL` .</span><span class="sxs-lookup"><span data-stu-id="b391a-110">If the policy of the Native Image Generator (Ngen.exe) cannot be updated, the method returns `E_FAIL`.</span></span>  
  
 <span data-ttu-id="b391a-111">`ICorDebugProcess5::EnableNGenPolicy`Metodę można wywołać w dowolnym momencie w okresie istnienia procesu.</span><span class="sxs-lookup"><span data-stu-id="b391a-111">The `ICorDebugProcess5::EnableNGenPolicy` method can be called at any time during the lifetime of the process.</span></span> <span data-ttu-id="b391a-112">Zasady obowiązują dla wszystkich modułów, które są ładowane po ustawieniu zasad.</span><span class="sxs-lookup"><span data-stu-id="b391a-112">The policy is in effect for any modules that are loaded after the policy is set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b391a-113">Wymagania</span><span class="sxs-lookup"><span data-stu-id="b391a-113">Requirements</span></span>  

 <span data-ttu-id="b391a-114">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b391a-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b391a-115">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="b391a-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b391a-116">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="b391a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b391a-117">**.NET Framework wersje:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b391a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b391a-118">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="b391a-118">See also</span></span>

- [<span data-ttu-id="b391a-119">ICorDebugProcess5 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="b391a-119">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="b391a-120">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="b391a-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="b391a-121">Debugowanie</span><span class="sxs-lookup"><span data-stu-id="b391a-121">Debugging</span></span>](index.md)
