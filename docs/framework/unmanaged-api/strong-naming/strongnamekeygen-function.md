---
title: StrongNameKeyGen — Funkcja
ms.date: 03/30/2017
api_name:
- StrongNameKeyGen
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyGen
helpviewer_keywords:
- StrongNameKeyGen function [.NET Framework strong naming]
ms.assetid: 883e413a-ad2f-4f7f-b1b9-aeb8fe5b65f8
topic_type:
- apiref
ms.openlocfilehash: 4844701784a3e6a1008a5deb2bdff3b3ba47aa7e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95691412"
---
# <a name="strongnamekeygen-function"></a>StrongNameKeyGen — Funkcja

Tworzy nową parę kluczy publiczny/prywatny w celu użycia silnej nazwy.  
  
 Ta funkcja jest przestarzała. Zamiast tego użyj metody [ICLRStrongName:: StrongNameKeyGen —](../hosting/iclrstrongname-strongnamekeygen-method.md) .  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
BOOLEAN StrongNameKeyGen (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
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
  
 `ppbKeyBlob`  
 określoną Zwracana para kluczy publiczny/prywatny.  
  
 `pcbKeyBlob`  
 określoną Rozmiar, w bajtach, z `ppbKeyBlob` .  
  
## <a name="return-value"></a>Wartość zwracana  

 `true` Po pomyślnym zakończeniu; w przeciwnym razie `false` .  
  
## <a name="remarks"></a>Uwagi  

 `StrongNameKeyGen`Funkcja tworzy klucz 1024-bitowy. Po pobraniu klucza należy wywołać funkcję [StrongNameFreeBuffer —](strongnamefreebuffer-function.md) , aby zwolnić przydzieloną pamięć.  
  
 Jeśli `StrongNameKeyGen` Funkcja nie zakończy się pomyślnie, wywołaj funkcję [StrongNameErrorInfo —](strongnameerrorinfo-function.md) w celu pobrania ostatniego wygenerowanego błędu.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** StrongName. h  
  
 **Biblioteka:** Uwzględnione jako zasób w MsCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [StrongNameKeyGen, metoda](../hosting/iclrstrongname-strongnamekeygen-method.md)
- [StrongNameKeyGenEx, metoda](../hosting/iclrstrongname-strongnamekeygenex-method.md)
- [ICLRStrongName — Interfejs](../hosting/iclrstrongname-interface.md)
