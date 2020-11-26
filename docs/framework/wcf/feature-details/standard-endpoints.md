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
# <a name="standard-endpoints"></a><span data-ttu-id="69957-102">Standardowe punkty końcowe</span><span class="sxs-lookup"><span data-stu-id="69957-102">Standard Endpoints</span></span>

<span data-ttu-id="69957-103">Punkty końcowe są definiowane przez określenie adresu, powiązania i kontraktu.</span><span class="sxs-lookup"><span data-stu-id="69957-103">Endpoints are defined by specifying an address, a binding, and a contract.</span></span> <span data-ttu-id="69957-104">Inne parametry, które można ustawić w punkcie końcowym, obejmują konfigurację zachowań, nagłówki i identyfikatory URI nasłuchiwania.</span><span class="sxs-lookup"><span data-stu-id="69957-104">Other parameters that may be set on an endpoint include behavior configuration, headers, and listen URIs.</span></span>  <span data-ttu-id="69957-105">W przypadku niektórych typów punktów końcowych te wartości nie zmieniają się.</span><span class="sxs-lookup"><span data-stu-id="69957-105">For certain types of endpoints these values do not change.</span></span> <span data-ttu-id="69957-106">Na przykład punkty końcowe wymiany metadanych zawsze korzystają z <xref:System.ServiceModel.Description.IMetadataExchange> kontraktu.</span><span class="sxs-lookup"><span data-stu-id="69957-106">For example, metadata exchange endpoints always use the <xref:System.ServiceModel.Description.IMetadataExchange> contract.</span></span> <span data-ttu-id="69957-107">Inne punkty końcowe, takie jak <xref:System.ServiceModel.Description.WebHttpEndpoint> zawsze wymagają określonego zachowania punktu końcowego.</span><span class="sxs-lookup"><span data-stu-id="69957-107">Other endpoints, such as <xref:System.ServiceModel.Description.WebHttpEndpoint> always require a specified endpoint behavior.</span></span> <span data-ttu-id="69957-108">Użyteczność punktu końcowego można ulepszyć, mając punkty końcowe z wartościami domyślnymi często używanych właściwości punktu końcowego.</span><span class="sxs-lookup"><span data-stu-id="69957-108">The usability of an endpoint can be improved by having endpoints with default values for commonly used endpoint properties.</span></span> <span data-ttu-id="69957-109">Standardowe punkty końcowe umożliwiają deweloperowi zdefiniowanie punktu końcowego, który ma wartości domyślne lub nie powoduje zmiany właściwości jednego lub więcej punktów końcowych.</span><span class="sxs-lookup"><span data-stu-id="69957-109">Standard endpoints enable a developer to define an endpoint that has default values or where one or more endpoint’s properties does not change.</span></span>  <span data-ttu-id="69957-110">Punkty końcowe umożliwiają użycie takiego punktu końcowego bez konieczności określania informacji o charakterze statycznym.</span><span class="sxs-lookup"><span data-stu-id="69957-110">These endpoints allow you to use such an endpoint without having to specify information of a static nature.</span></span> <span data-ttu-id="69957-111">Standardowe punkty końcowe mogą być używane dla punktów końcowych infrastruktury i aplikacji.</span><span class="sxs-lookup"><span data-stu-id="69957-111">Standard endpoints can be used for infrastructure and application endpoints.</span></span>  
  
