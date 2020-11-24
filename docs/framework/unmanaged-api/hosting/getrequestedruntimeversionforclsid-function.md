---
title: GetRequestedRuntimeVersionForCLSID — Funkcja
ms.date: 03/30/2017
api_name:
- GetRequestedRuntimeVersionForCLSID
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetRequestedRuntimeVersionForCLSID
helpviewer_keywords:
- GetRequestedRuntimeVersionForCLSID function [.NET Framework hosting]
ms.assetid: 5bb12f9a-0612-434b-b4ed-2db636a20bec
topic_type:
- apiref
ms.openlocfilehash: 3afb89a42d7e26c5e89e6f9458ef3406cc0102ca
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684190"
---
# <a name="getrequestedruntimeversionforclsid-function"></a>GetRequestedRuntimeVersionForCLSID — Funkcja

Pobiera odpowiednie informacje o wersji środowiska uruchomieniowego języka wspólnego (CLR) dla klasy z określonym `CLSID` .  
  
 Ta funkcja jest przestarzała w .NET Framework 4.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetRequestedRuntimeVersionForCLSID (  
    [in]  REFCLSID   rclsid,
    [out]  LPWSTR     pVersion,
    [in]  DWORD      cchBuffer,
    [out] DWORD*     dwLength,
    [in]  CLSID_RESOLUTION_FLAGS dwResolutionFlags  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `rclsid`  
 podczas  `CLSID` Składnika.  
  
 `pVersion`  
 określoną  Bufor zawierający ciąg numeru wersji po pomyślnym zakończeniu.  
  
 `cchBuffer`  
 podczas  Rozmiar, w postaci znaków dwubajtowych, `pVersion` buforu.  
  
 `dwLength`  
 określoną Długość (w bajtach) zwróconego buforu.  
  
 `dwResolutionFlags`  
 podczas  Jedna z wartości CLSID_RESOLUTION_FLAGS. Obsługiwane są następujące wartości:  
  
- CLSID_RESOLUTION_DEFAULT: (0x0) określa, że należy użyć domyślnego zachowania międzyoperacyjności.  
  
- CLSID_RESOLUTION_REGISTERED: (0x1) określa, że rejestr powinien być przeszukiwany, a zasady podkładki powinny być stosowane.  
  
## <a name="return-value"></a>Wartość zwracana  
  
|HRESULT|Opis|  
|-------------|-----------------|  
|S_OK|Funkcja została pomyślnie zwrócona.|  
|E_INVALIDARG|Jeden z parametrów ma nieprawidłowy typ lub format.|  
|ERROR_INSUFFICIENT_BUFFER|`pVersion`Bufor nie jest wystarczająco duży, aby pomieścić cały ciąg wersji.|  
|REGDB_E_CLASSNOTREG|Nie ma żadnej klasy zarejestrowanej dla określonej `CLSID` .|  
|E_POINTER|`dwLength` ma wartość null lub `cchBuffer` jest wystarczająco duży, aby pomieścić ciąg wersji, ale `pVersion` ma wartość null.|  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE. h  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Przestarzałe funkcje hostingu środowiska CLR](deprecated-clr-hosting-functions.md)
