---
title: COR_DEBUG_STEP_RANGE — Struktura
ms.date: 03/30/2017
api_name:
- COR_DEBUG_STEP_RANGE
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_DEBUG_STEP_RANGE
helpviewer_keywords:
- COR_DEBUG_STEP_RANGE structure [.NET Framework debugging]
ms.assetid: 8809d00e-beaa-4dcf-b4e8-e89d0a5406b7
topic_type:
- apiref
ms.openlocfilehash: cd85ba2e6a907ff9546614e02b4da5f45e74b924
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726642"
---
# <a name="cor_debug_step_range-structure"></a>COR_DEBUG_STEP_RANGE — Struktura

Zawiera informacje o przesunięciu dla zakresu kodu.  
  
 Ta struktura jest używana przez metodę [ICorDebugStepper:: StepRange —](icordebugstepper-steprange-method.md) .  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
typedef struct {  
    ULONG32 startOffset;  
    ULONG32 endOffset;  
} COR_DEBUG_STEP_RANGE;  
```  
  
## <a name="members"></a>Elementy członkowskie  
  
|Członek|Opis|  
|------------|-----------------|  
|`startOffset`|Przesunięcie początku zakresu.|  
|`endOffset`|Przesunięcie końca zakresu.|  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [StepRange, metoda](icordebugstepper-steprange-method.md)
- [Struktury debugowania](debugging-structures.md)
- [Debugowanie](index.md)
