---
title: <samlSecurityTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 09202d12-88d3-49cc-953b-703bcc1690eb
author: BrucePerlerMS
ms.openlocfilehash: f93ec0007b537e306a570b166eaa4cd2fe7f81e2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91157034"
---
# \<samlSecurityTokenRequirement>

<span data-ttu-id="ba6d2-101">Zapewnia konfigurację <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> klasy, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> klasy lub klasy pochodnej jednej z tych klas.</span><span class="sxs-lookup"><span data-stu-id="ba6d2-101">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span> <span data-ttu-id="ba6d2-102">Reprezentowane przez <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> klasę.</span><span class="sxs-lookup"><span data-stu-id="ba6d2-102">Represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<samlSecurityTokenRequirement>**  
  
## <a name="syntax"></a><span data-ttu-id="ba6d2-103">Składnia</span><span class="sxs-lookup"><span data-stu-id="ba6d2-103">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add>  
        <samlSecurityTokenRequirement
            issuerCertificateValidationMode="None||ChainTrust||PeerTrust||PeerOrChainTrust||Custom"  
            issuerCertificateRevocationMode="NoCheck||Offline||Online"  
            issuerCertificateTrustedStoreLocation="CurrentLocation||LocalMachine"  
            issuerCertificateValidator="Namespace.Class Assembly"  
            mapToWindows=xs:boolean  
          <nameClaimType value=xs:string />  
          <roleClaimType value=xs:string />  
        </samlSecurityTokenRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ba6d2-104">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="ba6d2-104">Attributes and Elements</span></span>  

 <span data-ttu-id="ba6d2-105">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="ba6d2-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ba6d2-106">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="ba6d2-106">Attributes</span></span>  
  
|<span data-ttu-id="ba6d2-107">Atrybut</span><span class="sxs-lookup"><span data-stu-id="ba6d2-107">Attribute</span></span>|<span data-ttu-id="ba6d2-108">Opis</span><span class="sxs-lookup"><span data-stu-id="ba6d2-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ba6d2-109">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="ba6d2-109">mapToWindows</span></span>|<span data-ttu-id="ba6d2-110">Określa, czy program obsługi tokenów powinien mapować token walidacji na konto systemu Windows przy użyciu przychodzącego oświadczenie nazwy UPN.</span><span class="sxs-lookup"><span data-stu-id="ba6d2-110">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="ba6d2-111">Wartość domyślna to "false".</span><span class="sxs-lookup"><span data-stu-id="ba6d2-111">The default is "false".</span></span>|  
|<span data-ttu-id="ba6d2-112">issuerCertificateRevocationMode</span><span class="sxs-lookup"><span data-stu-id="ba6d2-112">issuerCertificateRevocationMode</span></span>|<span data-ttu-id="ba6d2-113"><xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>Wartość określająca tryb odwołania, który ma być używany dla certyfikatu X. 509.</span><span class="sxs-lookup"><span data-stu-id="ba6d2-113">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="ba6d2-114">Wartość domyślna to "online".</span><span class="sxs-lookup"><span data-stu-id="ba6d2-114">The default value is "Online".</span></span>|  
|<span data-ttu-id="ba6d2-115">issuerCertificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="ba6d2-115">issuerCertificateValidationMode</span></span>|<span data-ttu-id="ba6d2-116">Wartość określająca <xref:System.ServiceModel.Security.X509CertificateValidationMode> tryb walidacji, który ma być używany dla certyfikatu X. 509.</span><span class="sxs-lookup"><span data-stu-id="ba6d2-116">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="ba6d2-117">Wartość domyślna to "PeerOrChainTrust".</span><span class="sxs-lookup"><span data-stu-id="ba6d2-117">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="ba6d2-118">issuerCertificateTrustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="ba6d2-118">issuerCertificateTrustedStoreLocation</span></span>|<span data-ttu-id="ba6d2-119">Wartość określająca <xref:System.Security.Cryptography.X509Certificates.StoreLocation> Magazyn certyfikatów X. 509.</span><span class="sxs-lookup"><span data-stu-id="ba6d2-119">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="ba6d2-120">Wartość domyślna to "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="ba6d2-120">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="ba6d2-121">issuerCertificateValidator</span><span class="sxs-lookup"><span data-stu-id="ba6d2-121">issuerCertificateValidator</span></span>|<span data-ttu-id="ba6d2-122">Typ niestandardowy, który pochodzi od <xref:System.IdentityModel.Selectors.X509CertificateValidator> .</span><span class="sxs-lookup"><span data-stu-id="ba6d2-122">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="ba6d2-123">Jeśli `issuerCertificateValidationMode` atrybut jest "Custom", wystąpienie tego typu jest używane na potrzeby walidacji certyfikatu wystawcy.</span><span class="sxs-lookup"><span data-stu-id="ba6d2-123">If the `issuerCertificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ba6d2-124">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="ba6d2-124">Child Elements</span></span>  
  
