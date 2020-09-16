---
title: <peerAuthentication>
ms.date: 03/30/2017
ms.assetid: ad545e6f-f06e-4549-ac92-09d758d5c636
ms.openlocfilehash: 6f0ae05d3397e8fd981037dc58be1f80a661b5c5
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90536005"
---
# \<peerAuthentication>
<span data-ttu-id="13c62-101">Określa ustawienia uwierzytelniania dla certyfikatu równorzędnego używanego przez węzeł równorzędny.</span><span class="sxs-lookup"><span data-stu-id="13c62-101">Specifies authentication settings for a peer certificate used by a peer node.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<peerAuthentication>**  
  
## <a name="syntax"></a><span data-ttu-id="13c62-102">Składnia</span><span class="sxs-lookup"><span data-stu-id="13c62-102">Syntax</span></span>  
  
```xml  
<peerAuthentication customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                    certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                    revocationMode="NoCheck/Online/Offline"
                    trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="13c62-103">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="13c62-103">Attributes and Elements</span></span>  
 <span data-ttu-id="13c62-104">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="13c62-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="13c62-105">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="13c62-105">Attributes</span></span>  
  
|<span data-ttu-id="13c62-106">Atrybut</span><span class="sxs-lookup"><span data-stu-id="13c62-106">Attribute</span></span>|<span data-ttu-id="13c62-107">Opis</span><span class="sxs-lookup"><span data-stu-id="13c62-107">Description</span></span>|  
|---------------|-----------------|  
|`certificateValidationMode`|<span data-ttu-id="13c62-108">Opcjonalne Wyliczenie.</span><span class="sxs-lookup"><span data-stu-id="13c62-108">Optional enumeration.</span></span> <span data-ttu-id="13c62-109">Określa jeden z trzech trybów używanych do walidacji poświadczeń.</span><span class="sxs-lookup"><span data-stu-id="13c62-109">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="13c62-110">Ten atrybut jest typu <xref:System.ServiceModel.Security.X509CertificateValidationMode> .</span><span class="sxs-lookup"><span data-stu-id="13c62-110">This attribute is of type <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span></span> <span data-ttu-id="13c62-111">Jeśli jest ustawiona na `Custom` , `customCertificateValidator` należy również podać wartość.</span><span class="sxs-lookup"><span data-stu-id="13c62-111">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|`customCertificateValidatorType`|<span data-ttu-id="13c62-112">Opcjonalny ciąg.</span><span class="sxs-lookup"><span data-stu-id="13c62-112">Optional string.</span></span> <span data-ttu-id="13c62-113">Określa typ i zestaw używany do walidacji typu niestandardowego.</span><span class="sxs-lookup"><span data-stu-id="13c62-113">Specifies a type and assembly used to validate a custom type.</span></span> <span data-ttu-id="13c62-114">Ten atrybut musi być ustawiony `certificateValidationMode` , gdy jest ustawiony na `Custom` .</span><span class="sxs-lookup"><span data-stu-id="13c62-114">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span> <span data-ttu-id="13c62-115">Ten atrybut jest typu <xref:System.IdentityModel.Selectors.X509CertificateValidator> .</span><span class="sxs-lookup"><span data-stu-id="13c62-115">This attribute is of type <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="13c62-116">Windows Communication Foundation (WCF) udostępnia domyślny moduł sprawdzania poprawności certyfikatu równorzędnego, który weryfikuje certyfikat równorzędny w magazynie zaufanych osób.</span><span class="sxs-lookup"><span data-stu-id="13c62-116">Windows Communication Foundation (WCF) provides a default peer certificate validator that verifies the peer certificate against the trusted people store.</span></span> <span data-ttu-id="13c62-117">Sprawdza również, czy certyfikat jest łańcuchem do prawidłowego katalogu głównego.</span><span class="sxs-lookup"><span data-stu-id="13c62-117">It also verifies that the certificate chains up to a valid root.</span></span> <span data-ttu-id="13c62-118">Możesz zaimplementować niestandardowy moduł sprawdzania poprawności, aby określić inne zachowanie i użyć tego atrybutu, aby wskazać niestandardowy moduł sprawdzania poprawności.</span><span class="sxs-lookup"><span data-stu-id="13c62-118">You can implement a custom validator to specify a different behavior and use this attribute to point to the custom validator.</span></span>|  
|`revocationMode`|<span data-ttu-id="13c62-119">Opcjonalne Wyliczenie.</span><span class="sxs-lookup"><span data-stu-id="13c62-119">Optional enumeration.</span></span> <span data-ttu-id="13c62-120">Określa tryb odwoływania certyfikatu.</span><span class="sxs-lookup"><span data-stu-id="13c62-120">Specifies the certificate revocation mode.</span></span> <span data-ttu-id="13c62-121">Ten atrybut jest typu <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> .</span><span class="sxs-lookup"><span data-stu-id="13c62-121">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span></span> <span data-ttu-id="13c62-122">System sprawdza, czy certyfikat równorzędny nie został odwołany, sprawdzając go na liście odwołanych certyfikatów.</span><span class="sxs-lookup"><span data-stu-id="13c62-122">The system verifies that the peer certificate has not been revoked by looking it up in the revoked certificate list.</span></span> <span data-ttu-id="13c62-123">Ten test można przeprowadzić przez sprawdzenie w trybie online lub w odniesieniu do buforowanej listy odwołania.</span><span class="sxs-lookup"><span data-stu-id="13c62-123">This check can be performed either by checking online or against a cached revocation list.</span></span> <span data-ttu-id="13c62-124">Sprawdzanie odwołania można wyłączyć, ustawiając ten atrybut na NOCHECK.</span><span class="sxs-lookup"><span data-stu-id="13c62-124">Revocation checking can be turned off by setting this attribute to NoCheck.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="13c62-125">Opcjonalne Wyliczenie.</span><span class="sxs-lookup"><span data-stu-id="13c62-125">Optional enumeration.</span></span> <span data-ttu-id="13c62-126">Określa lokalizację zaufanego magazynu, w której certyfikat równorzędny jest sprawdzany przez system zabezpieczeń WCF.</span><span class="sxs-lookup"><span data-stu-id="13c62-126">Specifies the trusted store location where the peer certificate is validated by the WCF security system.</span></span> <span data-ttu-id="13c62-127">Ten atrybut jest typu <xref:System.Security.Cryptography.X509Certificates.StoreLocation> .</span><span class="sxs-lookup"><span data-stu-id="13c62-127">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="13c62-128">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="13c62-128">Child Elements</span></span>  
 <span data-ttu-id="13c62-129">Brak.</span><span class="sxs-lookup"><span data-stu-id="13c62-129">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="13c62-130">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="13c62-130">Parent Elements</span></span>  
  
|<span data-ttu-id="13c62-131">Element</span><span class="sxs-lookup"><span data-stu-id="13c62-131">Element</span></span>|<span data-ttu-id="13c62-132">Opis</span><span class="sxs-lookup"><span data-stu-id="13c62-132">Description</span></span>|  
|-------------|-----------------|  
|[\<peer>](peer-of-servicecredentials.md)|<span data-ttu-id="13c62-133">Określa bieżące poświadczenia dla węzła równorzędnego.</span><span class="sxs-lookup"><span data-stu-id="13c62-133">Specifies the current credentials for a peer node.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="13c62-134">Uwagi</span><span class="sxs-lookup"><span data-stu-id="13c62-134">Remarks</span></span>  
 <span data-ttu-id="13c62-135">`<authentication>`Element odnosi się do <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication> klasy.</span><span class="sxs-lookup"><span data-stu-id="13c62-135">The `<authentication>` element corresponds to the <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication> class.</span></span> <span data-ttu-id="13c62-136">Ten element określa moduł sprawdzania poprawności, który jest wywoływany podczas uwierzytelniania sąsiada-sąsiada w sieci.</span><span class="sxs-lookup"><span data-stu-id="13c62-136">This element specifies a validator, which is invoked during neighbor-to-neighbor authentication in the mesh.</span></span> <span data-ttu-id="13c62-137">Gdy nowy element równorzędny podejmie próbę nawiązania połączenia sąsiada, przekazuje własne poświadczenie do elementu równorzędnego odpowiadającego.</span><span class="sxs-lookup"><span data-stu-id="13c62-137">When a new peer tries to establish a neighbor connection, it passes its own credential to the responding peer.</span></span> <span data-ttu-id="13c62-138">Moduł sprawdzania poprawności jest wywoływany w celu zweryfikowania poświadczeń strony zdalnej.</span><span class="sxs-lookup"><span data-stu-id="13c62-138">The validator of the responder is invoked to verify the credential of the remote party.</span></span> <span data-ttu-id="13c62-139">Za każdym razem, gdy połączenie równorzędne jest nawiązane w sieci, oba elementy równorzędne są uwierzytelniane wzajemnie, co oznacza, że są wywoływane walidacje na obu końcach.</span><span class="sxs-lookup"><span data-stu-id="13c62-139">Whenever a peer connection is established in the mesh, both peers are mutually authenticated, meaning validators on both ends are invoked.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13c62-140">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="13c62-140">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.PeerAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.PeerAuthentication%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- [<span data-ttu-id="13c62-141">Praca z certyfikatami</span><span class="sxs-lookup"><span data-stu-id="13c62-141">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="13c62-142">Sieci równorzędne</span><span class="sxs-lookup"><span data-stu-id="13c62-142">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="13c62-143">[Uwierzytelnianie komunikatów kanału równorzędnego](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="13c62-143">[Peer Channel Message Authentication](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="13c62-144">[Uwierzytelnianie niestandardowe kanału równorzędnego](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="13c62-144">[Peer Channel Custom Authentication](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="13c62-145">Zabezpieczanie aplikacji kanałów równorzędnych</span><span class="sxs-lookup"><span data-stu-id="13c62-145">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
