---
title: ICorDebugStepper::Deactivate — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.Deactivate
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::Deactivate
helpviewer_keywords:
- Deactivate method [.NET Framework debugging]
- ICorDebugStepper::Deactivate method [.NET Framework debugging]
ms.assetid: 855f4199-b62d-40ce-998e-1eb4a1772142
topic_type:
- apiref
ms.openlocfilehash: 0d7d5e7e6c9bc1a68feda85c5214f3ae95df9b97
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730594"
---
# <a name="icordebugstepperdeactivate-method"></a><span data-ttu-id="0a8d9-102">ICorDebugStepper::Deactivate — Metoda</span><span class="sxs-lookup"><span data-stu-id="0a8d9-102">ICorDebugStepper::Deactivate Method</span></span>

<span data-ttu-id="0a8d9-103">Powoduje anulowanie przez ten ICorDebugStepper polecenia ostatniego kroku.</span><span class="sxs-lookup"><span data-stu-id="0a8d9-103">Causes this ICorDebugStepper to cancel the last step command that it received.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a8d9-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="0a8d9-104">Syntax</span></span>  
  
```cpp  
HRESULT Deactivate ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="0a8d9-105">Uwagi</span><span class="sxs-lookup"><span data-stu-id="0a8d9-105">Remarks</span></span>  

 <span data-ttu-id="0a8d9-106">Nowe polecenie krokowe może zostać wydane po anulowaniu niedawno otrzymanego kroku polecenia.</span><span class="sxs-lookup"><span data-stu-id="0a8d9-106">A new stepping command may be issued after the most recently received step command has been canceled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a8d9-107">Wymagania</span><span class="sxs-lookup"><span data-stu-id="0a8d9-107">Requirements</span></span>  

 <span data-ttu-id="0a8d9-108">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0a8d9-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a8d9-109">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="0a8d9-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0a8d9-110">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="0a8d9-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0a8d9-111">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a8d9-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
