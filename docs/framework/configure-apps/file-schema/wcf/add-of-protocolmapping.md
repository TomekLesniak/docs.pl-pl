---
title: <add> dla <protocolMapping>
ms.date: 03/30/2017
ms.assetid: 08e62249-1641-41d1-91b1-66d7b46244e4
ms.openlocfilehash: 46ba21b65f524f88bfce81739f0cd73040a2ad45
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91205012"
---
# <a name="add-of-protocolmapping"></a>\<add> dla \<protocolMapping>

Reprezentuje domyślne mapowanie protokołu między schematem protokołu transportowego (np. http, net. TCP, net. pipe itp.) i powiązaniem Windows Communication Foundation (WCF). Podczas tworzenia domyślnych punktów końcowych w środowisku uruchomieniowym środowisko WCF przegląda skonfigurowane mapowania i decyduje o tym, które powiązanie ma być używane dla określonego adresu.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<protocolMapping>**](protocolmapping.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a>Składnia  
  
```xml  
<protocolMapping>
  <add binding="String"
       bindingConfiguration="String"
       scheme="http/net.msmq/net.pipe/net.tcp" />
</protocolMapping>
```  
  
## <a name="attributes-and-elements"></a>Atrybuty i elementy  

 W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.  
  
### <a name="attributes"></a>Atrybuty  
  
|Element|Opis|  
|-------------|-----------------|  
|powiązanie|Ciąg określający typ powiązania, które ma być używane dla punktu końcowego podczas domyślnego tworzenia punktu końcowego.|  
|bindingConfiguration|Ciąg określający nazwę sekcji konfiguracji powiązania, do której ma zostać utworzone odwołanie.|  
|schemat|Schemat protokołu transportowego, który ma być używany dla domyślnego punktu końcowego.|  
  
### <a name="child-elements"></a>Elementy podrzędne  

 Brak.  
  
### <a name="parent-elements"></a>Elementy nadrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|[\<protocolMapping>](protocolmapping.md)|Reprezentuje sekcję konfiguracji definiującą domyślne mapowania protokołów między schematami protokołu transportowego (np. http, net. TCP, net. pipe itp.) i powiązaniami Windows Communication Foundation (WCF).|  
  
## <a name="example"></a>Przykład  

 Poniższy przykład konfiguracji przedstawia mapowanie domyślnego protokołu w pliku machine.config. To mapowanie domyślne można zastąpić na poziomie komputera, modyfikując plik machine.config. Lub jeśli chcesz, aby przesłonić ją tylko w ramach zakresu aplikacji, możesz zastąpić tę sekcję w pliku konfiguracji aplikacji i zmienić mapowanie poszczególnych schematów protokołu.  
  
```xml  
<protocolMapping>
  <add scheme="http"
       binding="basicHttpBinding" />
  <add scheme="net.tcp"
       binding="netTcpBinding" />
  <add scheme="net.pipe"
       binding="netNamedPipeBinding" />
  <add scheme="net.msmq"
       binding="netMsmqBinding" />
</protocolMapping>
```  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.ServiceModel.Configuration.ProtocolMappingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Configuration.ProtocolMappingElement?displayProperty=nameWithType>
