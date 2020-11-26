---
title: 'Instrukcje: Tworzenie niestandardowego wystawcy uwierzytelniania tokenu zabezpieczeń'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, authentication
ms.assetid: 10e245f7-d31e-42e7-82a2-d5780325d372
ms.openlocfilehash: 667dc82502ba881b067b5588271947f7c18c8810
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96249257"
---
# <a name="how-to-create-a-custom-security-token-authenticator"></a>Instrukcje: Tworzenie niestandardowego wystawcy uwierzytelniania tokenu zabezpieczeń

W tym temacie pokazano, jak utworzyć niestandardowy wystawca uwierzytelnienia tokenu zabezpieczającego i jak zintegrować go z niestandardowym menedżerem tokenów zabezpieczających. Wystawca uwierzytelnienia tokenów zabezpieczających weryfikuje zawartość tokenu zabezpieczającego podanego w komunikacie przychodzącym. Jeśli sprawdzanie poprawności zakończy się pomyślnie, wystawca uwierzytelnienia zwróci kolekcję <xref:System.IdentityModel.Policy.IAuthorizationPolicy> wystąpień, które po ocenie zwraca zestaw oświadczeń.  
  
 Aby użyć niestandardowego wystawcy uwierzytelnienia tokenu zabezpieczającego w programie Windows Communication Foundation (WCF), należy najpierw utworzyć niestandardowe poświadczenia i implementacje Menedżera tokenów zabezpieczających. Aby uzyskać więcej informacji na temat tworzenia poświadczeń niestandardowych i Menedżera tokenów zabezpieczających, zobacz [Przewodnik: Tworzenie niestandardowych poświadczeń klienta i usługi](walkthrough-creating-custom-client-and-service-credentials.md).
  
## <a name="procedures"></a>Procedury  
  
#### <a name="to-create-a-custom-security-token-authenticator"></a>Aby utworzyć niestandardowy wystawca uwierzytelnienia tokenu zabezpieczającego  
  
1. Zdefiniuj nową klasę pochodną <xref:System.IdentityModel.Selectors.SecurityTokenAuthenticator> klasy.  
  
2. Zastąp <xref:System.IdentityModel.Selectors.SecurityTokenAuthenticator.CanValidateTokenCore%2A> metodę. Metoda zwraca `true` lub w zależności od tego, `false` czy niestandardowy wystawca uwierzytelnienia może sprawdzić poprawność typu tokenu przychodzącego.  
  
