---
title: <issuer> dla <issuedTokenParameters>
ms.date: 03/30/2017
ms.assetid: d6a95f32-d58c-40fc-8658-dd92564d3c90
ms.openlocfilehash: bfe8163d2d6baba1d6e8053f7f6579673d8b4b21
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91157281"
---
# <a name="issuer-of-issuedtokenparameters"></a><span data-ttu-id="faa4b-102">\<issuer> dla \<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="faa4b-102">\<issuer> of \<issuedTokenParameters></span></span>

<span data-ttu-id="faa4b-103">Określa usługę tokenu zabezpieczającego (STS), która wystawia tokeny zabezpieczające.</span><span class="sxs-lookup"><span data-stu-id="faa4b-103">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenParameters>**](issuedtokenparameters.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuer>**  
  
## <a name="syntax"></a><span data-ttu-id="faa4b-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="faa4b-104">Syntax</span></span>  
  
```xml  
<issuer address="Uri" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="faa4b-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="faa4b-105">Attributes and Elements</span></span>  

 <span data-ttu-id="faa4b-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="faa4b-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="faa4b-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="faa4b-107">Attributes</span></span>  
  
|<span data-ttu-id="faa4b-108">Atrybut</span><span class="sxs-lookup"><span data-stu-id="faa4b-108">Attribute</span></span>|<span data-ttu-id="faa4b-109">Opis</span><span class="sxs-lookup"><span data-stu-id="faa4b-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="faa4b-110">adres</span><span class="sxs-lookup"><span data-stu-id="faa4b-110">address</span></span>|<span data-ttu-id="faa4b-111">Wymagany ciąg.</span><span class="sxs-lookup"><span data-stu-id="faa4b-111">Required string.</span></span> <span data-ttu-id="faa4b-112">Adres URL usługi STS.</span><span class="sxs-lookup"><span data-stu-id="faa4b-112">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="faa4b-113">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="faa4b-113">Child Elements</span></span>  
  
|<span data-ttu-id="faa4b-114">Element</span><span class="sxs-lookup"><span data-stu-id="faa4b-114">Element</span></span>|<span data-ttu-id="faa4b-115">Opis</span><span class="sxs-lookup"><span data-stu-id="faa4b-115">Description</span></span>|  
|-------------|-----------------|  
|[\<headers>](headers-element.md)|<span data-ttu-id="faa4b-116">Kolekcja nagłówków adresów dla punktów końcowych, które może utworzyć Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="faa4b-116">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[\<identity>](identity.md)|<span data-ttu-id="faa4b-117">W przypadku korzystania z wystawionego tokenu określa ustawienia, które umożliwiają klientowi uwierzytelnienie serwera.</span><span class="sxs-lookup"><span data-stu-id="faa4b-117">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="faa4b-118">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="faa4b-118">Parent Elements</span></span>  
  
|<span data-ttu-id="faa4b-119">Element</span><span class="sxs-lookup"><span data-stu-id="faa4b-119">Element</span></span>|<span data-ttu-id="faa4b-120">Opis</span><span class="sxs-lookup"><span data-stu-id="faa4b-120">Description</span></span>|  
|-------------|-----------------|  
|[\<issuedTokenParameters>](issuedtokenparameters.md)|<span data-ttu-id="faa4b-121">Określa bieżący token wystawiony.</span><span class="sxs-lookup"><span data-stu-id="faa4b-121">Specifies the current issued token.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="faa4b-122">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="faa4b-122">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.AdditionalRequestParameters%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.AdditionalRequestParameters%2A>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="faa4b-123">Uwierzytelnianie i tożsamość usług</span><span class="sxs-lookup"><span data-stu-id="faa4b-123">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="faa4b-124">Federacja i wystawione tokeny</span><span class="sxs-lookup"><span data-stu-id="faa4b-124">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="faa4b-125">Możliwości zabezpieczeń wiązań niestandardowych</span><span class="sxs-lookup"><span data-stu-id="faa4b-125">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="faa4b-126">Federacja i wystawione tokeny</span><span class="sxs-lookup"><span data-stu-id="faa4b-126">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="faa4b-127">Powiązania</span><span class="sxs-lookup"><span data-stu-id="faa4b-127">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="faa4b-128">Rozszerzanie powiązań</span><span class="sxs-lookup"><span data-stu-id="faa4b-128">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="faa4b-129">Powiązania niestandardowe</span><span class="sxs-lookup"><span data-stu-id="faa4b-129">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [<span data-ttu-id="faa4b-130">Instrukcje: tworzenie niestandardowego wiązania za pomocą elementu SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="faa4b-130">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="faa4b-131">Zabezpieczenia wiązania niestandardowego</span><span class="sxs-lookup"><span data-stu-id="faa4b-131">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
