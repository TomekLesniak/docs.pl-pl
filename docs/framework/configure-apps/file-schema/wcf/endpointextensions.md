---
title: <endpointExtensions>
ms.date: 03/30/2017
ms.assetid: 33396e0a-1fae-4616-b822-923584eebfd1
ms.openlocfilehash: d0587ae942d1b0c7eb72bee830ca3ced76e4270c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91190036"
---
# \<endpointExtensions>

Ta sekcja rejestruje nowy standardowy punkt końcowy w sekcji rozszerzeń w pliku konfiguracyjnym komputera lub aplikacji. Można dodać standardowy punkt końcowy do tej kolekcji przy użyciu `add` słowa kluczowego i ustawić `type` atrybut elementu na typ punktu końcowego, a także `name` atrybut na nazwę standardowego punktu końcowego.  
  
 W poniższym przykładzie użyto `add` elementu, a także `name` atrybutu, aby dodać standardowy punkt końcowy do `<endpointExtensions>` sekcji pliku konfiguracji.  
  
```xml  
<system.serviceModel>
  <extensions>
    <endpointExtensions>
      <add name="udpDiscoveryEndpoint"
           type="System.Discovery.UdpEndpointCollectionElement, System.Discovery.dll, Version=1.0.0.0, Culture=neutral, PublicKeyToken=ffffffffffffffff"/>
    </endpointExtensions>
  </extensions>
</system.serviceModel>
```  
  
 Po zarejestrowaniu standardowego punktu końcowego można go użyć, jak pokazano w poniższym przykładzie. W [\<endpoint>](endpoint-element.md) elemencie `kind` atrybut określa standardowy typ punktu końcowego, który został zarejestrowany w `<endpointExtensions>` sekcji. Ten `endpointConfiguration` atrybut będzie taki sam jak `name` atrybut elementu konfiguracji standardowego punktu końcowego w `<standardEndpoints>` sekcji.  
  
```xml  
<system.serviceModel>
  <services>
    <service name="Service1">
      <endpoint kind="udpDiscoveryEndpoint"
                endpointConfiguration="udpConfig" />
    </service>
  </services>
  <standardEndpoints>
    <udpDiscoveryEndpoint>
      <standardEndpoint name="udpConfig"
                        multicastAddress="soap.udp://239.255.255.250:3703"
                        ... />
    </udpDiscoveryEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
