---
title: SpawnDerivedClass — funkcja (niezarządzana dokumentacja interfejsu API)
description: Funkcja SpawnDerivedClass tworzy nowy obiekt, który pochodzi od obiektu.
ms.date: 11/06/2017
api_name:
- SpawnDerivedClass
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- SpawnDerivedClass
helpviewer_keywords:
- SpawnDerivedClass function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 8020dd851b6773e6c76c53892c4b2bc21e4261bb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716515"
---
# <a name="spawnderivedclass-function"></a>SpawnDerivedClass, funkcja

Tworzy nowo pochodny obiekt klasy na podstawie określonego obiektu.
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT SpawnDerivedClass (
   [in] int                  vFunc,
   [in] IWbemClassObject*    ptr,
   [in] LONG                 lFlags,
   [out] IWbemClassObject**  ppNewClass);
```  

## <a name="parameters"></a>Parametry

`vFunc`  
podczas Ten parametr jest nieużywany.

`ptr`  
podczas Wskaźnik do wystąpienia [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .

`lFlags`  
podczas Rezerwacj. Ten parametr musi być równy 0.

`ppNewClass`  
określoną Odbiera wskaźnik do nowego obiektu definicji klasy. Jeśli wystąpi błąd, nowy obiekt nie jest zwracany i `ppNewClass` pozostaje niemodyfikowany. Wartość nie może być `null` .

## <a name="return-value"></a>Wartość zwracana

Następujące wartości zwracane przez tę funkcję są zdefiniowane w pliku nagłówkowym *WbemCli. h* lub można je definiować jako stałe w kodzie:

|Stała  |Wartość  |Opis  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | Wystąpił błąd ogólny. |
| `WBEM_E_INVALID_OPERATION` | 0x80041016 | Zażądano nieprawidłowej operacji, takiej jak duplikowanie klasy z wystąpienia. |
| `WBEM_E_INCOMPLETE_CLASS` | Klasa źródłowa nie została całkowicie zdefiniowana lub zarejestrowana w usłudze zarządzania systemem Windows, więc nowa klasa pochodna jest niedozwolona. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Za mało dostępnej pamięci, aby ukończyć tę operację. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | `ppNewClass` to `null`. |
| `WBEM_S_NO_ERROR` | 0 | Wywołanie funkcji zakończyło się pomyślnie.  |
  
## <a name="remarks"></a>Uwagi

Ta funkcja otacza wywołanie metody [IWbemClassObject:: SpawnDerivedClass](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) .

`ptr` musi być definicją klasy, która jest klasą nadrzędną podanego obiektu. Zwrócony obiekt zostanie podklasą bieżącego obiektu.

Nowy obiekt zwrócony w programie `ppNewClass` automatycznie zostanie podklasą bieżącego obiektu. Tego zachowania nie można zastąpić. Nie istnieje inna metoda, za pomocą której można tworzyć podklasy (klasy pochodne).

## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** WMINet_Utils. idl  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Zobacz także

- [WMI i liczniki wydajności (niezarządzana dokumentacja interfejsu API)](index.md)
