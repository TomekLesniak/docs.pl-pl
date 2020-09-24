---
title: <knownCertificates>
ms.date: 03/30/2017
ms.assetid: 678e21b4-6493-47c3-8359-fcf0d37e2138
ms.openlocfilehash: 7ddb292b8f0ffe38133c7f142be751a87d2be11c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91150911"
---
# \<knownCertificates>

<span data-ttu-id="e5a9b-101">Reprezentuje kolekcję certyfikatów X. 509, które są dostarczane w celu uwierzytelnienia poświadczeń zabezpieczeń wydanych z usługi tokenu zabezpieczającego (STS).</span><span class="sxs-lookup"><span data-stu-id="e5a9b-101">Represents a collection of X.509 certificates that are provided to authenticate security credentials issued from a Security Token Service (STS).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenAuthentication>**](issuedtokenauthentication-of-servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<knownCertificates>**  
  
## <a name="syntax"></a><span data-ttu-id="e5a9b-102">Składnia</span><span class="sxs-lookup"><span data-stu-id="e5a9b-102">Syntax</span></span>  
  
```xml  
<knownCertificates>
  <add findValue="String"
       storeLocation="CurrentUser/LocalMachine"
       storeName=" CurrentUser/LocalMachine"
       x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
</knownCertificates>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e5a9b-103">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="e5a9b-103">Attributes and Elements</span></span>  

 <span data-ttu-id="e5a9b-104">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="e5a9b-104">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e5a9b-105">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="e5a9b-105">Attributes</span></span>  

 <span data-ttu-id="e5a9b-106">Brak.</span><span class="sxs-lookup"><span data-stu-id="e5a9b-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e5a9b-107">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="e5a9b-107">Child Elements</span></span>  
  
|<span data-ttu-id="e5a9b-108">Element</span><span class="sxs-lookup"><span data-stu-id="e5a9b-108">Element</span></span>|<span data-ttu-id="e5a9b-109">Opis</span><span class="sxs-lookup"><span data-stu-id="e5a9b-109">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-of-knowncertificates.md)|<span data-ttu-id="e5a9b-110">Dodaje certyfikat X. 509 do kolekcji.</span><span class="sxs-lookup"><span data-stu-id="e5a9b-110">Adds an X.509 certificate to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e5a9b-111">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="e5a9b-111">Parent Elements</span></span>  
  
|<span data-ttu-id="e5a9b-112">Element</span><span class="sxs-lookup"><span data-stu-id="e5a9b-112">Element</span></span>|<span data-ttu-id="e5a9b-113">Opis</span><span class="sxs-lookup"><span data-stu-id="e5a9b-113">Description</span></span>|  
|-------------|-----------------|  
|[\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="e5a9b-114">Określa token wystawiony jako poświadczenie usługi.</span><span class="sxs-lookup"><span data-stu-id="e5a9b-114">Specifies a token issued as a service credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e5a9b-115">Uwagi</span><span class="sxs-lookup"><span data-stu-id="e5a9b-115">Remarks</span></span>  

 <span data-ttu-id="e5a9b-116">Scenariusz wystawionego tokenu ma trzy etapy.</span><span class="sxs-lookup"><span data-stu-id="e5a9b-116">The issued token scenario has three stages.</span></span> <span data-ttu-id="e5a9b-117">Na pierwszym etapie klient próbujący uzyskać dostęp do usługi jest nazywany *usługą bezpiecznego tokenu*.</span><span class="sxs-lookup"><span data-stu-id="e5a9b-117">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="e5a9b-118">Usługa Secure Tokens następnie uwierzytelnia klienta, a następnie wystawia klientowi token, zwykle tokena "Security Assertions Markup Language" (SAML).</span><span class="sxs-lookup"><span data-stu-id="e5a9b-118">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="e5a9b-119">Klient następnie wraca do usługi przy użyciu tokenu.</span><span class="sxs-lookup"><span data-stu-id="e5a9b-119">The client then returns to the service with the token.</span></span> <span data-ttu-id="e5a9b-120">Usługa bada token dla danych, które umożliwiają usłudze uwierzytelnianie tokenu i w związku z tym klienta.</span><span class="sxs-lookup"><span data-stu-id="e5a9b-120">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="e5a9b-121">Aby uwierzytelnić token, certyfikat, którego używa usługa bezpiecznego tokenu, musi być znany usłudze.</span><span class="sxs-lookup"><span data-stu-id="e5a9b-121">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="e5a9b-122">[\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md)Element jest repozytorium dla wszystkich takich certyfikatów usługi Secure Token Service.</span><span class="sxs-lookup"><span data-stu-id="e5a9b-122">The [\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md) element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="e5a9b-123">Aby dodać certyfikaty, użyj [ \<knownCertificates> elementu](knowncertificates.md).</span><span class="sxs-lookup"><span data-stu-id="e5a9b-123">To add certificates, use the [\<knownCertificates> element](knowncertificates.md).</span></span> <span data-ttu-id="e5a9b-124">Wstaw [\<add>](add-of-knowncertificates.md) dla każdego certyfikatu, jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="e5a9b-124">Insert an [\<add>](add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
```xml  
<issuedTokenAuthentication>
  <knownCertificates>
    <add findValue="www.contoso.com"
         storeLocation="LocalMachine"
         storeName="My"
         X509FindType="FindBySubjectName" />
  </knownCertificates>
</issuedTokenAuthentication>
```  
  
 <span data-ttu-id="e5a9b-125">Domyślnie certyfikaty muszą być uzyskiwane z usługi bezpiecznego tokenu.</span><span class="sxs-lookup"><span data-stu-id="e5a9b-125">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="e5a9b-126">Te "znane" certyfikaty zapewniają dostęp do usługi tylko uprawnionym klientom.</span><span class="sxs-lookup"><span data-stu-id="e5a9b-126">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="e5a9b-127">Aby sprawdzić warunki wymagane przez klienta do uwierzytelniania za pomocą usługi federacyjnej, a także więcej informacji na temat korzystania z tego elementu konfiguracji, zobacz [How to: Configure Credentials in a usługa federacyjna](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span><span class="sxs-lookup"><span data-stu-id="e5a9b-127">To review conditions required for a client to be authenticated by a federated service, as well as more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span> <span data-ttu-id="e5a9b-128">Aby uzyskać więcej informacji na temat scenariuszy federacyjnych, zobacz [federacyjnego i wystawione tokeny](../../../wcf/feature-details/federation-and-issued-tokens.md).</span><span class="sxs-lookup"><span data-stu-id="e5a9b-128">For more information about federated scenarios, see [Federation and Issued Tokens](../../../wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
 <span data-ttu-id="e5a9b-129">Aby zapoznać się z przykładem, który pokazuje, jak wypełnić kolekcję w konfiguracji, zobacz [\<add>](add-of-knowncertificates.md) .</span><span class="sxs-lookup"><span data-stu-id="e5a9b-129">For an example that shows how to populate the collection in configuration, see [\<add>](add-of-knowncertificates.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5a9b-130">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="e5a9b-130">See also</span></span>

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>
- [\<add>](add-of-knowncertificates.md)
- [\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md)
- [<span data-ttu-id="e5a9b-131">Zachowania zabezpieczeń</span><span class="sxs-lookup"><span data-stu-id="e5a9b-131">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="e5a9b-132">Instrukcje: konfigurowanie poświadczeń usługi federacyjnej</span><span class="sxs-lookup"><span data-stu-id="e5a9b-132">How to: Configure Credentials on a Federation Service</span></span>](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [<span data-ttu-id="e5a9b-133">Praca z certyfikatami</span><span class="sxs-lookup"><span data-stu-id="e5a9b-133">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="e5a9b-134">Federacja i wystawione tokeny</span><span class="sxs-lookup"><span data-stu-id="e5a9b-134">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [\<add>](add-of-knowncertificates.md)
- [<span data-ttu-id="e5a9b-135">Zabezpieczanie usług i klientów</span><span class="sxs-lookup"><span data-stu-id="e5a9b-135">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
