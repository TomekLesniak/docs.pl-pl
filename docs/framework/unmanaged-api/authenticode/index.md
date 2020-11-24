---
title: Authenticode (niezarządzana dokumentacja interfejsu API)
ms.date: 03/30/2017
ms.assetid: 7e8cc303-6e77-4116-aa8b-7ea297a3a467
ms.openlocfilehash: 9b3e1585278bda82dedf7542e866a551867b9c9f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674050"
---
# <a name="authenticode-unmanaged-api-reference"></a><span data-ttu-id="b67b7-102">Authenticode (niezarządzana dokumentacja interfejsu API)</span><span class="sxs-lookup"><span data-stu-id="b67b7-102">Authenticode (Unmanaged API Reference)</span></span>

<span data-ttu-id="b67b7-103">Obsługuje moduł tworzenia i weryfikacji licencji XrML Authenticode.</span><span class="sxs-lookup"><span data-stu-id="b67b7-103">Supports the Authenticode XrML license creation and verification module.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b67b7-104">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="b67b7-104">In This Section</span></span>  

 [<span data-ttu-id="b67b7-105">Funkcja _AxlGetIssuerPublicKeyHash</span><span class="sxs-lookup"><span data-stu-id="b67b7-105">_AxlGetIssuerPublicKeyHash Function</span></span>](axlgetissuerpublickeyhash-function.md)  
 <span data-ttu-id="b67b7-106">Pobiera skrót SHA-1 klucza publicznego skojarzonego z kluczem prywatnym, który jest używany do podpisywania określonego certyfikatu.</span><span class="sxs-lookup"><span data-stu-id="b67b7-106">Retrieves the SHA-1 hash of the public key associated with the private key that is used to sign the specified certificate.</span></span>  
  
 [<span data-ttu-id="b67b7-107">Funkcja _AxlPublicKeyBlobToPublicKeyToken</span><span class="sxs-lookup"><span data-stu-id="b67b7-107">_AxlPublicKeyBlobToPublicKeyToken Function</span></span>](axlpublickeyblobtopublickeytoken-function.md)  
 <span data-ttu-id="b67b7-108">Oblicza token klucza publicznego o silnej nazwie w formacie PublicKeyBlob — dostawcy usług kryptograficznych.</span><span class="sxs-lookup"><span data-stu-id="b67b7-108">Computes the strong name public key token from a CSP PUBLICKEYBLOB format.</span></span>  
  
 [<span data-ttu-id="b67b7-109">Funkcja _AxlRSAKeyValueToPublicKeyToken</span><span class="sxs-lookup"><span data-stu-id="b67b7-109">_AxlRSAKeyValueToPublicKeyToken Function</span></span>](axlrsakeyvaluetopublickeytoken-function.md)  
 <span data-ttu-id="b67b7-110">Konwertuje modulo i wykładnik na token klucza publicznego o silnej nazwie.</span><span class="sxs-lookup"><span data-stu-id="b67b7-110">Converts a Modulus and Exponent to a strong name public key token.</span></span>  
  
 [<span data-ttu-id="b67b7-111">Funkcja CertFreeAuthenticodeSignerInfo</span><span class="sxs-lookup"><span data-stu-id="b67b7-111">CertFreeAuthenticodeSignerInfo Function</span></span>](certfreeauthenticodesignerinfo-function.md)  
 <span data-ttu-id="b67b7-112">Zwalnia zasoby przydzieloną dla struktury AXL_AUTHENTICODE_SIGNER_INFO.</span><span class="sxs-lookup"><span data-stu-id="b67b7-112">Frees resources allocated for the AXL_AUTHENTICODE_SIGNER_INFO structure.</span></span>  
  
 [<span data-ttu-id="b67b7-113">Funkcja CertFreeAuthenticodeTimestamperInfo</span><span class="sxs-lookup"><span data-stu-id="b67b7-113">CertFreeAuthenticodeTimestamperInfo Function</span></span>](certfreeauthenticodetimestamperinfo-function.md)  
 <span data-ttu-id="b67b7-114">Zwalnia zasoby przydzieloną dla struktury AXL_AUTHENTICODE_TIMESTAMPER_INFO.</span><span class="sxs-lookup"><span data-stu-id="b67b7-114">Frees resources allocated for the AXL_AUTHENTICODE_TIMESTAMPER_INFO structure.</span></span>  
  
 [<span data-ttu-id="b67b7-115">Funkcja CertTimestampAuthenticodeLicense</span><span class="sxs-lookup"><span data-stu-id="b67b7-115">CertTimestampAuthenticodeLicense Function</span></span>](certtimestampauthenticodelicense-function.md)  
 <span data-ttu-id="b67b7-116">Sygnatura czasowa oznacza licencję na technologię XrML Authenticode utworzoną przez CertCreateAuthenticodeLicense.</span><span class="sxs-lookup"><span data-stu-id="b67b7-116">Time stamps an Authenticode XrML license created by CertCreateAuthenticodeLicense.</span></span>  
  
 [<span data-ttu-id="b67b7-117">Funkcja CertVerifyAuthenticodeLicense</span><span class="sxs-lookup"><span data-stu-id="b67b7-117">CertVerifyAuthenticodeLicense Function</span></span>](certverifyauthenticodelicense-function.md)  
 <span data-ttu-id="b67b7-118">Weryfikuje ważność licencji XrML Authenticode.</span><span class="sxs-lookup"><span data-stu-id="b67b7-118">Verifies the validity of an Authenticode XrML license.</span></span>  
  
 [<span data-ttu-id="b67b7-119">Struktura AXL_AUTHENTICODE_SIGNER_INFO</span><span class="sxs-lookup"><span data-stu-id="b67b7-119">AXL_AUTHENTICODE_SIGNER_INFO Structure</span></span>](axl-authenticode-signer-info-structure.md)  
 <span data-ttu-id="b67b7-120">Definiuje informacje o podpisie Authenticode.</span><span class="sxs-lookup"><span data-stu-id="b67b7-120">Defines the Authenticode signer information.</span></span>  
  
 [<span data-ttu-id="b67b7-121">Struktura AXL_AUTHENTICODE_TIMESTAMPER_INFO</span><span class="sxs-lookup"><span data-stu-id="b67b7-121">AXL_AUTHENTICODE_TIMESTAMPER_INFO Structure</span></span>](axl-authenticode-timestamper-info-structure.md)  
 <span data-ttu-id="b67b7-122">Definiuje informacje o sygnaturze czasowym Authenticode.</span><span class="sxs-lookup"><span data-stu-id="b67b7-122">Defines the Authenticode time stamper information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b67b7-123">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="b67b7-123">See also</span></span>

- [<span data-ttu-id="b67b7-124">Niezarządzana dokumentacja interfejsu API</span><span class="sxs-lookup"><span data-stu-id="b67b7-124">Unmanaged API Reference</span></span>](../index.md)
