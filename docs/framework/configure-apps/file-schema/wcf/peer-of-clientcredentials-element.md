---
title: <peer><clientCredentials>elementu
ms.date: 03/30/2017
ms.assetid: 505bd987-0042-4622-b68e-94f439729d53
ms.openlocfilehash: 75d8543d7db5eee1345d54f934fc89c9593b85ac
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91186994"
---
# <a name="peer-of-clientcredentials-element"></a>\<peer>\<clientCredentials>elementu

Określa poświadczenia używane podczas uwierzytelniania klientów równorzędnych.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<peer>**  
  
## <a name="syntax"></a>Składnia  
  
```xml  
<peer>
  <certificate />
  <peerAuthentication />
  <messageSenderAuthentication />
</peer>
```  
  
## <a name="attributes-and-elements"></a>Atrybuty i elementy  

 W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.  
  
### <a name="attributes"></a>Atrybuty  

 Brak.  
  
### <a name="child-elements"></a>Elementy podrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|[\<certificate>](certificate-element.md)|Określa certyfikat X. 509 używany do podpisywania i szyfrowania komunikatów dla klientów równorzędnych. .|  
|[\<peerAuthentication>](peerauthentication-element.md)|Określa opcje uwierzytelniania dla klientów równorzędnych.|  
|[\<messageSenderAuthentication>](messagesenderauthentication-element.md)|Określa opcje uwierzytelniania dla nadawców wiadomości.|  
  
### <a name="parent-elements"></a>Elementy nadrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|Określa poświadczenia używane do uwierzytelniania klienta w usłudze.|  
  
## <a name="remarks"></a>Uwagi  

 Ten element konfiguracji określa poświadczenia używane przez węzeł równorzędny do samodzielnego uwierzytelnienia w innych węzłach w sieci, a także ustawień uwierzytelniania używanych przez węzeł równorzędny do uwierzytelniania innych węzłów równorzędnych. Aby uzyskać więcej informacji, zobacz [uwierzytelnianie komunikatów kanału równorzędnego](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90)) i [Zabezpieczanie aplikacji kanału równorzędnego](../../../wcf/feature-details/securing-peer-channel-applications.md).  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Peer%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.Peer%2A>
- <xref:System.ServiceModel.Security.PeerCredential>
- [Sieci równorzędne](../../../wcf/feature-details/peer-to-peer-networking.md)
- [Zabezpieczanie klientów [WCF]](../../../wcf/securing-clients.md)
- [Uwierzytelnianie komunikatów kanału równorzędnego](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))
- [Uwierzytelnianie niestandardowe kanału równorzędnego](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))
- [Zabezpieczanie aplikacji kanałów równorzędnych](../../../wcf/feature-details/securing-peer-channel-applications.md)
- [Zabezpieczanie usług i klientów](../../../wcf/feature-details/securing-services-and-clients.md)
