---
title: PNRP w projektowaniu aplikacji
ms.date: 03/30/2017
ms.assetid: 265615d6-4423-4b5d-8626-752e456f4f4e
ms.openlocfilehash: 7c59b2be8384c8f8cc6bbdc4546a678cfe1c538d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96263194"
---
# <a name="pnrp-in-application-development"></a><span data-ttu-id="db514-102">PNRP w projektowaniu aplikacji</span><span class="sxs-lookup"><span data-stu-id="db514-102">PNRP in Application Development</span></span>

<span data-ttu-id="db514-103">W systemie Windows Vista aplikacje sieciowe mogą uzyskać dostęp do funkcji publikowania i rozpoznawania nazw za pomocą uproszczonego interfejsu programowania aplikacji (API) protokołu PNRP.</span><span class="sxs-lookup"><span data-stu-id="db514-103">In Windows Vista, networking applications can access name publication and resolution functions through a simplified PNRP application programming interface (API).</span></span>  
  
## <a name="implementing-the-peer-name-resolution-protocol"></a><span data-ttu-id="db514-104">Implementowanie protokołu rozpoznawania nazw równorzędnych</span><span class="sxs-lookup"><span data-stu-id="db514-104">Implementing the Peer Name Resolution Protocol</span></span>  

 <span data-ttu-id="db514-105">W uproszczonym interfejsie API protokołu PNRP chmury nie są jawnie określone w celu zarejestrowania nazwy i adresów; składnik PNRP automatycznie określa odpowiednie chmury do przyłączenia i adresy do opublikowania w chmurach.</span><span class="sxs-lookup"><span data-stu-id="db514-105">With the simplified PNRP API, clouds are not explicitly specified to register the name and addresses; the PNRP component automatically determines the appropriate clouds to join and the addresses to publish within the clouds.</span></span>  
  
 <span data-ttu-id="db514-106">W przypadku wysoce uproszczonego rozpoznawania nazw PNRP w systemie Windows Vista nazwy PNRP są teraz zintegrowane z funkcją Windows Sockets getaddrinfo ().</span><span class="sxs-lookup"><span data-stu-id="db514-106">For highly simplified PNRP name resolution in Windows Vista, PNRP names are now integrated into the getaddrinfo() Windows Sockets function.</span></span> <span data-ttu-id="db514-107">Aby użyć protokołu PNRP do rozpoznawania nazwy na adres IPv6, aplikacje mogą używać funkcji getaddrinfo () do rozpoznawania w pełni kwalifikowanej nazwy domeny (FQDN) name.prnp.net, w której nazwa jest rozpoznawana jako nazwa elementu równorzędnego.</span><span class="sxs-lookup"><span data-stu-id="db514-107">To use PNRP to resolve a name to an IPv6 address, applications can use the getaddrinfo() function to resolve the Fully Qualified Domain Name (FQDN) name.prnp.net, in which name is peer name being resolved.</span></span> <span data-ttu-id="db514-108">Domena pnrp.net jest domeną zastrzeżoną w systemie Windows Vista do rozpoznawania nazw PNRP.</span><span class="sxs-lookup"><span data-stu-id="db514-108">The pnrp.net domain is a reserved domain in Windows Vista for PNRP name resolution.</span></span>  
  
 <span data-ttu-id="db514-109">Przekazywanie komunikatów między aplikacjami PeerToPeer jest nadal obsługiwane przez bazowe architektury, takie jak PeerChannel i [dane dużych danych WCF i przesyłania strumieniowego](../wcf/feature-details/large-data-and-streaming.md).</span><span class="sxs-lookup"><span data-stu-id="db514-109">Message passing between PeerToPeer applications is still handled by underlying architectures such as PeerChannel and WCF [Large Data and Streaming](../wcf/feature-details/large-data-and-streaming.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db514-110">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="db514-110">See also</span></span>

- <xref:System.Net.PeerToPeer>
