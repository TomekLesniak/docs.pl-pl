---
title: COR_ARRAY_LAYOUT — Struktury
ms.date: 03/30/2017
api_name:
- COR_ARRAY_LAYOUT
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_ARRAY_LAYOUT
helpviewer_keywords:
- COR_DEBUG_IL_TO_NATIVE_MAP structure [.NET Framework debugging]
ms.assetid: aa20ac3d-6f60-4aa2-91c5-f3a86f82eba8
topic_type:
- apiref
ms.openlocfilehash: 2ca6c89a671c4d7882e7cefdb820d07ac5636530
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727409"
---
# <a name="cor_array_layout-structure"></a>COR_ARRAY_LAYOUT — Struktury

Zawiera informacje o układzie obiektu tablicy w pamięci.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
typedef struct COR_ARRAY_LAYOUT {  
    COR_TYPEID componentID;  
    CorElementType componentType;  
    ULONG32 firstElementOffset;  
    ULONG32 elementSize;  
    ULONG32 countOffset;
    ULONG32 rankSize;
    ULONG32 numRanks;
    ULONG32 rankOffset;
} COR_ARRAY_LAYOUT;  
```  
  
## <a name="members"></a>Elementy członkowskie  
  
|Członek|Opis|  
|------------|-----------------|  
|`componentID`|Identyfikator typu obiektów, które zawiera tablica.|  
|`componentType`|Wartość wyliczenia CorElementType —, która wskazuje, czy składnik jest odwołaniem do wyrzucania elementów bezużytecznych, klasą wartości lub elementem pierwotnym.|  
|`firstElementOffset`|Przesunięcie do pierwszego elementu w tablicy.|  
|`elementSize`|Rozmiar każdego elementu.|  
|`countOffset`|Przesunięcie do liczby elementów w tablicy.|  
|`rankSize`|Rozmiar rangi w bajtach.|  
|`numRanks`|Liczba rangi w tablicy.|  
|`rankOffset`|Przesunięcie, od którego są uruchamiane Range.|  
  
## <a name="remarks"></a>Uwagi  

 `rankSize`Pole określa rozmiar rangi w tablicy wielowymiarowej. Jest to dokładne dla tablic jednowymiarowych.  
  
 Wartość jest równa `numRanks` 1 dla jednowymiarowej tablicy i `N` dla wielowymiarowej tablicy `N` wymiarów.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Struktury debugowania](debugging-structures.md)
- [Debugowanie](index.md)
