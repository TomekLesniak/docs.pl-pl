---
title: <issuedTokenParameters>
ms.date: 03/30/2017
ms.assetid: 120b3f37-7331-4816-b712-d6aab39655a4
ms.openlocfilehash: c90024a0629f39d160967ca00434e48f682d8933
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91157320"
---
# \<issuedTokenParameters>

<span data-ttu-id="acd65-101">Określa parametry tokenu zabezpieczającego wydanego w federacyjnym scenariuszu zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="acd65-101">Specifies the parameters for a security token issued in a Federated security scenario.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuedTokenParameters>**  
  
## <a name="syntax"></a><span data-ttu-id="acd65-102">Składnia</span><span class="sxs-lookup"><span data-stu-id="acd65-102">Syntax</span></span>  
  
```xml  
<issuedTokenParameters defaultMessageSecurityVersion="System.ServiceModel.MessageSecurityVersion"
                       inclusionMode="AlwaysToInitiator/AlwaysToRecipient/Never/Once"
                       keySize="Integer"
                       keyType="AsymmetricKey/BearerKey/SymmetricKey"
                       tokenType="String">
  <additionalRequestParameters />
  <claimTypeRequirements>
    <add claimType="URI"
         isOptional="Boolean" />
  </claimTypeRequirements>
  <issuer address="String"
          binding="" />
  <issuerMetadata address="String" />
</issuedTokenParameters>
```  
  
## <a name="type"></a><span data-ttu-id="acd65-103">Typ</span><span class="sxs-lookup"><span data-stu-id="acd65-103">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="acd65-104">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="acd65-104">Attributes and Elements</span></span>  

 <span data-ttu-id="acd65-105">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="acd65-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="acd65-106">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="acd65-106">Attributes</span></span>  
  
|<span data-ttu-id="acd65-107">Atrybut</span><span class="sxs-lookup"><span data-stu-id="acd65-107">Attribute</span></span>|<span data-ttu-id="acd65-108">Opis</span><span class="sxs-lookup"><span data-stu-id="acd65-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="acd65-109">defaultMessageSecurityVersion</span><span class="sxs-lookup"><span data-stu-id="acd65-109">defaultMessageSecurityVersion</span></span>|<span data-ttu-id="acd65-110">Określa wersje specyfikacji zabezpieczeń (WS-Security, WS-Trust, WS-Secure konwersacja i zasady WS-Security), które muszą być obsługiwane przez powiązanie.</span><span class="sxs-lookup"><span data-stu-id="acd65-110">Specifies the versions of the security specifications, (WS-Security, WS-Trust, WS-Secure Conversation and WS-Security Policy) that must be supported by the binding.</span></span> <span data-ttu-id="acd65-111">Ta wartość jest typu <xref:System.ServiceModel.MessageSecurityVersion>.</span><span class="sxs-lookup"><span data-stu-id="acd65-111">This value is of type <xref:System.ServiceModel.MessageSecurityVersion>.</span></span>|  
|<span data-ttu-id="acd65-112">Dołączanie</span><span class="sxs-lookup"><span data-stu-id="acd65-112">inclusionMode</span></span>|<span data-ttu-id="acd65-113">Określa wymagania dotyczące dołączania tokenu.</span><span class="sxs-lookup"><span data-stu-id="acd65-113">Specifies the token inclusion requirements.</span></span> <span data-ttu-id="acd65-114">Ten atrybut jest typu <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode> .</span><span class="sxs-lookup"><span data-stu-id="acd65-114">This attribute is of type <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode>.</span></span>|  
|<span data-ttu-id="acd65-115">keySize</span><span class="sxs-lookup"><span data-stu-id="acd65-115">keySize</span></span>|<span data-ttu-id="acd65-116">Liczba całkowita określająca rozmiar klucza tokenu.</span><span class="sxs-lookup"><span data-stu-id="acd65-116">An integer that specifies the token key size.</span></span> <span data-ttu-id="acd65-117">Wartość domyślna to 256.</span><span class="sxs-lookup"><span data-stu-id="acd65-117">The default value is 256.</span></span>|  
|<span data-ttu-id="acd65-118">keyType</span><span class="sxs-lookup"><span data-stu-id="acd65-118">keyType</span></span>|<span data-ttu-id="acd65-119">Prawidłowa wartość określająca <xref:System.IdentityModel.Tokens.SecurityKeyType> Typ klucza.</span><span class="sxs-lookup"><span data-stu-id="acd65-119">A valid value of <xref:System.IdentityModel.Tokens.SecurityKeyType> that specifies the key type.</span></span> <span data-ttu-id="acd65-120">Wartość domyślna to `SymmetricKey`.</span><span class="sxs-lookup"><span data-stu-id="acd65-120">The default is `SymmetricKey`.</span></span>|  
|<span data-ttu-id="acd65-121">Obiektu TokenType</span><span class="sxs-lookup"><span data-stu-id="acd65-121">tokenType</span></span>|<span data-ttu-id="acd65-122">Ciąg określający typ tokenu.</span><span class="sxs-lookup"><span data-stu-id="acd65-122">A string that specifies the token type.</span></span> <span data-ttu-id="acd65-123">Wartość domyślna to "http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAML".</span><span class="sxs-lookup"><span data-stu-id="acd65-123">The default is "http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAML".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="acd65-124">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="acd65-124">Child Elements</span></span>  
  
