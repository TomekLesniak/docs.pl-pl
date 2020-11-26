---
title: Standardowe punkty końcowe
ms.date: 03/30/2017
ms.assetid: 3fcb4225-addc-44f2-935d-30e4943a8812
ms.openlocfilehash: a2f8d45990c5bc845aeee87ee82a2d043d6d1292
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96246449"
---
# <a name="standard-endpoints"></a>Standardowe punkty końcowe

Punkty końcowe są definiowane przez określenie adresu, powiązania i kontraktu. Inne parametry, które można ustawić w punkcie końcowym, obejmują konfigurację zachowań, nagłówki i identyfikatory URI nasłuchiwania.  W przypadku niektórych typów punktów końcowych te wartości nie zmieniają się. Na przykład punkty końcowe wymiany metadanych zawsze korzystają z <xref:System.ServiceModel.Description.IMetadataExchange> kontraktu. Inne punkty końcowe, takie jak <xref:System.ServiceModel.Description.WebHttpEndpoint> zawsze wymagają określonego zachowania punktu końcowego. Użyteczność punktu końcowego można ulepszyć, mając punkty końcowe z wartościami domyślnymi często używanych właściwości punktu końcowego. Standardowe punkty końcowe umożliwiają deweloperowi zdefiniowanie punktu końcowego, który ma wartości domyślne lub nie powoduje zmiany właściwości jednego lub więcej punktów końcowych.  Punkty końcowe umożliwiają użycie takiego punktu końcowego bez konieczności określania informacji o charakterze statycznym. Standardowe punkty końcowe mogą być używane dla punktów końcowych infrastruktury i aplikacji.  
  
## <a name="infrastructure-endpoints"></a>Punkty końcowe infrastruktury  

 Usługa może uwidaczniać punkty końcowe z niejawnie zaimplementowanymi właściwościami autora usługi. Na przykład punkt końcowy wymiany metadanych uwidacznia <xref:System.ServiceModel.Description.IMetadataExchange> umowę, ale jako autora usługi nie wdrożono tego interfejsu, jest on implementowany przez funkcję WCF. Takie punkty końcowe infrastruktury mają wartości domyślne dla jednej lub większej liczby właściwości punktu końcowego, a niektóre z nich mogą być niezmienione. <xref:System.ServiceModel.Description.ServiceEndpoint.Contract%2A>Właściwość punktu końcowego wymiany metadanych musi być <xref:System.ServiceModel.Description.IMetadataExchange> , podczas gdy inne właściwości, takie jak powiązanie, mogą zostać dostarczone przez dewelopera. Punkty końcowe infrastruktury są identyfikowane przez ustawienie <xref:System.ServiceModel.Description.ServiceEndpoint.IsSystemEndpoint%2A> właściwości na `true` .  
  
## <a name="application-endpoints"></a>Punkty końcowe aplikacji  

 Deweloperzy aplikacji mogą definiować własne standardowe punkty końcowe, które określają wartości domyślne dla adresu, powiązania lub kontraktu. Można zdefiniować standardowy punkt końcowy, wprowadzając klasę z <xref:System.ServiceModel.Description.ServiceEndpoint> i ustawiając odpowiednie właściwości punktu końcowego. Można podać wartości domyślne dla właściwości, które można zmienić. Niektóre inne właściwości będą mieć wartości statyczne, których nie można zmienić. Poniższy przykład pokazuje, jak zaimplementować standardowy punkt końcowy.  
  
```csharp
public class CustomEndpoint : ServiceEndpoint
{
    public CustomEndpoint()
        : this(string.Empty)
    { }  

    public CustomEndpoint(string address)
        : this(address, ContractDescription.GetContract(typeof(ICalculator)))
    { }  

    // Create the custom endpoint with a fixed binding
    public CustomEndpoint(string address, ContractDescription contract)
        : base(contract)
    {
        this.Binding = new BasicHttpBinding();
        this.IsSystemEndpoint = false;
    }

    // Definition of the additional property of this endpoint
    public bool Property { get; set; }
}
```
  
 Aby użyć niestandardowego punktu końcowego zdefiniowanego przez użytkownika w pliku konfiguracji, należy utworzyć klasę z <xref:System.ServiceModel.Configuration.StandardEndpointElement> , utworzyć klasę z <xref:System.ServiceModel.Configuration.StandardEndpointCollectionElement%602> i zarejestrować nowy standardowy punkt końcowy w sekcji rozszerzeń w app.config lub machine.config.  <xref:System.ServiceModel.Configuration.StandardEndpointElement> Zapewnia obsługę konfiguracji dla standardowego punktu końcowego, jak pokazano w poniższym przykładzie.  
  
```csharp
public class CustomEndpointElement : StandardEndpointElement
{
    // Definition of the additional property for the standard endpoint element
    public bool Property
    {
        get { return (bool)base["property"]; }
        set { base["property"] = value; }
    }

    // The additional property needs to be added to the properties of the standard endpoint element
    protected override ConfigurationPropertyCollection Properties
    {
        get
        {
            ConfigurationPropertyCollection properties = base.Properties;
            properties.Add(new ConfigurationProperty("property", typeof(bool), false, ConfigurationPropertyOptions.None));
            return properties;
        }
    }

    // Return the type of this standard endpoint
    protected override Type EndpointType
    {
        get { return typeof(CustomEndpoint); }
    }

    // Create the custom service endpoint
    protected override ServiceEndpoint CreateServiceEndpoint(ContractDescription contract)
    {
        return new CustomEndpoint();
    }

    // Read the value given to the property in config and save it
    protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ServiceEndpointElement serviceEndpointElement)
    {
        CustomEndpoint customEndpoint = (CustomEndpoint)endpoint;
        customEndpoint.Property = this.Property;
    }

    // Read the value given to the property in config and save it
    protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ChannelEndpointElement channelEndpointElement)
    {
        CustomEndpoint customEndpoint = (CustomEndpoint)endpoint;
        customEndpoint.Property = this.Property;
    }

    // No validation in this sample
    protected override void OnInitializeAndValidate(ServiceEndpointElement serviceEndpointElement)
    {
    }

    // No validation in this sample
    protected override void OnInitializeAndValidate(ChannelEndpointElement channelEndpointElement)
    {
    }
}
```  
  
 <xref:System.ServiceModel.Configuration.StandardEndpointCollectionElement%602>Udostępnia typ kopii zapasowej dla kolekcji, która jest wyświetlana w `standardEndpoints` sekcji <> w konfiguracji standardowego punktu końcowego.  Poniższy przykład pokazuje, jak zaimplementować tę klasę.  
  
