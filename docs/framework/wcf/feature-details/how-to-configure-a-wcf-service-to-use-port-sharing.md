---
title: 'Instrukcje: Konfigurowanie usługi Windows Communication Foundation na potrzeby współużytkowania portów'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6400bc71-a858-4ac2-8d5a-caa72d3b5482
ms.openlocfilehash: 39b9da1096c38eba648f528f7c2b3ecaa39ab7c2
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96257512"
---
# <a name="how-to-configure-a-windows-communication-foundation-service-to-use-port-sharing"></a>Instrukcje: Konfigurowanie usługi Windows Communication Foundation na potrzeby współużytkowania portów

Najprostszym sposobem korzystania z net. TCP://udostępniania portów w aplikacji Windows Communication Foundation (WCF) jest udostępnienie usługi przy użyciu <xref:System.ServiceModel.NetTcpBinding> .  
  
 To powiązanie zawiera <xref:System.ServiceModel.NetTcpBinding.PortSharingEnabled%2A> Właściwość, która kontroluje, czy jest włączone udostępnianie net. TCP://portu dla usługi skonfigurowanej przy użyciu tego powiązania.  
  
 Poniższa procedura pokazuje, jak używać <xref:System.ServiceModel.NetTcpBinding> klasy do otwierania punktu końcowego w Uniform Resource Identifier (URI) net. TCP://localhost/MyService, najpierw w kodzie, a następnie za pomocą elementów konfiguracji.  
  
### <a name="to-enable-nettcp-port-sharing-on-a-nettcpbinding-in-code"></a>Aby włączyć udostępnianie za pomocą protokołu net. TCP://portu na NetTcpBinding w kodzie  
  
1. Utwórz usługę do implementowania kontraktu o nazwie `IMyService` i Wywołaj ją `MyService` ,.  
  
     [!code-csharp[c_ConfigurePortSharing#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_configureportsharing/cs/source.cs#1)]
     [!code-vb[c_ConfigurePortSharing#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_configureportsharing/vb/source.vb#1)]  
  
2. Utwórz wystąpienie <xref:System.ServiceModel.NetTcpBinding> klasy i ustaw <xref:System.ServiceModel.NetTcpBinding.PortSharingEnabled%2A> Właściwość na `true` .  
  
     [!code-csharp[c_ConfigurePortSharing#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_configureportsharing/cs/source.cs#2)]
     [!code-vb[c_ConfigurePortSharing#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_configureportsharing/vb/source.vb#2)]  
  
3. Utwórz <xref:System.ServiceModel.ServiceHost> i Dodaj do niego punkt końcowy usługi dla programu `MyService` , który korzysta z włączonego udostępniania portów <xref:System.ServiceModel.NetTcpBinding> i który nasłuchuje pod adresem punktu końcowego URI "net. TCP://localhost/MyService".  
  
     [!code-csharp[c_ConfigurePortSharing#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_configureportsharing/cs/source.cs#3)]
     [!code-vb[c_ConfigurePortSharing#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_configureportsharing/vb/source.vb#3)]  
  
    > [!NOTE]
    > W tym przykładzie jest stosowany domyślny port TCP 808, ponieważ identyfikator URI adresu punktu końcowego nie określa innego numeru portu. Ponieważ Udostępnianie portów jest jawnie włączone dla powiązania transportowego, ta usługa może współużytkować port 808 z innymi usługami w innych procesach. Jeśli Udostępnianie portów było niedozwolone, a inna aplikacja już korzysta z portu 808, ta usługa spowodowałaby zgłoszenie <xref:System.ServiceModel.AddressAlreadyInUseException> podczas otwierania.  
  
### <a name="to-enable-nettcp-port-sharing-on-a-nettcpbinding-in-configuration"></a>Aby włączyć udostępnianie za pomocą protokołu net. TCP://portu na NetTcpBinding w konfiguracji  
  
1. Poniższy przykład pokazuje, jak włączyć Udostępnianie portów i dodać punkt końcowy usługi przy użyciu elementów konfiguracji.  
  
```xml  
<system.serviceModel>  
  <bindings>  
    <netTcpBinding name="portSharingBinding"
                   portSharingEnabled="true" />  
  </bindings>  
  <services>  
    <service name="MyService">  
        <endpoint address="net.tcp://localhost/MyService"  
                  binding="netTcpBinding"  
                  contract="IMyService"  
                  bindingConfiguration="portSharingBinding" />  
    </service>  
  </services>  
</system.serviceModel>  
```  
  
## <a name="see-also"></a>Zobacz też

- [Współużytkowanie portów w składniku Net.TCP](net-tcp-port-sharing.md)
- [Instrukcje: włączanie usługi współużytkowania portów Net.TCP](how-to-enable-the-net-tcp-port-sharing-service.md)