|<span data-ttu-id="acd65-125">Element</span><span class="sxs-lookup"><span data-stu-id="acd65-125">Element</span></span>|<span data-ttu-id="acd65-126">Opis</span><span class="sxs-lookup"><span data-stu-id="acd65-126">Description</span></span>|  
|-------------|-----------------|  
|[\<additionalRequestParameters>](additionalrequestparameters-element.md)|<span data-ttu-id="acd65-127">Kolekcja elementów konfiguracji, które określają dodatkowe parametry żądania.</span><span class="sxs-lookup"><span data-stu-id="acd65-127">A collection of configuration elements that specify additional request parameters.</span></span>|  
|[\<claimTypeRequirements>](claimtyperequirements-element.md)|<span data-ttu-id="acd65-128">Określa kolekcję wymaganych typów roszczeń.</span><span class="sxs-lookup"><span data-stu-id="acd65-128">Specifies a collection of required claim types.</span></span><br /><br /> <span data-ttu-id="acd65-129">W scenariuszu federacyjnym usługi określają wymagania dotyczące poświadczeń przychodzących.</span><span class="sxs-lookup"><span data-stu-id="acd65-129">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="acd65-130">Na przykład poświadczenia przychodzące muszą mieć określony zestaw typów roszczeń.</span><span class="sxs-lookup"><span data-stu-id="acd65-130">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="acd65-131">Każdy element w tej kolekcji określa typy wymaganych i opcjonalnych oświadczeń, które powinny być wyświetlane w federacyjnym poświadczeniu.</span><span class="sxs-lookup"><span data-stu-id="acd65-131">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
|[\<issuer>](issuer-of-issuedtokenparameters.md)|<span data-ttu-id="acd65-132">Element konfiguracji, który określa punkt końcowy, który wystawia bieżący token.</span><span class="sxs-lookup"><span data-stu-id="acd65-132">A configuration element that specifies the endpoint that issues the current token.</span></span>|  
|[\<issuerMetadata>](issuermetadata-of-issuedtokenparameters.md)|<span data-ttu-id="acd65-133">Element konfiguracji, który określa adres punktu końcowego metadanych wystawcy tokenu.</span><span class="sxs-lookup"><span data-stu-id="acd65-133">A configuration element that specifies the endpoint address of the token issuer's metadata.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="acd65-134">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="acd65-134">Parent Elements</span></span>  
  
|<span data-ttu-id="acd65-135">Element</span><span class="sxs-lookup"><span data-stu-id="acd65-135">Element</span></span>|<span data-ttu-id="acd65-136">Opis</span><span class="sxs-lookup"><span data-stu-id="acd65-136">Description</span></span>|  
|-------------|-----------------|  
|[\<secureConversationBootstrap>](secureconversationbootstrap.md)|<span data-ttu-id="acd65-137">Określa wartości domyślne używane do inicjowania usługi bezpiecznej konwersacji.</span><span class="sxs-lookup"><span data-stu-id="acd65-137">Specifies the default values used for initiating a secure conversation service.</span></span>|  
|[\<security>](security-of-custombinding.md)|<span data-ttu-id="acd65-138">Określa opcje zabezpieczeń dla niestandardowego powiązania.</span><span class="sxs-lookup"><span data-stu-id="acd65-138">Specifies the security options for a custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="acd65-139">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="acd65-139">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>
- <xref:System.ServiceModel.Configuration.SecurityElementBase.IssuedTokenParameters%2A>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="acd65-140">Powiązania</span><span class="sxs-lookup"><span data-stu-id="acd65-140">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="acd65-141">Rozszerzanie powiązań</span><span class="sxs-lookup"><span data-stu-id="acd65-141">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="acd65-142">Powiązania niestandardowe</span><span class="sxs-lookup"><span data-stu-id="acd65-142">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [<span data-ttu-id="acd65-143">Instrukcje: tworzenie niestandardowego wiązania za pomocą elementu SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="acd65-143">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="acd65-144">Zabezpieczenia wiązania niestandardowego</span><span class="sxs-lookup"><span data-stu-id="acd65-144">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
- [<span data-ttu-id="acd65-145">Uwierzytelnianie i tożsamość usług</span><span class="sxs-lookup"><span data-stu-id="acd65-145">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="acd65-146">Federacja i wystawione tokeny</span><span class="sxs-lookup"><span data-stu-id="acd65-146">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="acd65-147">Możliwości zabezpieczeń wiązań niestandardowych</span><span class="sxs-lookup"><span data-stu-id="acd65-147">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="acd65-148">Federacja i wystawione tokeny</span><span class="sxs-lookup"><span data-stu-id="acd65-148">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
