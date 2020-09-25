---
title: <message> elementu <ws2007FederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 52cd941d-e230-4c82-8b29-333a7d20eca8
ms.openlocfilehash: d71bce5e94568bdad3c52226fa1029a1dd87bfd9
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204921"
---
# <a name="message-element-of-ws2007federationhttpbinding"></a><span data-ttu-id="09736-102">\<message> elementu \<ws2007FederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="09736-102">\<message> element of \<ws2007FederationHttpBinding></span></span>

<span data-ttu-id="09736-103">Definiuje ustawienia zabezpieczeń na poziomie wiadomości dla [\<ws2007FederationHttpBinding>](ws2007federationhttpbinding.md) elementu.</span><span class="sxs-lookup"><span data-stu-id="09736-103">Defines settings for the message-level security for the [\<ws2007FederationHttpBinding>](ws2007federationhttpbinding.md) element.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007FederationHttpBinding>**](ws2007federationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-element-of-ws2007federationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**  
  
## <a name="syntax"></a><span data-ttu-id="09736-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="09736-104">Syntax</span></span>  
  
```xml  
<ws2007FederationBinding>
  <binding>
    <security>
      <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               issuedTokenType="string"
               issuedKeyType="SymmetricKey/PublicKey"
               negotiateServiceCredential="Boolean">
        <claimTypeRequirements>
          <add claimType="URI"
               isOptional="Boolean" />
        </claimTypeRequirements>
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
        <issuerMetadata address="String">
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
                                  X509FindType="System.Security.Cryptography.X509certificates.X509findtype" />
            <dns value="String" />
            <rsa value="String" />
            <servicePrincipalName value="String" />
            <usePrincipalName value="String" />
          </identity>
        </issuerMetadata>
        <tokenRequestParameters>
          <xmlElement>
          </xmlElement>
        </tokenRequestParameters>
      </message>
    </security>
  </binding>
</ws2007FederationBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="09736-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="09736-105">Attributes and Elements</span></span>  

 <span data-ttu-id="09736-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="09736-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="09736-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="09736-107">Attributes</span></span>  
  
|<span data-ttu-id="09736-108">Atrybut</span><span class="sxs-lookup"><span data-stu-id="09736-108">Attribute</span></span>|<span data-ttu-id="09736-109">Opis</span><span class="sxs-lookup"><span data-stu-id="09736-109">Description</span></span>|  
|---------------|-----------------|  
|`algorithmSuite`|<span data-ttu-id="09736-110">Opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="09736-110">Optional.</span></span> <span data-ttu-id="09736-111">Ustawia szyfrowanie wiadomości, sygnaturę i algorytmy zawijania kluczy.</span><span class="sxs-lookup"><span data-stu-id="09736-111">Sets the message encryption, signature, and key-wrap algorithms.</span></span> <span data-ttu-id="09736-112">Algorytmy i rozmiary kluczy są określane przez <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> klasę.</span><span class="sxs-lookup"><span data-stu-id="09736-112">The algorithms and the key sizes are determined by the <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> class.</span></span> <span data-ttu-id="09736-113">Te algorytmy są mapowane na te określone w specyfikacji języka zasad zabezpieczeń (WS-SecurityPolicy).</span><span class="sxs-lookup"><span data-stu-id="09736-113">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span><br /><br /> <span data-ttu-id="09736-114">Zapoznaj się z poniższą tabelą, aby poznać możliwe wartości.</span><span class="sxs-lookup"><span data-stu-id="09736-114">See the following table for possible values.</span></span> <span data-ttu-id="09736-115">Wartość domyślna to Basic256.</span><span class="sxs-lookup"><span data-stu-id="09736-115">The default value is Basic256.</span></span>|  
|`issuedKeyType`|<span data-ttu-id="09736-116">Określa typ klucza do wystawienia.</span><span class="sxs-lookup"><span data-stu-id="09736-116">Specifies the type of key to be issued.</span></span> <span data-ttu-id="09736-117">Prawidłowe wartości to:</span><span class="sxs-lookup"><span data-stu-id="09736-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="09736-118">- SymmetricKey</span><span class="sxs-lookup"><span data-stu-id="09736-118">-   SymmetricKey</span></span><br /><span data-ttu-id="09736-119">-PublicKey</span><span class="sxs-lookup"><span data-stu-id="09736-119">-   PublicKey</span></span><br /><span data-ttu-id="09736-120">- BearerKey</span><span class="sxs-lookup"><span data-stu-id="09736-120">-   BearerKey</span></span><br /><br /> <span data-ttu-id="09736-121">Wartość domyślna to SymmetricKey.</span><span class="sxs-lookup"><span data-stu-id="09736-121">The default is SymmetricKey.</span></span> <span data-ttu-id="09736-122">Ten atrybut jest typu <xref:System.IdentityModel.Tokens.SecurityKeyType> .</span><span class="sxs-lookup"><span data-stu-id="09736-122">This attribute is of type <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span></span>|  
|`issuedTokenType`|<span data-ttu-id="09736-123">Identyfikator URI, który określa typ tokenu do wystawienia.</span><span class="sxs-lookup"><span data-stu-id="09736-123">A URI that specifies the type of token to be issued.</span></span> <span data-ttu-id="09736-124">Wartość domyślna to `null`.</span><span class="sxs-lookup"><span data-stu-id="09736-124">The default is `null`.</span></span>|  
|`negotiateServiceCredential`|<span data-ttu-id="09736-125">Wartość określająca, czy poświadczenie usługi powinno być wymieniane jako część negocjacji, czy też jest dostępne poza pasmem.</span><span class="sxs-lookup"><span data-stu-id="09736-125">A value that specifies whether the service credential should be exchanged as part of negotiation or is available out of band.</span></span> <span data-ttu-id="09736-126">Wartość domyślna to `true` , co oznacza, że poświadczenie usługi jest negocjowane.</span><span class="sxs-lookup"><span data-stu-id="09736-126">The default is `true`, which means that the service credential is negotiated.</span></span>|  
  
## <a name="algorithmsuite-attribute"></a><span data-ttu-id="09736-127">algorithmSuite — atrybut</span><span class="sxs-lookup"><span data-stu-id="09736-127">algorithmSuite Attribute</span></span>  
  
|<span data-ttu-id="09736-128">Wartość</span><span class="sxs-lookup"><span data-stu-id="09736-128">Value</span></span>|<span data-ttu-id="09736-129">Opis</span><span class="sxs-lookup"><span data-stu-id="09736-129">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="09736-130">Basic128</span><span class="sxs-lookup"><span data-stu-id="09736-130">Basic128</span></span>|<span data-ttu-id="09736-131">Użyj szyfrowania Aes128, SHA1 dla skrótu wiadomości i RSA-OAEP-mgf1p do zawijania kluczy.</span><span class="sxs-lookup"><span data-stu-id="09736-131">Use Aes128 encryption, Sha1 for message digest, and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="09736-132">Basic192</span><span class="sxs-lookup"><span data-stu-id="09736-132">Basic192</span></span>|<span data-ttu-id="09736-133">Użyj szyfrowania Aes192, SHA1 dla skrótu wiadomości, RSA-OAEP-mgf1p do zawijania kluczy.</span><span class="sxs-lookup"><span data-stu-id="09736-133">Use Aes192 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="09736-134">Basic256</span><span class="sxs-lookup"><span data-stu-id="09736-134">Basic256</span></span>|<span data-ttu-id="09736-135">Użyj szyfrowania AES256, SHA1 dla skrótu wiadomości, RSA-OAEP-mgf1p do zawijania kluczy.</span><span class="sxs-lookup"><span data-stu-id="09736-135">Use Aes256 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="09736-136">Basic256Rsa15</span><span class="sxs-lookup"><span data-stu-id="09736-136">Basic256Rsa15</span></span>|<span data-ttu-id="09736-137">Użyj AES256 na potrzeby szyfrowania wiadomości, SHA1 dla skrótu wiadomości i Rsa15 do zawijania kluczy.</span><span class="sxs-lookup"><span data-stu-id="09736-137">Use Aes256 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="09736-138">Basic192Rsa15</span><span class="sxs-lookup"><span data-stu-id="09736-138">Basic192Rsa15</span></span>|<span data-ttu-id="09736-139">Użyj Aes192 na potrzeby szyfrowania wiadomości, SHA1 dla skrótu wiadomości i Rsa15 do zawijania kluczy.</span><span class="sxs-lookup"><span data-stu-id="09736-139">Use Aes192 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="09736-140">TripleDes</span><span class="sxs-lookup"><span data-stu-id="09736-140">TripleDes</span></span>|<span data-ttu-id="09736-141">Użyj szyfrowania TripleDes, SHA1 dla skrótu wiadomości, RSA-OAEP-mgf1p do zawijania kluczy.</span><span class="sxs-lookup"><span data-stu-id="09736-141">Use TripleDes encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="09736-142">Basic128Rsa15</span><span class="sxs-lookup"><span data-stu-id="09736-142">Basic128Rsa15</span></span>|<span data-ttu-id="09736-143">Użyj Aes128 na potrzeby szyfrowania wiadomości, SHA1 dla skrótu wiadomości i Rsa15 do zawijania kluczy.</span><span class="sxs-lookup"><span data-stu-id="09736-143">Use Aes128 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="09736-144">TripleDesRsa15</span><span class="sxs-lookup"><span data-stu-id="09736-144">TripleDesRsa15</span></span>|<span data-ttu-id="09736-145">Użyj szyfrowania TripleDes, SHA1 dla skrótu wiadomości i Rsa15 do zawijania kluczy.</span><span class="sxs-lookup"><span data-stu-id="09736-145">Use TripleDes encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="09736-146">Basic128Sha256</span><span class="sxs-lookup"><span data-stu-id="09736-146">Basic128Sha256</span></span>|<span data-ttu-id="09736-147">Użyj AES256 na potrzeby szyfrowania wiadomości, SHA256 dla skrótu wiadomości i RSA-OAEP-mgf1p do zawijania kluczy.</span><span class="sxs-lookup"><span data-stu-id="09736-147">Use Aes256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="09736-148">Basic192Sha256</span><span class="sxs-lookup"><span data-stu-id="09736-148">Basic192Sha256</span></span>|<span data-ttu-id="09736-149">Użyj Aes192 na potrzeby szyfrowania wiadomości, SHA256 dla skrótu wiadomości i RSA-OAEP-mgf1p do zawijania kluczy.</span><span class="sxs-lookup"><span data-stu-id="09736-149">Use Aes192 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="09736-150">Basic256Sha256</span><span class="sxs-lookup"><span data-stu-id="09736-150">Basic256Sha256</span></span>|<span data-ttu-id="09736-151">Użyj AES256 na potrzeby szyfrowania wiadomości, SHA256 dla skrótu wiadomości i RSA-OAEP-mgf1p do zawijania kluczy.</span><span class="sxs-lookup"><span data-stu-id="09736-151">Use Aes256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="09736-152">TripleDesSha256</span><span class="sxs-lookup"><span data-stu-id="09736-152">TripleDesSha256</span></span>|<span data-ttu-id="09736-153">Użyj TripleDes na potrzeby szyfrowania wiadomości, SHA256 dla skrótu wiadomości i RSA-OAEP-mgf1p do zawijania kluczy.</span><span class="sxs-lookup"><span data-stu-id="09736-153">Use TripleDes for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="09736-154">Basic128Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="09736-154">Basic128Sha256Rsa15</span></span>|<span data-ttu-id="09736-155">Użyj Aes128 na potrzeby szyfrowania wiadomości, SHA256 dla skrótu wiadomości i Rsa15 dla zawijania kluczy.</span><span class="sxs-lookup"><span data-stu-id="09736-155">Use Aes128 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="09736-156">Basic192Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="09736-156">Basic192Sha256Rsa15</span></span>|<span data-ttu-id="09736-157">Użyj Aes192 na potrzeby szyfrowania wiadomości, SHA256 dla skrótu wiadomości i Rsa15 dla zawijania kluczy.</span><span class="sxs-lookup"><span data-stu-id="09736-157">Use Aes192 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="09736-158">Basic256Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="09736-158">Basic256Sha256Rsa15</span></span>|<span data-ttu-id="09736-159">Użyj AES256 na potrzeby szyfrowania wiadomości, SHA256 dla skrótu wiadomości i Rsa15 dla zawijania kluczy.</span><span class="sxs-lookup"><span data-stu-id="09736-159">Use Aes256 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="09736-160">TripleDesSha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="09736-160">TripleDesSha256Rsa15</span></span>|<span data-ttu-id="09736-161">Użyj TripleDes na potrzeby szyfrowania wiadomości, SHA256 dla skrótu wiadomości i Rsa15 dla zawijania kluczy.</span><span class="sxs-lookup"><span data-stu-id="09736-161">Use TripleDes for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="09736-162">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="09736-162">Child Elements</span></span>  
  
|<span data-ttu-id="09736-163">Element</span><span class="sxs-lookup"><span data-stu-id="09736-163">Element</span></span>|<span data-ttu-id="09736-164">Opis</span><span class="sxs-lookup"><span data-stu-id="09736-164">Description</span></span>|  
|-------------|-----------------|  
|[\<claimTypeRequirements>](claimtyperequirements-element.md)|<span data-ttu-id="09736-165">Określa kolekcję typów roszczeń dla tego powiązania.</span><span class="sxs-lookup"><span data-stu-id="09736-165">Specifies a collection of claim types for this binding.</span></span> <span data-ttu-id="09736-166">Każdy element jest typu <xref:System.ServiceModel.Configuration.ClaimTypeElement> .</span><span class="sxs-lookup"><span data-stu-id="09736-166">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span>|  
|[\<issuer>](issuer.md)|<span data-ttu-id="09736-167">Określa punkt końcowy, który wystawia token zabezpieczający.</span><span class="sxs-lookup"><span data-stu-id="09736-167">Specifies an endpoint that issues a security token.</span></span> <span data-ttu-id="09736-168">Ten element jest typu <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement> .</span><span class="sxs-lookup"><span data-stu-id="09736-168">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span></span>|  
|[\<issuerMetadata>](issuermetadata.md)|<span data-ttu-id="09736-169">Określa adres punktu końcowego wystawcy.</span><span class="sxs-lookup"><span data-stu-id="09736-169">Specifies the endpoint address of the issuer.</span></span>|  
|[\<tokenRequestParameters>](tokenrequestparameters.md)|<span data-ttu-id="09736-170">Kolekcja parametrów żądania tokenu.</span><span class="sxs-lookup"><span data-stu-id="09736-170">A collection of token request parameters.</span></span> <span data-ttu-id="09736-171">Każdy parametr jest elementem XML.</span><span class="sxs-lookup"><span data-stu-id="09736-171">Each parameter is an XML element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="09736-172">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="09736-172">Parent Elements</span></span>  
  
|<span data-ttu-id="09736-173">Element</span><span class="sxs-lookup"><span data-stu-id="09736-173">Element</span></span>|<span data-ttu-id="09736-174">Opis</span><span class="sxs-lookup"><span data-stu-id="09736-174">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-element-of-ws2007federationhttpbinding.md)|<span data-ttu-id="09736-175">Definiuje ustawienia zabezpieczeń dla powiązania.</span><span class="sxs-lookup"><span data-stu-id="09736-175">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="09736-176">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="09736-176">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement.Message%2A>
- <xref:System.ServiceModel.WSFederationHttpSecurity.Message%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>
- [<span data-ttu-id="09736-177">Zabezpieczanie usług i klientów</span><span class="sxs-lookup"><span data-stu-id="09736-177">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="09736-178">Powiązania</span><span class="sxs-lookup"><span data-stu-id="09736-178">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="09736-179">Konfigurowanie powiązań dostarczanych przez system</span><span class="sxs-lookup"><span data-stu-id="09736-179">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="09736-180">Konfigurowanie usług i klientów za pomocą wiązań</span><span class="sxs-lookup"><span data-stu-id="09736-180">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
