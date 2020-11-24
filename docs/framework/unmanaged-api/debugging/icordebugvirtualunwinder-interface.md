---
title: ICorDebugVirtualUnwinder — interfejs
ms.date: 03/30/2017
ms.assetid: a09e9ccc-0b37-43e3-95c1-bc5fa7ee5f42
ms.openlocfilehash: 67f2234d37165e421874815bdc2ef34f8f50749a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679380"
---
# <a name="icordebugvirtualunwinder-interface"></a>ICorDebugVirtualUnwinder — interfejs

Zapewnia metody pomagające w rozwinięcia stosu.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Nazwa|  
|------------|----------|  
|[GetContext — Metoda](icordebugvirtualunwinder-getcontext-method.md)|Pobiera bieżący kontekst tego elementu unwiatrer.|  
|[Next, metoda](icordebugvirtualunwinder-next-method.md)|Przechodzi do kontekstu obiektu wywołującego.|  
  
## <a name="remarks"></a>Uwagi  

 Elementy członkowskie `ICorDebugVirtualUnwinder` interfejsu są implementowane przez debuger, aby pomóc w rozwinięcia stosu.  
  
> [!NOTE]
> Ten interfejs jest dostępny tylko dla .NET Native. W przypadku zaimplementowania tego interfejsu dla scenariuszy ICorDebug poza .NET Native, środowisko uruchomieniowe języka wspólnego zignoruje ten interfejs.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Debugowanie — Interfejsy](debugging-interfaces.md)
- [Debugowanie](index.md)