## <a name="infrastructure-endpoints"></a><span data-ttu-id="69957-112">Punkty końcowe infrastruktury</span><span class="sxs-lookup"><span data-stu-id="69957-112">Infrastructure Endpoints</span></span>  

 <span data-ttu-id="69957-113">Usługa może uwidaczniać punkty końcowe z niejawnie zaimplementowanymi właściwościami autora usługi.</span><span class="sxs-lookup"><span data-stu-id="69957-113">A service may expose endpoints with some of the properties not explicitly implemented by the service author.</span></span> <span data-ttu-id="69957-114">Na przykład punkt końcowy wymiany metadanych uwidacznia <xref:System.ServiceModel.Description.IMetadataExchange> umowę, ale jako autora usługi nie wdrożono tego interfejsu, jest on implementowany przez funkcję WCF.</span><span class="sxs-lookup"><span data-stu-id="69957-114">For example, the metadata exchange endpoint exposes the <xref:System.ServiceModel.Description.IMetadataExchange> contract but as a service author you do not implement that interface, it is implemented by WCF.</span></span> <span data-ttu-id="69957-115">Takie punkty końcowe infrastruktury mają wartości domyślne dla jednej lub większej liczby właściwości punktu końcowego, a niektóre z nich mogą być niezmienione.</span><span class="sxs-lookup"><span data-stu-id="69957-115">Such infrastructure endpoints have default values for one or more endpoint properties, some of which may be unalterable.</span></span> <span data-ttu-id="69957-116"><xref:System.ServiceModel.Description.ServiceEndpoint.Contract%2A>Właściwość punktu końcowego wymiany metadanych musi być <xref:System.ServiceModel.Description.IMetadataExchange> , podczas gdy inne właściwości, takie jak powiązanie, mogą zostać dostarczone przez dewelopera.</span><span class="sxs-lookup"><span data-stu-id="69957-116">The <xref:System.ServiceModel.Description.ServiceEndpoint.Contract%2A> property of the metadata exchange endpoint must be <xref:System.ServiceModel.Description.IMetadataExchange>, while other properties like binding can be supplied by the developer.</span></span> <span data-ttu-id="69957-117">Punkty końcowe infrastruktury są identyfikowane przez ustawienie <xref:System.ServiceModel.Description.ServiceEndpoint.IsSystemEndpoint%2A> właściwości na `true` .</span><span class="sxs-lookup"><span data-stu-id="69957-117">Infrastructure endpoints are identified by setting the <xref:System.ServiceModel.Description.ServiceEndpoint.IsSystemEndpoint%2A> property to `true`.</span></span>  
  
## <a name="application-endpoints"></a><span data-ttu-id="69957-118">Punkty końcowe aplikacji</span><span class="sxs-lookup"><span data-stu-id="69957-118">Application Endpoints</span></span>  

 <span data-ttu-id="69957-119">Deweloperzy aplikacji mogą definiować własne standardowe punkty końcowe, które określają wartości domyślne dla adresu, powiązania lub kontraktu.</span><span class="sxs-lookup"><span data-stu-id="69957-119">Application developers can define their own standard endpoints which specify default values for the address, binding, or contract.</span></span> <span data-ttu-id="69957-120">Można zdefiniować standardowy punkt końcowy, wprowadzając klasę z <xref:System.ServiceModel.Description.ServiceEndpoint> i ustawiając odpowiednie właściwości punktu końcowego.</span><span class="sxs-lookup"><span data-stu-id="69957-120">You define a standard endpoint by deriving a class from <xref:System.ServiceModel.Description.ServiceEndpoint> and setting the appropriate endpoint properties.</span></span> <span data-ttu-id="69957-121">Można podać wartości domyślne dla właściwości, które można zmienić.</span><span class="sxs-lookup"><span data-stu-id="69957-121">You can provide default values for properties that can be changed.</span></span> <span data-ttu-id="69957-122">Niektóre inne właściwości będą mieć wartości statyczne, których nie można zmienić.</span><span class="sxs-lookup"><span data-stu-id="69957-122">Some other properties will have static values that cannot change.</span></span> <span data-ttu-id="69957-123">Poniższy przykład pokazuje, jak zaimplementować standardowy punkt końcowy.</span><span class="sxs-lookup"><span data-stu-id="69957-123">The following example shows how to implement a standard endpoint.</span></span>  
  
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
  
 <span data-ttu-id="69957-124">Aby użyć niestandardowego punktu końcowego zdefiniowanego przez użytkownika w pliku konfiguracji, należy utworzyć klasę z <xref:System.ServiceModel.Configuration.StandardEndpointElement> , utworzyć klasę z <xref:System.ServiceModel.Configuration.StandardEndpointCollectionElement%602> i zarejestrować nowy standardowy punkt końcowy w sekcji rozszerzeń w app.config lub machine.config.  <xref:System.ServiceModel.Configuration.StandardEndpointElement> Zapewnia obsługę konfiguracji dla standardowego punktu końcowego, jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="69957-124">To use a user-defined custom endpoint in a configuration file you must derive a class from <xref:System.ServiceModel.Configuration.StandardEndpointElement>, derive a class from <xref:System.ServiceModel.Configuration.StandardEndpointCollectionElement%602>, and register the new standard endpoint in the extensions section in app.config or machine.config.  The <xref:System.ServiceModel.Configuration.StandardEndpointElement> provides configuration support for the standard endpoint, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="69957-125"><xref:System.ServiceModel.Configuration.StandardEndpointCollectionElement%602>Udostępnia typ kopii zapasowej dla kolekcji, która jest wyświetlana w `standardEndpoints` sekcji <> w konfiguracji standardowego punktu końcowego.</span><span class="sxs-lookup"><span data-stu-id="69957-125">The <xref:System.ServiceModel.Configuration.StandardEndpointCollectionElement%602> provides the backing type for the collection that appears under the <`standardEndpoints`> section in the configuration for the standard endpoint.</span></span>  <span data-ttu-id="69957-126">Poniższy przykład pokazuje, jak zaimplementować tę klasę.</span><span class="sxs-lookup"><span data-stu-id="69957-126">The following example shows how to implement this class.</span></span>  
  
