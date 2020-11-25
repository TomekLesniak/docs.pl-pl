---
title: Funkcja QualifierSet_Next (niezarządzana dokumentacja interfejsu API)
description: Funkcja QualifierSet_Next pobiera następny kwalifikator w wyliczeniu.
ms.date: 11/06/2017
api_name:
- QualifierSet_Next
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Next
helpviewer_keywords:
- QualifierSet_Next function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 54d79a3dc081e9cdcb42153b6f7aa457557e3399
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721130"
---
# <a name="qualifierset_next-function"></a>Funkcja QualifierSet_Next

Pobiera następny kwalifikator w wyliczeniu, który rozpoczął wywoływanie funkcji [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) .

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT QualifierSet_Next (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LONG                 lFlags,
   [out] BSTR*               pstrName,
   [out] VARIANT*            pVal,
   [out] LONG*               plFlavor
);
```  

## <a name="parameters"></a>Parametry

`vFunc` podczas Ten parametr jest nieużywany.

`ptr` podczas Wskaźnik do wystąpienia [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) .

`lFlags` podczas Rezerwacj. Ten parametr musi być równy 0.

`pstrName` określoną Nazwa kwalifikatora. Jeśli `null` , ten parametr jest ignorowany; w przeciwnym razie `pstrName` nie powinien wskazywać prawidłowego `BSTR` lub wycieku pamięci. Jeśli wartość nie jest równa null, funkcja zawsze przydziela nowe, `BSTR` gdy zwraca `WBEM_S_NO_ERROR` .

`pVal` określoną Po pomyślnym wykonaniu tej operacji wartość kwalifikatora. Jeśli funkcja się nie powiedzie, `VARIANT` wskazywane przez `pVal` nie jest modyfikowane. Jeśli ten parametr ma wartość `null` , parametr jest ignorowany.

`plFlavor` określoną Wskaźnik do LONG, który odbiera wersję kwalifikatora. Jeśli informacje o wersji nie są potrzebne, ten parametr może być `null` .

## <a name="return-value"></a>Wartość zwracana

Następujące wartości zwracane przez tę funkcję są zdefiniowane w pliku nagłówkowym *WbemCli. h* lub można je definiować jako stałe w kodzie:

|Stała  |Wartość  |Opis  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Parametr jest nieprawidłowy. |
|`WBEM_E_UNEXPECTED` | 0x8004101d | Obiekt wywołujący nie wywołał [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md). |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Za mało dostępnej pamięci, aby rozpocząć nowe Wyliczenie. |
| `WBEM_S_NO_MORE_DATA` | 0x40005 | W wyliczeniu nie ma więcej kwalifikatorów. |
|`WBEM_S_NO_ERROR` | 0 | Wywołanie funkcji zakończyło się pomyślnie.  |
  
## <a name="remarks"></a>Uwagi

Ta funkcja zawija wywołanie do metody [IWbemQualifierSet:: Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-next) .

Wywołaj `QualifierSet_Next` funkcję wielokrotnie, aby wyliczyć wszystkie kwalifikatory do momentu zwrócenia funkcji `WBEM_S_NO_MORE_DATA` . Aby przerwać wyliczanie, wywołaj funkcję [QualifierSet_EndEnumeration](qualifierset-endenumeration.md) .

Kolejność kwalifikatorów zwróconych podczas wyliczania jest niezdefiniowana.

## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** WMINet_Utils. idl  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Zobacz także

- [WMI i liczniki wydajności (niezarządzana dokumentacja interfejsu API)](index.md)
