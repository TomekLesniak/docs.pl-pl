---
title: Funkcja _AxlGetIssuerPublicKeyHash
ms.date: 03/30/2017
api_name:
- _AxlGetIssuerPublicKeyHash
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: fb626b41-b888-4625-84c3-2c02b5e3866f
ms.openlocfilehash: 49674e43109108e41b135cecbec061ad61e14865
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679965"
---
# <a name="_axlgetissuerpublickeyhash-function"></a>\_AxlGetIssuerPublicKeyHash, funkcja

Pobiera skrót SHA-1 klucza publicznego skojarzonego z kluczem prywatnym, który jest używany do podpisywania określonego certyfikatu.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT _AxlGetIssuerPublicKeyHash (  
    [in]  IN PCRYPT_DATA_BLOB   pChainContext,  
    [out] LPWSTR                *ppwszPublicKeyHash  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `pChainContext`  
 podczas Obiekt BLOB klucza publicznego dostawcy usług kryptograficznych. Zobacz strukturę [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) .  
  
 `ppwszPublicKeyHash`  
 określoną Wskaźnik do WCHAR *, aby otrzymać token klucza publicznego zakodowany w formacie szesnastkowym.  
  
## <a name="return-value"></a>Wartość zwracana  

 `S_OK` Jeśli funkcja się powiedzie; w przeciwnym razie `S_FALSE` .  
  
## <a name="see-also"></a>Zobacz także

- [Authenticode](index.md)
