---
title: GetPublicKeyToken — Metoda
ms.date: 03/30/2017
api_name:
- IALink2.GetPublicKeyToken
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetPublicKeyToken
helpviewer_keywords:
- GetPublicKeyToken method
ms.assetid: 4a16374c-94b0-47b0-9fed-88c2b0cdccd4
topic_type:
- apiref
ms.openlocfilehash: e41be6407076a2609a83a5be3b0c42d28914ec38
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720345"
---
# <a name="getpublickeytoken-method"></a>GetPublicKeyToken — Metoda

Pobiera token klucza publicznego dla danego keyfile lub kontenera kluczy.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetPublicKeyToken(  
    LPCWSTR pszKeyFile,  
    LPCWSTR pszKeyContainer,  
    void* pvPublicKeyToken,  
    DWORD* pcbPublicKeyToken  
) PURE;  
```  
  
## <a name="parameters"></a>Parametry  

 `pszKeyFile`  
 Nazwa pliku klucza.  
  
 `pszKeyContainer`  
 Nazwa kontenera kluczy.  
  
 `pvPublicKeyToken`  
 Adres, pod którym ma być przechowywany token klucza.  
  
 `pcbPublicKeyToken`  
 Określa rozmiar buforu wskazywanego przez `pvPublicKeyToken` . Po powrocie, zawiera rzeczywistą liczbę użytych bajtów.  
  
## <a name="return-value"></a>Wartość zwracana  

 Zwraca S_OK, jeśli metoda zakończy się pomyślnie.  
  
## <a name="requirements"></a>Wymagania  

 Wymaga Alink. h.  
  
## <a name="see-also"></a>Zobacz także

- [IALink2 — Interfejs](ialink2-interface.md)
- [IALink — Interfejs](ialink-interface.md)
- [ALink — interfejs API](index.md)
