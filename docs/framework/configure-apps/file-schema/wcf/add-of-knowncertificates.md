---
title: <add> dla <knownCertificates>
ms.date: 03/30/2017
ms.assetid: 128aaabe-3f1a-4c3b-b59f-898d0f02910f
ms.openlocfilehash: 453593918de15613edb801cca8a16c9dbf71aa90
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176087"
---
# <a name="add-of-knowncertificates"></a><span data-ttu-id="786e1-102">\<add> dla \<knownCertificates></span><span class="sxs-lookup"><span data-stu-id="786e1-102">\<add> of \<knownCertificates></span></span>

<span data-ttu-id="786e1-103">Dodaje certyfikat X. 509 do kolekcji znanych certyfikatów.</span><span class="sxs-lookup"><span data-stu-id="786e1-103">Adds an X.509 certificate to the collection of known certificates.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenAuthentication>**](issuedtokenauthentication-of-servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<knownCertificates>**](knowncertificates.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="786e1-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="786e1-104">Syntax</span></span>  
  
```xml  
<knownCertificates>
   <add findValue="String"
      storeLocation="CurrentUser/LocalMachine"
      storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
      x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"/>
</knownCertificates>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="786e1-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="786e1-105">Attributes and Elements</span></span>  

 <span data-ttu-id="786e1-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="786e1-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="786e1-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="786e1-107">Attributes</span></span>  
  
|<span data-ttu-id="786e1-108">Atrybut</span><span class="sxs-lookup"><span data-stu-id="786e1-108">Attribute</span></span>|<span data-ttu-id="786e1-109">Opis</span><span class="sxs-lookup"><span data-stu-id="786e1-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="786e1-110">findValue</span><span class="sxs-lookup"><span data-stu-id="786e1-110">findValue</span></span>|<span data-ttu-id="786e1-111">Ciąg.</span><span class="sxs-lookup"><span data-stu-id="786e1-111">String.</span></span> <span data-ttu-id="786e1-112">Wartość do wyszukania.</span><span class="sxs-lookup"><span data-stu-id="786e1-112">The value to search for.</span></span>|  
|<span data-ttu-id="786e1-113">storeLocation</span><span class="sxs-lookup"><span data-stu-id="786e1-113">storeLocation</span></span>|<span data-ttu-id="786e1-114">Licznik.</span><span class="sxs-lookup"><span data-stu-id="786e1-114">Enumeration.</span></span> <span data-ttu-id="786e1-115">Jedna z dwóch lokalizacji przechowywania do przeszukania.</span><span class="sxs-lookup"><span data-stu-id="786e1-115">One of the two store locations to search.</span></span>|  
|<span data-ttu-id="786e1-116">storeName</span><span class="sxs-lookup"><span data-stu-id="786e1-116">storeName</span></span>|<span data-ttu-id="786e1-117">Licznik.</span><span class="sxs-lookup"><span data-stu-id="786e1-117">Enumeration.</span></span> <span data-ttu-id="786e1-118">Jeden z magazynów systemu do przeszukania.</span><span class="sxs-lookup"><span data-stu-id="786e1-118">One of the system stores to search.</span></span>|  
|<span data-ttu-id="786e1-119">x509FindType</span><span class="sxs-lookup"><span data-stu-id="786e1-119">x509FindType</span></span>|<span data-ttu-id="786e1-120">Licznik.</span><span class="sxs-lookup"><span data-stu-id="786e1-120">Enumeration.</span></span> <span data-ttu-id="786e1-121">Jedno z pól certyfikatów do przeszukania.</span><span class="sxs-lookup"><span data-stu-id="786e1-121">One of the certificate fields to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="786e1-122">findValue — atrybut</span><span class="sxs-lookup"><span data-stu-id="786e1-122">findValue Attribute</span></span>  
  
|<span data-ttu-id="786e1-123">Wartość</span><span class="sxs-lookup"><span data-stu-id="786e1-123">Value</span></span>|<span data-ttu-id="786e1-124">Opis</span><span class="sxs-lookup"><span data-stu-id="786e1-124">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="786e1-125">String</span><span class="sxs-lookup"><span data-stu-id="786e1-125">String</span></span>|<span data-ttu-id="786e1-126">Wartość jest zależna od pola (określonego przez atrybut X509FindType), który jest przeszukiwany.</span><span class="sxs-lookup"><span data-stu-id="786e1-126">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="786e1-127">Na przykład, jeśli szukasz odcisku palca, wartość musi być ciągiem liczb szesnastkowych.</span><span class="sxs-lookup"><span data-stu-id="786e1-127">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="786e1-128">x509FindType — atrybut</span><span class="sxs-lookup"><span data-stu-id="786e1-128">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="786e1-129">Wartość</span><span class="sxs-lookup"><span data-stu-id="786e1-129">Value</span></span>|<span data-ttu-id="786e1-130">Opis</span><span class="sxs-lookup"><span data-stu-id="786e1-130">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="786e1-131">Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="786e1-131">Enumeration</span></span>|<span data-ttu-id="786e1-132">Dostępne są następujące wartości: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span><span class="sxs-lookup"><span data-stu-id="786e1-132">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="786e1-133">storeLocation — atrybut</span><span class="sxs-lookup"><span data-stu-id="786e1-133">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="786e1-134">Wartość</span><span class="sxs-lookup"><span data-stu-id="786e1-134">Value</span></span>|<span data-ttu-id="786e1-135">Opis</span><span class="sxs-lookup"><span data-stu-id="786e1-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="786e1-136">Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="786e1-136">Enumeration</span></span>|<span data-ttu-id="786e1-137">CurrentUser lub LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="786e1-137">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="786e1-138">storeName — atrybut</span><span class="sxs-lookup"><span data-stu-id="786e1-138">storeName Attribute</span></span>  
  
|<span data-ttu-id="786e1-139">Wartość</span><span class="sxs-lookup"><span data-stu-id="786e1-139">Value</span></span>|<span data-ttu-id="786e1-140">Opis</span><span class="sxs-lookup"><span data-stu-id="786e1-140">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="786e1-141">Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="786e1-141">Enumeration</span></span>|<span data-ttu-id="786e1-142">Dostępne są następujące wartości: AddressBook, AuthRoot, urząd certyfikacji, niedozwolone, my, root, TrustedPeople i TrustedPublisher.</span><span class="sxs-lookup"><span data-stu-id="786e1-142">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="786e1-143">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="786e1-143">Child Elements</span></span>  

 <span data-ttu-id="786e1-144">Brak.</span><span class="sxs-lookup"><span data-stu-id="786e1-144">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="786e1-145">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="786e1-145">Parent Elements</span></span>  
  
|<span data-ttu-id="786e1-146">Element</span><span class="sxs-lookup"><span data-stu-id="786e1-146">Element</span></span>|<span data-ttu-id="786e1-147">Opis</span><span class="sxs-lookup"><span data-stu-id="786e1-147">Description</span></span>|  
|-------------|-----------------|  
|[\<knownCertificates>](knowncertificates.md)|<span data-ttu-id="786e1-148">Reprezentuje kolekcję certyfikatów X. 509, które są dostarczane przez usługę tokenu zabezpieczającego (STS) do sprawdzania poprawności tokenów zabezpieczających.</span><span class="sxs-lookup"><span data-stu-id="786e1-148">Represents a collection of X.509 certificates that are provided by a Security Token Service (STS) for validation of security tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="786e1-149">Uwagi</span><span class="sxs-lookup"><span data-stu-id="786e1-149">Remarks</span></span>  

 <span data-ttu-id="786e1-150">Scenariusz wystawionego tokenu ma trzy etapy.</span><span class="sxs-lookup"><span data-stu-id="786e1-150">The issued token scenario has three stages.</span></span> <span data-ttu-id="786e1-151">Na pierwszym etapie klient próbujący uzyskać dostęp do usługi jest nazywany *usługą bezpiecznego tokenu*.</span><span class="sxs-lookup"><span data-stu-id="786e1-151">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="786e1-152">Usługa Secure Tokens następnie uwierzytelnia klienta, a następnie wystawia klientowi token, zwykle tokena "Security Assertions Markup Language" (SAML).</span><span class="sxs-lookup"><span data-stu-id="786e1-152">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="786e1-153">Klient następnie wraca do usługi przy użyciu tokenu.</span><span class="sxs-lookup"><span data-stu-id="786e1-153">The client then returns to the service with the token.</span></span> <span data-ttu-id="786e1-154">Usługa bada token dla danych, które umożliwiają usłudze uwierzytelnianie tokenu i w związku z tym klienta.</span><span class="sxs-lookup"><span data-stu-id="786e1-154">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="786e1-155">Aby uwierzytelnić token, certyfikat, którego używa usługa bezpiecznego tokenu, musi być znany usłudze.</span><span class="sxs-lookup"><span data-stu-id="786e1-155">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="786e1-156">[\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md)Element jest repozytorium dla wszystkich takich certyfikatów usługi Secure Token Service.</span><span class="sxs-lookup"><span data-stu-id="786e1-156">The [\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md) element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="786e1-157">Aby dodać certyfikaty, użyj [\<knownCertificates>](knowncertificates.md) .</span><span class="sxs-lookup"><span data-stu-id="786e1-157">To add certificates, use the [\<knownCertificates>](knowncertificates.md).</span></span> <span data-ttu-id="786e1-158">Wstaw [ \<add> \<knownCertificates> element](add-of-knowncertificates.md) elementu dla każdego certyfikatu, jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="786e1-158">Insert an [\<add> element \<knownCertificates> Element](add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="786e1-159">Domyślnie certyfikaty muszą być uzyskiwane z usługi bezpiecznego tokenu.</span><span class="sxs-lookup"><span data-stu-id="786e1-159">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="786e1-160">Te "znane" certyfikaty zapewniają dostęp do usługi tylko uprawnionym klientom.</span><span class="sxs-lookup"><span data-stu-id="786e1-160">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="786e1-161">Aby sprawdzić warunki wymagane przez klienta do uwierzytelniania za pomocą usługi federacyjnej, a także więcej informacji na temat korzystania z tego elementu konfiguracji, zobacz [How to: Configure Credentials in a usługa federacyjna](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span><span class="sxs-lookup"><span data-stu-id="786e1-161">To review conditions required for a client to be authenticated by a federated service, as well as more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span> <span data-ttu-id="786e1-162">Aby uzyskać więcej informacji na temat scenariuszy federacyjnych, zobacz [federacyjnego i wystawione tokeny](../../../wcf/feature-details/federation-and-issued-tokens.md).</span><span class="sxs-lookup"><span data-stu-id="786e1-162">For more information about federated scenarios, see [Federation and Issued Tokens](../../../wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="786e1-163">Przykład</span><span class="sxs-lookup"><span data-stu-id="786e1-163">Example</span></span>  

 <span data-ttu-id="786e1-164">Poniższy przykład dodaje certyfikat do repozytorium dla wszystkich certyfikatów usługi STS.</span><span class="sxs-lookup"><span data-stu-id="786e1-164">The following example adds certificate to the repository for any STS certificates.</span></span>  
  
```xml  
<serviceBehaviors>
  <behavior name="myServiceBehavior">
    <serviceCredentials>
      <issuedTokenAuthentication>
        <knownCertificates>
          <add findValue="www.contoso.com"
               storeLocation="LocalMachine"
               storeName="CertificateAuthority"
               x509FindType="FindByIssuerName" />
        </knownCertificates>
      </issuedTokenAuthentication>
    </serviceCredentials>
  </behavior>
</serviceBehaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="786e1-165">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="786e1-165">See also</span></span>

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>
- [\<knownCertificates>](knowncertificates.md)
- [<span data-ttu-id="786e1-166">Praca z certyfikatami</span><span class="sxs-lookup"><span data-stu-id="786e1-166">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="786e1-167">Federacja i wystawione tokeny</span><span class="sxs-lookup"><span data-stu-id="786e1-167">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="786e1-168">Instrukcje: konfigurowanie poświadczeń usługi federacyjnej</span><span class="sxs-lookup"><span data-stu-id="786e1-168">How to: Configure Credentials on a Federation Service</span></span>](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [<span data-ttu-id="786e1-169">Zabezpieczanie usług i klientów</span><span class="sxs-lookup"><span data-stu-id="786e1-169">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
