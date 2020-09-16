---
title: <custom>
ms.date: 03/30/2017
ms.assetid: a6f65a00-bd1a-4d4a-955a-fe009ec02ab8
ms.openlocfilehash: 4077aacab1c1c4594db76cc6663bfc0245d345d7
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555500"
---
# \<custom>
Określa ustawienia niestandardowej usługi rozpoznawania elementów równorzędnych.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<resolver>**](resolver.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<custom>**  
  
## <a name="syntax"></a>Składnia  
  
```xml  
<custom address="Uri"
        resolverType="String">
  <headers/>
  <identity/>
</custom>
```  
  
## <a name="attributes-and-elements"></a>Atrybuty i elementy  
 W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.  
  
### <a name="attributes"></a>Atrybuty  
  
|Atrybut|Opis|  
|---------------|-----------------|  
|`address`|Identyfikator URI, który określa adres punktu końcowego węzła równorzędnego, który hostuje niestandardową usługę rozpoznawania elementów równorzędnych.|  
|`resolverType`|Ciąg określający typ niestandardowej usługi rozpoznawania elementów równorzędnych.|  
  
### <a name="child-elements"></a>Elementy podrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|[\<identity>](identity.md)|Określa tożsamość niestandardowych resolverów równorzędnych skonfigurowanych przy użyciu tego elementu. Ten element jest typu <xref:System.ServiceModel.Configuration.IdentityElement> .|  
|[\<headers>](headers-element.md)|Kolekcja nagłówka adresu używana dla komunikatów SOAP obsłużonych przez niestandardowy program rozpoznawania elementów równorzędnych.|  
  
### <a name="parent-elements"></a>Elementy nadrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|[\<resolver>](resolver.md)|Równorzędny program rozpoznawania używany do rozpoznawania identyfikatora siatki równorzędnej w zestawie adresów węzłów równorzędnych reprezentujących kilka węzłów, które uczestniczą w sieci.|  
  
## <a name="remarks"></a>Uwagi  
 Ten element definiuje podstawowe ustawienia dla niestandardowej usługi rozpoznawania elementów równorzędnych, w tym adres punktu końcowego elementu równorzędnego obsługującego usługę i wszystkie określone ustawienia powiązań. Aby uzyskać więcej informacji na temat tworzenia niestandardowego programu rozpoznawania nazw, zobacz [Dodawanie niestandardowego programu rozpoznawania nazw do aplikacji PeerChannel](/previous-versions/ms730105(v=vs.90)).  
  
## <a name="see-also"></a>Zobacz także

- <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService>
- <xref:System.ServiceModel.PeerResolvers.PeerCustomResolverSettings>
- <xref:System.ServiceModel.Configuration.PeerResolverElement.Custom%2A>
- <xref:System.ServiceModel.Configuration.PeerCustomResolverElement>
- [Mechanizmy rozpoznawania elementów równorzędnych](../../../wcf/feature-details/peer-resolvers.md)
- [Dodawanie niestandardowego programu rozpoznawania nazw do aplikacji PeerChannel](/previous-versions/ms730105(v=vs.90))
