---
title: GetObjectText — funkcja (niezarządzana dokumentacja interfejsu API)
description: Funkcja GetObjectText zwraca renderowanie tekstu obiektu w składni MOF.
ms.date: 11/06/2017
api_name:
- GetObjectText
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetObjectText
helpviewer_keywords:
- GetObjectText function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 6ad2b29202222d594cc7976a13929002164314a7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718374"
---
# <a name="getobjecttext-function"></a>GetObjectText, funkcja

Zwraca renderowanie tekstowe obiektu w składni Managed Object Format (MOF).

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetObjectText (
   [in] int                vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LONG                lFlags,
   [out] BSTR*              pstrObjectText
);
```  

## <a name="parameters"></a>Parametry

`vFunc`  
podczas Ten parametr jest nieużywany.

`ptr`  
podczas Wskaźnik do wystąpienia [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .

`lFlags`  
podczas Zwykle 0. Jeśli `WBEM_FLAG_NO_FLAVORS` określono (lub 0x1), kwalifikatory są uwzględniane bez informacji o propagacji lub wersji.

`pstrObjectText` określoną Wskaźnik do `null` wpisu na wejściu. W przypadku powrotu, nowo przydzielony `BSTR` , który zawiera składnię MOF, renderowanie obiektu.  

## <a name="return-value"></a>Wartość zwracana

Następujące wartości zwracane przez tę funkcję są zdefiniowane w pliku nagłówkowym *WbemCli. h* lub można je definiować jako stałe w kodzie:

|Stała  |Wartość  |Opis  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | Wystąpił błąd ogólny. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Parametr jest nieprawidłowy. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Za mało dostępnej pamięci, aby ukończyć tę operację. |
|`WBEM_S_NO_ERROR` | 0 | Wywołanie funkcji zakończyło się pomyślnie.  |
  
## <a name="remarks"></a>Uwagi

Ta funkcja otacza wywołanie metody [IWbemClassObject:: GetObjectText](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getobjecttext) .

Zwrócony tekst MOF nie zawiera wszystkich informacji o obiekcie, ale tylko wystarczające informacje dla kompilatora MOF, aby można było odtworzyć oryginalny obiekt. Na przykład nie są uwzględniane żadne kwalifikatory propagowane ani właściwości klasy nadrzędnej.

Następujący algorytm służy do rekonstruowania tekstu parametrów metody:

1. Parametry są ponownie sekwencjonowane w kolejności ich wartości identyfikatorów.
1. Parametry, które są określone jako `[in]` i `[out]` są łączone w jeden parametr.

`pstrObjectText` musi być wskaźnikiem do elementu, `null` gdy funkcja jest wywoływana; nie może wskazywać ciągu, który jest prawidłowy przed wywołaniem metody, ponieważ wskaźnik nie zostanie cofnięty.

## <a name="requirements"></a>Wymagania  

**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** WMINet_Utils. idl  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Zobacz także

- [WMI i liczniki wydajności (niezarządzana dokumentacja interfejsu API)](index.md)
