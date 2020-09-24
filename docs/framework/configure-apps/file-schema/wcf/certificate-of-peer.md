---
title: <certificate> dla <peer>
ms.date: 03/30/2017
ms.assetid: 48b69142-c957-4305-a042-c9d0c9a55c0e
ms.openlocfilehash: 8ec839df02af4a01d31192eebc96e4c5e58313e9
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91151119"
---
# <a name="certificate-of-peer"></a><span data-ttu-id="12047-102">\<certificate> dla \<peer></span><span class="sxs-lookup"><span data-stu-id="12047-102">\<certificate> of \<peer></span></span>

<span data-ttu-id="12047-103">Określa certyfikat używany przez element równorzędny.</span><span class="sxs-lookup"><span data-stu-id="12047-103">Specifies a certificate used by a peer.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificate>**  
  
## <a name="syntax"></a><span data-ttu-id="12047-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="12047-104">Syntax</span></span>  
  
```xml  
<certificate findValue = "String"
             storeLocation = "CurrentUser/LocalMachine"
             storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
             X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="12047-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="12047-105">Attributes and Elements</span></span>  

 <span data-ttu-id="12047-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="12047-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="12047-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="12047-107">Attributes</span></span>  
  
|<span data-ttu-id="12047-108">Atrybut</span><span class="sxs-lookup"><span data-stu-id="12047-108">Attribute</span></span>|<span data-ttu-id="12047-109">Opis</span><span class="sxs-lookup"><span data-stu-id="12047-109">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="12047-110">Ciąg, który zawiera wartość do wyszukania w magazynie certyfikatów X. 509.</span><span class="sxs-lookup"><span data-stu-id="12047-110">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="12047-111">Typ zawarty w atrybucie musi spełniać wymagania określone `x509FindType` .</span><span class="sxs-lookup"><span data-stu-id="12047-111">The type contained in the attribute must satisfy the requirements of the specified `x509FindType`.</span></span> <span data-ttu-id="12047-112">Wartość domyślna to pusty ciąg.</span><span class="sxs-lookup"><span data-stu-id="12047-112">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="12047-113">Określa lokalizację magazynu certyfikatów X. 509, którego klient używa do weryfikacji certyfikatu elementu równorzędnego.</span><span class="sxs-lookup"><span data-stu-id="12047-113">Specifies the location of the X.509 certificate store that the client uses to validate the peer's certificate against.</span></span> <span data-ttu-id="12047-114">Prawidłowe wartości to:</span><span class="sxs-lookup"><span data-stu-id="12047-114">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="12047-115">-LocalMachine: Magazyn certyfikatów przypisany do komputera lokalnego.</span><span class="sxs-lookup"><span data-stu-id="12047-115">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="12047-116">-CurrentUser: Magazyn certyfikatów przypisany do bieżącego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="12047-116">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="12047-117">Wartość domyślna to LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="12047-117">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="12047-118">Określa nazwę magazynu certyfikatu X. 509 do otwarcia.</span><span class="sxs-lookup"><span data-stu-id="12047-118">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="12047-119">Prawidłowe wartości to:</span><span class="sxs-lookup"><span data-stu-id="12047-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="12047-120">-AddressBook: Magazyn certyfikatów dla innych użytkowników.</span><span class="sxs-lookup"><span data-stu-id="12047-120">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="12047-121">-AuthRoot: Magazyn certyfikatów dla urzędów certyfikacji innych firm.</span><span class="sxs-lookup"><span data-stu-id="12047-121">-   AuthRoot: Certificate store for third-party certificate authorities (CAs).</span></span><br /><span data-ttu-id="12047-122">-Urząd certyfikacji: Magazyn certyfikatów dla pośrednich urzędów certyfikacji (CA).</span><span class="sxs-lookup"><span data-stu-id="12047-122">-   CertificateAuthority: Certificate store for intermediate certificate authorities (CAs).</span></span><br /><span data-ttu-id="12047-123">-Niedozwolone: Magazyn certyfikatów dla odwołanych certyfikatów.</span><span class="sxs-lookup"><span data-stu-id="12047-123">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="12047-124">-My: Magazyn certyfikatów dla certyfikatów osobistych.</span><span class="sxs-lookup"><span data-stu-id="12047-124">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="12047-125">-Root: Magazyn certyfikatów dla zaufanych głównych urzędów certyfikacji (CA).</span><span class="sxs-lookup"><span data-stu-id="12047-125">-   Root: Certificate store for trusted root certificate authorities (CAs).</span></span><br /><span data-ttu-id="12047-126">-TrustedPeople: Magazyn certyfikatów dla bezpośrednio zaufanych osób i zasobów.</span><span class="sxs-lookup"><span data-stu-id="12047-126">-   TrustedPeople: Certificate store for directly-trusted people and resources.</span></span><br /><span data-ttu-id="12047-127">-TrustedPublisher: Magazyn certyfikatów dla bezpośrednio zaufanych wydawców.</span><span class="sxs-lookup"><span data-stu-id="12047-127">-   TrustedPublisher: Certificate store for directly-trusted publishers.</span></span><br /><br /> <span data-ttu-id="12047-128">Wartość domyślna to Moje.</span><span class="sxs-lookup"><span data-stu-id="12047-128">The default is My.</span></span>|  
|`X509FindType`|<span data-ttu-id="12047-129">Określa typ wyszukiwania X. 509, który ma zostać wykonany.</span><span class="sxs-lookup"><span data-stu-id="12047-129">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="12047-130">Prawidłowe wartości to:</span><span class="sxs-lookup"><span data-stu-id="12047-130">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="12047-131">- FindByThumbPrint</span><span class="sxs-lookup"><span data-stu-id="12047-131">-   FindByThumbPrint</span></span><br /><span data-ttu-id="12047-132">- FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="12047-132">-   FindBySubjectName</span></span><br /><span data-ttu-id="12047-133">- FindBySubjectDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="12047-133">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="12047-134">- FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="12047-134">-   FindByIssuerName</span></span><br /><span data-ttu-id="12047-135">- FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="12047-135">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="12047-136">- FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="12047-136">-   FindBySerialNumber</span></span><br /><span data-ttu-id="12047-137">- FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="12047-137">-   FindByTimeValid</span></span><br /><span data-ttu-id="12047-138">- FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="12047-138">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="12047-139">- FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="12047-139">-   FindByTemplateName</span></span><br /><span data-ttu-id="12047-140">- FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="12047-140">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="12047-141">- FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="12047-141">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="12047-142">- FindByExtension</span><span class="sxs-lookup"><span data-stu-id="12047-142">-   FindByExtension</span></span><br /><span data-ttu-id="12047-143">- FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="12047-143">-   FindByKeyUsage</span></span><br /><span data-ttu-id="12047-144">- FindBySubjectKeyIdentifier</span><span class="sxs-lookup"><span data-stu-id="12047-144">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="12047-145">Typ zawarty w `findValue` atrybucie musi spełniać wymagania określone `X509FindType` .</span><span class="sxs-lookup"><span data-stu-id="12047-145">The type contained in the `findValue` attribute must satisfy the requirements of the specified `X509FindType`.</span></span><br /><br /> <span data-ttu-id="12047-146">Wartość domyślna to FindBySubjectDistinguishedName.</span><span class="sxs-lookup"><span data-stu-id="12047-146">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="12047-147">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="12047-147">Child Elements</span></span>  

 <span data-ttu-id="12047-148">Brak.</span><span class="sxs-lookup"><span data-stu-id="12047-148">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="12047-149">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="12047-149">Parent Elements</span></span>  
  
|<span data-ttu-id="12047-150">Element</span><span class="sxs-lookup"><span data-stu-id="12047-150">Element</span></span>|<span data-ttu-id="12047-151">Opis</span><span class="sxs-lookup"><span data-stu-id="12047-151">Description</span></span>|  
|-------------|-----------------|  
|[\<peer>](peer-of-servicecredentials.md)|<span data-ttu-id="12047-152">Określa bieżące poświadczenia dla węzła równorzędnego.</span><span class="sxs-lookup"><span data-stu-id="12047-152">Specifies the current credentials for a peer node.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="12047-153">Uwagi</span><span class="sxs-lookup"><span data-stu-id="12047-153">Remarks</span></span>  

 <span data-ttu-id="12047-154">Ten element konfiguracji zawiera `X509Certificate2` wystąpienie używane podczas uwierzytelniania sąsiadów w sieci równorzędnej.</span><span class="sxs-lookup"><span data-stu-id="12047-154">This configuration element contains an `X509Certificate2` instance used when authenticating neighbors in the peer mesh.</span></span>  
  
 <span data-ttu-id="12047-155">Aby uzyskać więcej informacji na temat programowania peer-to-peer, zobacz [sieci peer-to-](../../../wcf/feature-details/peer-to-peer-networking.md)peer.</span><span class="sxs-lookup"><span data-stu-id="12047-155">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12047-156">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="12047-156">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateElement>
- <xref:System.ServiceModel.Security.PeerCredential.Certificate%2A>
- <xref:System.ServiceModel.Security.PeerCredential>
- [<span data-ttu-id="12047-157">Praca z certyfikatami</span><span class="sxs-lookup"><span data-stu-id="12047-157">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="12047-158">Sieci równorzędne</span><span class="sxs-lookup"><span data-stu-id="12047-158">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="12047-159">[Uwierzytelnianie komunikatów kanału równorzędnego](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="12047-159">[Peer Channel Message Authentication](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="12047-160">[Uwierzytelnianie niestandardowe kanału równorzędnego](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="12047-160">[Peer Channel Custom Authentication](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="12047-161">Zabezpieczanie aplikacji kanałów równorzędnych</span><span class="sxs-lookup"><span data-stu-id="12047-161">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
- [<span data-ttu-id="12047-162">Zabezpieczanie usług i klientów</span><span class="sxs-lookup"><span data-stu-id="12047-162">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
