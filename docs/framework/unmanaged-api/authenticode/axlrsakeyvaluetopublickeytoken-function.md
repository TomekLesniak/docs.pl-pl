---
title: Funkcja _AxlRSAKeyValueToPublicKeyToken
ms.date: 03/30/2017
api_name:
- _AxlRSAKeyValueToPublicKeyToken
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: d60f19fe-7bec-47ba-b60e-ba9ce66abf8c
ms.openlocfilehash: 5c1e2bfc7fd55e807af68744e28faa473daea772
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674219"
---
# <a name="_axlrsakeyvaluetopublickeytoken-function"></a><span data-ttu-id="2c993-102">\_AxlRSAKeyValueToPublicKeyToken, funkcja</span><span class="sxs-lookup"><span data-stu-id="2c993-102">\_AxlRSAKeyValueToPublicKeyToken function</span></span>

<span data-ttu-id="2c993-103">Konwertuje modulo i wykładnik na token klucza publicznego o silnej nazwie.</span><span class="sxs-lookup"><span data-stu-id="2c993-103">Converts a Modulus and Exponent to a strong name public key token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c993-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="2c993-104">Syntax</span></span>  
  
```cpp  
HRESULT _AxlRSAKeyValueToPublicKeyToken (  
    [in]  PCRYPT_DATA_BLOB pModulusBlob,  
    [in]  PCRYPT_DATA_BLOB pExponentBlob,  
    [out] LPWSTR           *ppwszPublicKeyToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2c993-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="2c993-105">Parameters</span></span>  

 `pModulusBlob`  
 <span data-ttu-id="2c993-106">podczas Obiekt BLOB modułu kodowanego algorytmem Base64 (z \<Modulus> elementu).</span><span class="sxs-lookup"><span data-stu-id="2c993-106">[in] The base64-encoded Modulus blob (from the \<Modulus> element).</span></span>  <span data-ttu-id="2c993-107">Zobacz strukturę [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) .</span><span class="sxs-lookup"><span data-stu-id="2c993-107">See the [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) structure.</span></span>  
  
 `pExponentBlob`  
 <span data-ttu-id="2c993-108">podczas Obiekt BLOB wykładnika zakodowany w formacie base64 (z \<Exponent> elementu).</span><span class="sxs-lookup"><span data-stu-id="2c993-108">[in] The base64-encoded Exponent blob (from the \<Exponent> element).</span></span> <span data-ttu-id="2c993-109">Zobacz strukturę [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) .</span><span class="sxs-lookup"><span data-stu-id="2c993-109">See the [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) structure.</span></span>  
  
 `ppwszPublicKeyToken`  
 <span data-ttu-id="2c993-110">określoną Wskaźnik do WCHAR \*, aby otrzymać token klucza publicznego zakodowany w formacie szesnastkowym.</span><span class="sxs-lookup"><span data-stu-id="2c993-110">[out] A pointer to WCHAR \* to receive the hex-encoded public key token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2c993-111">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="2c993-111">Return Value</span></span>  

 <span data-ttu-id="2c993-112">`S_OK` Jeśli funkcja się powiedzie.</span><span class="sxs-lookup"><span data-stu-id="2c993-112">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="2c993-113">W przeciwnym razie zwraca kod błędu.</span><span class="sxs-lookup"><span data-stu-id="2c993-113">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c993-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="2c993-114">See also</span></span>

- [<span data-ttu-id="2c993-115">Authenticode</span><span class="sxs-lookup"><span data-stu-id="2c993-115">Authenticode</span></span>](index.md)
