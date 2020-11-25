---
title: ICorDebugClass2::GetParameterizedType — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugClass2.GetParameterizedType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass2::GetParameterizedType
helpviewer_keywords:
- GetParameterizedType method [.NET Framework debugging]
- ICorDebugClass2::GetParameterizedType method [.NET Framework debugging]
ms.assetid: 94b591c4-9302-4af2-a510-089496afb036
topic_type:
- apiref
ms.openlocfilehash: 139181975d16c2cdacec10ed646cfc2b8fb31a20
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717997"
---
# <a name="icordebugclass2getparameterizedtype-method"></a>ICorDebugClass2::GetParameterizedType — Metoda

Pobiera deklarację typu dla tej klasy.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetParameterizedType (  
    [in] CorElementType                      elementType,  
    [in] ULONG32                             nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType  *ppTypeArgs[],  
    [out] ICorDebugType                    **ppType  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `elementType`  
 podczas Wartość wyliczenia CorElementType —, która określa typ elementu dla tej klasy: Ustaw tę wartość na ELEMENT_TYPE_VALUETYPE, jeśli ten ICorDebugClass2 reprezentuje typ wartości. Ustaw tę wartość na ELEMENT_TYPE_CLASS, jeśli `ICorDebugClass2` reprezentuje typ złożony.  
  
 `nTypeArgs`  
 podczas Liczba parametrów typu, jeśli typ jest ogólny. Liczba parametrów typu (jeśli istnieją) musi być zgodna z liczbą wymaganą przez klasę.  
  
 `ppTypeArgs`  
 podczas Tablica wskaźników, z których każdy wskazuje obiekt ICorDebugType reprezentujący parametr typu. Jeśli Klasa nie jest ogólna, ta wartość jest równa null.  
  
 `ppType`  
 określoną Wskaźnik do adresu `ICorDebugType` obiektu, który reprezentuje deklarację typu. Ten obiekt jest równoważny <xref:System.Type> obiektowi w kodzie zarządzanym.  
  
## <a name="remarks"></a>Uwagi  

 Jeśli klasa jest nieogólna, to oznacza, że jeśli nie ma parametrów typu, `GetParameterizedType` po prostu pobiera obiekt typu środowiska uruchomieniowego odpowiadający klasie. `elementType`Parametr powinien być ustawiony na prawidłowy typ elementu dla klasy: ELEMENT_TYPE_VALUETYPE, jeśli klasa jest typem wartości; w przeciwnym razie ELEMENT_TYPE_CLASS.  
  
 Jeśli Klasa akceptuje parametry typu (na przykład `ArrayList<T>` ), można użyć `GetParameterizedType` do konstruowania obiektu typu dla wystąpienia typu, takiego jak `ArrayList<int>` .  
  
## <a name="background-information"></a>Informacje uzupełniające  

 W .NET Framework wersje 1,0 i 1,1 Każdy typ w metadanych może być bezpośrednio zamapowany na typ w uruchomionym procesie. W ten sposób typ metadanych i typ środowiska uruchomieniowego miały jedną reprezentację w uruchomionym procesie. Jednak jeden typ ogólny w metadanych można zamapować na wiele różnych wystąpień typu w uruchomionym procesie. Na przykład typ metadanych `SortedList<K,V>` może być mapowany na `SortedList<String, EmployeeRecord>` , `SortedList<Int32, String>` , `SortedList<String,Array<Int32>>` , i tak dalej. W tym celu musisz mieć możliwość obsługi tworzenia wystąpienia typu.  
  
 W .NET Framework w wersji 2,0 wprowadzono `ICorDebugType` interfejs. W przypadku typu ogólnego `ICorDebugClass` `ICorDebugClass2` obiekt lub reprezentuje typ nieskonkretyzowany ( `SortedList<K,V>` ), a `ICorDebugType` obiekt reprezentuje różne typy wystąpień. Mając `ICorDebugClass` obiekt lub `ICorDebugClass2` , można utworzyć `ICorDebugType` obiekt dla dowolnego wystąpienia, wywołując `ICorDebugClass2::GetParameterizedType` metodę. Można również utworzyć `ICorDebugType` obiekt dla typu prostego, takiego jak Int32 lub dla typu innego niż ogólny.  
  
 Wprowadzenie `ICorDebugType` obiektu do reprezentowania koncepcji czasu wykonywania typu ma wpływ na działanie narzędzia Ripple w całym interfejsie API. Funkcje, które wcześniej brały `ICorDebugClass` obiekt lub, `ICorDebugClass2` a nawet `CorElementType` wartość, są uogólnione w celu wykonania `ICorDebugType` obiektu.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
