---
title: ICorDebugHeapEnum::Next — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugHeapEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapEnum::Next
helpviewer_keywords:
- ICorDebugHeapEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugHeapEnum interface [.NET Framework debugging]
ms.assetid: 2221fd06-9e27-4113-972e-2530db8c3594
topic_type:
- apiref
ms.openlocfilehash: 320b3ca55a60ec7751c88a246ab6ee90b6b6c4cc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724354"
---
# <a name="icordebugheapenumnext-method"></a>ICorDebugHeapEnum::Next — Metoda

Pobiera określoną liczbę wystąpień [COR_HEAPOBJECT](cor-heapobject-structure.md) , które zawierają informacje o obiektach na zarządzanym stosie.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_HEAPOBJECT  objects[],
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a>Parametry  

 celt  
 podczas Liczba obiektów do pobrania.  
  
  — obiekty  
 określoną Tablica wskaźników, z których każdy wskazuje obiekt [COR_HEAPOBJECT](cor-heapobject-structure.md) , który zawiera informacje na temat obiektu na zarządzanym stosie.  
  
 pceltFetched  
 określoną Wskaźnik do liczby obiektów [COR_HEAPOBJECT](cor-heapobject-structure.md) faktycznie zwróconych w `objects` . Ta wartość może być równa `null` `celt` 1.  
  
## <a name="remarks"></a>Uwagi  

 `COR_HEAPOBJECT.type`To pole jest identyfikatorem zagnieżdżonego, odwołującego się interfejsu com. To odwołanie musi zostać wydane przez wywołującego `ICorDebugHeapEnum::Next` .  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICorDebugHeapEnum — Interfejs](icordebugheapenum-interface.md)
- [Debugowanie — Interfejsy](debugging-interfaces.md)
