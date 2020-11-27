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
# <a name="pnrp-in-application-development"></a>PNRP w projektowaniu aplikacji

W systemie Windows Vista aplikacje sieciowe mogą uzyskać dostęp do funkcji publikowania i rozpoznawania nazw za pomocą uproszczonego interfejsu programowania aplikacji (API) protokołu PNRP.  
  
## <a name="implementing-the-peer-name-resolution-protocol"></a>Implementowanie protokołu rozpoznawania nazw równorzędnych  

 W uproszczonym interfejsie API protokołu PNRP chmury nie są jawnie określone w celu zarejestrowania nazwy i adresów; składnik PNRP automatycznie określa odpowiednie chmury do przyłączenia i adresy do opublikowania w chmurach.  
  
 W przypadku wysoce uproszczonego rozpoznawania nazw PNRP w systemie Windows Vista nazwy PNRP są teraz zintegrowane z funkcją Windows Sockets getaddrinfo (). Aby użyć protokołu PNRP do rozpoznawania nazwy na adres IPv6, aplikacje mogą używać funkcji getaddrinfo () do rozpoznawania w pełni kwalifikowanej nazwy domeny (FQDN) name.prnp.net, w której nazwa jest rozpoznawana jako nazwa elementu równorzędnego. Domena pnrp.net jest domeną zastrzeżoną w systemie Windows Vista do rozpoznawania nazw PNRP.  
  
 Przekazywanie komunikatów między aplikacjami PeerToPeer jest nadal obsługiwane przez bazowe architektury, takie jak PeerChannel i [dane dużych danych WCF i przesyłania strumieniowego](../wcf/feature-details/large-data-and-streaming.md).  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.Net.PeerToPeer>
