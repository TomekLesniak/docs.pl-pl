---
title: GetCORVersion — Funkcja
ms.date: 03/30/2017
api_name:
- GetCORVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetCORVersion
helpviewer_keywords:
- GetCORVersion function [.NET Framework hosting]
ms.assetid: 2f09cd37-bf3a-4cc5-87b0-adc42a7eed31
topic_type:
- apiref
ms.openlocfilehash: e7ef3f300c8cfa0c275d15913e171abe09385eea
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95681213"
---
# <a name="getcorversion-function"></a>GetCORVersion — Funkcja

Zwraca numer wersji środowiska uruchomieniowego języka wspólnego (CLR), który jest uruchomiony w bieżącym procesie.  
  
 Ta funkcja jest przestarzała w .NET Framework 4.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetCORVersion (  
    [in] LPWSTR  pbuffer,  
    [in]  DWORD   cchBuffer,
    [out] DWORD*  dwlength  
);
```  
  
## <a name="parameters"></a>Parametry  

 `pbuffer`  
 Wskaźnik do buforu, w którym środowisko CLR zwraca ciąg określający wersję środowiska uruchomieniowego, która jest aktualnie załadowana do procesu. Zwrócony ciąg przyjmuje ten sam formularz, co ciągi przesłane do [CorBindToRuntimeEx](corbindtoruntimeex-function.md), na przykład "v 1.0.1216". Jeśli środowisko uruchomieniowe nie zostało jeszcze załadowane do procesu, funkcja zwróci odpowiednie informacje dotyczące katalogu dla najnowszej wersji środowiska uruchomieniowego zainstalowanej na komputerze.  
  
 `cchBuffer`  
 Liczba znaków `WCHAR` , które mogą być przechowywane w `pbuffer` .  
  
 `dwLength`  
 Wskaźnik do liczby znaków faktycznie zwracanych przez `pbuffer` . Jeśli `pbuffer` jest wskaźnikiem typu null, środowisko uruchomieniowe zwraca E_POINTER. Jeśli liczba znaków jest większa niż długość `pbuffer` , środowisko uruchomieniowe zwraca ERROR_INSUFFICIENT_BUFFER.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE. h  
  
 **Biblioteka:** MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Przestarzałe funkcje hostingu środowiska CLR](deprecated-clr-hosting-functions.md)
