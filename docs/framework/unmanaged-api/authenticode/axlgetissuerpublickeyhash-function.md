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
# <a name="_axlgetissuerpublickeyhash-function"></a><span data-ttu-id="b6814-102">\_AxlGetIssuerPublicKeyHash, funkcja</span><span class="sxs-lookup"><span data-stu-id="b6814-102">\_AxlGetIssuerPublicKeyHash Function</span></span>

<span data-ttu-id="b6814-103">Pobiera skrót SHA-1 klucza publicznego skojarzonego z kluczem prywatnym, który jest używany do podpisywania określonego certyfikatu.</span><span class="sxs-lookup"><span data-stu-id="b6814-103">Retrieves the SHA-1 hash of the public key associated with the private key that is used to sign the specified certificate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6814-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="b6814-104">Syntax</span></span>  
  
```cpp  
HRESULT _AxlGetIssuerPublicKeyHash (  
    [in]  IN PCRYPT_DATA_BLOB   pChainContext,  
    [out] LPWSTR                *ppwszPublicKeyHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b6814-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="b6814-105">Parameters</span></span>  

 `pChainContext`  
 <span data-ttu-id="b6814-106">podczas Obiekt BLOB klucza publicznego dostawcy usług kryptograficznych.</span><span class="sxs-lookup"><span data-stu-id="b6814-106">[in] The CSP public key blob.</span></span> <span data-ttu-id="b6814-107">Zobacz strukturę [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) .</span><span class="sxs-lookup"><span data-stu-id="b6814-107">See the [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) structure.</span></span>  
  
 `ppwszPublicKeyHash`  
 <span data-ttu-id="b6814-108">określoną Wskaźnik do WCHAR \*, aby otrzymać token klucza publicznego zakodowany w formacie szesnastkowym.</span><span class="sxs-lookup"><span data-stu-id="b6814-108">[out] A pointer to WCHAR \* to receive the hex-encoded public key token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b6814-109">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="b6814-109">Return Value</span></span>  

 <span data-ttu-id="b6814-110">`S_OK` Jeśli funkcja się powiedzie; w przeciwnym razie `S_FALSE` .</span><span class="sxs-lookup"><span data-stu-id="b6814-110">`S_OK` if the function succeeds; otherwise `S_FALSE`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6814-111">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="b6814-111">See also</span></span>

- [<span data-ttu-id="b6814-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="b6814-112">Authenticode</span></span>](index.md)
