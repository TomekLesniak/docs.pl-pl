---
title: <endpointDiscovery>
ms.date: 03/30/2017
ms.assetid: 70812717-888a-4748-9640-0df6715ff029
ms.openlocfilehash: 621c742e3bb06ce91fa5a6b8951351295f73df9e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185811"
---
# \<endpointDiscovery>

<span data-ttu-id="79448-101">Określa różne ustawienia odnajdywania dla punktu końcowego, takie jak jego wykrywalność, zakresy i wszelkie niestandardowe rozszerzenia do swoich metadanych.</span><span class="sxs-lookup"><span data-stu-id="79448-101">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<endpointDiscovery>**  
  
## <a name="syntax"></a><span data-ttu-id="79448-102">Składnia</span><span class="sxs-lookup"><span data-stu-id="79448-102">Syntax</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="String">
      <endpointDiscovery enabled="Boolean">
        <scopes>
          <add scope="URI"/>
        </scopes>
        <extensions />
      </endpointDiscovery>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="79448-103">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="79448-103">Attributes and Elements</span></span>  

 <span data-ttu-id="79448-104">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="79448-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="79448-105">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="79448-105">Attributes</span></span>  
  
|<span data-ttu-id="79448-106">Atrybut</span><span class="sxs-lookup"><span data-stu-id="79448-106">Attribute</span></span>|<span data-ttu-id="79448-107">Opis</span><span class="sxs-lookup"><span data-stu-id="79448-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="79448-108">enabled</span><span class="sxs-lookup"><span data-stu-id="79448-108">enabled</span></span>|<span data-ttu-id="79448-109">Wartość logiczna określająca, czy wykrywalność jest włączona w tym punkcie końcowym.</span><span class="sxs-lookup"><span data-stu-id="79448-109">A Boolean value that specifies whether discoverability is enabled on this endpoint.</span></span> <span data-ttu-id="79448-110">Wartość domyślna to `false`.</span><span class="sxs-lookup"><span data-stu-id="79448-110">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="79448-111">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="79448-111">Child Elements</span></span>  
  
|<span data-ttu-id="79448-112">Element</span><span class="sxs-lookup"><span data-stu-id="79448-112">Element</span></span>|<span data-ttu-id="79448-113">Opis</span><span class="sxs-lookup"><span data-stu-id="79448-113">Description</span></span>|  
|-------------|-----------------|  
|[\<scopes>](scopes.md)|<span data-ttu-id="79448-114">Kolekcja identyfikatorów URI zakresu dla punktu końcowego.</span><span class="sxs-lookup"><span data-stu-id="79448-114">A collection of scope URIs for the endpoint.</span></span> <span data-ttu-id="79448-115">Więcej niż jeden identyfikator URI zakresu może być skojarzony z jednym punktem końcowym.</span><span class="sxs-lookup"><span data-stu-id="79448-115">More than one scope Uris can be associated with a single endpoint.</span></span>|  
|<span data-ttu-id="79448-116">[\<extensions>](extensions.md) [z \<endpointDiscovery> ]</span><span class="sxs-lookup"><span data-stu-id="79448-116">[\<extensions>](extensions.md) [of \<endpointDiscovery>]</span></span>|<span data-ttu-id="79448-117">Kolekcja elementów XML, która umożliwia określenie niestandardowych metadanych do opublikowania dla punktu końcowego.</span><span class="sxs-lookup"><span data-stu-id="79448-117">A collection of XML elements that allows you to specify custom metadata to be published for an endpoint.</span></span>|  
|\<types>|<span data-ttu-id="79448-118">Kolekcja interfejsów do wyszukania.</span><span class="sxs-lookup"><span data-stu-id="79448-118">A collection of interfaces to search for.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="79448-119">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="79448-119">Parent Elements</span></span>  
  
|<span data-ttu-id="79448-120">Element</span><span class="sxs-lookup"><span data-stu-id="79448-120">Element</span></span>|<span data-ttu-id="79448-121">Opis</span><span class="sxs-lookup"><span data-stu-id="79448-121">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="79448-122">Określa zachowanie elementu.</span><span class="sxs-lookup"><span data-stu-id="79448-122">Specifies a behavior element.</span></span>|  
|||  
  
