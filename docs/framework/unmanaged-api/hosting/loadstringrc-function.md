---
title: LoadStringRC — Funkcja
ms.date: 03/30/2017
api_name:
- LoadStringRC
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- LoadStringRC
helpviewer_keywords:
- LoadStringRC function [.NET Framework hosting]
ms.assetid: 752e49b4-987c-4c28-a118-1a0c1ed510c5
topic_type:
- apiref
ms.openlocfilehash: 16f95f8fce20f2cf46d4cda214e4494bd288bf60
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727552"
---
# <a name="loadstringrc-function"></a>LoadStringRC — Funkcja

Tłumaczy wartość HRESULT na komunikat o błędzie przy użyciu domyślnej kultury bieżącego wątku.  
  
 Ta funkcja jest przestarzała w .NET Framework 4.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT LoadStringRC (  
    [in]  UINT    iResourceID,
    [out] LPWSTR  szBuffer,
    [in]  int     iMax,
    [in]  int     bQuiet  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `iResourceID`  
 podczas WYNIK HRESULT.  
  
 `szBuffer`  
 określoną Bufor, który zawiera komunikat o błędzie po pomyślnym zakończeniu.  
  
 `iMax`  
 podczas Rozmiar buforu komunikatów o błędach.  
  
 `bQuiet`  
 podczas Ignoruj.  
  
## <a name="return-value"></a>Wartość zwracana  

 Ta metoda zwraca kody błędów standardowego Component Object Model (COM), jak zdefiniowano w WinError. h, oprócz następujących wartości.  
  
|Kod powrotu|Opis|  
|-----------------|-----------------|  
|S_OK|Metoda została ukończona pomyślnie.|  
|E_INVALIDARG|`szBuffer` ma wartość null lub `iMax` jest równa zero (0).|  
  
## <a name="remarks"></a>Uwagi  

 Jeśli metoda nie zakończy się pomyślnie, `szBuffer` zawiera pusty ciąg.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE. h  
  
 **Biblioteka:** MSCorEE.dll i Mscorwks.dll. Użyj MSCorEE.dll zamiast Mscorwks.dll, aby upewnić się, że docelowa jest poprawna wersja .NET Framework.  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [LoadStringRCEx — Funkcja](loadstringrcex-function.md)
- [Przestarzałe funkcje hostingu środowiska CLR](deprecated-clr-hosting-functions.md)
