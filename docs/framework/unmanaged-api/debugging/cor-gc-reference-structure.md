---
title: COR_GC_REFERENCE — Struktura
ms.date: 03/30/2017
api_name:
- COR_GC_REFERENCE
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_GC_REFERENCE
helpviewer_keywords:
- COR_GC_REFERENCE structure [.NET Framework debugging]
ms.assetid: 162e8179-0cd4-4110-8f06-5f387698bd62
topic_type:
- apiref
ms.openlocfilehash: bb4a8f7ff3ee54474804e3e5620dcce7c9f79fb5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726616"
---
# <a name="cor_gc_reference-structure"></a>COR_GC_REFERENCE — Struktura

Zawiera informacje o obiekcie, który ma zostać pobrany do pamięci podręcznej.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
typedef struct _COR_GC_REFERENCE {  
    ICorDebugAppDomain *domain;
    ICorDebugValue *location;  
    CorGCReferenceType type;  
    UINT64 extraData;  
} COR_GC_REFERENCE;  
```  
  
## <a name="members"></a>Elementy członkowskie  
  
|Członek|Opis|  
|------------|-----------------|  
|`domain`|Wskaźnik do domeny aplikacji, do której należy dojście lub obiekt. Jego wartość może być równa `null` .|  
|`location`|Interfejs ICorDebugValue lub ICorDebugReferenceValue, który odnosi się do obiektu, który ma zostać pobrany jako bezużyteczny.|  
|`type`|Wartość wyliczenia [CorGCReferenceType](corgcreferencetype-enumeration.md) , która wskazuje, skąd pochodzi element główny. Aby uzyskać więcej informacji, zobacz sekcję: Uwagi.|  
|`extraData`|Dodatkowe dane dotyczące obiektu, który ma zostać pobrany do pamięci. Te informacje są zależne od źródła obiektu, jak wskazano w `type` polu. Aby uzyskać więcej informacji, zobacz sekcję: Uwagi.|  
  
## <a name="remarks"></a>Uwagi  

 `type`Pole to [CorGCReferenceType](corgcreferencetype-enumeration.md) wartość wyliczenia, która wskazuje, skąd pochodzi odwołanie. Określona `COR_GC_REFERENCE` wartość może odzwierciedlać dowolny z następujących rodzajów obiektów zarządzanych:  
  
- Obiekty ze wszystkich stosów zarządzanych ( `CorGCReferenceType.CorReferenceStack` ). Obejmuje to dynamiczne odwołania w kodzie zarządzanym, a także obiekty utworzone przez środowisko uruchomieniowe języka wspólnego.  
  
- Obiekty z tabeli uchwytów ( `CorGCReferenceType.CorHandle*` ). Obejmuje to ścisłe odwołania ( `HNDTYPE_STRONG` i `HNDTYPE_REFCOUNT` ) oraz zmienne statyczne w module.  
  
- Obiekty z kolejki finalizatora ( `CorGCReferenceType.CorReferenceFinalizer` ). Obiekty główne kolejki finalizatora do momentu uruchomienia finalizatora.  
  
 `extraData`Pole zawiera dodatkowe dane w zależności od źródła (lub typu) odwołania. Możliwe wartości:  
  
- `DependentSource`. Jeśli `type` jest `CorGCREferenceType.CorHandleStrongDependent` , to pole jest obiektem, który, jeśli działa, jest katalogiem głównym obiektu, który ma zostać odrzucony `COR_GC_REFERENCE.Location` .  
  
- `RefCount`. Jeśli `type` jest `CorGCREferenceType.CorHandleStrongRefCount` , to pole jest liczbą odwołań do dojścia.  
  
- `Size`. Jeśli `type` jest `CorGCREferenceType.CorHandleStrongSizedByref` , to pole jest ostatnim rozmiarem drzewa obiektów, dla którego Moduł wyrzucania elementów bezużytecznych oblicza elementy główne obiektu. Należy zauważyć, że to obliczenie nie jest zawsze aktualne.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Struktury debugowania](debugging-structures.md)
- [Debugowanie](index.md)
