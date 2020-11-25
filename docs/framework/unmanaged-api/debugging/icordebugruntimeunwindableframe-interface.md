---
title: ICorDebugRuntimeUnwindableFrame — Interfejs
ms.date: 03/30/2017
api_name:
- ICorDebugUnwindableFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugUnwindableFrame
helpviewer_keywords:
- ICorDebugUnwindableFrame interface [.NET Framework debugging]
ms.assetid: cd6a3982-6ed3-4909-808d-a66055e813e0
topic_type:
- apiref
ms.openlocfilehash: 6619b8888588341f23a93b83865cd2e75cc9b3db
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712017"
---
# <a name="icordebugruntimeunwindableframe-interface"></a>ICorDebugRuntimeUnwindableFrame — Interfejs

Zapewnia obsługę niezarządzanych metod, które wymagają środowiska uruchomieniowego języka wspólnego (CLR), aby zwolnić ramkę.  
  
## <a name="remarks"></a>Uwagi  

 `ICorDebugRuntimeUnwindableFrame` to wyspecjalizowana wersja interfejsu ICorDebugFrame. Jest on używany przez metody niezarządzane, które wymagają wykonania przez środowisko uruchomieniowe ramki na bieżącym stosie. Istniejące konwencje odwinięcia nie działają, ponieważ nie używają kodu skompilowanego JIT. Gdy debuger widzi niewidocznyą ramkę, powinien użyć metody [ICorDebugStackWalk:: Next](icordebugstackwalk-next-method.md) , aby ją rozwinięcie, ale powinien wykonać inspekcję. Gdy debuger odbiera `ICorDebugRuntimeUnwindableFrame` , może wywołać metodę [ICorDebugStackWalk:: GetContext](icordebugstackwalk-getcontext-method.md) w celu pobrania kontekstu ramki.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Debugowanie — Interfejsy](debugging-interfaces.md)
- [Debugowanie](index.md)
