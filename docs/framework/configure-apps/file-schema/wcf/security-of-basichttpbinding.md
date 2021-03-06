---
title: <security> dla <basicHttpBinding>
ms.date: 03/30/2017
ms.assetid: 6432708d-5465-4bd9-bfc2-466742db99cb
ms.openlocfilehash: 6144e5448526d7f2a7c89693f70f71a7f26c4a22
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183666"
---
# <a name="security-of-basichttpbinding"></a>\<security> dla \<basicHttpBinding>

Definiuje możliwości zabezpieczeń programu [\<basicHttpBinding>](basichttpbinding.md) .  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<basicHttpBinding>**](basichttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a>Składnia  
  
```xml  
<security mode="Message/None/Transport/TransportWithCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             realm="string" />
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />
</security>
```  
  
## <a name="attributes-and-elements"></a>Atrybuty i elementy  

 W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.  
  
### <a name="attributes"></a>Atrybuty  
  
|Atrybut|Opis|  
|---------------|-----------------|  
|tryb|Opcjonalny. Określa typ używanego zabezpieczenia. Wartość domyślna to `None`. Ten atrybut jest typu <xref:System.ServiceModel.BasicHttpSecurityMode> .|  
  
## <a name="mode-attribute"></a>Atrybut Mode  
  
|Wartość|Opis|  
|-----------|-----------------|  
|Brak|-Komunikaty nie są zabezpieczane podczas transferu.|  
|Transport|Zabezpieczenia są udostępniane przy użyciu protokołu HTTPS. Komunikaty protokołu SOAP są zabezpieczone przy użyciu protokołu HTTPS. Usługa jest uwierzytelniana na kliencie przy użyciu certyfikatu X. 509 usługi. Klient jest uwierzytelniany przy użyciu dostarczonego obiekt ClientCredentialtype. Zobacz [\<transport>](transport-of-basichttpbinding.md) .|  
|Wiadomość|Zabezpieczenia są udostępniane przy użyciu zabezpieczeń komunikatów protokołu SOAP. Domyślnie treść jest zaszyfrowana i podpisana. W przypadku tego powiązania system wymaga, aby certyfikat serwera został dostarczony do klienta poza pasmem. Jedyna prawidłowa `ClientCredentialType` dla tego powiązania to `Certificate` .|  
|TransportWithMessageCredential|Integralność, poufność i uwierzytelnianie serwera są udostępniane przez zabezpieczenia transportu. Uwierzytelnianie klienta jest zapewniane przez zabezpieczenia komunikatów protokołu SOAP. Ten tryb jest istotny, gdy użytkownik jest uwierzytelniany przy użyciu nazwy użytkownika/hasła i istnieje wdrożenie HTTP na potrzeby zabezpieczania transferu komunikatów.|  
|TransportCredentialOnly|Ten tryb nie zapewnia integralności i poufności komunikatów. Zapewnia uwierzytelnianie klienta oparte na protokole HTTP. Ten tryb powinien być używany z zachowaniem ostrożności. Powinna być używana w środowiskach, w których zabezpieczenia transportu są dostarczane przy użyciu innych metod (takich jak IPSec) i tylko uwierzytelnianie klienta jest udostępniane przez infrastrukturę WCF.|  
  
### <a name="child-elements"></a>Elementy podrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|[\<transport>](transport-of-basichttpbinding.md)|Definiuje ustawienia zabezpieczeń transportu dla podstawowej usługi HTTP. Ten element odnosi się do <xref:System.ServiceModel.HttpTransportSecurity> .|  
|[\<message>](message-of-basichttpbinding.md)|Definiuje ustawienia zabezpieczeń wiadomości dla podstawowej usługi HTTP. Ten element odnosi się do <xref:System.ServiceModel.BasicHttpMessageSecurity> .|  
  
### <a name="parent-elements"></a>Elementy nadrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|powiązanie|Element Binding elementu [\<basicHttpBinding>](basichttpbinding.md) .|  
  
## <a name="remarks"></a>Uwagi  

 Domyślnie komunikat protokołu SOAP nie jest zabezpieczony i klient nie jest uwierzytelniany. Ten element umożliwia skonfigurowanie dodatkowych ustawień zabezpieczeń dla `basicHttpBinding` elementu.  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.ServiceModel.BasicHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [Zabezpieczanie usług i klientów](../../../wcf/feature-details/securing-services-and-clients.md)
- [Wybieranie typu poświadczeń](../../../wcf/feature-details/selecting-a-credential-type.md)
- [Powiązania](../../../wcf/bindings.md)
- [Konfigurowanie powiązań dostarczanych przez system](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Konfigurowanie usług i klientów za pomocą wiązań](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
