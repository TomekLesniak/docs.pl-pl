---
title: Metoda ICorDebugAssembly3::EnumerateContainedAssemblies
ms.date: 03/30/2017
ms.assetid: 98f15b05-afad-4616-9e2a-1a9af31948b6
ms.openlocfilehash: 1e040453d5eb7a312f2e665974486492b99de16d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719687"
---
# <a name="icordebugassembly3enumeratecontainedassemblies-method"></a>Metoda ICorDebugAssembly3::EnumerateContainedAssemblies

Pobiera moduł wyliczający dla zestawów zawartych w tym zestawie.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT EnumerateContainedAssemblies(  
    ICorDebugAssemblyEnum **ppAssemblies  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `ppAssemblies`  
 określoną Wskaźnik do adresu obiektu interfejsu ICorDebugAssemblyEnum, który jest modułem wyliczającym.  
  
## <a name="return-value"></a>Wartość zwracana  

 `S_OK` Jeśli ten `ICorDebugAssembly3` obiekt jest kontenerem; w przeciwnym razie, `S_FALSE` a Wyliczenie jest puste.  
  
## <a name="remarks"></a>Uwagi  

 Symbole są konieczne do wyliczenia zawartych zestawów. Jeśli ich nie ma, metoda zwraca `S_FALSE` i nie podano prawidłowego modułu wyliczającego.  
  
> [!NOTE]
> Ta metoda jest dostępna tylko z .NET Native.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Interfejs ICorDebugAssembly3](icordebugassembly3-interface.md)
- [Debugowanie — Interfejsy](debugging-interfaces.md)
