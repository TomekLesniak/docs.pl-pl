---
title: <bindingElementExtensions>
ms.date: 03/30/2017
ms.assetid: bb597fc0-c947-451c-afda-bf23d42f4f4d
ms.openlocfilehash: 6ba97adfa696e00b4d6b75faf104c31436e25447
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91151133"
---
# \<bindingElementExtensions>

Ta sekcja umożliwia korzystanie z niestandardowego elementu powiązania z pliku konfiguracji komputera lub aplikacji. Można dodać niestandardowy element powiązania do tej kolekcji przy użyciu `add` słowa kluczowego i ustawić `type` atrybut elementu na rozszerzenie elementu powiązania, a także `name` atrybut elementu niestandardowego powiązania.  
  
 Rozszerzenia powiązań umożliwiają użytkownikowi tworzenie elementów powiązania zdefiniowanych przez użytkownika do użycia w ramach powiązań niestandardowych. Programowe rozszerzenie powiązania jest typem, który implementuje klasę abstrakcyjną <xref:System.ServiceModel.Channels.BindingElement> . W pliku konfiguracji `bindingElementExtensions` sekcja służy do definiowania elementu rozszerzenia.  
  
 Poniższy przykład używa `add` elementu, a także `name` atrybutu, aby dodać rozszerzenie powiązania do `bindingElementExtensions` sekcji pliku konfiguracji.  
  
```xml  
<system.serviceModel>
  <extensions>
    <bindingElementExtensions>
      <add name="udpTransport"
           type="Microsoft.ServiceModel.Samples.UdpTransportSection, UdpTransport,
                 Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />
    </bindingElementExtensions>
  </extensions>
</system.serviceModel>
```  
  
 Aby dodać możliwości konfiguracji do elementu, użytkownik musi napisać i zarejestrować `bindingElementExtensionSection` element. Aby uzyskać więcej informacji na ten temat, zapoznaj się z <xref:System.Configuration> dokumentacją.  
  
 Po zdefiniowaniu elementu i jego typu konfiguracji rozszerzenie może być używane jako część niestandardowego powiązania, jak pokazano w poniższym przykładzie.  
  
```xml  
<customBinding>
  <binding name="test2">
    <udpTransport />
    <binaryMessageEncoding maxReadPoolSize="211"
                           maxWritePoolSize="2132"
                           maxSessionSize="3141" />
  </binding>
</customBinding>
```  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.ServiceModel.Configuration.BindingElementExtensionElement>
- [Rozszerzanie powiązań](../../../wcf/extending/extending-bindings.md)
