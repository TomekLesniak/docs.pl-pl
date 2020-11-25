---
title: COR_TYPE_LAYOUT — Struktura
ms.date: 03/30/2017
api_name:
- COR_TYPE_LAYOUT
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_TYPE_LAYOUT
helpviewer_keywords:
- COR_TYPE_LAYOUT structure [.NET Framework debugging]
ms.assetid: 43a7addd-f25a-4049-9907-abec3eb17af2
topic_type:
- apiref
ms.openlocfilehash: f33c8f5cf218979404063342d9b1cc5123839f83
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726330"
---
# <a name="cor_type_layout-structure"></a>COR_TYPE_LAYOUT — Struktura

Zawiera informacje na temat układu obiektu w pamięci.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
typedef struct COR_TYPE_LAYOUT {  
    COR_TYPEID parentID;  
    ULONG32 objectSize;  
    ULONG32 numFields;  
    ULONG32 boxOffset;  
    CorElementType type;  
} COR_TYPE_LAYOUT;  
```  
  
## <a name="members"></a>Elementy członkowskie  
  
|Członek|Opis|  
|------------|-----------------|  
|`parentID`|Identyfikator typu nadrzędnego dla tego typu. Będzie to identyfikator typu NULL (token1 = 0, token2 = 0), jeśli identyfikator typu odpowiada <xref:System.Object?displayProperty=nameWithType> .|  
|`objectSize`|Rozmiar podstawowy obiektu tego typu. Jest to całkowity rozmiar obiektów niezmiennych.|  
|`numFields`|Liczba pól uwzględnionych w obiektach tego typu.|  
|`boxOffset`|Jeśli ten typ jest opakowany, początkowe przesunięcie pól obiektu. To pole jest prawidłowe tylko dla typów wartości, takich jak elementy pierwotne i struktury.|  
|`type`|CorElementType —, do którego należy ten typ.|  
  
## <a name="remarks"></a>Uwagi  

 Jeśli `numFields` jest większa od zera, można wywołać metodę [ICorDebugProcess5:: GetTypeFields —](icordebugprocess5-gettypefields-method.md) , aby uzyskać informacje o polach w tym typie. Jeśli `type` jest `ELEMENT_TYPE_STRING` , `ELEMENT_TYPE_ARRAY` , lub `ELEMENT_TYPE_SZARRAY` , rozmiar obiektów tego typu jest zmienny i można przekazać strukturę [COR_TYPEID](cor-typeid-structure.md) do metody [ICorDebugProcess5:: GetArrayLayout —](icordebugprocess5-getarraylayout-method.md) .  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Struktury debugowania](debugging-structures.md)
- [Debugowanie](index.md)
