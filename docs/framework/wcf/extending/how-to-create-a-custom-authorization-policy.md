---
title: 'Instrukcje: tworzenie niestandardowych zasad autoryzacji'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 05b0549b-882d-4660-b6f0-5678543e5475
ms.openlocfilehash: fef7aa531c946ecacef30bb79f2362bad4d375ed
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96256030"
---
# <a name="how-to-create-a-custom-authorization-policy"></a>Instrukcje: tworzenie niestandardowych zasad autoryzacji

Infrastruktura modelu tożsamości w Windows Communication Foundation (WCF) obsługuje model autoryzacji oparty na żądaniach. Oświadczenia są wyodrębniane z tokenów, opcjonalnie przetworzonych przez niestandardowe zasady autoryzacji, a następnie umieszczane w usłudze <xref:System.IdentityModel.Policy.AuthorizationContext> , które następnie można sprawdzić w celu podejmowania decyzji dotyczących autoryzacji. Zasady niestandardowe mogą służyć do przekształcania oświadczeń z tokenów przychodzących do oświadczeń oczekiwanych przez aplikację. W ten sposób warstwa aplikacji może być izolowana od szczegółowych informacji o różnych oświadczeniach, które są obsługiwane przez różne typy tokenów obsługiwanych przez funkcję WCF. W tym temacie pokazano, jak zaimplementować niestandardowe zasady autoryzacji i jak dodać te zasady do kolekcji zasad używanych przez usługę.  
  
### <a name="to-implement-a-custom-authorization-policy"></a>Aby zaimplementować niestandardowe zasady autoryzacji  
  
1. Zdefiniuj nową klasę, która pochodzi od <xref:System.IdentityModel.Policy.IAuthorizationPolicy> .  
  
2. Zaimplementuj <xref:System.IdentityModel.Policy.IAuthorizationComponent.Id%2A> Właściwość tylko do odczytu, generując unikatowy ciąg w konstruktorze klasy i zwracając ten ciąg za każdym razem, gdy uzyskuje się dostęp do właściwości.  
  
3. Zaimplementuj właściwość tylko do odczytu, <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Issuer%2A> zwracając element <xref:System.IdentityModel.Claims.ClaimSet> reprezentujący wystawcę zasad. Może to być element `ClaimSet` reprezentujący aplikację lub wbudowaną `ClaimSet` (na przykład `ClaimSet` zwracaną przez właściwość statyczną <xref:System.IdentityModel.Claims.ClaimSet.System%2A> .  
  
4. Zaimplementuj <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> metodę zgodnie z opisem w poniższej procedurze.  
  
### <a name="to-implement-the-evaluate-method"></a>Aby zaimplementować metodę szacowania  
  
1. Do tej metody są przesyłane dwa parametry: wystąpienie <xref:System.IdentityModel.Policy.EvaluationContext> klasy i odwołania do obiektu.  
  
2. Jeśli niestandardowe zasady autoryzacji dodaje <xref:System.IdentityModel.Claims.ClaimSet> wystąpienia bez względu na bieżącą zawartość <xref:System.IdentityModel.Policy.EvaluationContext> , a następnie Dodaj każdy z nich, `ClaimSet` wywołując <xref:System.IdentityModel.Policy.EvaluationContext.AddClaimSet%28System.IdentityModel.Policy.IAuthorizationPolicy%2CSystem.IdentityModel.Claims.ClaimSet%29> metodę i zwracają `true` z <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%2A> metody. Zwrócenie `true` wskazuje na infrastrukturę autoryzacji, że zasady autoryzacji wykonała swoją pracy i nie muszą być ponownie wywoływane.  
  
3. Jeśli niestandardowe zasady autoryzacji dodają zestawy oświadczeń tylko wtedy, gdy pewne oświadczenia znajdują się już w `EvaluationContext` , należy poszukać tych oświadczeń poprzez sprawdzenie `ClaimSet` wystąpień zwracanych przez <xref:System.IdentityModel.Policy.EvaluationContext.ClaimSets%2A> Właściwość. Jeśli oświadczenia są obecne, Dodaj nowe zestawy oświadczeń przez wywołanie <xref:System.IdentityModel.Policy.EvaluationContext.AddClaimSet%28System.IdentityModel.Policy.IAuthorizationPolicy%2CSystem.IdentityModel.Claims.ClaimSet%29> metody i, jeśli nie ma więcej zestawów oświadczeń, zwróć `true` , wskazując na infrastrukturę autoryzacji, że zasady autoryzacji ukończyły pracę. Jeśli oświadczenia nie są obecne, zwróć `false` , wskazując, że zasady autoryzacji powinny być ponownie wywoływane, jeśli inne zasady autoryzacji dodają więcej zestawów oświadczeń do `EvaluationContext` .  
  
4. W bardziej złożonych scenariuszach przetwarzania drugi parametr <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> metody jest używany do przechowywania zmiennej stanu, którą infrastruktura autoryzacji przejdzie z powrotem podczas każdego kolejnego wywołania <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> metody dla określonej oceny.  
  
### <a name="to-specify-a-custom-authorization-policy-through-configuration"></a>Aby określić niestandardowe zasady autoryzacji za pomocą konfiguracji  
  
1. Określ typ niestandardowych zasad autoryzacji w atrybucie w elemencie elementu `policyType` `add` w elemencie `authorizationPolicies` `serviceAuthorization` .  
  
    ```xml  
    <configuration>  
     <system.serviceModel>  
      <behaviors>  
        <serviceAuthorization serviceAuthorizationManagerType=  
                  "Samples.MyServiceAuthorizationManager" >  
          <authorizationPolicies>  
            <add policyType="Samples.MyAuthorizationPolicy" />  
          </authorizationPolicies>  
        </serviceAuthorization>  
      </behaviors>  
     </system.serviceModel>  
    </configuration>  
    ```  
  
### <a name="to-specify-a-custom-authorization-policy-through-code"></a>Aby określić niestandardowe zasady autoryzacji za pomocą kodu  
  
1. Utwórz element <xref:System.Collections.Generic.List%601> <xref:System.IdentityModel.Policy.IAuthorizationPolicy> .  
  
2. Utwórz wystąpienie niestandardowych zasad autoryzacji.  
  
3. Dodaj wystąpienie zasad autoryzacji do listy.  
  
4. Powtórz kroki 2 i 3 dla każdej niestandardowej zasady autoryzacji.  
  
5. Przypisz do właściwości wersję z listy tylko do odczytu <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A> .  
  
     [!code-csharp[c_CustomAuthPol#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthpol/cs/c_customauthpol.cs#8)]
     [!code-vb[c_CustomAuthPol#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthpol/vb/source.vb#8)]  
  
## <a name="example"></a>Przykład  

 Poniższy przykład pokazuje kompletną <xref:System.IdentityModel.Policy.IAuthorizationPolicy> implementację.  
  
 [!code-csharp[c_CustomAuthPol#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthpol/cs/c_customauthpol.cs#5)]
 [!code-vb[c_CustomAuthPol#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthpol/vb/source.vb#5)]  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.ServiceModel.ServiceAuthorizationManager>
- [Instrukcje: porównywanie oświadczeń](how-to-compare-claims.md)
- [Instrukcje: tworzenie menedżera autoryzacji niestandardowej dla usługi](how-to-create-a-custom-authorization-manager-for-a-service.md)
- [Zasady autoryzacji](../samples/authorization-policy.md)
