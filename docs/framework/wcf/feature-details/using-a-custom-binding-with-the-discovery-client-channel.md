---
title: Używanie powiązania niestandardowego z kanałem klienta odnajdywania
ms.date: 03/30/2017
ms.assetid: 36f95e75-04f7-44f3-a995-a0d623624d7f
ms.openlocfilehash: d84739a0021262826c541ab3ff9df663adabf44a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96289662"
---
# <a name="using-a-custom-binding-with-the-discovery-client-channel"></a><span data-ttu-id="b73bb-102">Używanie powiązania niestandardowego z kanałem klienta odnajdywania</span><span class="sxs-lookup"><span data-stu-id="b73bb-102">Using a Custom Binding with the Discovery Client Channel</span></span>

<span data-ttu-id="b73bb-103">W przypadku używania niestandardowego powiązania z <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement> , należy zdefiniować, <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> które tworzy <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="b73bb-103">When using a custom binding with the <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>, you must define a <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> that creates <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> instances.</span></span>  
  
## <a name="creating-a-discoveryendpointprovider"></a><span data-ttu-id="b73bb-104">Tworzenie DiscoveryEndpointProvider</span><span class="sxs-lookup"><span data-stu-id="b73bb-104">Creating a DiscoveryEndpointProvider</span></span>  

 <span data-ttu-id="b73bb-105"><xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider>Jest odpowiedzialny za tworzenie <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> wystąpień na żądanie.</span><span class="sxs-lookup"><span data-stu-id="b73bb-105">The <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> is responsible for creating <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> instances on demand.</span></span> <span data-ttu-id="b73bb-106">Aby zdefiniować dostawcę punktu końcowego odnajdywania, należy utworzyć klasę z <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> i zastąpić <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider.GetDiscoveryEndpoint%2A> metodę i zwrócić nowy punkt końcowy odnajdywania.</span><span class="sxs-lookup"><span data-stu-id="b73bb-106">To define a discovery endpoint provider, derive a class from <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> and override the <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider.GetDiscoveryEndpoint%2A> method and return a new discovery endpoint.</span></span> <span data-ttu-id="b73bb-107">Poniższy przykład pokazuje, jak utworzyć dostawcę punktu końcowego odnajdywania.</span><span class="sxs-lookup"><span data-stu-id="b73bb-107">The following example shows how to create a discovery endpoint provider.</span></span>  
  
```csharp
// Extend DiscoveryEndpointProvider class to change the default DiscoveryEndpoint  
// to the DiscoveryClientBindingElement. The Discovery ClientChannel
// uses this endpoint to send Probe message.  
public class UdpDiscoveryEndpointProvider : DiscoveryEndpointProvider  
{  
   public override DiscoveryEndpoint GetDiscoveryEndpoint()  
   {  
      return new UdpDiscoveryEndpoint(DiscoveryVersion.WSDiscoveryApril2005);  
   }  
}  
```  
  
 <span data-ttu-id="b73bb-108">Po zdefiniowaniu dostawcy punktu końcowego odnajdywania można utworzyć niestandardowe powiązanie i dodać obiekt <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement> , który odwołuje się do dostawcy punktu końcowego odnajdywania, jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="b73bb-108">Once you have defined the discovery endpoint provider you can create a custom binding and add the <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>, which references the discovery endpoint provider as shown in the following example.</span></span>  
  
```csharp
DiscoveryClientBindingElement discoveryBindingElement = new DiscoveryClientBindingElement();  
  
// Provide the search criteria and the endpoint over which the probe is sent.  
discoveryBindingElement.FindCriteria = new FindCriteria(typeof(ICalculatorService));  
discoveryBindingElement.DiscoveryEndpointProvider = new UdpDiscoveryEndpointProvider();  
  
CustomBinding customBinding = new CustomBinding(new NetTcpBinding());  
// Insert DiscoveryClientBindingElement at the top of the BindingElement stack.  
// An exception is thrown if this binding element is not at the top.  
customBinding.Elements.Insert(0, discoveryBindingElement);  
```  
  
 <span data-ttu-id="b73bb-109">Aby uzyskać więcej informacji o korzystaniu z kanału klienta odnajdywania, zobacz [Korzystanie z kanału klienta odnajdywania](using-the-discovery-client-channel.md).</span><span class="sxs-lookup"><span data-stu-id="b73bb-109">For more information about using the discovery client channel, see [Using the Discovery Client Channel](using-the-discovery-client-channel.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b73bb-110">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b73bb-110">See also</span></span>

- [<span data-ttu-id="b73bb-111">Omówienie odnajdywania WCF</span><span class="sxs-lookup"><span data-stu-id="b73bb-111">WCF Discovery Overview</span></span>](wcf-discovery-overview.md)
- [<span data-ttu-id="b73bb-112">Używanie kanału klienta odnajdywania</span><span class="sxs-lookup"><span data-stu-id="b73bb-112">Using the Discovery Client Channel</span></span>](using-the-discovery-client-channel.md)
