---
title: ICorDebugAppDomain::EnumerateSteppers — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.EnumerateSteppers
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::EnumerateSteppers
helpviewer_keywords:
- ICorDebugAppDomain::EnumerateSteppers method [.NET Framework debugging]
- EnumerateSteppers method [.NET Framework debugging]
ms.assetid: 3f3c4503-570e-44c1-ae6a-a3c6b840c732
topic_type:
- apiref
ms.openlocfilehash: fd9243d9e0c12b572613694538661fd553e8a487
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715930"
---
# <a name="icordebugappdomainenumeratesteppers-method"></a><span data-ttu-id="8830f-102">ICorDebugAppDomain::EnumerateSteppers — Metoda</span><span class="sxs-lookup"><span data-stu-id="8830f-102">ICorDebugAppDomain::EnumerateSteppers Method</span></span>

<span data-ttu-id="8830f-103">Pobiera moduł wyliczający dla wszystkich aktywnych współdziałań w domenie aplikacji.</span><span class="sxs-lookup"><span data-stu-id="8830f-103">Gets an enumerator for all active steppers in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8830f-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="8830f-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateSteppers (  
    [out] ICorDebugStepperEnum   **ppSteppers  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8830f-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="8830f-105">Parameters</span></span>  

 `ppSteppers`  
 <span data-ttu-id="8830f-106">określoną Wskaźnik do adresu obiektu ICorDebugStepperEnum, który jest modułem wyliczającym dla wszystkich aktywnych współdziałań w domenie aplikacji.</span><span class="sxs-lookup"><span data-stu-id="8830f-106">[out] A pointer to the address of an ICorDebugStepperEnum object that is the enumerator for all active steppers in the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8830f-107">Wymagania</span><span class="sxs-lookup"><span data-stu-id="8830f-107">Requirements</span></span>  

 <span data-ttu-id="8830f-108">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8830f-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8830f-109">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="8830f-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8830f-110">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="8830f-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8830f-111">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8830f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
