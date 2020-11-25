---
title: StrongNameKeyGenEx — Funkcja
ms.date: 03/30/2017
api_name:
- StrongNameKeyGenEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyGenEx
helpviewer_keywords:
- StrongNameKeyGenEx function [.NET Framework strong naming]
ms.assetid: 36bd10b9-9857-45f3-8d3b-0da091d6169e
topic_type:
- apiref
ms.openlocfilehash: f28ee5767997240018d182b8303e4f65be81c702
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708546"
---
# <a name="strongnamekeygenex-function"></a>StrongNameKeyGenEx — Funkcja

Generuje nową parę kluczy publicznych/prywatnych z określonym rozmiarem klucza w celu użycia silnej nazwy.  
  
 Ta funkcja jest przestarzała. Zamiast tego użyj metody [ICLRStrongName:: StrongNameKeyGenEx —](../hosting/iclrstrongname-strongnamekeygenex-method.md) .  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
BOOLEAN StrongNameKeyGenEx (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [in]  DWORD     dwKeySize,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `wszKeyContainer`  
 podczas Nazwa żądanego kontenera kluczy. `wszKeyContainer` nie może być pustym ciągiem ani mieć wartości null w celu wygenerowania nazwy tymczasowej.  
  
 `dwFlags`  
 podczas Określa, czy klucz ma pozostać zarejestrowany. Obsługiwane są następujące wartości:  
  
- 0x00000000 — używany, gdy `wszKeyContainer` ma wartość null, aby wygenerować nazwę kontenera kluczy tymczasowych.  
  
- 0x00000001 ( `SN_LEAVE_KEY` ) — określa, że klucz powinien pozostać zarejestrowany.  
  
 `dwKeySize`  
 podczas Żądany rozmiar klucza w bitach.  
  
 `ppbKeyBlob`  
 określoną Zwracana para kluczy publiczny/prywatny.  
  
 `pcbKeyBlob`  
 określoną Rozmiar, w bajtach, z `ppbKeyBlob` .  
  
## <a name="return-value"></a>Wartość zwracana  

 `true` Po pomyślnym zakończeniu; w przeciwnym razie `false` .  
  
## <a name="remarks"></a>Uwagi  

 Do `dwKeySize` podpisania zestawu o silnej nazwie .NET Framework wersje 1,0 i 1,1 są wymagane z 1024 BITS; w wersji 2,0 dodano 2048 obsługę kluczy.  
  
 Po pobraniu klucza należy wywołać funkcję [StrongNameFreeBuffer —](strongnamefreebuffer-function.md) , aby zwolnić przydzieloną pamięć.  
  
 Jeśli `StrongNameKeyGenEx` Funkcja nie zakończy się pomyślnie, wywołaj funkcję [StrongNameErrorInfo —](strongnameerrorinfo-function.md) w celu pobrania ostatniego wygenerowanego błędu.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** StrongName. h  
  
 **Biblioteka:** Uwzględnione jako zasób w MsCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [StrongNameKeyGenEx, metoda](../hosting/iclrstrongname-strongnamekeygenex-method.md)
- [StrongNameKeyGen, metoda](../hosting/iclrstrongname-strongnamekeygen-method.md)
- [ICLRStrongName — Interfejs](../hosting/iclrstrongname-interface.md)