```csharp
public class CustomEndpointCollectionElement : StandardEndpointCollectionElement<CustomEndpoint, CustomEndpointElement>
{
    // ...
}
```

<span data-ttu-id="69957-127">Poniższy przykład pokazuje, jak zarejestrować standardowy punkt końcowy w sekcji rozszerzenia.</span><span class="sxs-lookup"><span data-stu-id="69957-127">The following example shows how to register a standard endpoint in the extensions section.</span></span>

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
  
## <a name="configuring-a-standard-endpoint"></a><span data-ttu-id="69957-128">Konfigurowanie standardowego punktu końcowego</span><span class="sxs-lookup"><span data-stu-id="69957-128">Configuring a Standard Endpoint</span></span>  

 <span data-ttu-id="69957-129">Standardowe punkty końcowe można dodać w kodzie lub w konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="69957-129">Standard endpoints can be added in code or in configuration.</span></span>  <span data-ttu-id="69957-130">Aby dodać standardowy punkt końcowy w kodzie po prostu utworzyć wystąpienie odpowiedniego standardowego typu punktu końcowego i dodać go do hosta usługi, jak pokazano w następującym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="69957-130">To add a standard endpoint in code simply instantiate the appropriate standard endpoint type and add it to the service host as shown in the following example:</span></span>  
  
