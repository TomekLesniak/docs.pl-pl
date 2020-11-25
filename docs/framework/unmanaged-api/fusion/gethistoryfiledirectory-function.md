---
title: GetHistoryFileDirectory — Funkcja
ms.date: 03/30/2017
api_name:
- GetHistoryFileDirectory
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- GetHistoryFileDirectory
helpviewer_keywords:
- GetHistoryFileDirectory function [.NET Framework fusion]
ms.assetid: 93232222-926e-42ac-b85d-8a6d33977672
topic_type:
- apiref
ms.openlocfilehash: 484adf288356b9955fe0cac0bb30002ec1f012d3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724441"
---
# <a name="gethistoryfiledirectory-function"></a>GetHistoryFileDirectory — Funkcja

Pobiera ścieżkę katalogu historii aplikacji.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetHistoryFileDirectory (  
    [in]      LPWSTR      wzDir,  
    [in,out]  LPCWSTR  *pdwsize,  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `wzDir`  
 określoną Bufor służący do przechowywania ścieżki do katalogu historii aplikacji.  
  
 `pdwSize`  
 [in. out] Długość buforu.  
  
## <a name="return-value"></a>Wartość zwracana  

 Ta metoda zwraca kody błędów standardowego modelu COM, jak zdefiniowano w pliku WinError. h oprócz następujących wartości.  
  
|Kod powrotu|Opis|  
|-----------------|-----------------|  
|S_OK|Metoda została ukończona pomyślnie.|  
|E_INVALIDARG|`wzDir` lub `pdwSize` ma wartość null lub ciąg wersji jest niepoprawny.|  
  
## <a name="remarks"></a>Uwagi  

 Po pomyślnym zakończeniu `pdwSize` argument ma ustawioną długość ciągu ścieżki.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Fusion. h  
  
 **Biblioteka:** Fusion.dll i Mscorwks.dll. Użyj Fusion.dll zamiast Mscorwks.dll, aby upewnić się, że docelowa jest poprawna wersja .NET Framework.  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [CreateHistoryReader — Funkcja](createhistoryreader-function.md)
- [NukeDownloadedCache — Funkcja](nukedownloadedcache-function.md)
- [Łączenie statycznych funkcji globalnych](fusion-global-static-functions.md)
