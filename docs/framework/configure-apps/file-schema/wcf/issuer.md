---
title: <issuer>
ms.date: 03/30/2017
ms.assetid: 8c49c6ae-fa1a-4179-a84b-613c3216dcde
ms.openlocfilehash: 9e92bbcacf529a97e1ae936e93e38c98eab19cab
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91157268"
---
# \<issuer>

<span data-ttu-id="cd0f3-101">Określa usługę tokenu zabezpieczającego (STS), która wystawia tokeny zabezpieczające.</span><span class="sxs-lookup"><span data-stu-id="cd0f3-101">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuer>**  
  
## <a name="syntax"></a><span data-ttu-id="cd0f3-102">Składnia</span><span class="sxs-lookup"><span data-stu-id="cd0f3-102">Syntax</span></span>  
  
```xml  
<issuer address="Uri">
  <headers>
    <add name="String"
         namespace="String" />
  </headers>
  <identity>
    <certificate encodedValue="String" />
    <certificateReference findValue="String"
                          isChainIncluded="Boolean"
                          storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                          storeLocation="LocalMachine/CurrentUser"
                          x509FindType="System.Security.Cryptography.X509certificates.X509findtype" />
    <dns value="String" />
    <rsa value="String" />
    <servicePrincipalName value="String" />
    <usePrincipalName value="String" />
  </identity>
</issuer>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cd0f3-103">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="cd0f3-103">Attributes and Elements</span></span>  

 <span data-ttu-id="cd0f3-104">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="cd0f3-104">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cd0f3-105">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="cd0f3-105">Attributes</span></span>  
  
|<span data-ttu-id="cd0f3-106">Atrybut</span><span class="sxs-lookup"><span data-stu-id="cd0f3-106">Attribute</span></span>|<span data-ttu-id="cd0f3-107">Opis</span><span class="sxs-lookup"><span data-stu-id="cd0f3-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cd0f3-108">adres</span><span class="sxs-lookup"><span data-stu-id="cd0f3-108">address</span></span>|<span data-ttu-id="cd0f3-109">Wymagany ciąg.</span><span class="sxs-lookup"><span data-stu-id="cd0f3-109">Required string.</span></span> <span data-ttu-id="cd0f3-110">Adres URL usługi STS.</span><span class="sxs-lookup"><span data-stu-id="cd0f3-110">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cd0f3-111">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="cd0f3-111">Child Elements</span></span>  
  
|<span data-ttu-id="cd0f3-112">Element</span><span class="sxs-lookup"><span data-stu-id="cd0f3-112">Element</span></span>|<span data-ttu-id="cd0f3-113">Opis</span><span class="sxs-lookup"><span data-stu-id="cd0f3-113">Description</span></span>|  
|-------------|-----------------|  
|[\<headers>](headers-element.md)|<span data-ttu-id="cd0f3-114">Kolekcja nagłówków adresów dla punktów końcowych, które może utworzyć Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="cd0f3-114">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[\<identity>](identity.md)|<span data-ttu-id="cd0f3-115">W przypadku korzystania z wystawionego tokenu określa ustawienia, które umożliwiają klientowi uwierzytelnienie serwera.</span><span class="sxs-lookup"><span data-stu-id="cd0f3-115">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cd0f3-116">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="cd0f3-116">Parent Elements</span></span>  
  
|<span data-ttu-id="cd0f3-117">Element</span><span class="sxs-lookup"><span data-stu-id="cd0f3-117">Element</span></span>|<span data-ttu-id="cd0f3-118">Opis</span><span class="sxs-lookup"><span data-stu-id="cd0f3-118">Description</span></span>|  
|-------------|-----------------|  
|[\<message>](message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="cd0f3-119">Definiuje ustawienia zabezpieczeń na poziomie wiadomości dla [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) elementu.</span><span class="sxs-lookup"><span data-stu-id="cd0f3-119">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cd0f3-120">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="cd0f3-120">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.Issuer%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>
- [<span data-ttu-id="cd0f3-121">Uwierzytelnianie i tożsamość usług</span><span class="sxs-lookup"><span data-stu-id="cd0f3-121">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="cd0f3-122">Federacja i wystawione tokeny</span><span class="sxs-lookup"><span data-stu-id="cd0f3-122">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="cd0f3-123">Uwierzytelnianie i tożsamość usług</span><span class="sxs-lookup"><span data-stu-id="cd0f3-123">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="cd0f3-124">Federacja i wystawione tokeny</span><span class="sxs-lookup"><span data-stu-id="cd0f3-124">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="cd0f3-125">Możliwości zabezpieczeń wiązań niestandardowych</span><span class="sxs-lookup"><span data-stu-id="cd0f3-125">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="cd0f3-126">Federacja i wystawione tokeny</span><span class="sxs-lookup"><span data-stu-id="cd0f3-126">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