```csharp  
serviceHost.AddServiceEndpoint(new CustomEndpoint());  
```  
  
 <span data-ttu-id="69957-131">Aby dodać standardowy punkt końcowy w konfiguracji, Dodaj `endpoint` element> <do `service` elementu <> i wszystkie potrzebne ustawienia konfiguracji w <`standardEndpoints`> elementu.</span><span class="sxs-lookup"><span data-stu-id="69957-131">To add a standard endpoint in configuration, add an <`endpoint`> element to the <`service`> element and any needed configuration settings in the <`standardEndpoints`> element.</span></span> <span data-ttu-id="69957-132">Poniższy przykład pokazuje, jak dodać <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> jeden ze standardowych punktów końcowych, które są dostarczane z [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="69957-132">The following example shows how to add a <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>, one of the standard endpoints that ships with [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span></span>  
  
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
  
 <span data-ttu-id="69957-133">Typ standardowego punktu końcowego jest określany przy użyciu atrybutu Kind w <`endpoint`> elementu.</span><span class="sxs-lookup"><span data-stu-id="69957-133">The type of standard endpoint is specified using the kind attribute in the <`endpoint`> element.</span></span> <span data-ttu-id="69957-134">Punkt końcowy jest skonfigurowany w <`standardEndpoints` elementu>.</span><span class="sxs-lookup"><span data-stu-id="69957-134">The endpoint is configured within the <`standardEndpoints`> element.</span></span> <span data-ttu-id="69957-135">W powyższym przykładzie <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> zostanie dodany i skonfigurowany punkt końcowy.</span><span class="sxs-lookup"><span data-stu-id="69957-135">In the example above, a <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> endpoint is added and configured.</span></span> <span data-ttu-id="69957-136">`udpDiscoveryEndpoint`Element> <zawiera <`standardEndpoint`>, który ustawia <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint.MulticastAddress%2A> Właściwość <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> .</span><span class="sxs-lookup"><span data-stu-id="69957-136">The <`udpDiscoveryEndpoint`> element contains a <`standardEndpoint`> that sets the <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint.MulticastAddress%2A> property of the <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>.</span></span>  
  
## <a name="standard-endpoints-shipped-with-the-net-framework"></a><span data-ttu-id="69957-137">Standardowe punkty końcowe dostarczane z .NET Framework</span><span class="sxs-lookup"><span data-stu-id="69957-137">Standard Endpoints Shipped with the .NET Framework</span></span>  

 <span data-ttu-id="69957-138">W poniższej tabeli wymieniono standardowe punkty końcowe dostarczone z [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="69957-138">The following table lists the standard endpoints shipped with [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span></span>  
  
 `Mex Endpoint`  
 <span data-ttu-id="69957-139">Standardowy punkt końcowy, który jest używany do ujawniania metadanych usługi.</span><span class="sxs-lookup"><span data-stu-id="69957-139">A standard endpoint that is used to expose service metadata.</span></span>  
  
 <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>  
 <span data-ttu-id="69957-140">Standardowy punkt końcowy używany przez usługi do wysyłania komunikatów anonsu.</span><span class="sxs-lookup"><span data-stu-id="69957-140">A standard endpoint that is used by services to send announcement messages.</span></span>  
  
 <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>  
 <span data-ttu-id="69957-141">Standardowy punkt końcowy używany przez usługi do wysyłania komunikatów odnajdywania.</span><span class="sxs-lookup"><span data-stu-id="69957-141">A standard endpoint that is used by services to send discovery messages.</span></span>  
  
 <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>  
 <span data-ttu-id="69957-142">Standardowy punkt końcowy, który jest wstępnie skonfigurowany dla operacji odnajdywania za pośrednictwem powiązania multiemisji UDP.</span><span class="sxs-lookup"><span data-stu-id="69957-142">A standard endpoint that is pre-configured for discovery operations over a UDP multicast binding.</span></span>  
  
 <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>  
 <span data-ttu-id="69957-143">Standardowy punkt końcowy używany przez usługi do wysyłania komunikatów anonsu za pośrednictwem powiązania UDP.</span><span class="sxs-lookup"><span data-stu-id="69957-143">A standard endpoint that is used by services to send announcement messages over a UDP binding.</span></span>  
  
 <xref:System.ServiceModel.Discovery.DynamicEndpoint>  
 <span data-ttu-id="69957-144">Standardowy punkt końcowy, który używa WS-Discovery do dynamicznego znajdowania adresu punktu końcowego w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="69957-144">A standard endpoint that uses WS-Discovery to find the endpoint address dynamically at runtime.</span></span>  
  
 <xref:System.ServiceModel.Description.ServiceMetadataEndpoint>  
 <span data-ttu-id="69957-145">Standardowy punkt końcowy dla wymiany metadanych.</span><span class="sxs-lookup"><span data-stu-id="69957-145">A standard endpoint for metadata exchange.</span></span>  
  
 <xref:System.ServiceModel.Description.WebHttpEndpoint>  
 <span data-ttu-id="69957-146">Standardowy punkt końcowy z <xref:System.ServiceModel.WebHttpBinding> powiązaniem, które automatycznie dodaje <xref:System.ServiceModel.Description.WebHttpBehavior> zachowanie</span><span class="sxs-lookup"><span data-stu-id="69957-146">A standard endpoint with a <xref:System.ServiceModel.WebHttpBinding> binding that automatically adds the <xref:System.ServiceModel.Description.WebHttpBehavior> behavior</span></span>  
  
 <xref:System.ServiceModel.Description.WebScriptEndpoint>  
 <span data-ttu-id="69957-147">Standardowy punkt końcowy z <xref:System.ServiceModel.WebHttpBinding> powiązaniem, które automatycznie dodaje <xref:System.ServiceModel.Description.WebScriptEnablingBehavior> zachowanie.</span><span class="sxs-lookup"><span data-stu-id="69957-147">A standard endpoint with a <xref:System.ServiceModel.WebHttpBinding> binding that automatically adds the <xref:System.ServiceModel.Description.WebScriptEnablingBehavior> behavior.</span></span>  
  
 <xref:System.ServiceModel.Description.WebServiceEndpoint>  
 <span data-ttu-id="69957-148">Standardowy punkt końcowy z <xref:System.ServiceModel.WebHttpBinding> powiązaniem.</span><span class="sxs-lookup"><span data-stu-id="69957-148">A standard endpoint with a <xref:System.ServiceModel.WebHttpBinding> binding.</span></span>  
  
 <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>  
 <span data-ttu-id="69957-149">Standardowy punkt końcowy, który umożliwia wywoływanie operacji sterowania w wystąpieniach przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="69957-149">A standard endpoint that enables you to call control operations on workflow instances.</span></span>  
  
 <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint>  
 <span data-ttu-id="69957-150">Standardowy punkt końcowy, który obsługuje tworzenie przepływu pracy i wznawianie zakładki.</span><span class="sxs-lookup"><span data-stu-id="69957-150">A standard endpoint that supports workflow creation and bookmark resumption.</span></span>