## <a name="remarks"></a><span data-ttu-id="79448-123">Uwagi</span><span class="sxs-lookup"><span data-stu-id="79448-123">Remarks</span></span>  

 <span data-ttu-id="79448-124">Po dodaniu do konfiguracji zachowania punktu końcowego i z `enabled` atrybutem ustawionym na `true` , ten element konfiguracji umożliwia odnajdywanie.</span><span class="sxs-lookup"><span data-stu-id="79448-124">When added to the endpoint’s behavior configuration and with the `enabled` attribute set to `true`, this configuration element enables its discoverability.</span></span> <span data-ttu-id="79448-125">Ponadto można użyć [\<scopes>](scopes.md) elementu podrzędnego, aby określić niestandardowe identyfikatory URI, których można użyć do filtrowania punktów końcowych usługi podczas zapytania, a także [\<extensions>](extensions.md) element podrzędny, aby określić niestandardowe metadane, które powinny być publikowane wraz ze standardowym odnajdywaniem metadanych (EPR, ContractTypeName, BindingName, Scope i ListenUri).</span><span class="sxs-lookup"><span data-stu-id="79448-125">In addition, you can use the [\<scopes>](scopes.md)child element to specifying custom scope Uris that can be used to filter service endpoints during query, as well as the [\<extensions>](extensions.md) child element to specify custom metadata that should be published along with the standard discoverable metadata (EPR, ContractTypeName, BindingName, Scope and ListenURI).</span></span>  
  
 <span data-ttu-id="79448-126">Ten element konfiguracji zależy od [\<serviceDiscovery>](servicediscovery.md) elementu, który zapewnia kontrolę poziomu usługi odnajdowania.</span><span class="sxs-lookup"><span data-stu-id="79448-126">This configuration element is dependent on the [\<serviceDiscovery>](servicediscovery.md) element that provides the service level control of discoverability.</span></span> <span data-ttu-id="79448-127">Oznacza to, że ustawienia tego elementu są ignorowane, jeśli [\<serviceDiscovery>](servicediscovery.md) nie są obecne w konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="79448-127">This means that this element’s settings are ignored if [\<serviceDiscovery>](servicediscovery.md) is not present in the configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="79448-128">Przykład</span><span class="sxs-lookup"><span data-stu-id="79448-128">Example</span></span>  

 <span data-ttu-id="79448-129">Poniższy przykład konfiguracji określa zakresy filtrowania i metadane rozszerzenia do opublikowania dla punktu końcowego.</span><span class="sxs-lookup"><span data-stu-id="79448-129">The following configuration example specifies filtering scopes and extension metadata to be published for an endpoint.</span></span>  
  
```xml  
<services>
  <service name="CalculatorService"
           behaviorConfiguration="CalculatorServiceBehavior">
    <endpoint binding="basicHttpBinding"
              address="calculator"
              contract="ICalculatorService"
              behaviorConfiguration="calculatorEndpointBehavior" />
  </service>
</services>
<behaviors>
  <serviceBehaviors>
    <behavior name="CalculatorServiceBehavior">
      <serviceDiscovery />
    </behavior>
  </serviceBehaviors>
  <endpointBehaviors>
    <behavior name="calculatorEndpointBehavior">
      <endpointDiscovery enabled="true">
        <scopes>
          <add scope="http://contoso/test1" />
          <add scope="http://contoso/test2" />
        </scopes>
        <extensions>
          <e:Publisher xmlns:e="http://example.org">
            <e:Name>The Example Organization</e:Name>
            <e:Address>One Example Way, ExampleTown, EX 12345</e:Address>
            <e:Contact>support@example.org</e:Contact>
          </e:Publisher>
          <AnotherCustomMetadata>Custom Metadata</AnotherCustomMetadata>
        </extensions>
      </endpointDiscovery>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="79448-130">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="79448-130">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