|<span data-ttu-id="ba6d2-125">Element</span><span class="sxs-lookup"><span data-stu-id="ba6d2-125">Element</span></span>|<span data-ttu-id="ba6d2-126">Opis</span><span class="sxs-lookup"><span data-stu-id="ba6d2-126">Description</span></span>|  
|-------------|-----------------|  
|[\<nameClaimType>](nameclaimtype.md)|<span data-ttu-id="ba6d2-127">Ustawia typ zgłoszenia, który określa <xref:System.Security.Principal.IIdentity.Name%2A> Właściwość.</span><span class="sxs-lookup"><span data-stu-id="ba6d2-127">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span>|  
|[\<roleClaimType>](roleclaimtype.md)|<span data-ttu-id="ba6d2-128">Określa typ oświadczenia, który definiuje oświadczenia typu roli w kolekcji <xref:System.Security.Claims.ClaimsIdentity> obiektów zwracanych przez <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> metodę procedury obsługi tokenu.</span><span class="sxs-lookup"><span data-stu-id="ba6d2-128">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ba6d2-129">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="ba6d2-129">Parent Elements</span></span>  
  
|<span data-ttu-id="ba6d2-130">Element</span><span class="sxs-lookup"><span data-stu-id="ba6d2-130">Element</span></span>|<span data-ttu-id="ba6d2-131">Opis</span><span class="sxs-lookup"><span data-stu-id="ba6d2-131">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add.md)|<span data-ttu-id="ba6d2-132">Dodaje określony program obsługi tokenów zabezpieczających do kolekcji obsługi tokenów.</span><span class="sxs-lookup"><span data-stu-id="ba6d2-132">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ba6d2-133">Uwagi</span><span class="sxs-lookup"><span data-stu-id="ba6d2-133">Remarks</span></span>  

 <span data-ttu-id="ba6d2-134">`<samlSecurityTokenRequirement>`Element jest reprezentowany przez <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> klasę w modelu obiektów i służy do konfigurowania `SamlSecurityTokenRequirement` właściwości w <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> lub <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> .</span><span class="sxs-lookup"><span data-stu-id="ba6d2-134">The `<samlSecurityTokenRequirement>` element is represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class in the object model and is used to configure the `SamlSecurityTokenRequirement` property on a <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> or a <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ba6d2-135">Przykład</span><span class="sxs-lookup"><span data-stu-id="ba6d2-135">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement issuerCertificateValidationMode="PeerOrChainTrust"  
                                  issuerCertificateRevocationMode="Online"  
                                  issuerCertificateTrustedStoreLocation="LocalMachine"  
                                  mapToWindows="false">  
  
        <nameClaimType value="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name" />  
        <roleClaimType value="schemas.microsoft.com/ws/2006/04/identity/claims/role" />  
    </samlSecurityTokenRequirement>  
</add>  
```
