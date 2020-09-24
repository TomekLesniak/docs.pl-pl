---
title: <serviceMetadata>
ms.date: 03/30/2017
ms.assetid: 2b4c3b4c-31d4-4908-a9b7-5bb411c221f2
ms.openlocfilehash: 2236361316254d065abd1fb62fd2e509be289a4c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153862"
---
# \<serviceMetadata>

<span data-ttu-id="40154-101">Określa publikację metadanych usługi i skojarzonych z nią informacji.</span><span class="sxs-lookup"><span data-stu-id="40154-101">Specifies the publication of service metadata and associated information.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceMetadata>**  
  
## <a name="syntax"></a><span data-ttu-id="40154-102">Składnia</span><span class="sxs-lookup"><span data-stu-id="40154-102">Syntax</span></span>  
  
```xml  
<serviceMetadata externalMetadataLocation="String"
                 httpGetBinding="String"
                 httpGetBindingConfiguration="String"
                 httpGetEnabled="Boolean"
                 httpGetUrl="String"
                 httpsGetBinding="String"
                 httpsGetBindingConfiguration="String"
                 httpsGetEnabled="Boolean"
                 httpsGetUrl="String"
                 policyVersion="Policy12/Policy15" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="40154-103">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="40154-103">Attributes and Elements</span></span>  

 <span data-ttu-id="40154-104">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="40154-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="40154-105">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="40154-105">Attributes</span></span>  
  
|<span data-ttu-id="40154-106">Atrybut</span><span class="sxs-lookup"><span data-stu-id="40154-106">Attribute</span></span>|<span data-ttu-id="40154-107">Opis</span><span class="sxs-lookup"><span data-stu-id="40154-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="40154-108">externalMetadataLocation</span><span class="sxs-lookup"><span data-stu-id="40154-108">externalMetadataLocation</span></span>|<span data-ttu-id="40154-109">Identyfikator URI, który zawiera lokalizację pliku WSDL, który jest zwracany do użytkownika w odpowiedzi na żądania WSDL i MEX zamiast automatycznie generowanego WSDL.</span><span class="sxs-lookup"><span data-stu-id="40154-109">A Uri that contains the location of a WSDL file, which is returned to the user in response to WSDL and MEX requests instead of the auto-generated WSDL.</span></span> <span data-ttu-id="40154-110">Gdy ten atrybut nie jest ustawiony, zwracany jest domyślny element WSDL.</span><span class="sxs-lookup"><span data-stu-id="40154-110">When this attribute is not set, the default WSDL is returned.</span></span> <span data-ttu-id="40154-111">Wartość domyślna to pusty ciąg.</span><span class="sxs-lookup"><span data-stu-id="40154-111">The default is an empty string.</span></span>|  
|<span data-ttu-id="40154-112">httpGetBinding</span><span class="sxs-lookup"><span data-stu-id="40154-112">httpGetBinding</span></span>|<span data-ttu-id="40154-113">Ciąg określający typ powiązania, które będzie używane na potrzeby pobierania metadanych za pośrednictwem protokołu HTTP GET.</span><span class="sxs-lookup"><span data-stu-id="40154-113">A string that specifies the type of the binding that will be used for metadata retrieval via HTTP GET.</span></span> <span data-ttu-id="40154-114">To ustawienie jest opcjonalne.</span><span class="sxs-lookup"><span data-stu-id="40154-114">This setting is optional.</span></span> <span data-ttu-id="40154-115">Jeśli nie zostanie określony, zostaną użyte domyślne powiązania.</span><span class="sxs-lookup"><span data-stu-id="40154-115">If it is not specified, the default bindings will be used.</span></span><br /><br /> <span data-ttu-id="40154-116">Obsługiwane są tylko powiązania z wewnętrznymi elementami powiązania, które obsługują <xref:System.ServiceModel.Channels.IReplyChannel> .</span><span class="sxs-lookup"><span data-stu-id="40154-116">Only bindings with inner binding elements that support <xref:System.ServiceModel.Channels.IReplyChannel> will be supported.</span></span> <span data-ttu-id="40154-117">Ponadto <xref:System.ServiceModel.Channels.MessageVersion> właściwość powiązania musi mieć wartość <xref:System.ServiceModel.Channels.MessageVersion.None%2A> .</span><span class="sxs-lookup"><span data-stu-id="40154-117">Additionally, the <xref:System.ServiceModel.Channels.MessageVersion> property of the binding must be <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span>|  
|<span data-ttu-id="40154-118">httpGetBindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="40154-118">httpGetBindingConfiguration</span></span>|<span data-ttu-id="40154-119">Ciąg określający nazwę powiązania, które jest określone w `httpGetBinding` atrybucie, który odwołuje się do dodatkowych informacji konfiguracyjnych tego powiązania.</span><span class="sxs-lookup"><span data-stu-id="40154-119">A string that sets the name of the binding that is specified in the `httpGetBinding` attribute, which references to the additional configuration information of this binding.</span></span> <span data-ttu-id="40154-120">Ta sama nazwa musi być zdefiniowana w `<bindings>` sekcji.</span><span class="sxs-lookup"><span data-stu-id="40154-120">The same name must be defined in the `<bindings>` section.</span></span>|  
|<span data-ttu-id="40154-121">httpGetEnabled</span><span class="sxs-lookup"><span data-stu-id="40154-121">httpGetEnabled</span></span>|<span data-ttu-id="40154-122">Wartość logiczna określająca, czy publikować metadane usługi do pobrania za pomocą żądania HTTP/GET.</span><span class="sxs-lookup"><span data-stu-id="40154-122">A Boolean value that specifies whether to publish service metadata for retrieval using an HTTP/Get request.</span></span> <span data-ttu-id="40154-123">Wartość domyślna to `false`.</span><span class="sxs-lookup"><span data-stu-id="40154-123">The default is `false`.</span></span><br /><br /> <span data-ttu-id="40154-124">Jeśli atrybut httpGetUrl nie jest określony, adres usługi, w którym publikowane są metadane, jest adresem usług i "WSDL".</span><span class="sxs-lookup"><span data-stu-id="40154-124">If the httpGetUrl attribute is not specified, the address at which the metadata is published is the service address plus a "?wsdl".</span></span> <span data-ttu-id="40154-125">Jeśli na przykład adres usługi to `http://localhost:8080/CalculatorService` , adres HTTP/GET metadanych to `http://localhost:8080/CalculatorService?wsdl` .</span><span class="sxs-lookup"><span data-stu-id="40154-125">For example, if the service address is `http://localhost:8080/CalculatorService`, the HTTP/Get metadata address is `http://localhost:8080/CalculatorService?wsdl`.</span></span><br /><br /> <span data-ttu-id="40154-126">Jeśli ta właściwość jest `false` lub adres usługi nie jest oparty na protokole HTTP lub https, "WSDL" jest ignorowany.</span><span class="sxs-lookup"><span data-stu-id="40154-126">If this property is `false`, or the address of the service is not based on HTTP or HTTPS, "?wsdl" is ignored.</span></span>|  
|<span data-ttu-id="40154-127">httpGetUrl</span><span class="sxs-lookup"><span data-stu-id="40154-127">httpGetUrl</span></span>|<span data-ttu-id="40154-128">Identyfikator URI, który określa adres, w którym publikowane są metadane do pobrania za pomocą żądania HTTP/GET.</span><span class="sxs-lookup"><span data-stu-id="40154-128">A Uri that specifies the address at which the metadata is published for retrieval using an HTTP/Get request.</span></span> <span data-ttu-id="40154-129">Jeśli określono względny identyfikator URI, będzie on traktowany jako względny w stosunku do adresu podstawowego usługi.</span><span class="sxs-lookup"><span data-stu-id="40154-129">If a relative Uri is specified it will be treated as relative to the service’s base address.</span></span>|  
|<span data-ttu-id="40154-130">httpsGetBinding</span><span class="sxs-lookup"><span data-stu-id="40154-130">httpsGetBinding</span></span>|<span data-ttu-id="40154-131">Ciąg określający typ powiązania, które będzie używane na potrzeby pobierania metadanych za pośrednictwem protokołu HTTPS GET.</span><span class="sxs-lookup"><span data-stu-id="40154-131">A string that specifies the type of the binding that will be used for metadata retrieval via HTTPS GET.</span></span> <span data-ttu-id="40154-132">To ustawienie jest opcjonalne.</span><span class="sxs-lookup"><span data-stu-id="40154-132">This setting is optional.</span></span> <span data-ttu-id="40154-133">Jeśli nie zostanie określony, zostaną użyte domyślne powiązania.</span><span class="sxs-lookup"><span data-stu-id="40154-133">If it is not specified, the default bindings will be used.</span></span><br /><br /> <span data-ttu-id="40154-134">Obsługiwane są tylko powiązania z wewnętrznymi elementami powiązania, które obsługują <xref:System.ServiceModel.Channels.IReplyChannel> .</span><span class="sxs-lookup"><span data-stu-id="40154-134">Only bindings with inner binding elements that support <xref:System.ServiceModel.Channels.IReplyChannel> will be supported.</span></span> <span data-ttu-id="40154-135">Ponadto <xref:System.ServiceModel.Channels.MessageVersion> właściwość powiązania musi mieć wartość <xref:System.ServiceModel.Channels.MessageVersion.None%2A> .</span><span class="sxs-lookup"><span data-stu-id="40154-135">Additionally, the <xref:System.ServiceModel.Channels.MessageVersion> property of the binding must be <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span>|  
|<span data-ttu-id="40154-136">httpsGetBindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="40154-136">httpsGetBindingConfiguration</span></span>|<span data-ttu-id="40154-137">Ciąg określający nazwę powiązania, które jest określone w `httpsGetBinding` atrybucie, który odwołuje się do dodatkowych informacji konfiguracyjnych tego powiązania.</span><span class="sxs-lookup"><span data-stu-id="40154-137">A string that sets the name of the binding that is specified in the `httpsGetBinding` attribute, which references to the additional configuration information of this binding.</span></span> <span data-ttu-id="40154-138">Ta sama nazwa musi być zdefiniowana w `<bindings>` sekcji.</span><span class="sxs-lookup"><span data-stu-id="40154-138">The same name must be defined in the `<bindings>` section.</span></span>|  
|<span data-ttu-id="40154-139">httpsGetEnabled</span><span class="sxs-lookup"><span data-stu-id="40154-139">httpsGetEnabled</span></span>|<span data-ttu-id="40154-140">Wartość logiczna określająca, czy publikować metadane usługi do pobrania za pomocą żądania HTTPS/GET.</span><span class="sxs-lookup"><span data-stu-id="40154-140">A Boolean value that specifies whether to publish service metadata for retrieval using an HTTPS/Get request.</span></span> <span data-ttu-id="40154-141">Wartość domyślna to `false`.</span><span class="sxs-lookup"><span data-stu-id="40154-141">The default is `false`.</span></span><br /><br /> <span data-ttu-id="40154-142">Jeśli atrybut httpsGetUrl nie jest określony, adres usługi, w którym publikowane są metadane, jest adresem usług i "WSDL".</span><span class="sxs-lookup"><span data-stu-id="40154-142">If the httpsGetUrl attribute is not specified, the address at which the metadata is published is the service address plus a "?wsdl".</span></span> <span data-ttu-id="40154-143">Jeśli na przykład adres usługi to " https://localhost:8080/CalculatorService ", adres HTTP/GET metadanych to " https://localhost:8080/CalculatorService?wsdl ".</span><span class="sxs-lookup"><span data-stu-id="40154-143">For example, if the service address is "https://localhost:8080/CalculatorService", the HTTP/Get metadata address is "https://localhost:8080/CalculatorService?wsdl".</span></span><br /><br /> <span data-ttu-id="40154-144">Jeśli ta właściwość jest `false` lub adres usługi nie jest oparty na protokole HTTP lub https, "WSDL" jest ignorowany.</span><span class="sxs-lookup"><span data-stu-id="40154-144">If this property is `false`, or the address of the service is not based on HTTP or HTTPS, "?wsdl" is ignored.</span></span>|  
|<span data-ttu-id="40154-145">httpsGetUrl</span><span class="sxs-lookup"><span data-stu-id="40154-145">httpsGetUrl</span></span>|<span data-ttu-id="40154-146">Identyfikator URI, który określa adres, w którym publikowane są metadane do pobrania za pomocą żądania HTTPS/GET.</span><span class="sxs-lookup"><span data-stu-id="40154-146">A Uri that specifies the address at which the metadata is published for retrieval using an HTTPS/Get request.</span></span>|  
|<span data-ttu-id="40154-147">policyVersion</span><span class="sxs-lookup"><span data-stu-id="40154-147">policyVersion</span></span>|<span data-ttu-id="40154-148">Ciąg określający używaną wersję specyfikacji WS-Policy.</span><span class="sxs-lookup"><span data-stu-id="40154-148">A string that specifies the version of the WS-Policy specification being used.</span></span> <span data-ttu-id="40154-149">Ten atrybut jest typu <xref:System.ServiceModel.Description.PolicyVersion> .</span><span class="sxs-lookup"><span data-stu-id="40154-149">This attribute is of type <xref:System.ServiceModel.Description.PolicyVersion>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="40154-150">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="40154-150">Child Elements</span></span>  

 <span data-ttu-id="40154-151">Brak</span><span class="sxs-lookup"><span data-stu-id="40154-151">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="40154-152">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="40154-152">Parent Elements</span></span>  
  