3. Zastąp <xref:System.IdentityModel.Selectors.SecurityTokenAuthenticator.ValidateTokenCore%2A> metodę. Ta metoda musi odpowiednio sprawdzić zawartość tokenu. Jeśli token przejdzie do kroku walidacji, zwraca kolekcję <xref:System.IdentityModel.Policy.IAuthorizationPolicy> wystąpień. W poniższym przykładzie zastosowano niestandardową implementację zasad autoryzacji, która zostanie utworzona w następnej procedurze.  
  
     [!code-csharp[C_CustomTokenAuthenticator#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtokenauthenticator/cs/source.cs#1)]
     [!code-vb[C_CustomTokenAuthenticator#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtokenauthenticator/vb/source.vb#1)]  
  
 Poprzedni kod zwraca kolekcję zasad autoryzacji w <xref:System.IdentityModel.Selectors.SecurityTokenAuthenticator.CanValidateToken%28System.IdentityModel.Tokens.SecurityToken%29> metodzie. Usługa WCF nie zapewnia publicznej implementacji tego interfejsu. Poniższa procedura pokazuje, jak to zrobić w ramach własnych wymagań.  
  
#### <a name="to-create-a-custom-authorization-policy"></a>Aby utworzyć niestandardowe zasady autoryzacji  
  
1. Zdefiniuj nową klasę implementującą <xref:System.IdentityModel.Policy.IAuthorizationPolicy> interfejs.  
  
2. Zaimplementuj <xref:System.IdentityModel.Policy.IAuthorizationComponent.Id%2A> Właściwość tylko do odczytu. Jednym ze sposobów implementacji tej właściwości jest wygenerowanie unikatowego identyfikatora globalnego (GUID) w konstruktorze klasy i zwrócenie go za każdym razem, gdy zostanie zażądana wartość tej właściwości.  
  
3. Zaimplementuj <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Issuer%2A> Właściwość tylko do odczytu. Ta właściwość musi zwracać wystawcę zestawów roszczeń uzyskanych z tokenu. Ten wystawca powinien odpowiadać wystawcy tokenu lub urzędu, który jest odpowiedzialny za sprawdzanie poprawności zawartości tokenu. W poniższym przykładzie używane jest zastrzeżenie wystawcy, które zostało przesłane do tej klasy z niestandardowego wystawcy uwierzytelnienia tokenu zabezpieczeń utworzonego w poprzedniej procedurze. Niestandardowy wystawca uwierzytelnienia tokenów zabezpieczających używa zestawu roszczeń dostarczonych przez system (zwracanego przez <xref:System.IdentityModel.Claims.ClaimSet.System%2A> Właściwość) do reprezentowania wystawcy tokenu nazwy użytkownika.  
  
4. Zaimplementuj <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%2A> metodę. Ta metoda wypełnia wystąpienie <xref:System.IdentityModel.Policy.EvaluationContext> klasy (przekazywane jako argument) z oświadczeniami opartymi na zawartości przychodzącego tokenu zabezpieczającego. Metoda zwraca, `true` gdy jest wykonywane z oceną. W przypadkach, gdy implementacja opiera się na obecności innych zasad autoryzacji, które dostarczają dodatkowych informacji do kontekstu oceny, ta metoda może zwrócić, `false` Jeśli wymagane informacje nie są jeszcze obecne w kontekście oceny. W takim przypadku WCF wywoła metodę ponownie po ocenie wszystkich innych zasad autoryzacji wygenerowanych dla komunikatu przychodzącego, jeśli co najmniej jedna z tych zasad autoryzacji zmodyfikował kontekst oceny.  
  
     [!code-csharp[c_CustomTokenAuthenticator#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtokenauthenticator/cs/source.cs#3)]
     [!code-vb[c_CustomTokenAuthenticator#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtokenauthenticator/vb/source.vb#3)]  

 [Przewodnik: Tworzenie niestandardowych poświadczeń klienta i usługi](walkthrough-creating-custom-client-and-service-credentials.md) zawiera opis sposobu tworzenia poświadczeń niestandardowych i niestandardowego menedżera tokenów zabezpieczających. Aby użyć niestandardowego wystawcy uwierzytelniania tokenów zabezpieczających utworzony w tym miejscu, implementacja Menedżera tokenów zabezpieczeń została zmodyfikowana w celu zwrócenia niestandardowej wystawcy uwierzytelnienia z <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenAuthenticator%2A> metody. Metoda zwraca wystawcę uwierzytelnienia, gdy wymagane jest odpowiednie wymaganie tokenu zabezpieczającego.  
  
#### <a name="to-integrate-a-custom-security-token-authenticator-with-a-custom-security-token-manager"></a>Aby zintegrować niestandardowy wystawca uwierzytelnienia tokenu zabezpieczeń z menedżerem niestandardowego tokenu zabezpieczeń  
  
1. Zastąp <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenAuthenticator%2A> metodę w niestandardowej implementacji Menedżera tokenów zabezpieczających.  
  
2. Dodaj logikę do metody, aby umożliwić jej zwrócenie niestandardowej wystawcy uwierzytelnienia tokenu zabezpieczającego na podstawie <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> parametru. Poniższy przykład zwraca niestandardową wystawcę uwierzytelnienia tokenu zabezpieczającego, jeśli typ tokenu wymagania tokenu to nazwa użytkownika (reprezentowana przez <xref:System.IdentityModel.Tokens.SecurityTokenTypes.UserName%2A> Właściwość) i kierunek komunikatu, dla którego żąda się wystawcy uwierzytelnienia tokenu zabezpieczającego, to dane wejściowe (reprezentowane przez <xref:System.ServiceModel.Description.MessageDirection.Input> pole).  
  
     [!code-csharp[c_CustomTokenAuthenticator#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtokenauthenticator/cs/source.cs#2)]
     [!code-vb[c_CustomTokenAuthenticator#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtokenauthenticator/vb/source.vb#2)]  

## <a name="see-also"></a>Zobacz też

- <xref:System.IdentityModel.Selectors.SecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SecurityTokenRequirement>
- <xref:System.IdentityModel.Selectors.SecurityTokenManager>
- <xref:System.IdentityModel.Tokens.UserNameSecurityToken>
- [Przewodnik: tworzenie niestandardowego klienta i poświadczeń usługi](walkthrough-creating-custom-client-and-service-credentials.md)
- [Instrukcje: tworzenie niestandardowego dostawcy tokenów zabezpieczeń](how-to-create-a-custom-security-token-provider.md)
