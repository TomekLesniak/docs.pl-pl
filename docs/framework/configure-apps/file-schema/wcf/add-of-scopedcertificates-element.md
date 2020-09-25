---
title: <add><scopedCertificates>elementu
ms.date: 03/30/2017
ms.assetid: e21c1ef8-d6d6-4bca-ac5a-6fbf4bd77412
ms.openlocfilehash: 28777ecac130295a8ba82a8e4d67cc519d088d8a
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91195145"
---
# <a name="add-of-scopedcertificates-element"></a><span data-ttu-id="3e8ea-102">\<add>\<scopedCertificates>elementu</span><span class="sxs-lookup"><span data-stu-id="3e8ea-102">\<add> of \<scopedCertificates> Element</span></span>

<span data-ttu-id="3e8ea-103">Dodaje certyfikat X. 509 do kolekcji certyfikatów z zakresem.</span><span class="sxs-lookup"><span data-stu-id="3e8ea-103">Adds an X.509 certificate to the collection of scoped certificates.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate-of-clientcredentials-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<scopedCertificates>**](scopedcertificates-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="3e8ea-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="3e8ea-104">Syntax</span></span>  
  
```xml  
<add findValue="String"
     storeLocation="CurrentUser/LocalMachine"
     storeName=" CurrentUser/LocalMachine"
     targetUri="string"
     x509Type="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3e8ea-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="3e8ea-105">Attributes and Elements</span></span>  

 <span data-ttu-id="3e8ea-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="3e8ea-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3e8ea-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="3e8ea-107">Attributes</span></span>  
  
|<span data-ttu-id="3e8ea-108">Atrybut</span><span class="sxs-lookup"><span data-stu-id="3e8ea-108">Attribute</span></span>|<span data-ttu-id="3e8ea-109">Opis</span><span class="sxs-lookup"><span data-stu-id="3e8ea-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3e8ea-110">Parametru TargetUri</span><span class="sxs-lookup"><span data-stu-id="3e8ea-110">targetUri</span></span>|<span data-ttu-id="3e8ea-111">Ciąg.</span><span class="sxs-lookup"><span data-stu-id="3e8ea-111">String.</span></span> <span data-ttu-id="3e8ea-112">Określa identyfikator URI usługi skojarzonej z certyfikatem.</span><span class="sxs-lookup"><span data-stu-id="3e8ea-112">Specifies the URI of the service associated with the certificate.</span></span>|  
|<span data-ttu-id="3e8ea-113">findValue</span><span class="sxs-lookup"><span data-stu-id="3e8ea-113">findValue</span></span>|<span data-ttu-id="3e8ea-114">Ciąg.</span><span class="sxs-lookup"><span data-stu-id="3e8ea-114">String.</span></span> <span data-ttu-id="3e8ea-115">Wartość do wyszukania.</span><span class="sxs-lookup"><span data-stu-id="3e8ea-115">The value to search for.</span></span>|  
|<span data-ttu-id="3e8ea-116">x509FindType</span><span class="sxs-lookup"><span data-stu-id="3e8ea-116">x509FindType</span></span>|<span data-ttu-id="3e8ea-117">Licznik.</span><span class="sxs-lookup"><span data-stu-id="3e8ea-117">Enumeration.</span></span> <span data-ttu-id="3e8ea-118">Jedno z pól certyfikatów do przeszukania.</span><span class="sxs-lookup"><span data-stu-id="3e8ea-118">One of the certificate fields to search.</span></span>|  
|<span data-ttu-id="3e8ea-119">storeLocation</span><span class="sxs-lookup"><span data-stu-id="3e8ea-119">storeLocation</span></span>|<span data-ttu-id="3e8ea-120">Licznik.</span><span class="sxs-lookup"><span data-stu-id="3e8ea-120">Enumeration.</span></span> <span data-ttu-id="3e8ea-121">Jedna z dwóch lokalizacji przechowywania do przeszukania.</span><span class="sxs-lookup"><span data-stu-id="3e8ea-121">One of the two store locations to search.</span></span>|  
|<span data-ttu-id="3e8ea-122">storeName</span><span class="sxs-lookup"><span data-stu-id="3e8ea-122">storeName</span></span>|<span data-ttu-id="3e8ea-123">Licznik.</span><span class="sxs-lookup"><span data-stu-id="3e8ea-123">Enumeration.</span></span> <span data-ttu-id="3e8ea-124">Jeden z magazynów systemu do przeszukania.</span><span class="sxs-lookup"><span data-stu-id="3e8ea-124">One of the system stores to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="3e8ea-125">findValue — atrybut</span><span class="sxs-lookup"><span data-stu-id="3e8ea-125">findValue Attribute</span></span>  
  
|<span data-ttu-id="3e8ea-126">Wartość</span><span class="sxs-lookup"><span data-stu-id="3e8ea-126">Value</span></span>|<span data-ttu-id="3e8ea-127">Opis</span><span class="sxs-lookup"><span data-stu-id="3e8ea-127">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3e8ea-128">String</span><span class="sxs-lookup"><span data-stu-id="3e8ea-128">String</span></span>|<span data-ttu-id="3e8ea-129">Wartość jest zależna od pola (określonego przez atrybut X509FindType), który jest przeszukiwany.</span><span class="sxs-lookup"><span data-stu-id="3e8ea-129">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="3e8ea-130">Na przykład, jeśli szukasz odcisku palca, wartość musi być ciągiem liczb szesnastkowych.</span><span class="sxs-lookup"><span data-stu-id="3e8ea-130">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="3e8ea-131">x509FindType — atrybut</span><span class="sxs-lookup"><span data-stu-id="3e8ea-131">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="3e8ea-132">Wartość</span><span class="sxs-lookup"><span data-stu-id="3e8ea-132">Value</span></span>|<span data-ttu-id="3e8ea-133">Opis</span><span class="sxs-lookup"><span data-stu-id="3e8ea-133">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3e8ea-134">Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="3e8ea-134">Enumeration</span></span>|<span data-ttu-id="3e8ea-135">Dostępne są następujące wartości: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span><span class="sxs-lookup"><span data-stu-id="3e8ea-135">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="3e8ea-136">storeLocation — atrybut</span><span class="sxs-lookup"><span data-stu-id="3e8ea-136">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="3e8ea-137">Wartość</span><span class="sxs-lookup"><span data-stu-id="3e8ea-137">Value</span></span>|<span data-ttu-id="3e8ea-138">Opis</span><span class="sxs-lookup"><span data-stu-id="3e8ea-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3e8ea-139">Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="3e8ea-139">Enumeration</span></span>|<span data-ttu-id="3e8ea-140">CurrentUser lub LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="3e8ea-140">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="3e8ea-141">storeName — atrybut</span><span class="sxs-lookup"><span data-stu-id="3e8ea-141">storeName Attribute</span></span>  
  
|<span data-ttu-id="3e8ea-142">Wartość</span><span class="sxs-lookup"><span data-stu-id="3e8ea-142">Value</span></span>|<span data-ttu-id="3e8ea-143">Opis</span><span class="sxs-lookup"><span data-stu-id="3e8ea-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3e8ea-144">Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="3e8ea-144">Enumeration</span></span>|<span data-ttu-id="3e8ea-145">Dostępne są następujące wartości: AddressBook, AuthRoot, urząd certyfikacji, niedozwolone, my, root, TrustedPeople i TrustedPublisher.</span><span class="sxs-lookup"><span data-stu-id="3e8ea-145">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3e8ea-146">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="3e8ea-146">Child Elements</span></span>  

 <span data-ttu-id="3e8ea-147">Brak.</span><span class="sxs-lookup"><span data-stu-id="3e8ea-147">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3e8ea-148">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="3e8ea-148">Parent Elements</span></span>  
  
|<span data-ttu-id="3e8ea-149">Element</span><span class="sxs-lookup"><span data-stu-id="3e8ea-149">Element</span></span>|<span data-ttu-id="3e8ea-150">Opis</span><span class="sxs-lookup"><span data-stu-id="3e8ea-150">Description</span></span>|  
|-------------|-----------------|  
|[\<scopedCertificates>](scopedcertificates-element.md)|<span data-ttu-id="3e8ea-151">Reprezentuje kolekcję certyfikatów X. 509 dostarczonych przez określone usługi (w zakresie) do uwierzytelniania.</span><span class="sxs-lookup"><span data-stu-id="3e8ea-151">Represents a collection of X.509 certificates provided by specific services (scoped) for authentication.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3e8ea-152">Uwagi</span><span class="sxs-lookup"><span data-stu-id="3e8ea-152">Remarks</span></span>  

 <span data-ttu-id="3e8ea-153">Ten element umożliwia klientowi skonfigurowanie certyfikatu usługi do użycia na podstawie adresu URL usługi, z którą się komunikuje.</span><span class="sxs-lookup"><span data-stu-id="3e8ea-153">This element enables the client to configure a service certificate to use based on the URL of the service it communicates with.</span></span> <span data-ttu-id="3e8ea-154">Jest to szczególnie przydatne w scenariuszach wystawionych tokenów, w których klient może komunikować się z wieloma usługami (usługą końcową oraz usługami tokenów zabezpieczających).</span><span class="sxs-lookup"><span data-stu-id="3e8ea-154">This is especially useful in issued token scenarios where a client can be communicating to multiple services (the end service as well as intermediary security token services).</span></span> <span data-ttu-id="3e8ea-155">W przypadku powiązań korzystających z zabezpieczeń komunikatów opartych na certyfikatach ten certyfikat jest używany do szyfrowania komunikatów do usługi i powinien być używany przez usługę do podpisywania odpowiedzi do klienta.</span><span class="sxs-lookup"><span data-stu-id="3e8ea-155">For bindings that use certificate-based message security, this certificate is used to encrypt messages to the service, and is expected to be used by the service for signing replies to the client.</span></span>  
  
 <span data-ttu-id="3e8ea-156">Jeśli powiązanie wymaga certyfikatu dla usługi i nie zostanie znaleziony konkretny certyfikat dla adresu URL usługi w ScopedCertificates, zostanie użyty certyfikat domyślny.</span><span class="sxs-lookup"><span data-stu-id="3e8ea-156">If a binding requires a certificate for the service and no specific certificate for the service URL is found in the ScopedCertificates, the default certificate is used.</span></span>  
  
 <span data-ttu-id="3e8ea-157">Aby uzyskać więcej informacji, zobacz sekcję "certyfikaty w zakresie" w temacie [How to: Create a Federation Client](../../../wcf/feature-details/how-to-create-a-federated-client.md).</span><span class="sxs-lookup"><span data-stu-id="3e8ea-157">For more information, see the "Scoped Certificates" section of [How to: Create a Federated Client](../../../wcf/feature-details/how-to-create-a-federated-client.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3e8ea-158">Przykład</span><span class="sxs-lookup"><span data-stu-id="3e8ea-158">Example</span></span>  

 <span data-ttu-id="3e8ea-159">Poniższy przykład dodaje do kolekcji certyfikat X. 509.</span><span class="sxs-lookup"><span data-stu-id="3e8ea-159">The following example adds an X.509 certificate the collection.</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="MyEndpointBehavior">
      <clientCredentials>
        <serviceCertificate>
          <scopedCertificates>
            <add targetUri="http://www.contoso.com"
                 findValue="www.Contoso.com"
                 storeLocation="LocalMachine"
                 storeName="Root"
                 x509FindType="FindByIssuerName" />
          </scopedCertificates>
        </serviceCertificate>
      </clientCredentials>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="3e8ea-160">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="3e8ea-160">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement.ScopedCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElementCollection>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.ScopedCertificates%2A>
- [<span data-ttu-id="3e8ea-161">Instrukcje: tworzenie klienta federacyjnego</span><span class="sxs-lookup"><span data-stu-id="3e8ea-161">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="3e8ea-162">Praca z certyfikatami</span><span class="sxs-lookup"><span data-stu-id="3e8ea-162">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- <span data-ttu-id="3e8ea-163">[Zabezpieczanie klientów [WCF]](../../../wcf/securing-clients.md)</span><span class="sxs-lookup"><span data-stu-id="3e8ea-163">[Securing Clients](../../../wcf/securing-clients.md)</span></span>
- [<span data-ttu-id="3e8ea-164">Zabezpieczanie usług i klientów</span><span class="sxs-lookup"><span data-stu-id="3e8ea-164">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
