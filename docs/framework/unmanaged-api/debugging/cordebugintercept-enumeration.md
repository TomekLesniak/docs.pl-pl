---
title: CorDebugIntercept — Wyliczenie
ms.date: 03/30/2017
api_name:
- CorDebugIntercept
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugIntercept
helpviewer_keywords:
- CorDebugIntercept enumeration [.NET Framework debugging]
ms.assetid: 3d5b642e-7ef2-428b-a5ae-509c35ed461a
topic_type:
- apiref
ms.openlocfilehash: 3d3d4af8e9ee073c0aefec418a3b53c4589adf0d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729112"
---
# <a name="cordebugintercept-enumeration"></a>CorDebugIntercept — Wyliczenie

Wskazuje typy kodu, które mogą być przechwytywane (to jest, w trakcie).  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
typedef enum CorDebugIntercept {  
    INTERCEPT_NONE                = 0x0,  
    INTERCEPT_CLASS_INIT          = 0x01,  
    INTERCEPT_EXCEPTION_FILTER    = 0x02,  
    INTERCEPT_SECURITY            = 0x04,  
    INTERCEPT_CONTEXT_POLICY      = 0x08,  
    INTERCEPT_INTERCEPTION        = 0x10,  
    INTERCEPT_ALL                 = 0xffff  
} CorDebugIntercept;  
```  
  
## <a name="members"></a>Elementy członkowskie  
  
|Członek|Opis|  
|------------|-----------------|  
|`INTERCEPT_NONE`|Kod nie może być przechwytywany.|  
|`INTERCEPT_CLASS_INIT`|Konstruktor może być przechwytywany.|  
|`INTERCEPT_EXCEPTION_FILTER`|Filtr wyjątku może być przechwytywany.|  
|`INTERCEPT_SECURITY`|Kod, który wymusza zabezpieczenia, może być przechwytywany.|  
|`INTERCEPT_CONTEXT_POLICY`|Zasady kontekstu mogą być przechwytywane.|  
|`INTERCEPT_INTERCEPTION`|Nie używany.|  
|`INTERCEPT_ALL`|Cały kod może być przechwytywany.|  
  
## <a name="remarks"></a>Uwagi  

 Użyj metody [ICorDebugStepper:: SetInterceptMask —](icordebugstepper-setinterceptmask-method.md) , aby określić typy kodu, które mogą być przechwytywane.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Debugowanie — wyliczenia](debugging-enumerations.md)
