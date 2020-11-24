---
title: 'ICorDebugVariableHomeEnum:: Next — Metoda'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHomeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHomeEnum::Next
helpviewer_keywords:
- ICorDebugVariableHomeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugVariableHomeEnum interface [.NET Framework debugging]
ms.assetid: eb9ea96c-5b58-4655-8104-094fc8b393b8
topic_type:
- apiref
ms.openlocfilehash: 4ef4ed19033b0857b9970ee8103bbd92f383898c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679536"
---
# <a name="icordebugvariablehomeenumnext-method"></a>ICorDebugVariableHomeEnum:: Next — Metoda

Pobiera określoną liczbę wystąpień [ICorDebugVariableHome](icordebugvariablehome-interface.md) , które zawierają informacje o zmiennych lokalnych i argumentach w funkcji.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)] ICorDebugVariableHome *homes[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `celt`  
 podczas Liczba obiektów do pobrania.  
  
 `homes`  
 Tablica wskaźników, z których każdy wskazuje obiekt [ICorDebugVariableHome](icordebugvariablehome-interface.md) , który zawiera informacje na temat zmiennej lokalnej lub argumentu funkcji.  
  
 `pceltFetched`  
 określoną Liczba wystąpień faktycznie zwracanych w obiektach.  
  
## <a name="return-value"></a>Wartość zwracana  

 Metoda zwraca następujące wartości.  
  
|HRESULT|Opis|  
|-------------|-----------------|  
|`S_OK`|Metoda została ukończona pomyślnie.|  
|`S_FALSE`|Rzeczywista liczba pobranych wystąpień, odzwierciedlona w `pceltFetched` , jest mniejsza niż liczba żądanych wystąpień.|  
  
## <a name="remarks"></a>Uwagi  

 Metoda [ICorDebugVariableHomeEnum:: Next](icordebugvariablehomeenum-next-method.md) pobiera maksymalnie  `celt` obiektów, rozpoczynając od bieżącego położenia modułu wyliczającego. Gdy metoda zwraca, `pceltFetched` zawiera rzeczywistą liczbę pobranych obiektów.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICorDebugVariableHomeEnum, interfejs](icordebugvariablehomeenum-interface.md)
- [ICorDebugVariableHome, interfejs](icordebugvariablehome-interface.md)
