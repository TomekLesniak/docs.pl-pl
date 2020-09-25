---
title: <message> elementu <wsFederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 9d710389-d9d8-4454-9bf2-da4ccda31cec
ms.openlocfilehash: ea320b1d97e742d4f90ec55502f3bd429803283d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204895"
---
# <a name="message-element-of-wsfederationhttpbinding"></a><span data-ttu-id="2e0f3-102">\<message> elementu \<wsFederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="2e0f3-102">\<message> element of \<wsFederationHttpBinding></span></span>

<span data-ttu-id="2e0f3-103">Definiuje ustawienia zabezpieczeń na poziomie wiadomości dla [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="2e0f3-103">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**  
  
## <a name="syntax"></a><span data-ttu-id="2e0f3-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="2e0f3-104">Syntax</span></span>  
  
```xml  
<wsFederationBinding>
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
</wsFederationBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2e0f3-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="2e0f3-105">Attributes and Elements</span></span>  

 <span data-ttu-id="2e0f3-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="2e0f3-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2e0f3-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="2e0f3-107">Attributes</span></span>  
  
|<span data-ttu-id="2e0f3-108">Atrybut</span><span class="sxs-lookup"><span data-stu-id="2e0f3-108">Attribute</span></span>|<span data-ttu-id="2e0f3-109">Opis</span><span class="sxs-lookup"><span data-stu-id="2e0f3-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2e0f3-110">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="2e0f3-110">algorithmSuite</span></span>|<span data-ttu-id="2e0f3-111">Ustawia szyfrowanie komunikatów i algorytmy zawijania kluczy.</span><span class="sxs-lookup"><span data-stu-id="2e0f3-111">Sets the message encryption and key-wrap algorithms.</span></span> <span data-ttu-id="2e0f3-112">Zobacz tabelę "atrybut algorithmSuite", aby uzyskać prawidłowe wartości tego atrybutu.</span><span class="sxs-lookup"><span data-stu-id="2e0f3-112">See the "algorithmSuite attribute" table for valid values of this attribute.</span></span> <span data-ttu-id="2e0f3-113">Wartość domyślna to `Basic256`.</span><span class="sxs-lookup"><span data-stu-id="2e0f3-113">The default value is `Basic256`.</span></span><br /><br /> <span data-ttu-id="2e0f3-114">Ten atrybut jest typu <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> .</span><span class="sxs-lookup"><span data-stu-id="2e0f3-114">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span></span> <span data-ttu-id="2e0f3-115">Te algorytmy są mapowane na te określone w specyfikacji języka zasad zabezpieczeń (WS-SecurityPolicy).</span><span class="sxs-lookup"><span data-stu-id="2e0f3-115">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span>|  
|<span data-ttu-id="2e0f3-116">issuedKeyType</span><span class="sxs-lookup"><span data-stu-id="2e0f3-116">issuedKeyType</span></span>|<span data-ttu-id="2e0f3-117">Określa typ klucza do wystawienia.</span><span class="sxs-lookup"><span data-stu-id="2e0f3-117">Specifies the type of key to be issued.</span></span> <span data-ttu-id="2e0f3-118">Prawidłowe wartości to:</span><span class="sxs-lookup"><span data-stu-id="2e0f3-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="2e0f3-119">- SymmetricKey</span><span class="sxs-lookup"><span data-stu-id="2e0f3-119">-   SymmetricKey</span></span><br /><span data-ttu-id="2e0f3-120">-PublicKey</span><span class="sxs-lookup"><span data-stu-id="2e0f3-120">-   PublicKey</span></span><br /><br /> <span data-ttu-id="2e0f3-121">Wartość domyślna to `SymmetricKey`.</span><span class="sxs-lookup"><span data-stu-id="2e0f3-121">The default is `SymmetricKey`.</span></span> <span data-ttu-id="2e0f3-122">Ten atrybut jest typu <xref:System.IdentityModel.Tokens.SecurityKeyType> .</span><span class="sxs-lookup"><span data-stu-id="2e0f3-122">This attribute is of type <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span></span>|  
|<span data-ttu-id="2e0f3-123">issuedTokenType</span><span class="sxs-lookup"><span data-stu-id="2e0f3-123">issuedTokenType</span></span>|<span data-ttu-id="2e0f3-124">Ciąg zawierający identyfikator URI, który określa typ tokenu do wystawienia.</span><span class="sxs-lookup"><span data-stu-id="2e0f3-124">A string that contains a URI that specifies the type of token to be issued.</span></span> <span data-ttu-id="2e0f3-125">Wartość domyślna to `null`.</span><span class="sxs-lookup"><span data-stu-id="2e0f3-125">The default is `null`.</span></span>|  
|<span data-ttu-id="2e0f3-126">negotiateServiceCredential</span><span class="sxs-lookup"><span data-stu-id="2e0f3-126">negotiateServiceCredential</span></span>|<span data-ttu-id="2e0f3-127">Wartość logiczna określająca, czy poświadczenie usługi powinno być wymieniane jako część negocjacji lub jest dostępne poza pasmem.</span><span class="sxs-lookup"><span data-stu-id="2e0f3-127">A Boolean value that specifies whether the service credential should be exchanged as part of negotiation or is available out of band.</span></span> <span data-ttu-id="2e0f3-128">Wartość domyślna to `true` , co oznacza, że poświadczenie usługi jest negocjowane.</span><span class="sxs-lookup"><span data-stu-id="2e0f3-128">The default is `true`, which means that the service credential is negotiated.</span></span>|  
  
## <a name="algorithmsuite-attribute"></a><span data-ttu-id="2e0f3-129">algorithmSuite — atrybut</span><span class="sxs-lookup"><span data-stu-id="2e0f3-129">algorithmSuite Attribute</span></span>  
  
|<span data-ttu-id="2e0f3-130">Wartość</span><span class="sxs-lookup"><span data-stu-id="2e0f3-130">Value</span></span>|<span data-ttu-id="2e0f3-131">Opis</span><span class="sxs-lookup"><span data-stu-id="2e0f3-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2e0f3-132">Basic128</span><span class="sxs-lookup"><span data-stu-id="2e0f3-132">Basic128</span></span>|<span data-ttu-id="2e0f3-133">Użyj szyfrowania Basic128, SHA1 dla skrótu wiadomości i RSA-OAEP-mgf1p do zawijania kluczy.</span><span class="sxs-lookup"><span data-stu-id="2e0f3-133">Use Basic128 encryption, Sha1 for message digest, and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="2e0f3-134">Basic192</span><span class="sxs-lookup"><span data-stu-id="2e0f3-134">Basic192</span></span>|<span data-ttu-id="2e0f3-135">Użyj szyfrowania Basic192, SHA1 dla skrótu wiadomości, RSA-OAEP-mgf1p do zawijania kluczy.</span><span class="sxs-lookup"><span data-stu-id="2e0f3-135">Use Basic192 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="2e0f3-136">Basic256</span><span class="sxs-lookup"><span data-stu-id="2e0f3-136">Basic256</span></span>|<span data-ttu-id="2e0f3-137">Użyj szyfrowania Basic256, SHA1 dla skrótu wiadomości, RSA-OAEP-mgf1p do zawijania kluczy.</span><span class="sxs-lookup"><span data-stu-id="2e0f3-137">Use Basic256 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="2e0f3-138">Basic256Rsa15</span><span class="sxs-lookup"><span data-stu-id="2e0f3-138">Basic256Rsa15</span></span>|<span data-ttu-id="2e0f3-139">Użyj Basic256 na potrzeby szyfrowania wiadomości, SHA1 dla skrótu wiadomości i Rsa15 do zawijania kluczy.</span><span class="sxs-lookup"><span data-stu-id="2e0f3-139">Use Basic256 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="2e0f3-140">Basic192Rsa15</span><span class="sxs-lookup"><span data-stu-id="2e0f3-140">Basic192Rsa15</span></span>|<span data-ttu-id="2e0f3-141">Użyj Basic192 na potrzeby szyfrowania wiadomości, SHA1 dla skrótu wiadomości i Rsa15 do zawijania kluczy.</span><span class="sxs-lookup"><span data-stu-id="2e0f3-141">Use Basic192 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="2e0f3-142">TripleDes</span><span class="sxs-lookup"><span data-stu-id="2e0f3-142">TripleDes</span></span>|<span data-ttu-id="2e0f3-143">Użyj szyfrowania TripleDes, SHA1 dla skrótu wiadomości, RSA-OAEP-mgf1p do zawijania kluczy.</span><span class="sxs-lookup"><span data-stu-id="2e0f3-143">Use TripleDes encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="2e0f3-144">Basic128Rsa15</span><span class="sxs-lookup"><span data-stu-id="2e0f3-144">Basic128Rsa15</span></span>|<span data-ttu-id="2e0f3-145">Użyj Basic128 na potrzeby szyfrowania wiadomości, SHA1 dla skrótu wiadomości i Rsa15 do zawijania kluczy.</span><span class="sxs-lookup"><span data-stu-id="2e0f3-145">Use Basic128 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="2e0f3-146">TripleDesRsa15</span><span class="sxs-lookup"><span data-stu-id="2e0f3-146">TripleDesRsa15</span></span>|<span data-ttu-id="2e0f3-147">Użyj szyfrowania TripleDes, SHA1 dla skrótu wiadomości i Rsa15 do zawijania kluczy.</span><span class="sxs-lookup"><span data-stu-id="2e0f3-147">Use TripleDes encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="2e0f3-148">Basic128Sha256</span><span class="sxs-lookup"><span data-stu-id="2e0f3-148">Basic128Sha256</span></span>|<span data-ttu-id="2e0f3-149">Użyj Basic128 na potrzeby szyfrowania wiadomości, SHA256 dla skrótu wiadomości i RSA-OAEP-mgf1p do zawijania kluczy.</span><span class="sxs-lookup"><span data-stu-id="2e0f3-149">Use Basic128 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="2e0f3-150">Basic192Sha256</span><span class="sxs-lookup"><span data-stu-id="2e0f3-150">Basic192Sha256</span></span>|<span data-ttu-id="2e0f3-151">Użyj Basic192 na potrzeby szyfrowania wiadomości, SHA256 dla skrótu wiadomości i RSA-OAEP-mgf1p do zawijania kluczy.</span><span class="sxs-lookup"><span data-stu-id="2e0f3-151">Use Basic192 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="2e0f3-152">Basic256Sha256</span><span class="sxs-lookup"><span data-stu-id="2e0f3-152">Basic256Sha256</span></span>|<span data-ttu-id="2e0f3-153">Użyj Basic256 na potrzeby szyfrowania wiadomości, SHA256 dla skrótu wiadomości i RSA-OAEP-mgf1p do zawijania kluczy.</span><span class="sxs-lookup"><span data-stu-id="2e0f3-153">Use Basic256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="2e0f3-154">TripleDesSha256</span><span class="sxs-lookup"><span data-stu-id="2e0f3-154">TripleDesSha256</span></span>|<span data-ttu-id="2e0f3-155">Użyj TripleDes na potrzeby szyfrowania wiadomości, SHA256 dla skrótu wiadomości i RSA-OAEP-mgf1p do zawijania kluczy.</span><span class="sxs-lookup"><span data-stu-id="2e0f3-155">Use TripleDes for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="2e0f3-156">Basic128Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="2e0f3-156">Basic128Sha256Rsa15</span></span>|<span data-ttu-id="2e0f3-157">Użyj Basic128 na potrzeby szyfrowania wiadomości, SHA256 dla skrótu wiadomości i Rsa15 dla zawijania kluczy.</span><span class="sxs-lookup"><span data-stu-id="2e0f3-157">Use Basic128 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="2e0f3-158">Basic192Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="2e0f3-158">Basic192Sha256Rsa15</span></span>|<span data-ttu-id="2e0f3-159">Użyj Aes192 na potrzeby szyfrowania wiadomości, SHA256 dla skrótu wiadomości i Rsa15 dla zawijania kluczy.</span><span class="sxs-lookup"><span data-stu-id="2e0f3-159">Use Aes192 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="2e0f3-160">Basic256Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="2e0f3-160">Basic256Sha256Rsa15</span></span>|<span data-ttu-id="2e0f3-161">Użyj Basic256 na potrzeby szyfrowania wiadomości, SHA256 dla skrótu wiadomości i Rsa15 dla zawijania kluczy.</span><span class="sxs-lookup"><span data-stu-id="2e0f3-161">Use Basic256 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="2e0f3-162">TripleDesSha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="2e0f3-162">TripleDesSha256Rsa15</span></span>|<span data-ttu-id="2e0f3-163">Użyj TripleDes na potrzeby szyfrowania wiadomości, SHA256 dla skrótu wiadomości i Rsa15 dla zawijania kluczy.</span><span class="sxs-lookup"><span data-stu-id="2e0f3-163">Use TripleDes for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2e0f3-164">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="2e0f3-164">Child Elements</span></span>  
  
|<span data-ttu-id="2e0f3-165">Element</span><span class="sxs-lookup"><span data-stu-id="2e0f3-165">Element</span></span>|<span data-ttu-id="2e0f3-166">Opis</span><span class="sxs-lookup"><span data-stu-id="2e0f3-166">Description</span></span>|  
|-------------|-----------------|  
|[\<claimTypeRequirements>](claimtyperequirements-element.md)|<span data-ttu-id="2e0f3-167">Określa kolekcję typów roszczeń dla tego powiązania.</span><span class="sxs-lookup"><span data-stu-id="2e0f3-167">Specifies a collection of claim types for this binding.</span></span> <span data-ttu-id="2e0f3-168">Każdy element jest typu <xref:System.ServiceModel.Configuration.ClaimTypeElement> .</span><span class="sxs-lookup"><span data-stu-id="2e0f3-168">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span>|  
|<span data-ttu-id="2e0f3-169">issuer</span><span class="sxs-lookup"><span data-stu-id="2e0f3-169">issuer</span></span>|<span data-ttu-id="2e0f3-170">Określa punkt końcowy, który wystawia token zabezpieczający.</span><span class="sxs-lookup"><span data-stu-id="2e0f3-170">Specifies an endpoint that issues a security token.</span></span> <span data-ttu-id="2e0f3-171">Ten element jest typu <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement> .</span><span class="sxs-lookup"><span data-stu-id="2e0f3-171">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span></span>|  
|<span data-ttu-id="2e0f3-172">issuerMetadata</span><span class="sxs-lookup"><span data-stu-id="2e0f3-172">issuerMetadata</span></span>|<span data-ttu-id="2e0f3-173">Określa adres punktu końcowego wystawcy.</span><span class="sxs-lookup"><span data-stu-id="2e0f3-173">Specifies the endpoint address of the issuer.</span></span>|  
|[\<tokenRequestParameters>](tokenrequestparameters.md)|<span data-ttu-id="2e0f3-174">Kolekcja parametrów żądania tokenu.</span><span class="sxs-lookup"><span data-stu-id="2e0f3-174">A collection of token request parameters.</span></span> <span data-ttu-id="2e0f3-175">Każdy parametr jest elementem XML.</span><span class="sxs-lookup"><span data-stu-id="2e0f3-175">Each parameter is an XML element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2e0f3-176">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="2e0f3-176">Parent Elements</span></span>  
  
|<span data-ttu-id="2e0f3-177">Element</span><span class="sxs-lookup"><span data-stu-id="2e0f3-177">Element</span></span>|<span data-ttu-id="2e0f3-178">Opis</span><span class="sxs-lookup"><span data-stu-id="2e0f3-178">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-wsfederationhttpbinding.md)|<span data-ttu-id="2e0f3-179">Definiuje ustawienia zabezpieczeń dla powiązania.</span><span class="sxs-lookup"><span data-stu-id="2e0f3-179">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2e0f3-180">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="2e0f3-180">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement.Message%2A>
- <xref:System.ServiceModel.WSFederationHttpSecurity.Message%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>
- [<span data-ttu-id="2e0f3-181">Zabezpieczanie usług i klientów</span><span class="sxs-lookup"><span data-stu-id="2e0f3-181">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="2e0f3-182">Powiązania</span><span class="sxs-lookup"><span data-stu-id="2e0f3-182">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="2e0f3-183">Konfigurowanie powiązań dostarczanych przez system</span><span class="sxs-lookup"><span data-stu-id="2e0f3-183">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="2e0f3-184">Konfigurowanie usług i klientów za pomocą wiązań</span><span class="sxs-lookup"><span data-stu-id="2e0f3-184">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
