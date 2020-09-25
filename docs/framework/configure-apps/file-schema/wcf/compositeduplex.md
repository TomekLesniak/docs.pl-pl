---
title: <compositeDuplex>
ms.date: 03/30/2017
ms.assetid: 725004d1-ce88-4405-a220-78e89844f81f
ms.openlocfilehash: a5209efddd489f8cb04b3266e6ba0bb033eeae6c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176022"
---
# \<compositeDuplex>

Definiuje element powiązania, który jest używany, gdy klient musi uwidocznić punkt końcowy dla usługi w celu wysłania komunikatów z powrotem do klienta.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<compositeDuplex>**  
  
## <a name="syntax"></a>Składnia  
  
```xml  
<compositeDuplex clientBaseAddress="URI" />
```  
  
## <a name="attributes-and-elements"></a>Atrybuty i elementy  

 W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.  
  
### <a name="attributes"></a>Atrybuty  
  
|Atrybut|Opis|  
|---------------|-----------------|  
|clientBaseAddress|Identyfikator URI, który ustawia adres kanału zwrotnego w trybie dupleksu. Usługa używa tego adresu do nawiązywania kontaktu i nawiązania połączenia z klientem.<br /><br /> Jeśli ten atrybut nie jest ustawiony, zostanie wygenerowany domyślny adres " `full qualified name+default port\TemporaryIndigoAddress\guid` ". Wartość domyślna to `null`.|  
  
### <a name="child-elements"></a>Elementy podrzędne  

 Brak  
  
### <a name="parent-elements"></a>Elementy nadrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|Definiuje wszystkie możliwości powiązań niestandardowego powiązania.|  
  
## <a name="remarks"></a>Uwagi  

 Ten element konfiguracji jest używany z transportami, które nie zezwalają na natywną komunikację bezstronną, na przykład HTTP. Protokół TCP, w przeciwieństwie, umożliwia natywną komunikację bezstronną i nie wymaga użycia tego elementu powiązania dla usługi do wysyłania komunikatów z powrotem do klienta.  
  
 Klient musi uwidocznić adres usługi, aby nawiązać kontakt i nawiązać połączenie. Ten adres klienta jest dostarczany przez `clientBaseAddress` atrybut. Należy pamiętać, że Windows Communication Foundation (WCF) automatycznie generuje element ClientBaseAddress, jeśli nie został jawnie ustawiony przez użytkownika.  
  
## <a name="example"></a>Przykład  
  
```xml  
<compositeDuplex clientBaseAddress="http://www.contoso.com" />
```  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.ServiceModel.Configuration.CompositeDuplexElement>
- <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Powiązania](../../../wcf/bindings.md)
- [Rozszerzanie powiązań](../../../wcf/extending/extending-bindings.md)
- [Powiązania niestandardowe](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
