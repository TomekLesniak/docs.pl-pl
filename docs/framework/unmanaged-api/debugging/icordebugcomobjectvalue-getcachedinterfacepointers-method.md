---
title: ICorDebugComObjectValue::GetCachedInterfacePointers — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugComObjectValue::GetCachedInterfacePointers
api_location:
- mscordbi.dll
f1_keywords:
- ICorDebugComObjectValue::GetCachedInterfacePointers
helpviewer_keywords:
- ICorDebugComObjectValue::GetCachedInterfacePointers method [.NET Framework debugging]
- GetCachedInterfacePointers method, ICorDebugComObjectValue interface [.NET Framework debugging]
ms.assetid: 08dbd558-bd39-4263-94c2-71e70687aaf0
topic_type:
- apiref
ms.openlocfilehash: c3120a0dd859f581e6356fc260043cb83250ae9e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724835"
---
# <a name="icordebugcomobjectvaluegetcachedinterfacepointers-method"></a>ICorDebugComObjectValue::GetCachedInterfacePointers — Metoda

Pobiera pierwotne wskaźniki interfejsu w pamięci podręcznej dla bieżącej otoki (RCW) w czasie wykonywania.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetCachedInterfacePointers(  
    [in] BOOL bIInspectableOnly,  
    [in] ULONG32 celt,  
    [out] ULONG32 *pceltFetched,  
    [out, size_is(celt), length_is(*pceltFetched) CORDB_ADDRESS *ptrs);  
```  
  
## <a name="parameters"></a>Parametry  

 `bIInspectableOnly`  
 podczas Wartość wskazująca, czy metoda zwróci tylko środowisko wykonawcze systemu Windows interfejsy ( `IInspectable` interfejsy) czy wszystkie interfejsy com, które są buforowane przez otokę wywoływaną przez środowisko uruchomieniowe (otoka).  
  
 `celt`  
 podczas Liczba obiektów, których adresy mają zostać pobrane.  
  
 `pceltFetched`  
 określoną Wskaźnik do liczby `CORDB_ADDRESS` wartości faktycznie zwracanych w `ptrs` .  
  
 `ptrs`  
 Wskaźnik na adres początkowy tablicy `CORDB_ADDRESS` wartości zawierającej adresy buforowanych obiektów interfejsu.  
  
## <a name="remarks"></a>Uwagi  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICorDebugComObjectValue — Interfejs](icordebugcomobjectvalue-interface.md)
- [Debugowanie — Interfejsy](debugging-interfaces.md)
