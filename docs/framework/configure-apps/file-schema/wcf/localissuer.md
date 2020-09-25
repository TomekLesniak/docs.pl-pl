---
title: <localIssuer>
ms.date: 03/30/2017
ms.assetid: 26bdd0df-0e7d-4b9e-bbeb-f28c53769385
ms.openlocfilehash: e08d2c0b42cfd8e302223915f0256f8cb2d1468b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204960"
---
# \<localIssuer>

<span data-ttu-id="71814-101">Określa adres i powiązanie wystawcy lokalnego używanego do uzyskania tokenu zabezpieczającego.</span><span class="sxs-lookup"><span data-stu-id="71814-101">Specifies the address and binding of the local issuer to be used to obtain a security token.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedToken>**](issuedtoken.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<localIssuer>**  
  
## <a name="syntax"></a><span data-ttu-id="71814-102">Składnia</span><span class="sxs-lookup"><span data-stu-id="71814-102">Syntax</span></span>  
  
```xml  
<localIssuer address="String"
             binding="String"
             bindingConfiguration="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="71814-103">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="71814-103">Attributes and Elements</span></span>  

 <span data-ttu-id="71814-104">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="71814-104">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="71814-105">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="71814-105">Attributes</span></span>  
  
|<span data-ttu-id="71814-106">Atrybut</span><span class="sxs-lookup"><span data-stu-id="71814-106">Attribute</span></span>|<span data-ttu-id="71814-107">Opis</span><span class="sxs-lookup"><span data-stu-id="71814-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="71814-108">adres</span><span class="sxs-lookup"><span data-stu-id="71814-108">address</span></span>|<span data-ttu-id="71814-109">Wymagany ciąg.</span><span class="sxs-lookup"><span data-stu-id="71814-109">Required string.</span></span> <span data-ttu-id="71814-110">Określa identyfikator URI wystawcy lokalnego.</span><span class="sxs-lookup"><span data-stu-id="71814-110">Specifies the URI of the local issuer.</span></span>|  
|<span data-ttu-id="71814-111">powiązanie</span><span class="sxs-lookup"><span data-stu-id="71814-111">binding</span></span>|<span data-ttu-id="71814-112">Opcjonalny ciąg.</span><span class="sxs-lookup"><span data-stu-id="71814-112">Optional string.</span></span> <span data-ttu-id="71814-113">Jedno z powiązań dostarczonych przez system.</span><span class="sxs-lookup"><span data-stu-id="71814-113">One of the system-provided bindings.</span></span> <span data-ttu-id="71814-114">Aby uzyskać listę, zobacz [powiązania dostarczone przez system](../../../wcf/system-provided-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="71814-114">For a list, see [System-Provided Bindings](../../../wcf/system-provided-bindings.md).</span></span>|  
|<span data-ttu-id="71814-115">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="71814-115">bindingConfiguration</span></span>|<span data-ttu-id="71814-116">Opcjonalny ciąg.</span><span class="sxs-lookup"><span data-stu-id="71814-116">Optional string.</span></span> <span data-ttu-id="71814-117">Określa konfigurację powiązania znalezioną w pliku konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="71814-117">Specifies a binding configuration found in the configuration file.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="71814-118">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="71814-118">Child Elements</span></span>  
  
|<span data-ttu-id="71814-119">Element</span><span class="sxs-lookup"><span data-stu-id="71814-119">Element</span></span>|<span data-ttu-id="71814-120">Opis</span><span class="sxs-lookup"><span data-stu-id="71814-120">Description</span></span>|  
|-------------|-----------------|  
|[\<identity>](identity.md)|<span data-ttu-id="71814-121">Określa informacje o tożsamości dla wystawcy lokalnego.</span><span class="sxs-lookup"><span data-stu-id="71814-121">Specifies identity information for the local issuer.</span></span>|  
|[\<headers>](headers-element.md)|<span data-ttu-id="71814-122">Kolekcja nagłówków adresów, które są wymagane w celu prawidłowego adresowania wystawcy lokalnego.</span><span class="sxs-lookup"><span data-stu-id="71814-122">A collection of address headers that are required in order to correctly address the local issuer.</span></span> <span data-ttu-id="71814-123">Możesz użyć `add` słowa kluczowego, aby dodać nagłówek do tej kolekcji.</span><span class="sxs-lookup"><span data-stu-id="71814-123">You can use the `add` keyword to add a header to this collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="71814-124">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="71814-124">Parent Elements</span></span>  
  
|<span data-ttu-id="71814-125">Element</span><span class="sxs-lookup"><span data-stu-id="71814-125">Element</span></span>|<span data-ttu-id="71814-126">Opis</span><span class="sxs-lookup"><span data-stu-id="71814-126">Description</span></span>|  
|-------------|-----------------|  
|[\<issuedToken>](issuedtoken.md)|<span data-ttu-id="71814-127">Określa niestandardowy token używany do uwierzytelniania klienta w usłudze.</span><span class="sxs-lookup"><span data-stu-id="71814-127">Specifies a custom token used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="71814-128">Uwagi</span><span class="sxs-lookup"><span data-stu-id="71814-128">Remarks</span></span>  

 <span data-ttu-id="71814-129">W przypadku uzyskiwania wystawionego tokenu z usługi tokenu zabezpieczającego (STS), aplikacja kliencka musi być skonfigurowana przy użyciu adresu i powiązania, które ma być używane do komunikacji z usługą STS.</span><span class="sxs-lookup"><span data-stu-id="71814-129">When obtaining an issued token from a Security Token Service (STS), the client application must be configured with the address and binding to use to communicate with the STS.</span></span> <span data-ttu-id="71814-130">Jeśli nie <xref:System.ServiceModel.WSFederationHttpBinding> podasz adresu URL usługi tokenu zabezpieczającego lub gdy adres wystawcy powiązania federacyjnego to `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` lub `null` , kanał Windows Communication Foundation (WCF) klienta używa wartości określonych przez `address` i `binding` do komunikacji z usługą STS w celu uzyskania wystawionego tokenu.</span><span class="sxs-lookup"><span data-stu-id="71814-130">When the <xref:System.ServiceModel.WSFederationHttpBinding> does not supply a URL for the security token service, or when the issuer address of a federated binding is `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` or `null`, the client's Windows Communication Foundation (WCF) channel uses the values specified by `address` and `binding` to communicate with the STS to obtain the issued token.</span></span> <span data-ttu-id="71814-131">Aby uzyskać więcej informacji na temat konfigurowania wystawcy lokalnego, zobacz [How to: Configure a Local wystawca](../../../wcf/feature-details/how-to-configure-a-local-issuer.md).</span><span class="sxs-lookup"><span data-stu-id="71814-131">For more information on configuring a local issuer, see [How to: Configure a Local Issuer](../../../wcf/feature-details/how-to-configure-a-local-issuer.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="71814-132">Przykład</span><span class="sxs-lookup"><span data-stu-id="71814-132">Example</span></span>  

 <span data-ttu-id="71814-133">W poniższym przykładzie ustawiono `address` atrybuty, `binding` , i `bindingConfiguration` `localIssuer` elementu.</span><span class="sxs-lookup"><span data-stu-id="71814-133">The following example sets the `address`, `binding`, and `bindingConfiguration` attributes of a `localIssuer` element.</span></span>  
  
```xml  
<system.serviceModel>
  <behaviors>
    <endpointBehaviors>
      <behavior name="MyEndpointBehavior">
        <clientCredentials>
          <issuedToken cacheIssuedTokens="false"
                       defaultKeyEntropyMode="ClientEntropy">
            <localIssuer address="net.tcp://cohowinery/tokens"
                         binding="netTcpBinding"
                         bindingConfiguration="myTcpBindingConfig" />
          </issuedToken>
        </clientCredentials>
      </behavior>
    </endpointBehaviors>
  </behaviors>
</system.serviceModel>
```  
  
## <a name="see-also"></a><span data-ttu-id="71814-134">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="71814-134">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.LocalIssuer%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential>
- [<span data-ttu-id="71814-135">Zachowania zabezpieczeń</span><span class="sxs-lookup"><span data-stu-id="71814-135">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="71814-136">Instrukcje: konfigurowanie lokalnego wystawcy</span><span class="sxs-lookup"><span data-stu-id="71814-136">How to: Configure a Local Issuer</span></span>](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="71814-137">Uwierzytelnianie i tożsamość usług</span><span class="sxs-lookup"><span data-stu-id="71814-137">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="71814-138">Zachowania zabezpieczeń</span><span class="sxs-lookup"><span data-stu-id="71814-138">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="71814-139">Federacja i wystawione tokeny</span><span class="sxs-lookup"><span data-stu-id="71814-139">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="71814-140">Zabezpieczanie usług i klientów</span><span class="sxs-lookup"><span data-stu-id="71814-140">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- <span data-ttu-id="71814-141">[Zabezpieczanie klientów [WCF]](../../../wcf/securing-clients.md)</span><span class="sxs-lookup"><span data-stu-id="71814-141">[Securing Clients](../../../wcf/securing-clients.md)</span></span>
- [<span data-ttu-id="71814-142">Instrukcje: tworzenie klienta federacyjnego</span><span class="sxs-lookup"><span data-stu-id="71814-142">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="71814-143">Federacja i wystawione tokeny</span><span class="sxs-lookup"><span data-stu-id="71814-143">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
