---
title: GetTypeLibInfo — Funkcja
ms.date: 03/30/2017
api_name:
- GetTypeLibInfo
api_location:
- TlbRef.dll
api_type:
- DLLExport
f1_keywords:
- GetTypeLibInfo
helpviewer_keywords:
- GetTypeLibInfo function [.NET Framework]
ms.assetid: a1c4d165-9bdc-4ca8-940e-292d4ffcc338
topic_type:
- apiref
ms.openlocfilehash: e9f6ae9a0fcd6651395c54c2e44973e53668c1ac
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708325"
---
# <a name="gettypelibinfo-function"></a>GetTypeLibInfo — Funkcja

Zwraca informacje o określonej bibliotece typów, badając jej strukturę [TLIBATTR](/windows/win32/api/oaidl/ns-oaidl-tlibattr) .  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetTypeLibInfo(  
    [in]   LPWSTR     szFile,  
    [out]  GUID      *pTypeLibID,  
    [out]  LCID      *pTypeLibLCID,  
    [out]  SYSKIND   *pTypeLibPlatform,  
    [out]  USHORT    *pTypeLibMajorVer,  
    [out]  USHORT    *pTypeLibMinorVer  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `szFile`  
 podczas Nazwa pliku biblioteki typów.  
  
 `pTypeLibID`  
 określoną Identyfikator GUID biblioteki typów.  
  
 `pTypeLibLCID`  
 określoną Identyfikator lokalizacji biblioteki typów.  
  
 `pTypeLibPlatform`  
 określoną Flaga [SYSKIND](/windows/win32/api/oaidl/ne-oaidl-syskind) , która identyfikuje docelowy system operacyjny dla biblioteki typów. Typowe wartości to SYS_WIN32 i SYS_WIN64.  
  
 `pTypeLibMajorVer`  
 określoną Numer wersji głównej biblioteki typów. Na przykład w przypadku wersji *x. y* główny numer wersji to *x*.  
  
 `pTypeLibMinorVer`  
 określoną Numer wersji pomocniczej biblioteki typów. Na przykład w przypadku wersji *x. y* pomocniczy numer wersji to *y*.  
  
## <a name="remarks"></a>Uwagi  

 `GetTypeLibInfo`Funkcja jest wywoływana przez [Tlbexp.exe (Eksporter biblioteki typów)](../../tools/tlbexp-exe-type-library-exporter.md). To narzędzie generuje bibliotekę typów, która opisuje typy w zestawie środowiska uruchomieniowego języka wspólnego (CLR).  
  
 Jeśli dowolny parametr ma wartość null, funkcja zwraca wartość `HRESULT` `E_POINTER` . W przeciwnym razie zwraca `S_OK` .  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** TlbRef. h  
  
 **Biblioteka:** TlbRef. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Tlbexp — funkcje pomocy](index.md)
- [LoadTypeLibEx, funkcja](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
