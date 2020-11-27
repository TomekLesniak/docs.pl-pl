---
title: 'IXCLRDataProcess:: GetRuntimeNameByAddress, Metoda'
ms.date: 4/27/2020
api.name:
- IXCLRDataProcess::GetRuntimeNameByAddress Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::GetRuntimeNameByAddress Method
helpviewer.keywords:
- IXCLRDataProcess::GetRuntimeNameByAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: tommcdon
ms.author: tommcdon
ms.openlocfilehash: 6648bdafe6e5cdd402bcfa02a148c57f0f1e209e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96270492"
---
# <a name="ixclrdataprocessgetruntimenamebyaddress-method"></a>IXCLRDataProcess:: GetRuntimeNameByAddress, Metoda

Pobiera nazwę dla danego adresu.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Składnia

```cpp
HRESULT GetRuntimeNameByAddress(
    [in] CLRDATA_ADDRESS address,
    [in] ULONG32 flags,
    [in] ULONG32 bufLen,
    [out] ULONG32 *nameLen,
    [out, size_is(bufLen)] WCHAR nameBuf[],
    [out] CLRDATA_ADDRESS* displacement
);
```

## <a name="parameters"></a>Parametry

`address`\
podczas `CLRDATA_ADDRESS` Wartość, która reprezentuje adres kodu.

`flags`\
podczas Ustaw wartość "0".

`bufLen`\
podczas Długość buforu.

`namLen`\
określoną Wskaźnik do liczby zwracanych znaków.

`namBuf`\
[out, size_is ( `bufLen` )] wejściowy bufor o długości `bufLen` , który przechowuje nazwę środowiska uruchomieniowego.

`displacement`\
określoną `CLRDATA_ADDRESS` Wskaźnik do przesunięcia kodu zwróconego symbolu.

## <a name="remarks"></a>Uwagi

Podana metoda jest częścią `IXCLRDataProcess` interfejsu i odpowiada szesnastemu gnieździe tabeli metody wirtualnej.

> [!NOTE]
> Jeśli bufor nie jest wystarczająco duży dla nazwy, ta metoda zwraca `S_FALSE` i ustawia `nameLen` wymaganą długość buforu.

## <a name="requirements"></a>Wymagania

**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md)\
**Nagłówek:** Dawaj
**Biblioteka:** Dawaj
**.NET Framework wersje:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]

## <a name="see-also"></a>Zobacz też

- [Debugowanie](index.md)
- [IXCLRDataProcess, interfejs](ixclrdataprocess-interface.md)
