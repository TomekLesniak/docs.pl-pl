---
title: Zagadnienia dotyczące zabezpieczeń w programie WCF
ms.date: 03/30/2017
helpviewer_keywords:
- security [WCF]
- Windows Communication Foundation, security
- WCF, security
ms.assetid: 42055ee0-6d0c-443d-9d89-788dfc345d6d
ms.openlocfilehash: 796098258601ec5fa208fd8a8060b28c3eeeb4d6
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96276025"
---
# <a name="security-considerations-in-wcf"></a>Zagadnienia dotyczące zabezpieczeń w programie WCF

W tematach w tej sekcji przedstawiono różne elementy związane z zabezpieczeniami, które należy wziąć pod uwagę podczas projektowania aplikacji Windows Communication Foundation (WCF).  
  
## <a name="in-this-section"></a>W tej sekcji  

 [Information Disclosure (ujawnienie informacji)](information-disclosure.md)  
 W tym artykule omówiono różne sposoby, w których informacje mogą być ujawnione lub zaatakowane oraz jak można je złagodzić.  
  
 [Elevation of Privilege (podniesienie uprawnień)](elevation-of-privilege.md)  
 W tym artykule omówiono skutki udzielenia uprawnień autoryzacji osoby atakującej poza tymi, które zostały początkowo przyznane i jak można je złagodzić.  
  
 [Denial of Service (odmowa usługi)](denial-of-service.md)  
 W tym artykule omówiono, co się dzieje, gdy system nie może prawidłowo przetwarzać komunikatów i jak można je ograniczyć.  
  
 [Tampering (manipulowanie)](tampering.md)  
 W tym artykule omówiono zmiany komunikatów lub dostarczania komunikatów oraz sposób ich ograniczania.  
  
 [Ataki oparte na metodzie powtórzeń](replay-attacks.md)  
 W tym artykule omówiono, co się dzieje, gdy osoba atakująca skopiuje strumień komunikatów między dwiema stronami i odtwarza strumień do jednej lub kilku stron, a także jak to zrobić.  
  
 [Zagadnienia dotyczące zabezpieczeń bezpiecznych sesji](security-considerations-for-secure-sessions.md)  
 W tym artykule omówiono następujące elementy, które mają wpływ na zabezpieczenia podczas implementowania bezpiecznych sesji.  
  
 [Nieobsługiwane scenariusze](unsupported-scenarios.md)  
 Wyświetla listę różnych scenariuszy, które nie obsługują określonego aspektu zabezpieczeń i należy je unikać lub rozważać.  
  
## <a name="reference"></a>Dokumentacja  

 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a>Sekcje pokrewne  

 [Wytyczne dotyczące zabezpieczeń i najlepsze rozwiązania](security-guidance-and-best-practices.md)  
  
## <a name="see-also"></a>Zobacz też

- [Bezpieczeństwo](security.md)
