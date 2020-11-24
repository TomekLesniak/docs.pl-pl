---
title: Funkcja _AxlPublicKeyBlobToPublicKeyToken
ms.date: 03/30/2017
api_name:
- _AxlPublicKeyBlobToPublicKeyToken
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 2d92a746-d68c-4f53-a16e-727f071a2d80
ms.openlocfilehash: 989e99198efd1519f607a2e3164ff4de584e88af
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679887"
---
# <a name="_axlpublickeyblobtopublickeytoken-function"></a>\_AxlPublicKeyBlobToPublicKeyToken, funkcja

Oblicza token klucza publicznego o silnej nazwie w formacie PublicKeyBlob — dostawcy usług kryptograficznych.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT _AxlPublicKeyBlobToPublicKeyToken (  
    [in]  PCCERT_CHAIN_CONTEXT   pCspPublicKeyBlob,  
    [out] LPWSTR                 *ppwszPublicKeyToken  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `pCspPublicKeyBlob`  
 podczas Obiekt BLOB klucza publicznego dostawcy usług kryptograficznych.  
  
 `ppwszPublicKeyHash`  
 określoną Wskaźnik do WCHAR *, aby otrzymać skrót klucza publicznego zakodowany szesnastkowo.  
  
## <a name="return-value"></a>Wartość zwracana  

 `S_OK` Jeśli funkcja się powiedzie; w przeciwnym razie `S_FALSE` .  
  
## <a name="see-also"></a>Zobacz także

- [Authenticode](index.md)
