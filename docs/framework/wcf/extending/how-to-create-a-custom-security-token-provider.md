---
title: 'Instrukcje: tworzenie niestandardowego dostawcy tokenów zabezpieczeń'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [WCF], providing credentials
ms.assetid: db8cb478-aa43-478b-bf97-c6489ad7c7fd
ms.openlocfilehash: 94de506b16d97ec82b84ec6eed34111e99f62977
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96249270"
---
# <a name="how-to-create-a-custom-security-token-provider"></a>Instrukcje: tworzenie niestandardowego dostawcy tokenów zabezpieczeń

W tym temacie pokazano, jak utworzyć nowe typy tokenów za pomocą niestandardowego dostawcy tokenów zabezpieczających oraz jak zintegrować dostawcę z menedżerem niestandardowego tokenu zabezpieczeń.  
  
> [!NOTE]
> Utwórz niestandardowego dostawcę tokenów, jeśli tokeny dostarczone przez system w <xref:System.IdentityModel.Tokens> przestrzeni nazw nie pasują do Twoich wymagań.  
  
 Dostawca tokenów zabezpieczających tworzy reprezentację tokenu zabezpieczającego na podstawie informacji zawartych w poświadczeniach klienta lub usługi. Aby użyć niestandardowego dostawcy tokenów zabezpieczeń w ramach zabezpieczeń programu Windows Communication Foundation (WCF), należy utworzyć niestandardowe poświadczenia i implementacje Menedżera tokenów zabezpieczających.  
  
 Aby uzyskać więcej informacji na temat poświadczeń niestandardowych i Menedżera tokenów zabezpieczających, zobacz [Przewodnik: Tworzenie niestandardowego klienta i poświadczeń usługi](walkthrough-creating-custom-client-and-service-credentials.md).  
  
### <a name="to-create-a-custom-security-token-provider"></a>Aby utworzyć niestandardowego dostawcę tokenów zabezpieczających  
  
1. Zdefiniuj nową klasę pochodną <xref:System.IdentityModel.Selectors.SecurityTokenProvider> klasy.  
  
2. Zaimplementuj <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%28System.TimeSpan%29> metodę. Metoda jest odpowiedzialna za utworzenie i zwrócenie wystąpienia tokenu zabezpieczającego. Poniższy przykład tworzy klasę o nazwie `MySecurityTokenProvider` i zastępuje <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%28System.TimeSpan%29> metodę zwracającą wystąpienie <xref:System.IdentityModel.Tokens.X509SecurityToken> klasy. Konstruktor klasy wymaga wystąpienia <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> klasy.  
  
     [!code-csharp[c_CustomTokenProvider#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtokenprovider/cs/source.cs#1)]
     [!code-vb[c_CustomTokenProvider#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtokenprovider/vb/source.vb#1)]  
  
### <a name="to-integrate-a-custom-security-token-provider-with-a-custom-security-token-manager"></a>Aby zintegrować niestandardowego dostawcę tokenów zabezpieczających z menedżerem niestandardowego tokenu zabezpieczeń  
  
1. Zdefiniuj nową klasę pochodną <xref:System.IdentityModel.Selectors.SecurityTokenManager> klasy. (Poniższy przykład pochodzi od <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> klasy, która pochodzi od <xref:System.IdentityModel.Selectors.SecurityTokenManager> klasy).  
  
2. Zastąp <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenProvider%28System.IdentityModel.Selectors.SecurityTokenRequirement%29> metodę, jeśli nie została jeszcze przesłonięta.  
  
     <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenProvider%28System.IdentityModel.Selectors.SecurityTokenRequirement%29>Metoda jest odpowiedzialna za zwracanie wystąpienia <xref:System.IdentityModel.Selectors.SecurityTokenProvider> klasy właściwej dla <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> parametru przesłanego do metody przez strukturę zabezpieczeń WCF. Zmodyfikuj metodę w celu zwrócenia niestandardowej implementacji dostawcy tokenów zabezpieczeń (utworzonej w poprzedniej procedurze), gdy metoda jest wywoływana z odpowiednim parametrem tokenu zabezpieczającego. Aby uzyskać więcej informacji na temat Menedżera tokenów zabezpieczeń, zobacz [Przewodnik: Tworzenie niestandardowego klienta i poświadczeń usługi](walkthrough-creating-custom-client-and-service-credentials.md).  
  
3. Dodaj logikę niestandardową do metody, aby umożliwić jej zwrócenie niestandardowego dostawcy tokenów zabezpieczających na podstawie <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> parametru. Poniższy przykład zwraca niestandardowego dostawcę tokenów zabezpieczających w przypadku spełnienia wymagań dotyczących tokenu. Wymagania obejmują token zabezpieczający X. 509 oraz kierunek komunikatów (używany token do wyprowadzania wiadomości). We wszystkich innych przypadkach kod wywołuje klasę bazową, aby zachować zachowanie dostarczone przez system dla innych wymagań dotyczących tokenów zabezpieczających.  
  
 [!code-csharp[c_CustomTokenProvider#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtokenprovider/cs/source.cs#2)]
 [!code-vb[c_CustomTokenProvider#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtokenprovider/vb/source.vb#2)]  
  
## <a name="example"></a>Przykład  

 Poniżej przedstawiono kompletną <xref:System.IdentityModel.Selectors.SecurityTokenProvider> implementację wraz z odpowiadającą jej <xref:System.IdentityModel.Selectors.SecurityTokenManager> implementacją.  
  
 [!code-csharp[c_CustomTokenProvider#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtokenprovider/cs/source.cs#0)]
 [!code-vb[c_CustomTokenProvider#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtokenprovider/vb/source.vb#0)]  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.IdentityModel.Selectors.SecurityTokenProvider>
- <xref:System.IdentityModel.Selectors.SecurityTokenRequirement>
- <xref:System.IdentityModel.Selectors.SecurityTokenManager>
- <xref:System.IdentityModel.Tokens.X509SecurityToken>
- [Przewodnik: tworzenie niestandardowego klienta i poświadczeń usługi](walkthrough-creating-custom-client-and-service-credentials.md)
- [Instrukcje: tworzenie niestandardowego wystawcy uwierzytelniania tokenu zabezpieczeń](how-to-create-a-custom-security-token-authenticator.md)
