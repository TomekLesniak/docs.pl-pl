---
title: <endpoint>, element
ms.date: 03/30/2017
ms.assetid: 2fc8fedc-78d0-4e87-8142-fbfd26c15a4e
ms.openlocfilehash: befebc090900576b1e0f7ca679e1f5f5cd15af9a
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183809"
---
# <a name="endpoint-element"></a><span data-ttu-id="23549-102">\<endpoint>, element</span><span class="sxs-lookup"><span data-stu-id="23549-102">\<endpoint> element</span></span>

<span data-ttu-id="23549-103">Określa powiązanie, kontrakt i właściwości adresu dla punktu końcowego usługi, który jest używany do udostępniania usług.</span><span class="sxs-lookup"><span data-stu-id="23549-103">Specifies binding, contract, and address properties for a service endpoint, which is used to expose services.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<endpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="23549-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="23549-104">Syntax</span></span>  
  
```xml  
<endpoint address="String"
          behaviorConfiguration="String"
          binding="String"
          bindingConfiguration="String"
          bindingName="String"
          bindingNamespace="String"
          contract="String"
          endpointConfiguration="String"
          isSystemEndpoint="Boolean"
          kind="String"
          listenUriMode="Explicit/Unique"
          listenUri="Uri">
</endpoint>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="23549-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="23549-105">Attributes and Elements</span></span>  

 <span data-ttu-id="23549-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="23549-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="23549-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="23549-107">Attributes</span></span>  
  
|<span data-ttu-id="23549-108">Atrybut</span><span class="sxs-lookup"><span data-stu-id="23549-108">Attribute</span></span>|<span data-ttu-id="23549-109">Opis</span><span class="sxs-lookup"><span data-stu-id="23549-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="23549-110">adres</span><span class="sxs-lookup"><span data-stu-id="23549-110">address</span></span>|<span data-ttu-id="23549-111">Ciąg zawierający adres punktu końcowego.</span><span class="sxs-lookup"><span data-stu-id="23549-111">A string that contains the address of the endpoint.</span></span> <span data-ttu-id="23549-112">Adres może być określony jako adres bezwzględny lub względny.</span><span class="sxs-lookup"><span data-stu-id="23549-112">The address can be specified as an absolute or relative address.</span></span> <span data-ttu-id="23549-113">Jeśli zostanie podany adres względny, host powinien podać adres podstawowy odpowiedni dla schematu transportu używanego w powiązaniu.</span><span class="sxs-lookup"><span data-stu-id="23549-113">If a relative address is provided, the host is expected to provide a base address appropriate for the transport scheme used in the binding.</span></span> <span data-ttu-id="23549-114">Jeśli adres nie jest skonfigurowany, zakłada się, że adres podstawowy jest adresem dla tego punktu końcowego.</span><span class="sxs-lookup"><span data-stu-id="23549-114">If an address is not configured, the base address is assumed to be the address for that endpoint.</span></span><br /><br /> <span data-ttu-id="23549-115">Wartość domyślna to pusty ciąg.</span><span class="sxs-lookup"><span data-stu-id="23549-115">The default is an empty string.</span></span>|  
|<span data-ttu-id="23549-116">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="23549-116">behaviorConfiguration</span></span>|<span data-ttu-id="23549-117">Ciąg zawierający nazwę zachowania do użycia w punkcie końcowym.</span><span class="sxs-lookup"><span data-stu-id="23549-117">A string that contains the name of the behavior to be used in the endpoint.</span></span>|  
|<span data-ttu-id="23549-118">powiązanie</span><span class="sxs-lookup"><span data-stu-id="23549-118">binding</span></span>|<span data-ttu-id="23549-119">Wymagany atrybut ciągu, który określa typ powiązania do użycia.</span><span class="sxs-lookup"><span data-stu-id="23549-119">Required string attribute that specifies the type of binding to use.</span></span> <span data-ttu-id="23549-120">Aby można było odwołać, typ musi mieć zarejestrowaną sekcję konfiguracyjną.</span><span class="sxs-lookup"><span data-stu-id="23549-120">The type must have a registered configuration section in order to be referenced.</span></span> <span data-ttu-id="23549-121">Typ jest typem zarejestrowanym według nazwy sekcji, a nie nazwą typu powiązania.</span><span class="sxs-lookup"><span data-stu-id="23549-121">The type is the registered by section name, rather than by the type name of the binding.</span></span>|  
|<span data-ttu-id="23549-122">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="23549-122">bindingConfiguration</span></span>|<span data-ttu-id="23549-123">Ciąg określający nazwę powiązania powiązania do użycia podczas tworzenia wystąpienia punktu końcowego.</span><span class="sxs-lookup"><span data-stu-id="23549-123">A string that specifies the binding name of the binding to use when the endpoint is instantiated.</span></span> <span data-ttu-id="23549-124">Nazwa powiązania musi znajdować się w zakresie w punkcie, w którym jest zdefiniowany punkt końcowy.</span><span class="sxs-lookup"><span data-stu-id="23549-124">The binding name must be in scope at the point the endpoint is defined.</span></span> <span data-ttu-id="23549-125">Wartość domyślna to pusty ciąg.</span><span class="sxs-lookup"><span data-stu-id="23549-125">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="23549-126">Ten atrybut jest używany w połączeniu z programem w `binding` celu odwoływania się do określonej konfiguracji powiązań w pliku konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="23549-126">This attribute is used in conjunction with `binding` to reference a specific binding configuration in the configuration file.</span></span> <span data-ttu-id="23549-127">Ustaw ten atrybut, jeśli próbujesz użyć niestandardowego powiązania.</span><span class="sxs-lookup"><span data-stu-id="23549-127">Set this attribute if you are attempting to use a custom binding.</span></span> <span data-ttu-id="23549-128">W przeciwnym razie może zostać zgłoszony wyjątek.</span><span class="sxs-lookup"><span data-stu-id="23549-128">Otherwise, an exception may be thrown.</span></span>|  
|<span data-ttu-id="23549-129">powiązaniename</span><span class="sxs-lookup"><span data-stu-id="23549-129">bindingName</span></span>|<span data-ttu-id="23549-130">Ciąg określający unikalną kwalifikowaną nazwę powiązania w celu eksportu definicji za pomocą WSDL.</span><span class="sxs-lookup"><span data-stu-id="23549-130">A string that specifies the unique qualified name of the binding for definition export through WSDL.</span></span> <span data-ttu-id="23549-131">Wartość domyślna to pusty ciąg.</span><span class="sxs-lookup"><span data-stu-id="23549-131">The default is an empty string.</span></span>|  
|<span data-ttu-id="23549-132">bindingNamespace</span><span class="sxs-lookup"><span data-stu-id="23549-132">bindingNamespace</span></span>|<span data-ttu-id="23549-133">Ciąg określający kwalifikowaną nazwę przestrzeni nazw powiązania w celu eksportu definicji za pomocą WSDL.</span><span class="sxs-lookup"><span data-stu-id="23549-133">A string that specifies the qualified name of the namespace of the binding for definition export through WSDL.</span></span> <span data-ttu-id="23549-134">Wartość domyślna to pusty ciąg.</span><span class="sxs-lookup"><span data-stu-id="23549-134">The default is an empty string.</span></span>|  
|<span data-ttu-id="23549-135">przedsiębiorc</span><span class="sxs-lookup"><span data-stu-id="23549-135">contract</span></span>|<span data-ttu-id="23549-136">Ciąg wskazujący, który kontrakt jest ujawniany przez ten punkt końcowy.</span><span class="sxs-lookup"><span data-stu-id="23549-136">A string that indicates which contract this endpoint is exposing.</span></span> <span data-ttu-id="23549-137">Zestaw musi implementować typ kontraktu.</span><span class="sxs-lookup"><span data-stu-id="23549-137">The assembly must implement the contract type.</span></span> <span data-ttu-id="23549-138">Jeśli implementacja usługi implementuje pojedynczy typ kontraktu, ta właściwość może zostać pominięta.</span><span class="sxs-lookup"><span data-stu-id="23549-138">If a service implementation implements a single contract type, then this property can be omitted.</span></span> <span data-ttu-id="23549-139">Wartość domyślna to pusty ciąg.</span><span class="sxs-lookup"><span data-stu-id="23549-139">The default is an empty string.</span></span>|  
|<span data-ttu-id="23549-140">endpointConfiguration</span><span class="sxs-lookup"><span data-stu-id="23549-140">endpointConfiguration</span></span>|<span data-ttu-id="23549-141">Ciąg określający nazwę standardowego punktu końcowego, który jest ustawiany przez `kind` atrybut, który odwołuje się do dodatkowych informacji konfiguracyjnych tego standardowego punktu końcowego.</span><span class="sxs-lookup"><span data-stu-id="23549-141">A string that specifies the name of the standard endpoint that is set by the `kind` attribute, which references to the additional configuration information of this standard endpoint.</span></span> <span data-ttu-id="23549-142">Ta sama nazwa musi być zdefiniowana w `<standardEndpoints>` sekcji.</span><span class="sxs-lookup"><span data-stu-id="23549-142">The same name must be defined in the `<standardEndpoints>` section.</span></span>|  
|<span data-ttu-id="23549-143">isSystemEndpoint</span><span class="sxs-lookup"><span data-stu-id="23549-143">isSystemEndpoint</span></span>|<span data-ttu-id="23549-144">Wartość logiczna określająca, czy punkt końcowy jest punktem końcowym infrastruktury.</span><span class="sxs-lookup"><span data-stu-id="23549-144">A Boolean value that specifies whether an endpoint is an infrastructure endpoint.</span></span>|  
|<span data-ttu-id="23549-145">Natur</span><span class="sxs-lookup"><span data-stu-id="23549-145">kind</span></span>|<span data-ttu-id="23549-146">Ciąg określający typ stosowanego standardowego punktu końcowego.</span><span class="sxs-lookup"><span data-stu-id="23549-146">A string that specifies the type of standard endpoint applied.</span></span> <span data-ttu-id="23549-147">Typ musi być zarejestrowany w `<extensions>` sekcji lub w machine.config. Jeśli nic nie zostanie określone, tworzony jest wspólny punkt końcowy usługi.</span><span class="sxs-lookup"><span data-stu-id="23549-147">The type must be registered in the `<extensions>` section or in machine.config. If nothing is specified, a common service endpoint is created.</span></span>|  
|<span data-ttu-id="23549-148">listenUriMode</span><span class="sxs-lookup"><span data-stu-id="23549-148">listenUriMode</span></span>|<span data-ttu-id="23549-149">Określa sposób, w jaki transport traktuje `ListenUri` podany na potrzeby nasłuchiwania usługi.</span><span class="sxs-lookup"><span data-stu-id="23549-149">Specifies how the transport treats the `ListenUri` provided for the service to listen on.</span></span> <span data-ttu-id="23549-150">Prawidłowe wartości to</span><span class="sxs-lookup"><span data-stu-id="23549-150">Valid values are</span></span><br /><br /> <span data-ttu-id="23549-151">-Jawne</span><span class="sxs-lookup"><span data-stu-id="23549-151">-   Explicit</span></span><br /><span data-ttu-id="23549-152">-Unikatowy</span><span class="sxs-lookup"><span data-stu-id="23549-152">-   Unique</span></span><br /><br /> <span data-ttu-id="23549-153">Wartość domyślna to explicit.</span><span class="sxs-lookup"><span data-stu-id="23549-153">The default value is Explicit.</span></span>|  
|<span data-ttu-id="23549-154">ListenUri o wartości</span><span class="sxs-lookup"><span data-stu-id="23549-154">listenUri</span></span>|<span data-ttu-id="23549-155">Ciąg określający identyfikator URI, z którego nasłuchuje punkt końcowy usługi.</span><span class="sxs-lookup"><span data-stu-id="23549-155">A string that specifies the URI at which the service endpoint listens.</span></span> <span data-ttu-id="23549-156">Wartość domyślna to pusty ciąg.</span><span class="sxs-lookup"><span data-stu-id="23549-156">The default is an empty string.</span></span>|  
|<span data-ttu-id="23549-157">name</span><span class="sxs-lookup"><span data-stu-id="23549-157">name</span></span>|<span data-ttu-id="23549-158">Atrybut opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="23549-158">Optional attribute.</span></span> <span data-ttu-id="23549-159">Ciąg określający nazwę punktu końcowego usługi.</span><span class="sxs-lookup"><span data-stu-id="23549-159">A string that specifies the name the service endpoint.</span></span> <span data-ttu-id="23549-160">Wartość domyślna to połączenie nazwy powiązania i nazwy opisu kontraktu.</span><span class="sxs-lookup"><span data-stu-id="23549-160">The default value is the concatenation of the binding name and the contract description name.</span></span> <span data-ttu-id="23549-161">Usługi mogą mieć wiele punktów końcowych, więc atrybut punktu końcowego `name` różni się od nazwy usługi.</span><span class="sxs-lookup"><span data-stu-id="23549-161">Services may have multiple endpoints, so the endpoint’s `name` attribute is distinct from the name of the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="23549-162">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="23549-162">Child Elements</span></span>  
  
|<span data-ttu-id="23549-163">Element</span><span class="sxs-lookup"><span data-stu-id="23549-163">Element</span></span>|<span data-ttu-id="23549-164">Opis</span><span class="sxs-lookup"><span data-stu-id="23549-164">Description</span></span>|  
|-------------|-----------------|  
|[\<headers>](headers.md)|<span data-ttu-id="23549-165">Kolekcja nagłówków adresów.</span><span class="sxs-lookup"><span data-stu-id="23549-165">A collection of address headers.</span></span>|  
|[\<identity>](identity.md)|<span data-ttu-id="23549-166">Tożsamość, która umożliwia uwierzytelnianie punktu końcowego przez inne punkty końcowe wymieniające z nim komunikaty.</span><span class="sxs-lookup"><span data-stu-id="23549-166">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="23549-167">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="23549-167">Parent Elements</span></span>  
  
|<span data-ttu-id="23549-168">Element</span><span class="sxs-lookup"><span data-stu-id="23549-168">Element</span></span>|<span data-ttu-id="23549-169">Opis</span><span class="sxs-lookup"><span data-stu-id="23549-169">Description</span></span>|  
|-------------|-----------------|  
|[\<service>](service.md)|<span data-ttu-id="23549-170">Sekcja konfiguracji, która definiuje listę punktów końcowych, z którymi klient może się połączyć.</span><span class="sxs-lookup"><span data-stu-id="23549-170">A configuration section that defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="23549-171">Przykład</span><span class="sxs-lookup"><span data-stu-id="23549-171">Example</span></span>  

 <span data-ttu-id="23549-172">Jest to przykład konfiguracji punktu końcowego usługi.</span><span class="sxs-lookup"><span data-stu-id="23549-172">This is an example of a service endpoint configuration.</span></span>  
  
```xml  
<endpoint address="/HelloWorld/"
          bindingConfiguration="usingDefaults"
          bindingName="MyBinding"
          binding="customBinding"
          contract="HelloWorld">
  <headers>
    <region xmlns="http://tempuri.org/">EastCoast</region>
    <member xmlns="http://tempuri.org/">Gold</member>
  </headers>
</endpoint>
```  
  
## <a name="see-also"></a><span data-ttu-id="23549-173">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="23549-173">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceEndpointElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.Description.ServiceEndpoint>
- [<span data-ttu-id="23549-174">Punkty końcowe: adresy, wiązania i kontrakty</span><span class="sxs-lookup"><span data-stu-id="23549-174">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
- [<span data-ttu-id="23549-175">Instrukcje: tworzenie punktu końcowego usługi w konfiguracji</span><span class="sxs-lookup"><span data-stu-id="23549-175">How to: Create a Service Endpoint in Configuration</span></span>](../../../wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)