|<span data-ttu-id="40154-153">Element</span><span class="sxs-lookup"><span data-stu-id="40154-153">Element</span></span>|<span data-ttu-id="40154-154">Opis</span><span class="sxs-lookup"><span data-stu-id="40154-154">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="40154-155">Określa zachowanie elementu.</span><span class="sxs-lookup"><span data-stu-id="40154-155">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="40154-156">Uwagi</span><span class="sxs-lookup"><span data-stu-id="40154-156">Remarks</span></span>  

 <span data-ttu-id="40154-157">Ten element konfiguracji umożliwia kontrolowanie funkcji publikowania metadanych usługi.</span><span class="sxs-lookup"><span data-stu-id="40154-157">This configuration element allows you to control the metadata publishing features of a service.</span></span> <span data-ttu-id="40154-158">Aby zapobiec przypadkowemu ujawnieniu potencjalnie poufnych metadanych usługi, konfiguracja domyślna dla usług Windows Communication Foundation (WCF) wyłącza Publikowanie metadanych.</span><span class="sxs-lookup"><span data-stu-id="40154-158">To prevent unintentional disclosure of potentially sensitive service metadata, the default configuration for Windows Communication Foundation (WCF) services disables metadata publishing.</span></span> <span data-ttu-id="40154-159">To zachowanie jest zabezpieczone domyślnie, ale oznacza to, że nie można użyć narzędzia do importowania metadanych (takiego jak Svcutil.exe) do wygenerowania kodu klienta wymaganego do wywołania usługi, chyba że zachowanie publikowania metadanych usługi jest jawnie włączone w konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="40154-159">This behavior is secure by default, but also means that you cannot use a metadata import tool (such as Svcutil.exe) to generate the client code required to call the service unless the service’s metadata publishing behavior is explicitly enabled in configuration.</span></span> <span data-ttu-id="40154-160">Za pomocą tego elementu konfiguracji można włączyć to zachowanie publikowania dla usługi.</span><span class="sxs-lookup"><span data-stu-id="40154-160">Using this configuration element, you can enable this publishing behavior for your service.</span></span>  
  
 <span data-ttu-id="40154-161">Szczegółowy przykład konfigurowania tego zachowania znajduje się w temacie [zachowanie publikowania metadanych](../../../wcf/samples/metadata-publishing-behavior.md).</span><span class="sxs-lookup"><span data-stu-id="40154-161">For a detailed example of configuring this behavior, see [Metadata Publishing Behavior](../../../wcf/samples/metadata-publishing-behavior.md).</span></span>  
  
 <span data-ttu-id="40154-162">Opcjonalne `httpGetBinding` i `httpsGetBinding` atrybuty umożliwiają skonfigurowanie powiązań używanych na potrzeby pobierania metadanych za pośrednictwem protokołu HTTP GET (lub HTTPS GET).</span><span class="sxs-lookup"><span data-stu-id="40154-162">The optional `httpGetBinding` and `httpsGetBinding` attributes allow you to configure the bindings used for metadata retrieval via HTTP GET (or HTTPS GET).</span></span> <span data-ttu-id="40154-163">Jeśli nie są one określone, domyślne powiązania ( `HttpTransportBindingElement` w przypadku protokołu HTTP i `HttpsTransportBindingElement` , w przypadku protokołu HTTPS) są używane do pobierania metadanych zgodnie z potrzebami.</span><span class="sxs-lookup"><span data-stu-id="40154-163">If they are not specified, the default bindings (`HttpTransportBindingElement`, in the case of HTTP and `HttpsTransportBindingElement`, in the case of HTTPS) are used for metadata retrieval as appropriate.</span></span> <span data-ttu-id="40154-164">Należy zauważyć, że nie można używać tych atrybutów z wbudowanymi powiązaniami programu WCF.</span><span class="sxs-lookup"><span data-stu-id="40154-164">Notice that you cannot use these attributes with the built-in WCF bindings.</span></span> <span data-ttu-id="40154-165">Obsługiwane są tylko powiązania z wewnętrznymi elementami powiązania, które obsługują <xref:System.ServiceModel.Channels.IReplyChannel> .</span><span class="sxs-lookup"><span data-stu-id="40154-165">Only bindings with inner binding elements that support <xref:System.ServiceModel.Channels.IReplyChannel> will be supported.</span></span> <span data-ttu-id="40154-166">Ponadto <xref:System.ServiceModel.Channels.MessageVersion> właściwość powiązania musi mieć wartość <xref:System.ServiceModel.Channels.MessageVersion.None%2A> .</span><span class="sxs-lookup"><span data-stu-id="40154-166">Additionally, the <xref:System.ServiceModel.Channels.MessageVersion> property of the binding must be <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span>  
  
 <span data-ttu-id="40154-167">Aby zmniejszyć narażenie usługi na złośliwych użytkowników, można zabezpieczyć transfer przy użyciu mechanizmu protokołu SSL przez HTTP (HTTPS).</span><span class="sxs-lookup"><span data-stu-id="40154-167">To reduce the exposure of a service to malicious users, it is possible to secure the transfer using the SSL over HTTP (HTTPS) mechanism.</span></span> <span data-ttu-id="40154-168">W tym celu należy najpierw powiązać odpowiedni certyfikat X. 509 z określonym portem na komputerze hostującym usługę.</span><span class="sxs-lookup"><span data-stu-id="40154-168">To do so, you must first bind a suitable X.509 certificate to a specific port on the computer that is hosting the service.</span></span> <span data-ttu-id="40154-169">(Aby uzyskać więcej informacji, zobacz [Praca z certyfikatami](../../../wcf/feature-details/working-with-certificates.md).) Następnie należy dodać ten element do konfiguracji usługi i ustawić `httpsGetEnabled` atrybut na `true` .</span><span class="sxs-lookup"><span data-stu-id="40154-169">(For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).) Second, add this element to the service configuration and set the `httpsGetEnabled` attribute to `true`.</span></span> <span data-ttu-id="40154-170">Na koniec Ustaw `httpsGetUrl` atrybut na adres URL punktu końcowego metadanych usługi, jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="40154-170">Finally, set the `httpsGetUrl` attribute to the URL of the service metadata endpoint, as shown in the following example.</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="NewBehavior">
      <serviceMetadata httpsGetEnabled="true"
                       httpsGetUrl="https://myComputerName/myEndpoint" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="example"></a><span data-ttu-id="40154-171">Przykład</span><span class="sxs-lookup"><span data-stu-id="40154-171">Example</span></span>  

 <span data-ttu-id="40154-172">Poniższy przykład umożliwia skonfigurowanie usługi do uwidaczniania metadanych przy użyciu \<serviceMetadata> elementu.</span><span class="sxs-lookup"><span data-stu-id="40154-172">The following example configure a service to expose metadata by using the \<serviceMetadata> element.</span></span> <span data-ttu-id="40154-173">Umożliwia również skonfigurowanie punktu końcowego w celu udostępnienia `IMetadataExchange` kontraktu jako implementacji protokołu WS-MetadataExchange (Mex).</span><span class="sxs-lookup"><span data-stu-id="40154-173">It also configures an endpoint to expose the `IMetadataExchange` contract as an implementation of a WS-MetadataExchange (MEX) protocol.</span></span> <span data-ttu-id="40154-174">W przykładzie użyto `mexHttpBinding` , który jest wygodnym powiązaniem standardowym, które jest równoważne z `wsHttpBinding` trybem zabezpieczeń ustawionym na `None` .</span><span class="sxs-lookup"><span data-stu-id="40154-174">The example uses the `mexHttpBinding`, which is a convenience standard binding that is equivalent to the `wsHttpBinding` with the security mode set to `None`.</span></span> <span data-ttu-id="40154-175">Adres względny "Mex" jest używany w punkcie końcowym, który po rozwiązaniu z adresem podstawowym usług powoduje adres punktu końcowego `http://localhost/servicemodelsamples/service.svc/mex` .</span><span class="sxs-lookup"><span data-stu-id="40154-175">A relative address of "mex" is used in the endpoint, which when resolved against the services base address results in an endpoint address of `http://localhost/servicemodelsamples/service.svc/mex`.</span></span>  
  
