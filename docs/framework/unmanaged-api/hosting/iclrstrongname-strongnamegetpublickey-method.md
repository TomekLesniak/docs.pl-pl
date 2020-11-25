---
title: ICLRStrongName::StrongNameGetPublicKey — Metoda
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameGetPublicKey
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameGetPublicKey
helpviewer_keywords:
- StrongNameGetPublicKey method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameGetPublicKey method [.NET Framework hosting]
ms.assetid: a31dcaa9-a404-4c1d-8cc7-081827c52935
topic_type:
- apiref
ms.openlocfilehash: 5bd314b2b63474d2a1d159f74564e2d4ca13aef6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725550"
---
# <a name="iclrstrongnamestrongnamegetpublickey-method"></a>ICLRStrongName::StrongNameGetPublicKey — Metoda

Pobiera klucz publiczny z pary kluczy publiczny/prywatny. Para kluczy może być podana jako nazwa kontenera klucza w ramach dostawcy usług kryptograficznych (CSP) lub jako pierwotna kolekcja bajtów.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT StrongNameGetPublicKey (
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `szKeyContainer`  
 podczas Nazwa kontenera kluczy, który zawiera parę kluczy publiczny/prywatny. Jeśli `pbKeyBlob` ma wartość null, `szKeyContainer` należy określić prawidłowy kontener w ramach dostawcy CSP. W takim przypadku Metoda [ICLRStrongName:: StrongNameGetPublicKey —](iclrstrongname-strongnamegetpublickey-method.md) wyodrębnia klucz publiczny z pary kluczy przechowywanej w kontenerze.  
  
 Jeśli `pbKeyBlob` wartość nie jest równa null, przyjmuje się, że para kluczy jest zawarta w kluczowym dużym obiekcie binarnym (BLOB).  
  
 Klucze muszą być 1024-bitowe Rivest-Shamir-Adleman (RSA) kluczy podpisywania. W tej chwili nie są obsługiwane żadne inne typy kluczy.  
  
 `pbKeyBlob`  
 podczas Wskaźnik do pary kluczy publicznych/prywatnych. Ta para jest w formacie utworzonym przez funkcję Win32 `CryptExportKey` . Jeśli `pbKeyBlob` ma wartość null, zakłada się, że kontener kluczy określony przez `szKeyContainer` ma zawierać parę kluczy.  
  
 `cbKeyBlob`  
 podczas Rozmiar, w bajtach, z `pbKeyBlob` .  
  
 `ppbPublicKeyBlob`  
 określoną Zwrócony obiekt BLOB klucza publicznego. `ppbPublicKeyBlob`Parametr jest przypisywany przez środowisko uruchomieniowe języka wspólnego i zwracany do obiektu wywołującego. Obiekt wywołujący musi zwolnić pamięć przy użyciu metody [ICLRStrongName:: StrongNameFreeBuffer —](iclrstrongname-strongnamefreebuffer-method.md) .  
  
 `pcbPublicKeyBlob`  
 określoną Rozmiar zwróconego obiektu BLOB klucza publicznego.  
  
## <a name="return-value"></a>Wartość zwracana  

 `S_OK` Jeśli metoda została ukończona pomyślnie; w przeciwnym razie wartość HRESULT wskazująca niepowodzenie (zobacz [typowe wartości HRESULT](/windows/win32/seccrypto/common-hresult-values) dla listy).  
  
## <a name="remarks"></a>Uwagi  

 Klucz publiczny jest zawarty w strukturze [PublicKeyBlob —](../strong-naming/publickeyblob-structure.md) .  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Obiekt ServiceHost. h  
  
 **Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [StrongNameTokenFromPublicKey, metoda](iclrstrongname-strongnametokenfrompublickey-method.md)
- [PublicKeyBlob — Struktura](../strong-naming/publickeyblob-structure.md)
- [ICLRStrongName — Interfejs](iclrstrongname-interface.md)
