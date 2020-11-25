---
title: ICorDebugGuidToTypeEnum::Next — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugGuidToTypeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGuidToTypeEnum::Next
helpviewer_keywords:
- ICorDebugGuidToTypeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugGuidToTypeEnum interface [.NET Framework debugging]
ms.assetid: c9937666-8e18-484d-9fe0-b9ac95199530
topic_type:
- apiref
ms.openlocfilehash: 68f548705213da7d715ae569116abae0cd24129d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705660"
---
# <a name="icordebugguidtotypeenumnext-method"></a>ICorDebugGuidToTypeEnum::Next — Metoda

Pobiera określoną liczbę wystąpień [CorDebugGuidToTypeMapping —](cordebugguidtotypemapping-structure.md) , które MAPUJĄ identyfikatory GUID na informacje o typie.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched] CorDebugGuidToTypeMapping values[  ],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `celt`  
 podczas Liczba obiektów mapowania GUID-to-Type do pobrania.  
  
 `values`  
 określoną Tablica wskaźników, z których każdy wskazuje obiekt [CorDebugGuidToTypeMapping —](cordebugguidtotypemapping-structure.md) , który MAPUJE identyfikator GUID środowisko wykonawcze systemu Windows do odpowiadającego mu obiektu ICorDebugType.  
  
 `pceltFetched`  
 określoną Wskaźnik do liczby obiektów [CorDebugGuidToTypeMapping —](cordebugguidtotypemapping-structure.md) faktycznie zwróconych w elemencie `values` .  
  
## <a name="remarks"></a>Uwagi  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** środowisko wykonawcze systemu Windows  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICorDebugGuidToTypeEnum — Interfejs](icordebugguidtotypeenum-interface.md)
- [Debugowanie — Interfejsy](debugging-interfaces.md)
