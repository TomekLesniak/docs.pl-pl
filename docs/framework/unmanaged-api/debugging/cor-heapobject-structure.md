---
title: COR_HEAPOBJECT — Struktura
ms.date: 03/30/2017
api_name:
- COR_HEAPOBJECT
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_HEAPOBJECT
helpviewer_keywords:
- COR_HEAPOBJECT structure [.NET Framework debugging]
ms.assetid: a92fdf95-492b-49ae-a741-2186e5c1d7c5
topic_type:
- apiref
ms.openlocfilehash: 54af02b48dabdf2042763954805f0d454323ac89
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726369"
---
# <a name="cor_heapobject-structure"></a>COR_HEAPOBJECT — Struktura

Zawiera informacje o obiekcie na zarządzanym stosie.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
typedef struct _COR_HEAPOBJECT {  
    CORDB_ADDRESS address;
    ULONG64 size;
    COR_TYPEID type;
} COR_HEAPOBJECT;  
```  
  
## <a name="members"></a>Elementy członkowskie  
  
|Członek|Opis|  
|------------|-----------------|  
|`address`|Adres obiektu w pamięci.|  
|`size`|Łączny rozmiar obiektu w bajtach.|  
|`type`|Token [COR_TYPEID](cor-typeid-structure.md) , który reprezentuje typ obiektu.|  
  
## <a name="remarks"></a>Uwagi  

 `COR_HEAPOBJECT` wystąpienia mogą być pobierane przez Wyliczenie obiektu interfejsu [ICorDebugHeapEnum](icordebugheapenum-interface.md) , który jest wypełniany przez wywołanie metody [ICorDebugProcess5:: EnumerateHeap —](icordebugprocess5-enumerateheap-method.md) .  
  
 `COR_HEAPOBJECT`Wystąpienie zawiera informacje dotyczące aktywnego obiektu na zarządzanym stosie lub o obiekcie, który nie jest odblokowany przez żaden obiekt, ale nie został jeszcze zebrany przez moduł wyrzucania elementów bezużytecznych.  
  
 W celu uzyskania lepszej wydajności `COR_HEAPOBJECT.address` pole to `CORDB_ADDRESS` wartość, a nie wartość interfejsu ICorDebugValue użyta w większości interfejsu API debugowania. Aby uzyskać obiekt ICorDebugValue dla danego adresu obiektu, można przekazać `CORDB_ADDRESS` wartość do metody [ICorDebugProcess5:: GetObject](icordebugprocess5-getobject-method.md) .  
  
 W celu uzyskania lepszej wydajności `COR_HEAPOBJECT.type` pole to `COR_TYPEID` wartość, a nie wartość interfejsu ICorDebugType użyta w większości interfejsu API debugowania. Aby uzyskać obiekt ICorDebugType dla danego identyfikatora typu, można przekazać `COR_TYPEID` wartość do metody [ICorDebugProcess5:: GetTypeForTypeID —](icordebugprocess5-gettypefortypeid-method.md) .  
  
 `COR_HEAPOBJECT`Struktura zawiera interfejs com liczony z odwołaniami. Jeśli pobrano `COR_HEAPOBJECT` wystąpienie z modułu wyliczającego, wywołując metodę [ICorDebugHeapEnum:: Next](icordebugheapenum-next-method.md) , należy następnie zwolnić odwołanie.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Struktury debugowania](debugging-structures.md)
- [Debugowanie](index.md)
