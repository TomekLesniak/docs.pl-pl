---
title: LoadStringRCEx — Funkcja
ms.date: 03/30/2017
api_name:
- LoadStringRCEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- LoadStringRCEx
helpviewer_keywords:
- LoadStringRCEx function [.NET Framework hosting]
ms.assetid: bc789636-ca14-4f07-8f77-9305874d7495
topic_type:
- apiref
ms.openlocfilehash: 1aa5c9f5dd7dd63e69c2eed1f6dd8ad6f007f01f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727539"
---
# <a name="loadstringrcex-function"></a>LoadStringRCEx — Funkcja

Tłumaczy wartość HRESULT na odpowiedni komunikat o błędzie dla określonej kultury.  
  
 Ta funkcja jest przestarzała w .NET Framework 4.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT LoadStringRCEx (  
    [in]  LCID    lcid,
    [in]  UINT    iResouceID,
    [out] LPWSTR  szBuffer,
    [in]  int     iMax,
    [in]  int     bQuiet,
    [out] int    *pcwchUsed  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `lcid`  
 podczas Identyfikator kultury. Przekaż `lcid` wartość 1, aby użyć domyślnej kultury.  
  
 `iResourceID`  
 podczas WYNIK HRESULT.  
  
 `szBuffer`  
 określoną Bufor, który zawiera komunikat o błędzie po pomyślnym zakończeniu.  
  
 `iMax`  
 podczas Rozmiar buforu komunikatów o błędach.  
  
 `bQuiet`  
 podczas Ignoruj.  
  
 `pcwchUsed`  
 określoną Wskaźnik do długości komunikatu o błędzie.  
  
## <a name="return-value"></a>Wartość zwracana  

 Ta metoda zwraca standardowe kody błędów COM, jak zdefiniowano w WinError. h, oprócz następujących wartości.  
  
|Kod powrotu|Opis|  
|-----------------|-----------------|  
|S_OK|Metoda została ukończona pomyślnie.|  
|E_INVALIDARG|`szBuffer` ma wartość null lub `iMax` jest równa zero (0).|  
  
## <a name="remarks"></a>Uwagi  

 Jeśli metoda nie zakończy się pomyślnie, `szBuffer` zawiera pusty ciąg.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE. h  
  
 **Biblioteka:** MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- <xref:System.Globalization.CultureInfo.LCID%2A?displayProperty=nameWithType>
- [LoadStringRC — Funkcja](loadstringrc-function.md)
- [Przestarzałe funkcje hostingu środowiska CLR](deprecated-clr-hosting-functions.md)
