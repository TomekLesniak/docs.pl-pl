---
title: <protocolMapping>
ms.date: 03/30/2017
ms.assetid: 5076644b-1f33-4f26-9488-87de9fcda04c
ms.openlocfilehash: 0a79aa18c74ddb8ec47f02620d16d391b4a36b68
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91162299"
---
# \<protocolMapping>

Reprezentuje sekcję konfiguracyjną służącą do definiowania zestawu domyślnego mapowania protokołów między schematami protokołu transportowego (np. http, net. TCP, net. pipe itp.) i powiązaniami WCF. Podczas tworzenia domyślnych punktów końcowych w czasie wykonywania Windows Communication Foundation (WCF) przegląda skonfigurowane mapowania i decyduje o tym, które powiązanie ma być używane dla określonego adresu.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<protocolMapping>**  
  
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

 Brak.  
  
### <a name="child-elements"></a>Elementy podrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|[\<filters>](filters-of-routing.md)|Zawiera domyślne mapowanie protokołu między schematem protokołu transportowego (np. http, net. TCP, net. pipe itp.) i powiązaniem WCF.|  
  
### <a name="parent-elements"></a>Elementy nadrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|[\<system.serviceModel>](system-servicemodel.md)|Element główny wszystkich elementów konfiguracji WCF.|  
  
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
