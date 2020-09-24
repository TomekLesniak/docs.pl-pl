---
title: <certificate><clientCertificate>elementu
ms.date: 03/30/2017
ms.assetid: 00297efb-a7f2-4e03-bc2b-943d545610fc
ms.openlocfilehash: 35ea3814e208921abaf44e6ef431c4e1b44cde60
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91151144"
---
# <a name="certificate-of-clientcertificate-element"></a><span data-ttu-id="6b053-102">\<certificate>\<clientCertificate>elementu</span><span class="sxs-lookup"><span data-stu-id="6b053-102">\<certificate> of \<clientCertificate> Element</span></span>

<span data-ttu-id="6b053-103">Określa certyfikat X. 509 używany do podpisywania i szyfrowania wiadomości.</span><span class="sxs-lookup"><span data-stu-id="6b053-103">Specifies an X.509 certificate used to sign and encrypt messages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCertificate>**](clientcertificate-of-servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificate>**  
  
## <a name="syntax"></a><span data-ttu-id="6b053-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="6b053-104">Syntax</span></span>  
  
```xml  
<certificate findValue="String"
             storeLocation = "CurrentUser/LocalMachine"
             storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
             X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6b053-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="6b053-105">Attributes and Elements</span></span>  

 <span data-ttu-id="6b053-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="6b053-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6b053-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="6b053-107">Attributes</span></span>  
  
|<span data-ttu-id="6b053-108">Atrybut</span><span class="sxs-lookup"><span data-stu-id="6b053-108">Attribute</span></span>|<span data-ttu-id="6b053-109">Opis</span><span class="sxs-lookup"><span data-stu-id="6b053-109">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="6b053-110">Ciąg, który zawiera wartość do wyszukania w magazynie certyfikatów X. 509.</span><span class="sxs-lookup"><span data-stu-id="6b053-110">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="6b053-111">Typ zawarty w atrybucie musi spełniać wymagania określone X509FindType.</span><span class="sxs-lookup"><span data-stu-id="6b053-111">The type contained in the attribute must satisfy the requirements of the specified X509FindType.</span></span> <span data-ttu-id="6b053-112">Wartość domyślna to pusty ciąg.</span><span class="sxs-lookup"><span data-stu-id="6b053-112">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="6b053-113">Określa lokalizację magazynu certyfikatu X. 509, którego klient używa do weryfikacji certyfikatu serwera.</span><span class="sxs-lookup"><span data-stu-id="6b053-113">Specifies the location of the X.509 certificate store that the client uses to validate the server’s certificate against.</span></span> <span data-ttu-id="6b053-114">Prawidłowe wartości to:</span><span class="sxs-lookup"><span data-stu-id="6b053-114">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="6b053-115">-LocalMachine: Magazyn certyfikatów przypisany do komputera lokalnego.</span><span class="sxs-lookup"><span data-stu-id="6b053-115">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="6b053-116">-CurrentUser: Magazyn certyfikatów przypisany do bieżącego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="6b053-116">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="6b053-117">Wartość domyślna to LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="6b053-117">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="6b053-118">Określa nazwę magazynu certyfikatu X. 509 do otwarcia.</span><span class="sxs-lookup"><span data-stu-id="6b053-118">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="6b053-119">Prawidłowe wartości to:</span><span class="sxs-lookup"><span data-stu-id="6b053-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="6b053-120">-AddressBook: Magazyn certyfikatów dla innych użytkowników.</span><span class="sxs-lookup"><span data-stu-id="6b053-120">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="6b053-121">-AuthRoot: Magazyn certyfikatów dla urzędów certyfikacji innych firm.</span><span class="sxs-lookup"><span data-stu-id="6b053-121">-   AuthRoot: Certificate store for third-party certification authorities (CAs).</span></span><br /><span data-ttu-id="6b053-122">-Urząd certyfikacji: Magazyn certyfikatów dla pośrednich urzędów certyfikacji (CA).</span><span class="sxs-lookup"><span data-stu-id="6b053-122">-   CertificationAuthority: Certificate store for intermediate certification authorities (CAs).</span></span><br /><span data-ttu-id="6b053-123">-Niedozwolone: Magazyn certyfikatów dla odwołanych certyfikatów.</span><span class="sxs-lookup"><span data-stu-id="6b053-123">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="6b053-124">-My: Magazyn certyfikatów dla certyfikatów osobistych.</span><span class="sxs-lookup"><span data-stu-id="6b053-124">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="6b053-125">-Root: Magazyn certyfikatów dla zaufanych głównych urzędów certyfikacji (CA).</span><span class="sxs-lookup"><span data-stu-id="6b053-125">-   Root: Certificate store for trusted root certification authorities (CAs).</span></span><br /><span data-ttu-id="6b053-126">-TrustedPeople: Magazyn certyfikatów dla bezpośrednio zaufanych osób i zasobów.</span><span class="sxs-lookup"><span data-stu-id="6b053-126">-   TrustedPeople: Certificate store for directly trusted people and resources.</span></span><br /><span data-ttu-id="6b053-127">-TrustedPublisher: Magazyn certyfikatów dla bezpośrednio zaufanych wydawców.</span><span class="sxs-lookup"><span data-stu-id="6b053-127">-   TrustedPublisher: Certificate store for directly trusted publishers.</span></span><br /><br /> <span data-ttu-id="6b053-128">Wartość domyślna to Moje.</span><span class="sxs-lookup"><span data-stu-id="6b053-128">The default is My.</span></span>|  
|`X509FindType`|<span data-ttu-id="6b053-129">Określa typ wyszukiwania X. 509, który ma zostać wykonany.</span><span class="sxs-lookup"><span data-stu-id="6b053-129">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="6b053-130">Prawidłowe wartości to:</span><span class="sxs-lookup"><span data-stu-id="6b053-130">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="6b053-131">- FindByThumbPrint</span><span class="sxs-lookup"><span data-stu-id="6b053-131">-   FindByThumbPrint</span></span><br /><span data-ttu-id="6b053-132">- FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="6b053-132">-   FindBySubjectName</span></span><br /><span data-ttu-id="6b053-133">- FindBySubjectDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="6b053-133">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="6b053-134">- FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="6b053-134">-   FindByIssuerName</span></span><br /><span data-ttu-id="6b053-135">- FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="6b053-135">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="6b053-136">- FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="6b053-136">-   FindBySerialNumber</span></span><br /><span data-ttu-id="6b053-137">- FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="6b053-137">-   FindByTimeValid</span></span><br /><span data-ttu-id="6b053-138">- FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="6b053-138">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="6b053-139">- FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="6b053-139">-   FindByTemplateName</span></span><br /><span data-ttu-id="6b053-140">- FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="6b053-140">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="6b053-141">- FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="6b053-141">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="6b053-142">- FindByExtension</span><span class="sxs-lookup"><span data-stu-id="6b053-142">-   FindByExtension</span></span><br /><span data-ttu-id="6b053-143">- FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="6b053-143">-   FindByKeyUsage</span></span><br /><span data-ttu-id="6b053-144">- FindBySubjectKeyIdentifier</span><span class="sxs-lookup"><span data-stu-id="6b053-144">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="6b053-145">Typ zawarty w `findValue` atrybucie musi spełniać wymagania określone X509FindType.</span><span class="sxs-lookup"><span data-stu-id="6b053-145">The type contained in the `findValue` attribute must satisfy the requirements of the specified X509FindType.</span></span><br /><br /> <span data-ttu-id="6b053-146">Wartość domyślna to FindBySubjectDistinguishedName.</span><span class="sxs-lookup"><span data-stu-id="6b053-146">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6b053-147">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="6b053-147">Child Elements</span></span>  

 <span data-ttu-id="6b053-148">Brak.</span><span class="sxs-lookup"><span data-stu-id="6b053-148">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6b053-149">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="6b053-149">Parent Elements</span></span>  
  
|<span data-ttu-id="6b053-150">Element</span><span class="sxs-lookup"><span data-stu-id="6b053-150">Element</span></span>|<span data-ttu-id="6b053-151">Opis</span><span class="sxs-lookup"><span data-stu-id="6b053-151">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCertificate>](clientcertificate-of-servicecredentials.md)||  
  
## <a name="remarks"></a><span data-ttu-id="6b053-152">Uwagi</span><span class="sxs-lookup"><span data-stu-id="6b053-152">Remarks</span></span>  

 <span data-ttu-id="6b053-153">Ten `<certificate>` element jest używany, gdy usługa musi mieć certyfikat klienta z wyprzedzeniem do bezpiecznego komunikowania się z klientem.</span><span class="sxs-lookup"><span data-stu-id="6b053-153">The `<certificate>` element is used when the service must have the client's certificate in advance to communicate securely with the client.</span></span> <span data-ttu-id="6b053-154">Dzieje się tak w przypadku używania wzorca komunikacji dupleksowej.</span><span class="sxs-lookup"><span data-stu-id="6b053-154">This occurs when using the duplex communication pattern.</span></span> <span data-ttu-id="6b053-155">W przypadku bardziej typowego wzorca żądania/odpowiedzi klient zawiera swój certyfikat w żądaniu, którego usługa używa do szyfrowania i podpisywania odpowiedzi z powrotem do klienta.</span><span class="sxs-lookup"><span data-stu-id="6b053-155">In the more typical request/response pattern, the client includes its certificate in the request, which the service uses to encrypt and sign its response back to the client.</span></span> <span data-ttu-id="6b053-156">W przypadku wzorca komunikacji dupleksowej usługa nie ma jednak żądania od klienta i w związku z tym potrzebuje certyfikatu klienta z wyprzedzeniem, aby zabezpieczyć komunikat do klienta.</span><span class="sxs-lookup"><span data-stu-id="6b053-156">In the duplex communication pattern, however, the service does not have a request from the client and therefore it needs the client's certificate in advance to secure the message to the client.</span></span> <span data-ttu-id="6b053-157">W związku z tym należy uzyskać certyfikat klienta w negocjacji poza pasmem i określić certyfikat przy użyciu tego elementu.</span><span class="sxs-lookup"><span data-stu-id="6b053-157">Therefore you must obtain the client's certificate in an out-of-band negotiation, and specify the certificate using this element.</span></span> <span data-ttu-id="6b053-158">Aby uzyskać więcej informacji na temat usług dupleksowych, zobacz [How to: Create a Duplex kontraktu](../../../wcf/feature-details/how-to-create-a-duplex-contract.md).</span><span class="sxs-lookup"><span data-stu-id="6b053-158">For more information about duplex services, see [How to: Create a Duplex Contract](../../../wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6b053-159">Przykład</span><span class="sxs-lookup"><span data-stu-id="6b053-159">Example</span></span>  

 <span data-ttu-id="6b053-160">Poniższy kod określa, jak znaleźć odpowiedni certyfikat X. 509 i niestandardowy typ walidacji w `<authentication>` elemencie.</span><span class="sxs-lookup"><span data-stu-id="6b053-160">The following code specifies how to find an appropriate X.509 certificate and a custom validation type in the `<authentication>` element.</span></span>  
  
```xml  
<serviceBehaviors>
  <behavior name="myServiceBehavior">
    <clientCertificate>
      <certificate findValue="www.cohowinery.com"
                   storeLocation="CurrentUser"
                   storeName="TrustedPeople"
                   x509FindType="FindByIssuerName" />
      <authentication customCertificateValidatorType="MyTypes.Coho"
                      certificateValidationMode="Custom"
                      revocationMode="Offline"
                      includeWindowsGroups="false"
                      mapClientCertificateToWindowsAccount="true" />
    </clientCertificate>
  </behavior>
</serviceBehaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="6b053-161">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="6b053-161">See also</span></span>

- <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509ClientCertificateCredentialsElement>
- [<span data-ttu-id="6b053-162">Zachowania zabezpieczeń</span><span class="sxs-lookup"><span data-stu-id="6b053-162">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="6b053-163">Instrukcje: tworzenie usługi korzystającej z niestandardowego modułu weryfikacji certyfikatów</span><span class="sxs-lookup"><span data-stu-id="6b053-163">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)
- [<span data-ttu-id="6b053-164">Praca z certyfikatami</span><span class="sxs-lookup"><span data-stu-id="6b053-164">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
