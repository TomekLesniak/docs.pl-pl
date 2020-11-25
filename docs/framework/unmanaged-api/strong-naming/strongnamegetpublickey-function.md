---
title: StrongNameGetPublicKey — Funkcja
ms.date: 03/30/2017
api_name:
- StrongNameGetPublicKey
api_location:
- mscoree.dll
- mscorsn.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameGetPublicKey
helpviewer_keywords:
- StrongNameGetPublicKey function [.NET Framework strong naming]
ms.assetid: 5b58c87f-3f72-40df-9b9a-291076931cc3
topic_type:
- apiref
ms.openlocfilehash: c97cc0c1d4c022583d0823abeff998e2ed5f719e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710977"
---
# <a name="strongnamegetpublickey-function"></a>StrongNameGetPublicKey — Funkcja

Pobiera klucz publiczny z pary kluczy prywatnych/publicznych. Para kluczy może być podana jako nazwa kontenera klucza w ramach dostawcy usług kryptograficznych (CSP) lub jako pierwotna kolekcja bajtów.  
  
 Ta funkcja jest przestarzała. Zamiast tego użyj metody [ICLRStrongName:: StrongNameGetPublicKey —](../hosting/iclrstrongname-strongnamegetpublickey-method.md) .  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
BOOLEAN StrongNameGetPublicKey (
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `szKeyContainer`  
 podczas Nazwa kontenera kluczy, który zawiera parę kluczy publiczny/prywatny. Jeśli `pbKeyBlob` ma wartość null, `szKeyContainer` należy określić prawidłowy kontener w ramach dostawcy CSP. W takim przypadku `StrongNameGetPublicKey` wyodrębnia klucz publiczny z pary kluczy przechowywanej w kontenerze.  
  
 Jeśli `pbKeyBlob` wartość nie jest równa null, przyjmuje się, że para kluczy jest zawarta w kluczowym dużym obiekcie binarnym (BLOB).  
  
 Klucze muszą być 1024-bitowe Rivest-Shamir-Adleman (RSA) kluczy podpisywania. W tej chwili nie są obsługiwane żadne inne typy kluczy.  
  
 `pbKeyBlob`  
 podczas Wskaźnik do pary kluczy publicznych/prywatnych. Ta para jest w formacie utworzonym przez funkcję Win32 `CryptExportKey` . Jeśli `pbKeyBlob` ma wartość null, zakłada się, że kontener kluczy określony przez `szKeyContainer` ma zawierać parę kluczy.  
  
 `cbKeyBlob`  
 podczas Rozmiar, w bajtach, z `pbKeyBlob` .  
  
 `ppbPublicKeyBlob`  
 określoną Zwrócony obiekt BLOB klucza publicznego. `ppbPublicKeyBlob`Parametr jest przypisywany przez środowisko uruchomieniowe języka wspólnego i zwracany do obiektu wywołującego. Obiekt wywołujący musi zwolnić pamięć przy użyciu funkcji [StrongNameFreeBuffer —](strongnamefreebuffer-function.md) .  
  
 `pcbPublicKeyBlob`  
 określoną Rozmiar zwróconego obiektu BLOB klucza publicznego.  
  
## <a name="return-value"></a>Wartość zwracana  

 `true` Po pomyślnym zakończeniu; w przeciwnym razie `false` .  
  
## <a name="remarks"></a>Uwagi  

 Klucz publiczny jest zawarty w strukturze [PublicKeyBlob —](publickeyblob-structure.md) .  
  
 Jeśli `StrongNameGetPublicKey` Funkcja nie zakończy się pomyślnie, wywołaj funkcję [StrongNameErrorInfo —](strongnameerrorinfo-function.md) w celu pobrania ostatniego wygenerowanego błędu.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** StrongName. h  
  
 **Biblioteka:** Uwzględnione jako zasób w MsCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [StrongNameGetPublicKey, metoda](../hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [StrongNameTokenFromPublicKey, metoda](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [ICLRStrongName — Interfejs](../hosting/iclrstrongname-interface.md)
- [PublicKeyBlob — Struktura](publickeyblob-structure.md)
