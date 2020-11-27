---
title: Tworzenie oświadczenia i wartości zasobów
ms.date: 03/30/2017
helpviewer_keywords:
- claims [WCF], creation and resource values
ms.assetid: 30431f76-cbe7-4bad-bad7-8e43e23a82d4
ms.openlocfilehash: c3f36d607d88b208753066dcbd4e9baa6a2590fa
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96295135"
---
# <a name="claim-creation-and-resource-values"></a><span data-ttu-id="6045f-102">Tworzenie oświadczenia i wartości zasobów</span><span class="sxs-lookup"><span data-stu-id="6045f-102">Claim Creation and Resource Values</span></span>

<span data-ttu-id="6045f-103"><xref:System.IdentityModel.Claims.Claim>Klasa zawiera kilka metod tworzenia wystąpień wbudowanych typów oświadczeń.</span><span class="sxs-lookup"><span data-stu-id="6045f-103">The <xref:System.IdentityModel.Claims.Claim> class provides several methods for creating instances of built-in claims types.</span></span> <span data-ttu-id="6045f-104">Z tych metod nie należy sprawdzać semantyki ani formatowania w podanym zasobie:</span><span class="sxs-lookup"><span data-stu-id="6045f-104">Of these methods, the following perform no semantic or format checking on the supplied resource:</span></span>  
  
- <xref:System.IdentityModel.Claims.Claim.CreateDnsClaim%2A>  
  
- <span data-ttu-id="6045f-105"><xref:System.IdentityModel.Claims.Claim.CreateHashClaim%2A> (nie sprawdza długości ani zawartości tablicy bajtów)</span><span class="sxs-lookup"><span data-stu-id="6045f-105"><xref:System.IdentityModel.Claims.Claim.CreateHashClaim%2A> (does not check the length or content of the byte array)</span></span>  
  
- <xref:System.IdentityModel.Claims.Claim.CreateNameClaim%2A>  
  
- <xref:System.IdentityModel.Claims.Claim.CreateSpnClaim%2A>  
  
- <span data-ttu-id="6045f-106"><xref:System.IdentityModel.Claims.Claim.CreateThumbprintClaim%2A> (nie sprawdza długości ani zawartości tablicy bajtów)</span><span class="sxs-lookup"><span data-stu-id="6045f-106"><xref:System.IdentityModel.Claims.Claim.CreateThumbprintClaim%2A> (does not check the length or content of the byte array)</span></span>  
  
- <xref:System.IdentityModel.Claims.Claim.CreateUpnClaim%2A>  
  
 <span data-ttu-id="6045f-107">Należy zachować ostrożność podczas wywoływania powyższych metod, aby upewnić się, że przesyłane wartości zasobów mają prawidłowy format lub zawierają prawidłowy rodzaj informacji (lub oba).</span><span class="sxs-lookup"><span data-stu-id="6045f-107">Care should be taken when calling the above methods to ensure that the resource values passed in are of the correct format or contain the correct kind of information (or both).</span></span>  
  
 <span data-ttu-id="6045f-108">Następujące metody mają określone typy:</span><span class="sxs-lookup"><span data-stu-id="6045f-108">The following methods take specific types:</span></span>  
  
- <xref:System.IdentityModel.Claims.Claim.CreateDenyOnlyWindowsSidClaim%2A>  
  
- <xref:System.IdentityModel.Claims.Claim.CreateMailAddressClaim%2A>  
  
- <xref:System.IdentityModel.Claims.Claim.CreateRsaClaim%2A>  
  
- <xref:System.IdentityModel.Claims.Claim.CreateUriClaim%2A>  
  
- <xref:System.IdentityModel.Claims.Claim.CreateWindowsSidClaim%2A>  
  
- <xref:System.IdentityModel.Claims.Claim.CreateX500DistinguishedNameClaim%2A>  
  
## <a name="see-also"></a><span data-ttu-id="6045f-109">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="6045f-109">See also</span></span>

- <xref:System.IdentityModel.Claims.Claim>
- <xref:System.IdentityModel.Claims.ClaimSet>
- [<span data-ttu-id="6045f-110">Zarządzanie oświadczeniami i autoryzacją za pomocą modelu tożsamości</span><span class="sxs-lookup"><span data-stu-id="6045f-110">Managing Claims and Authorization with the Identity Model</span></span>](managing-claims-and-authorization-with-the-identity-model.md)
