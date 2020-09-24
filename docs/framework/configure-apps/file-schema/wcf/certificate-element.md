---
title: <certificate> Element
ms.date: 03/30/2017
ms.assetid: 9b3d9233-ef35-477a-bf5d-efd1e80a52f4
ms.openlocfilehash: 8cc0404a5896dd23cffce6f1f77b91a2f01f23d2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91151093"
---
# <a name="certificate-element"></a><span data-ttu-id="f54e7-102">\<certificate> Element</span><span class="sxs-lookup"><span data-stu-id="f54e7-102">\<certificate> Element</span></span>

<span data-ttu-id="f54e7-103">Określa certyfikat X. 509 używany do podpisywania i szyfrowania komunikatów dla klientów równorzędnych.</span><span class="sxs-lookup"><span data-stu-id="f54e7-103">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-clientcredentials-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificate>**  
  
## <a name="syntax"></a><span data-ttu-id="f54e7-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="f54e7-104">Syntax</span></span>  
  
```xml  
<certificate findValue="String"
             storeLocation="LocalMachine/CurrentUser"
             storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
             X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f54e7-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="f54e7-105">Attributes and Elements</span></span>  

 <span data-ttu-id="f54e7-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="f54e7-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f54e7-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="f54e7-107">Attributes</span></span>  
  
|<span data-ttu-id="f54e7-108">Atrybut</span><span class="sxs-lookup"><span data-stu-id="f54e7-108">Attribute</span></span>|<span data-ttu-id="f54e7-109">Opis</span><span class="sxs-lookup"><span data-stu-id="f54e7-109">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="f54e7-110">Ciąg, który zawiera wartość do wyszukania w magazynie certyfikatów X. 509.</span><span class="sxs-lookup"><span data-stu-id="f54e7-110">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="f54e7-111">Typ zawarty w atrybucie musi spełniać wymagania określone `x509FindType` .</span><span class="sxs-lookup"><span data-stu-id="f54e7-111">The type contained in the attribute must satisfy the requirements of the specified `x509FindType`.</span></span> <span data-ttu-id="f54e7-112">Wartość domyślna to pusty ciąg.</span><span class="sxs-lookup"><span data-stu-id="f54e7-112">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="f54e7-113">Określa lokalizację magazynu certyfikatów X. 509, którego klient używa do weryfikacji certyfikatu elementu równorzędnego.</span><span class="sxs-lookup"><span data-stu-id="f54e7-113">Specifies the location of the X.509 certificate store that the client uses to validate the peer's certificate against.</span></span> <span data-ttu-id="f54e7-114">Prawidłowe wartości to:</span><span class="sxs-lookup"><span data-stu-id="f54e7-114">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="f54e7-115">-LocalMachine: Magazyn certyfikatów przypisany do komputera lokalnego.</span><span class="sxs-lookup"><span data-stu-id="f54e7-115">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="f54e7-116">-CurrentUser: Magazyn certyfikatów przypisany do bieżącego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="f54e7-116">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="f54e7-117">Wartość domyślna to LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="f54e7-117">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="f54e7-118">Określa nazwę magazynu certyfikatu X. 509 do otwarcia.</span><span class="sxs-lookup"><span data-stu-id="f54e7-118">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="f54e7-119">Prawidłowe wartości to:</span><span class="sxs-lookup"><span data-stu-id="f54e7-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="f54e7-120">-AddressBook: Magazyn certyfikatów dla innych użytkowników.</span><span class="sxs-lookup"><span data-stu-id="f54e7-120">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="f54e7-121">-AuthRoot: Magazyn certyfikatów dla urzędów certyfikacji innych firm.</span><span class="sxs-lookup"><span data-stu-id="f54e7-121">-   AuthRoot: Certificate store for third-party certification authorities (CAs).</span></span><br /><span data-ttu-id="f54e7-122">-Urząd certyfikacji: Magazyn certyfikatów dla pośrednich urzędów certyfikacji (CA).</span><span class="sxs-lookup"><span data-stu-id="f54e7-122">-   CertificateAuthority: Certificate store for intermediate certification authorities (CAs).</span></span><br /><span data-ttu-id="f54e7-123">-Niedozwolone: Magazyn certyfikatów dla odwołanych certyfikatów.</span><span class="sxs-lookup"><span data-stu-id="f54e7-123">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="f54e7-124">-My: Magazyn certyfikatów dla certyfikatów osobistych.</span><span class="sxs-lookup"><span data-stu-id="f54e7-124">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="f54e7-125">-Root: Magazyn certyfikatów dla zaufanych głównych urzędów certyfikacji (CA).</span><span class="sxs-lookup"><span data-stu-id="f54e7-125">-   Root: Certificate store for trusted root certification authorities (CAs).</span></span><br /><span data-ttu-id="f54e7-126">-TrustedPeople: Magazyn certyfikatów dla bezpośrednio zaufanych osób i zasobów.</span><span class="sxs-lookup"><span data-stu-id="f54e7-126">-   TrustedPeople: Certificate store for directly-trusted people and resources.</span></span><br /><span data-ttu-id="f54e7-127">-TrustedPublisher: Magazyn certyfikatów dla bezpośrednio zaufanych wydawców.</span><span class="sxs-lookup"><span data-stu-id="f54e7-127">-   TrustedPublisher: Certificate store for directly-trusted publishers.</span></span><br /><br /> <span data-ttu-id="f54e7-128">Wartość domyślna to Moje.</span><span class="sxs-lookup"><span data-stu-id="f54e7-128">The default is My.</span></span>|  
|`X509FindType`|<span data-ttu-id="f54e7-129">Określa typ wyszukiwania X. 509, który ma zostać wykonany.</span><span class="sxs-lookup"><span data-stu-id="f54e7-129">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="f54e7-130">Prawidłowe wartości to:</span><span class="sxs-lookup"><span data-stu-id="f54e7-130">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="f54e7-131">- FindByThumbPrint</span><span class="sxs-lookup"><span data-stu-id="f54e7-131">-   FindByThumbPrint</span></span><br /><span data-ttu-id="f54e7-132">- FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="f54e7-132">-   FindBySubjectName</span></span><br /><span data-ttu-id="f54e7-133">- FindBySubjectDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="f54e7-133">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="f54e7-134">- FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="f54e7-134">-   FindByIssuerName</span></span><br /><span data-ttu-id="f54e7-135">- FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="f54e7-135">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="f54e7-136">- FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="f54e7-136">-   FindBySerialNumber</span></span><br /><span data-ttu-id="f54e7-137">- FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="f54e7-137">-   FindByTimeValid</span></span><br /><span data-ttu-id="f54e7-138">- FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="f54e7-138">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="f54e7-139">- FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="f54e7-139">-   FindByTemplateName</span></span><br /><span data-ttu-id="f54e7-140">- FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="f54e7-140">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="f54e7-141">- FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="f54e7-141">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="f54e7-142">- FindByExtension</span><span class="sxs-lookup"><span data-stu-id="f54e7-142">-   FindByExtension</span></span><br /><span data-ttu-id="f54e7-143">- FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="f54e7-143">-   FindByKeyUsage</span></span><br /><span data-ttu-id="f54e7-144">- FindBySubjectKeyIdentifier</span><span class="sxs-lookup"><span data-stu-id="f54e7-144">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="f54e7-145">Typ zawarty w `findValue` atrybucie musi spełniać wymagania określone `X509FindType` .</span><span class="sxs-lookup"><span data-stu-id="f54e7-145">The type contained in the `findValue` attribute must satisfy the requirements of the specified `X509FindType`.</span></span><br /><br /> <span data-ttu-id="f54e7-146">Wartość domyślna to FindBySubjectDistinguishedName.</span><span class="sxs-lookup"><span data-stu-id="f54e7-146">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f54e7-147">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="f54e7-147">Child Elements</span></span>  

 <span data-ttu-id="f54e7-148">Brak.</span><span class="sxs-lookup"><span data-stu-id="f54e7-148">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f54e7-149">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="f54e7-149">Parent Elements</span></span>  
  
|<span data-ttu-id="f54e7-150">Element</span><span class="sxs-lookup"><span data-stu-id="f54e7-150">Element</span></span>|<span data-ttu-id="f54e7-151">Opis</span><span class="sxs-lookup"><span data-stu-id="f54e7-151">Description</span></span>|  
|-------------|-----------------|  
|[\<peer>](peer-of-clientcredentials-element.md)|<span data-ttu-id="f54e7-152">Określa poświadczenia używane podczas uwierzytelniania klientów równorzędnych.</span><span class="sxs-lookup"><span data-stu-id="f54e7-152">Specifies credentials used when authenticating peer-to-peer clients.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f54e7-153">Uwagi</span><span class="sxs-lookup"><span data-stu-id="f54e7-153">Remarks</span></span>  

 <span data-ttu-id="f54e7-154">Ten element konfiguracji zawiera wystąpienie X509Certificate2 używane podczas uwierzytelniania sąsiadów w sieci równorzędnej.</span><span class="sxs-lookup"><span data-stu-id="f54e7-154">This configuration element contains a X509Certificate2 instance used when authenticating neighbors in the peer mesh.</span></span>  
  
 <span data-ttu-id="f54e7-155">Aby uzyskać więcej informacji na temat programowania peer-to-peer, zobacz [sieci peer-to-](../../../wcf/feature-details/peer-to-peer-networking.md)peer.</span><span class="sxs-lookup"><span data-stu-id="f54e7-155">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f54e7-156">Przykład</span><span class="sxs-lookup"><span data-stu-id="f54e7-156">Example</span></span>  

 <span data-ttu-id="f54e7-157">Poniższy kod określa, jak znaleźć certyfikat używany w scenariuszu równorzędnym.</span><span class="sxs-lookup"><span data-stu-id="f54e7-157">The following code specifies how to find the certificate used in a peer-to-peer scenario.</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="MyEndpointBehavior">
      <clientCredentials>
        <peer>
          <certificate findValue="www.contoso.com"
                       storeLocation="LocalMachine"
                       x509FindType="FindByIssuerName" />
        </peer>
      </clientCredentials>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="f54e7-158">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="f54e7-158">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateElement>
- <xref:System.ServiceModel.Security.PeerCredential.Certificate%2A>
- [<span data-ttu-id="f54e7-159">Praca z certyfikatami</span><span class="sxs-lookup"><span data-stu-id="f54e7-159">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="f54e7-160">Sieci równorzędne</span><span class="sxs-lookup"><span data-stu-id="f54e7-160">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="f54e7-161">[Uwierzytelnianie komunikatów kanału równorzędnego](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="f54e7-161">[Peer Channel Message Authentication](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="f54e7-162">[Uwierzytelnianie niestandardowe kanału równorzędnego](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="f54e7-162">[Peer Channel Custom Authentication](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="f54e7-163">Zabezpieczanie aplikacji kanałów równorzędnych</span><span class="sxs-lookup"><span data-stu-id="f54e7-163">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
