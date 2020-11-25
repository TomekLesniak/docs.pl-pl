---
title: PutMethod — funkcja (niezarządzana dokumentacja interfejsu API)
description: Funkcja PutMethod tworzy metodę.
ms.date: 11/06/2017
api_name:
- PutMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- PutMethod
helpviewer_keywords:
- PutMethod function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 8edbb8074573b98c017f98197d370c2ad37db80c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726759"
---
# <a name="putmethod-function"></a>PutMethod, funkcja

Tworzy metodę.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT PutMethod (
   [in] int                vFunc,
   [in] IWbemClassObject*  ptr,
   [in] LPCWSTR            wszName,
   [in] LONG               lFlags,
   [in] IWbemClassObject*  pInSignature,
   [in] IWbemClassObject*  pOutSignature
);
```  

## <a name="parameters"></a>Parametry

`vFunc`  
podczas Ten parametr jest nieużywany.

`ptr`  
podczas Wskaźnik do wystąpienia [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .

`wszName`  
podczas Nazwa metody do utworzenia.

`lFlags`  
podczas Rezerwacj. Ten parametr musi być równy 0.

`pSignatureIn`  
podczas Wskaźnik do kopii [klasy systemu __Parameters](/windows/desktop/WmiSdk/--parameters) , która zawiera `in` parametry dla metody. Ten parametr jest ignorowany, jeśli jest ustawiony na `null` .  

`pSignatureOut`  
podczas  Wskaźnik do kopii [klasy systemu __Parameters](/windows/desktop/WmiSdk/--parameters) , która zawiera `out` parametry dla metody. Ten parametr jest ignorowany, jeśli jest ustawiony na `null` .

## <a name="return-value"></a>Wartość zwracana

Następujące wartości zwracane przez tę funkcję są zdefiniowane w pliku nagłówkowym *WbemCli. h* lub można je definiować jako stałe w kodzie:

|Stała  |Wartość  |Opis  |
|---------|---------|---------|
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Co najmniej jeden parametr jest nieprawidłowy. |
| `WBEM_E_INVALID_DUPLICATE_PARAMETER` | 0x80041043 | `[in, out]`Parametr metody określony w obiektach *PInSignature* i *pOutSignature* ma różne kwalifikatory.
| `WBEM_E_MISSING_PARAMETER_ID` | 0x80041036 | Parametr metody nie zawiera specyfikacji kwalifikatora **ID** . |
| `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS` | 0x80041038 | Seria identyfikatorów, która jest przypisana do parametrów metody, nie jest powtarzana lub nie zaczyna się od 0. |
| `WBEM_E_PARAMETER_ID_ON_RETVAL` | 0x80041039 | Wartość zwracana dla metody ma kwalifikator **identyfikatora** . |
| `WBEM_E_PROPAGATED_METHOD` | 0x80041034 | Podjęto próbę ponownego użycia istniejącej nazwy metody z klasy nadrzędnej i sygnatury są niezgodne. |
| `WBEM_S_NO_ERROR` | 0 | Wywołanie funkcji zakończyło się pomyślnie. |
  
## <a name="remarks"></a>Uwagi

Ta funkcja otacza wywołanie metody [IWbemClassObject::P utmethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) .

To wywołanie metody jest obsługiwane tylko wtedy `ptr` , gdy jest definicją klasy CIM. Manipulowanie metodami nie jest dostępne ze wskaźników [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) , które wskazują wystąpienia modelu wspólnych informacji.

Użytkownicy nie mogą tworzyć metod o nazwach zaczynających się lub kończących znakiem podkreślenia. Jest to zarezerwowane dla klas systemowych i właściwości.

W przypadku metody `in` `out` Parametry i są opisane jako właściwości w obiektach [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .

`[in/out]`Parametr można zdefiniować przez dodanie tej samej właściwości do obu obiektów wskazywanych przez `pInSignature` `pOutSignature` Parametry i. W takim przypadku właściwości mają tę samą wartość kwalifikatora **ID** .

Każda właściwość w obiekcie klasy [__Parameters](/windows/desktop/WmiSdk/--parameters) innym niż `ReturnValue` musi mieć kwalifikator **identyfikatora** , wartość liczbową zero, która identyfikuje kolejność wyświetlania parametrów. Żadne dwa parametry nie mogą mieć tej samej wartości **identyfikatora** i nie można pominąć wartości **identyfikatora** . Jeśli wystąpi dowolny warunek, `PutMethod` Funkcja zwraca `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS` .

## <a name="example"></a>Przykład

Aby zapoznać się z przykładem, zobacz [IWbemClassObject::P utmethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) .

## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** WMINet_Utils. idl  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Zobacz także

- [WMI i liczniki wydajności (niezarządzana dokumentacja interfejsu API)](index.md)
