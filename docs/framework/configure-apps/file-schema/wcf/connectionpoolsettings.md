---
title: <connectionPoolSettings>
ms.date: 03/30/2017
ms.assetid: 6fa7fa65-2c6e-4eab-b8cf-7690112c0be5
ms.openlocfilehash: d8787bc2ef8da4fdc01237ac9b041dfdd66fce03
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91175996"
---
# \<connectionPoolSettings>

Określa dodatkowe ustawienia puli połączeń dla powiązania nazwanego potoku.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedPipeTransport>**](namedpipetransport.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<connectionPoolSettings>**  
  
## <a name="syntax"></a>Składnia  
  
```xml  
<connectionPoolSettings groupName="String"
                        idleTimeout="TimeSpan"
                        maxOutboundConnectionsPerEndpoint="Integer" />
```  
  
## <a name="attributes-and-elements"></a>Atrybuty i elementy  

 W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.  
  
### <a name="attributes"></a>Atrybuty  
  
|Atrybut|Opis|  
|---------------|-----------------|  
|`groupName`|Ciąg określający nazwę puli połączeń używanej dla kanałów wychodzących. W trybie przesyłania strumieniowego połączenia nie są udostępniane, co oznacza, że buforowanie połączeń jest wyłączone. Wartość domyślna to ciąg "default". Możesz zmodyfikować tę wartość, aby wyizolować połączenia dla określonego klienta w oddzielnych grupach.|  
|`idleTimeout`|Wartość dodatnia <xref:System.TimeSpan> , która określa maksymalny czas bezczynności połączenia przed jego rozłączeniem. Wartość domyślna to 00:02:00.|  
|`maxOutboundConnectionsPerEndpoint`|Dodatnia liczba całkowita, która określa maksymalną liczbę połączeń ze zdalnym punktem końcowym inicjowanym przez usługę. Połączenia przekraczające limit są umieszczane w kolejce do momentu udostępnienia odstępu poniżej limitu. `idleTimeout`Ogranicza czas, w którym połączenia pozostają w kolejce przed zgłoszeniem wyjątku. Wartość domyślna to 10.<br /><br /> Ten atrybut ogranicza liczbę jednoczesnych aktywnych połączeń z klienta do określonego punktu końcowego usługi. W przypadku przekroczenia tej wartości przy użyciu większej liczby aktywnych połączeń z klientem usługa może nie odpowiadać na klienta. W takim przypadku ta wartość powinna zostać zmieniona, aby przekroczyć maksymalną dozwoloną liczbę równoczesnych połączeń klienta do określonego punktu końcowego.|  
  
### <a name="child-elements"></a>Elementy podrzędne  

 Brak.  
  
### <a name="parent-elements"></a>Elementy nadrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|[\<namedPipeTransport>](namedpipetransport.md)|Definiuje transport, który powoduje, że kanał przesyła komunikaty przy użyciu nazwanych potoków.|  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.ServiceModel.Configuration.NamedPipeConnectionPoolSettingsElement>
- <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement.ConnectionPoolSettings%2A>
- <xref:System.ServiceModel.Channels.NamedPipeConnectionPoolSettings>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Transporty](../../../wcf/feature-details/transports.md)
- [Wybieranie transportu](../../../wcf/feature-details/choosing-a-transport.md)
- [Powiązania](../../../wcf/bindings.md)
- [Rozszerzanie powiązań](../../../wcf/extending/extending-bindings.md)
- [Powiązania niestandardowe](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
