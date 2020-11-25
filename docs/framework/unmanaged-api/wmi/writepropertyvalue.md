---
title: WritePropertyValue — funkcja (niezarządzana dokumentacja interfejsu API)
description: Funkcja WritePropertyValue zapisuje bajty do właściwości.
ms.date: 11/06/2017
api_name:
- WritePropertyValue
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- WritePropertyValue
helpviewer_keywords:
- WritePropertyValue function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: e225516b06c477dc1a24cf721bc3e1ade9076b75
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729411"
---
# <a name="writepropertyvalue-function"></a>WritePropertyValue, funkcja

Zapisuje określoną liczbę bajtów do właściwości identyfikowanej przez uchwyt właściwości.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT WritePropertyValue (
   [in] int                  vFunc,
   [in] IWbemObjectAccess*   ptr,
   [in] long                 lHandle,
   [in] long                 lNumBytes,
   [in] byte*                aData
);
```  

## <a name="parameters"></a>Parametry

`vFunc`  
podczas Ten parametr jest nieużywany.

`ptr`  
podczas Wskaźnik do wystąpienia [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) .

`lHandle`  
podczas Liczba całkowita, która zawiera uchwyt, który identyfikuje tę właściwość. Dojście można pobrać, wywołując funkcję [GetPropertyHandle](getpropertyhandle.md) .

`lNumBytes`  
podczas Liczba bajtów zapisywanych w właściwości. Zobacz sekcję [uwagi](#remarks) , aby uzyskać więcej informacji.

`pHandle` określoną Wskaźnik do tablicy bajtów zawierającej dane.

## <a name="return-value"></a>Wartość zwracana

Następujące wartości zwracane przez tę funkcję są zdefiniowane w pliku nagłówkowym *WbemCli. h* lub można je definiować jako stałe w kodzie:

|Stała  |Wartość  |Opis  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Parametr jest nieprawidłowy. |
|`WBEM_E_TYPE_MISMATCH` | 0x80041005 | Wystąpił niezgodność typów. |
|`WBEM_S_NO_ERROR` | 0 | Wywołanie funkcji zakończyło się pomyślnie.  |
  
## <a name="remarks"></a>Uwagi

Ta funkcja otacza wywołanie metody [IWbemClassObject:: WritePropertyValue](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-writepropertyvalue) .

Użyj tej funkcji, aby ustawić ciąg i wszystkie inne dane, które nie są `DWORD` `QWORD` danymi.

W przypadku wartości właściwości, które nie są ciągami, `lNumBytes` musi być poprawnym rozmiarem danych określonego typu właściwości. W przypadku wartości właściwości ciągu, `lNumBytes` musi być długością określonego ciągu w bajtach, a sam ciąg musi mieć długość w bajtach i mieć znak zakończenia o wartości null.

## <a name="requirements"></a>Wymagania  

**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** WMINet_Utils. idl  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Zobacz także

- [WMI i liczniki wydajności (niezarządzana dokumentacja interfejsu API)](index.md)