```xml  
<configuration>
  <system.serviceModel>
    <services>
      <service name="Microsoft.ServiceModel.Samples.CalculatorService"
               behaviorConfiguration="CalculatorServiceBehavior">
        <!-- This endpoint is exposed at the base address provided by the host: http://localhost/servicemodelsamples/service.svc -->
        <endpoint address=""
                  binding="wsHttpBinding"
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />
        <!-- The mex endpoint is exposed at http://localhost/servicemodelsamples/service.svc/mex
             To expose the IMetadataExchange contract, you must enable the serviceMetadata behavior as demonstrated below. -->
        <endpoint address="mex"
                  binding="mexHttpBinding"
                  contract="IMetadataExchange" />
      </service>
    </services>
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->
    <behaviors>
      <serviceBehaviors>
        <behavior name="CalculatorServiceBehavior">
          <!-- The serviceMetadata behavior publishes metadata through the IMetadataExchange contract. When this behavior is
               present, you can expose this contract through an endpoint as shown above. Setting httpGetEnabled to true publishes
               the service's WSDL at the <baseaddress>?wsdl eg. http://localhost/servicemodelsamples/service.svc?wsdl -->
          <serviceMetadata httpGetEnabled="True" />
          <serviceDebug includeExceptionDetailInFaults="False" />
        </behavior>
      </serviceBehaviors>
    </behaviors>
  </system.serviceModel>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="40154-176">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="40154-176">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceMetadataPublishingElement>
- <xref:System.ServiceModel.Description.ServiceMetadataBehavior>
- [<span data-ttu-id="40154-177">Zachowania zabezpieczeń</span><span class="sxs-lookup"><span data-stu-id="40154-177">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="40154-178">Zachowanie publikowania metadanych</span><span class="sxs-lookup"><span data-stu-id="40154-178">Metadata Publishing Behavior</span></span>](../../../wcf/samples/metadata-publishing-behavior.md)
