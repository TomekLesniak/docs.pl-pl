---
title: Funkcja CertTimestampAuthenticodeLicense
ms.date: 03/30/2017
api_name:
- CertTimestampAuthenticodeLicense
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: d468325a-21c5-43ce-8567-84e342b22308
ms.openlocfilehash: fc1a99572406a38aee8133d6435134b78a134175
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674102"
---
# <a name="certtimestampauthenticodelicense-function"></a>Funkcja CertTimestampAuthenticodeLicense

Sygnatura czasowa oznacza licencję z kodem XrML Authenticode.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT CertTimestampAuthenticodeLicense (  
    [in]  PCRYPT_DATA_BLOB   pSignedLicenseBlob,  
    [in]  LPCWSTR            pwszTimestampURI,  
    [out] PCRYPT_DATA_BLOB   pTimestampSignatureBlob  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `pSignedLicenseBlob`  
 podczas Sygnatura czasowa podpisanej licencji na technologię Authenticode. Zobacz strukturę [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) .  
  
 `pwszTimestampURI`  
 podczas Identyfikator URI serwera sygnatur czasowych.  
  
 `pTimestampSignatureBlob`  
 określoną Wskaźnik do CRYPT_DATA_BLOB otrzymywania sygnatury czasowej kodowanej algorytmem Base64. Jest on odpowiedzialny za bezpłatne `pTimestampSignatureBlob` -> `pbData` Korzystanie z programu `HepFree()` . Zobacz strukturę [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) .  
  
## <a name="remarks"></a>Uwagi  

 Sygnatura czasowa jest w rzeczywistości certyfikatem PKCS #7 SignedData, którego zawartość jest binarną formą SignatureValue z podpisu licencji. Zasadniczo to pełni rolę sygnatury z licencją.  
  
## <a name="return-value"></a>Wartość zwracana  

 `S_OK` Jeśli funkcja się powiedzie. W przeciwnym razie zwraca kod błędu.  
  
## <a name="see-also"></a>Zobacz także

- [Authenticode](index.md)