```csharp
public class CustomEndpointCollectionElement : StandardEndpointCollectionElement<CustomEndpoint, CustomEndpointElement>
{
    // ...
}
```

Poniższy przykład pokazuje, jak zarejestrować standardowy punkt końcowy w sekcji rozszerzenia.

```xml  
<extensions>  
      <standardEndpointExtensions>  
        <add  
          name="customStandardEndpoint"  
          type="CustomEndpointCollectionElement, Example.dll,  
                Version=1.0.0.0, Culture=neutral, PublicKeyToken=ffffffffffffffff"/>  
      </standardEndpointExtensions>
</extensions>  
```  
  
## <a name="configuring-a-standard-endpoint"></a>Konfigurowanie standardowego punktu końcowego  

 Standardowe punkty końcowe można dodać w kodzie lub w konfiguracji.  Aby dodać standardowy punkt końcowy w kodzie po prostu utworzyć wystąpienie odpowiedniego standardowego typu punktu końcowego i dodać go do hosta usługi, jak pokazano w następującym przykładzie:  
  
```csharp  
serviceHost.AddServiceEndpoint(new CustomEndpoint());  
```  
  
 Aby dodać standardowy punkt końcowy w konfiguracji, Dodaj `endpoint` element> <do `service` elementu <> i wszystkie potrzebne ustawienia konfiguracji w <`standardEndpoints`> elementu. Poniższy przykład pokazuje, jak dodać <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> jeden ze standardowych punktów końcowych, które są dostarczane z [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] .  
  
```xml  
<services>  
  <service>  
    <endpoint isSystemEndpoint="true" kind="udpDiscoveryEndpoint" />  
  </service>  
</services>  
<standardEndpoints>
  <udpDiscoveryEndpoint>  
     <standardEndpoint multicastAddress="soap.udp://239.255.255.250:3702" />
  </udpDiscoveryEndpoint>
</standardEndpoints>
```  
  
 Typ standardowego punktu końcowego jest określany przy użyciu atrybutu Kind w <`endpoint`> elementu. Punkt końcowy jest skonfigurowany w <`standardEndpoints` elementu>. W powyższym przykładzie <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> zostanie dodany i skonfigurowany punkt końcowy. `udpDiscoveryEndpoint`Element> <zawiera <`standardEndpoint`>, który ustawia <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint.MulticastAddress%2A> Właściwość <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> .  
  
## <a name="standard-endpoints-shipped-with-the-net-framework"></a>Standardowe punkty końcowe dostarczane z .NET Framework  

 W poniższej tabeli wymieniono standardowe punkty końcowe dostarczone z [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] .  
  
 `Mex Endpoint`  
 Standardowy punkt końcowy, który jest używany do ujawniania metadanych usługi.  
  
 <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>  
 Standardowy punkt końcowy używany przez usługi do wysyłania komunikatów anonsu.  
  
 <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>  
 Standardowy punkt końcowy używany przez usługi do wysyłania komunikatów odnajdywania.  
  
 <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>  
 Standardowy punkt końcowy, który jest wstępnie skonfigurowany dla operacji odnajdywania za pośrednictwem powiązania multiemisji UDP.  
  
 <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>  
 Standardowy punkt końcowy używany przez usługi do wysyłania komunikatów anonsu za pośrednictwem powiązania UDP.  
  
 <xref:System.ServiceModel.Discovery.DynamicEndpoint>  
 Standardowy punkt końcowy, który używa WS-Discovery do dynamicznego znajdowania adresu punktu końcowego w czasie wykonywania.  
  
 <xref:System.ServiceModel.Description.ServiceMetadataEndpoint>  
 Standardowy punkt końcowy dla wymiany metadanych.  
  
 <xref:System.ServiceModel.Description.WebHttpEndpoint>  
 Standardowy punkt końcowy z <xref:System.ServiceModel.WebHttpBinding> powiązaniem, które automatycznie dodaje <xref:System.ServiceModel.Description.WebHttpBehavior> zachowanie  
  
 <xref:System.ServiceModel.Description.WebScriptEndpoint>  
 Standardowy punkt końcowy z <xref:System.ServiceModel.WebHttpBinding> powiązaniem, które automatycznie dodaje <xref:System.ServiceModel.Description.WebScriptEnablingBehavior> zachowanie.  
  
 <xref:System.ServiceModel.Description.WebServiceEndpoint>  
 Standardowy punkt końcowy z <xref:System.ServiceModel.WebHttpBinding> powiązaniem.  
  
 <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>  
 Standardowy punkt końcowy, który umożliwia wywoływanie operacji sterowania w wystąpieniach przepływu pracy.  
  
 <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint>  
 Standardowy punkt końcowy, który obsługuje tworzenie przepływu pracy i wznawianie zakładki.
