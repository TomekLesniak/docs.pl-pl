---
title: Niestandardowe poświadczenia i weryfikacja poświadczeń
ms.date: 03/30/2017
helpviewer_keywords:
- credentials [WCF], custom
- credentials [WCF]
- custom credentials [WCF]
- credential validation [WCF]
- credentials [WCF], validation
ms.assetid: da831bec-e281-4d44-b343-437b5eef688e
ms.openlocfilehash: 5f2909bb088a5f3d3203fe3c9e24b2df3450aa3f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96257831"
---
# <a name="custom-credential-and-credential-validation"></a>Niestandardowe poświadczenia i weryfikacja poświadczeń

Zabezpieczenia w programie Windows Communication Foundation (WCF) bazują na wymianie poświadczeń między usługami i klientami. Większość scenariuszy zabezpieczeń można spełnić przy użyciu wspólnych typów poświadczeń, takich jak Windows (Kerberos), nazwa użytkownika i hasła oraz certyfikaty. Jeśli jednak jest wymagany nowy typ poświadczeń, w tematach w tej sekcji wyjaśniono, jak obsługiwać i sprawdzać poprawność nowych typów.  
  
## <a name="in-this-section"></a>W tej sekcji  

 [Instrukcje: tworzenie usługi korzystającej z niestandardowego modułu weryfikacji certyfikatów](how-to-create-a-service-that-employs-a-custom-certificate-validator.md)  
 Wyjaśnia, jak dostosować walidację programu WCF przez dziedziczenie z <xref:System.IdentityModel.Selectors.X509CertificateValidator> klasy.  
  
 [Przewodnik: tworzenie niestandardowego klienta i poświadczeń usługi](walkthrough-creating-custom-client-and-service-credentials.md)  
 Pokazuje, w jaki sposób można rozciągnąć <xref:System.ServiceModel.Description.ClientCredentials> klasy i, <xref:System.ServiceModel.Description.ServiceCredentials> aby pomieścić nowe typy poświadczeń. Jest to pierwsza część tematów, które umożliwiają tworzenie niestandardowych typów poświadczeń.  
  
 [Instrukcje: tworzenie niestandardowego dostawcy tokenów zabezpieczeń](how-to-create-a-custom-security-token-provider.md)  
 Wyjaśnia, jak utworzyć dostawcę tokenów zabezpieczających do obsługi nowych typów poświadczeń i zwracać nowe tokeny dla poświadczenia. Jest to drugi temat w serii.  
  
 [Instrukcje: tworzenie niestandardowego wystawcy uwierzytelniania tokenu zabezpieczeń](how-to-create-a-custom-security-token-authenticator.md)  
 Wyjaśnia, jak utworzyć niestandardowy wystawca uwierzytelnienia w celu uwierzytelnienia nowego typu poświadczeń. Jest to trzeci temat w tej serii.  
  
## <a name="reference"></a>Dokumentacja  

 <xref:System.ServiceModel.Security>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Selectors>  
  
 <xref:System.IdentityModel.Selectors.X509CertificateValidator>  
  
 <xref:System.ServiceModel.Description.ClientCredentials>  
  
 <xref:System.ServiceModel.Description.ServiceCredentials>  
  
## <a name="related-sections"></a>Sekcje pokrewne  

 [Authentication](../feature-details/authentication-in-wcf.md)  
  
 [Federacja i wystawione tokeny](../feature-details/federation-and-issued-tokens.md)  
  
 [Autoryzacja](../feature-details/authorization-in-wcf.md)  
  
## <a name="see-also"></a>Zobacz też

- [Bezpieczeństwo](../feature-details/security.md)
