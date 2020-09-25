---
title: <certificateReference>
ms.date: 03/30/2017
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
author: BrucePerlerMS
ms.openlocfilehash: c21e5186b8afdf8c72cbfc605af94c95bc2bc0d5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201383"
---
# \<certificateReference>

<span data-ttu-id="f652f-101">Określa ustawienia, które są używane do znajdowania i weryfikowania certyfikatu X. 509 w magazynie certyfikatów.</span><span class="sxs-lookup"><span data-stu-id="f652f-101">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateReference>**  
  
## <a name="syntax"></a><span data-ttu-id="f652f-102">Składnia</span><span class="sxs-lookup"><span data-stu-id="f652f-102">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <serviceCertificate>  
      <certificateReference
        storeName="AddressBook||AuthRoot||CertificateAuthority||Disallowed||My||Root||TrustedPeople||TrustedPublisher"  
        storeLocation="CurrentUser||LocalMachine"  
        x509FindType="FindByThumbprint||FindBySubjectName||FindBySubjectDistinguishedName||FindByIssuerName||FindByIssuerDistinguishedName||FindBySerialNumber||FindByTimeValid||FindByTimeNotYetValid||FindByTimeExpired||FindByTemplateName||FindByApplicationPolicy||FindByCertificatePolicy||FindByExtension||FindByKeyUsage||FindBySubjectKeyIdentifier"  
        findValue=xs:String  
        isChainIncluded=xs:Boolean >  
      </certificateReference>  
    </serviceCertificate>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f652f-103">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="f652f-103">Attributes and Elements</span></span>  

 <span data-ttu-id="f652f-104">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="f652f-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f652f-105">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="f652f-105">Attributes</span></span>  
  
|<span data-ttu-id="f652f-106">Atrybut</span><span class="sxs-lookup"><span data-stu-id="f652f-106">Attribute</span></span>|<span data-ttu-id="f652f-107">Opis</span><span class="sxs-lookup"><span data-stu-id="f652f-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f652f-108">storeName</span><span class="sxs-lookup"><span data-stu-id="f652f-108">storeName</span></span>|<span data-ttu-id="f652f-109">Nazwa magazynu certyfikatów X. 509.</span><span class="sxs-lookup"><span data-stu-id="f652f-109">The name of the X.509 certificate store.</span></span> <span data-ttu-id="f652f-110">Wartość domyślna to "my".</span><span class="sxs-lookup"><span data-stu-id="f652f-110">The default is "My".</span></span> <span data-ttu-id="f652f-111">Opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="f652f-111">Optional.</span></span>|  
|<span data-ttu-id="f652f-112">storeLocation</span><span class="sxs-lookup"><span data-stu-id="f652f-112">storeLocation</span></span>|<span data-ttu-id="f652f-113"><xref:System.Security.Cryptography.X509Certificates.StoreLocation>Wartość, która określa lokalizację magazynu certyfikatów X. 509.</span><span class="sxs-lookup"><span data-stu-id="f652f-113">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the location of the X.509 certificate store.</span></span> <span data-ttu-id="f652f-114">Wartość domyślna to "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="f652f-114">The default value is "LocalMachine".</span></span> <span data-ttu-id="f652f-115">Opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="f652f-115">Optional.</span></span>|  
|<span data-ttu-id="f652f-116">x509FindType</span><span class="sxs-lookup"><span data-stu-id="f652f-116">x509FindType</span></span>|<span data-ttu-id="f652f-117">Wartość określająca <xref:System.Security.Cryptography.X509Certificates.X509FindType> Typ wyszukiwania, które ma zostać wykonane.</span><span class="sxs-lookup"><span data-stu-id="f652f-117">An <xref:System.Security.Cryptography.X509Certificates.X509FindType> value that specifies the type of search that is to be executed.</span></span> <span data-ttu-id="f652f-118">Wartość domyślna to "FindBySubjectDistinguishedName".</span><span class="sxs-lookup"><span data-stu-id="f652f-118">The default is "FindBySubjectDistinguishedName".</span></span> <span data-ttu-id="f652f-119">Opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="f652f-119">Optional.</span></span>|  
|<span data-ttu-id="f652f-120">findValue</span><span class="sxs-lookup"><span data-stu-id="f652f-120">findValue</span></span>|<span data-ttu-id="f652f-121">Wartość do wyszukania w magazynie certyfikatów X. 509.</span><span class="sxs-lookup"><span data-stu-id="f652f-121">The value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="f652f-122">Opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="f652f-122">Optional.</span></span>|  
|<span data-ttu-id="f652f-123">isChainIncluded</span><span class="sxs-lookup"><span data-stu-id="f652f-123">isChainIncluded</span></span>|<span data-ttu-id="f652f-124">Określa, czy należy przeprowadzić walidację przy użyciu łańcucha certyfikatów.</span><span class="sxs-lookup"><span data-stu-id="f652f-124">Specifies whether validation should be performed by using the certificate chain.</span></span> <span data-ttu-id="f652f-125">Wartość domyślna to "true"; Walidacja jest przeprowadzana przy użyciu łańcucha certyfikatów.</span><span class="sxs-lookup"><span data-stu-id="f652f-125">The default is "true"; validation is performed by using the certificate chain.</span></span> <span data-ttu-id="f652f-126">Opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="f652f-126">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f652f-127">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="f652f-127">Child Elements</span></span>  

 <span data-ttu-id="f652f-128">Brak</span><span class="sxs-lookup"><span data-stu-id="f652f-128">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f652f-129">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="f652f-129">Parent Elements</span></span>  
  
|<span data-ttu-id="f652f-130">Element</span><span class="sxs-lookup"><span data-stu-id="f652f-130">Element</span></span>|<span data-ttu-id="f652f-131">Opis</span><span class="sxs-lookup"><span data-stu-id="f652f-131">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCertificate>](servicecertificate.md)|<span data-ttu-id="f652f-132">Konfiguruje certyfikat używany do szyfrowania i odszyfrowywania tokenów.</span><span class="sxs-lookup"><span data-stu-id="f652f-132">Configures the certificate that is used to encrypt and decrypt tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f652f-133">Uwagi</span><span class="sxs-lookup"><span data-stu-id="f652f-133">Remarks</span></span>  

 <span data-ttu-id="f652f-134">`<certificateReference>`Element określa ustawienia, które są używane do znajdowania i weryfikowania certyfikatu X. 509 w magazynie certyfikatów.</span><span class="sxs-lookup"><span data-stu-id="f652f-134">The `<certificateReference>` element specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span> <span data-ttu-id="f652f-135">Gdy jest określony jako element podrzędny `<serviceCertificate>` elementu, określa lokalizację i ustawienia weryfikacji certyfikatu X. 509, który jest używany do szyfrowania i odszyfrowywania tokenów.</span><span class="sxs-lookup"><span data-stu-id="f652f-135">When it is specified as the child element of the `<serviceCertificate>` element, it specifies the location and verification settings of the X.509 certificate that is used to encrypt and decrypt tokens.</span></span> <span data-ttu-id="f652f-136">`<certificateReference>`Element jest reprezentowany przez <xref:System.ServiceModel.Configuration.CertificateReferenceElement> klasę.</span><span class="sxs-lookup"><span data-stu-id="f652f-136">The `<certificateReference>` element is represented by the <xref:System.ServiceModel.Configuration.CertificateReferenceElement> class.</span></span>
