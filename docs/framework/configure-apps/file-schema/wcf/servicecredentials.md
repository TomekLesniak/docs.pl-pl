---
title: <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: 96db336c-4f7a-4193-81a5-910b8ffd804f
ms.openlocfilehash: 63368355027856118546bc70183b41864eddb0e6
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91172882"
---
# \<serviceCredentials>

<span data-ttu-id="0fb81-101">Określa poświadczenie, które ma być używane w uwierzytelnianiu usługi i ustawień związanych z walidacją poświadczeń klienta.</span><span class="sxs-lookup"><span data-stu-id="0fb81-101">Specifies the credential to be used in authenticating the service and the client credential validation-related settings.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceCredentials>**  
  
## <a name="syntax"></a><span data-ttu-id="0fb81-102">Składnia</span><span class="sxs-lookup"><span data-stu-id="0fb81-102">Syntax</span></span>  
  
```xml  
<serviceCredentials type="String">
  <clientCertificate>
  </clientCertificate>
  <issuedTokenAuthentication>
  </issuedTokenAuthentication>
  <peer>
  </peer>
  <secureConversationAuthentication>
  </secureConversationAuthentication>
  <serviceCertificate>
  </serviceCertificate>
  <userNameAuthentication>
  </userNameAuthentication>
  <windowsAuthentication>
  </windowsAuthentication>
</serviceCredentials>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0fb81-103">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="0fb81-103">Attributes and Elements</span></span>  

 <span data-ttu-id="0fb81-104">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="0fb81-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0fb81-105">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="0fb81-105">Attributes</span></span>  
  
|<span data-ttu-id="0fb81-106">Atrybut</span><span class="sxs-lookup"><span data-stu-id="0fb81-106">Attribute</span></span>|<span data-ttu-id="0fb81-107">Opis</span><span class="sxs-lookup"><span data-stu-id="0fb81-107">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="0fb81-108">Ciąg określający typ tego elementu konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="0fb81-108">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0fb81-109">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="0fb81-109">Child Elements</span></span>  
  
|<span data-ttu-id="0fb81-110">Element</span><span class="sxs-lookup"><span data-stu-id="0fb81-110">Element</span></span>|<span data-ttu-id="0fb81-111">Opis</span><span class="sxs-lookup"><span data-stu-id="0fb81-111">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCertificate>](clientcertificate-of-servicecredentials.md)|<span data-ttu-id="0fb81-112">Określa certyfikat, który ma być używany, gdy certyfikat klienta jest dostępny poza pasmem.</span><span class="sxs-lookup"><span data-stu-id="0fb81-112">Specifies the certificate to be used when the client certificate is available out-of-band.</span></span> <span data-ttu-id="0fb81-113">Ten element określa również ustawienia weryfikacji certyfikatu klienta.</span><span class="sxs-lookup"><span data-stu-id="0fb81-113">This element also specifies client certificate validation settings.</span></span> <span data-ttu-id="0fb81-114">Ten element jest typu <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement> .</span><span class="sxs-lookup"><span data-stu-id="0fb81-114">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span></span>|  
|[\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="0fb81-115">Określa bieżący token wystawiony dla tej usługi.</span><span class="sxs-lookup"><span data-stu-id="0fb81-115">Specifies the current issued token for this service.</span></span> <span data-ttu-id="0fb81-116">Ten element jest typu <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement> .</span><span class="sxs-lookup"><span data-stu-id="0fb81-116">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span></span>|  
|[\<peer>](peer-of-servicecredentials.md)|<span data-ttu-id="0fb81-117">Określa bieżące poświadczenia dla węzła równorzędnego.</span><span class="sxs-lookup"><span data-stu-id="0fb81-117">Specifies the current credentials for a peer node.</span></span> <span data-ttu-id="0fb81-118">Ten element jest typu <xref:System.ServiceModel.Configuration.PeerCredentialElement> .</span><span class="sxs-lookup"><span data-stu-id="0fb81-118">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[\<secureConversationAuthentication>](secureconversationauthentication-of-servicecredential.md)|<span data-ttu-id="0fb81-119">Określa bieżące poświadczenia dla bezpiecznej konwersacji.</span><span class="sxs-lookup"><span data-stu-id="0fb81-119">Specifies the current credentials for a secure conversation.</span></span> <span data-ttu-id="0fb81-120">Ten element jest typu <xref:System.ServiceModel.Configuration.SecureConversationServiceElement> .</span><span class="sxs-lookup"><span data-stu-id="0fb81-120">This element is of type <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span></span>|  
|[\<serviceCertificate>](servicecertificate-of-servicecredentials.md)|<span data-ttu-id="0fb81-121">Określa certyfikat używany przez usługę do zidentyfikowania siebie.</span><span class="sxs-lookup"><span data-stu-id="0fb81-121">Specifies a certificate used by a service to identify itself.</span></span> <span data-ttu-id="0fb81-122">Ten element jest typu <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement> .</span><span class="sxs-lookup"><span data-stu-id="0fb81-122">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span></span>|  
|[\<userNameAuthentication>](usernameauthentication.md)|<span data-ttu-id="0fb81-123">Określa ustawienia dla walidacji hasła użytkownika.</span><span class="sxs-lookup"><span data-stu-id="0fb81-123">Specifies the settings for username password validation.</span></span> <span data-ttu-id="0fb81-124">Ten element jest typu <xref:System.ServiceModel.Configuration.UserNameServiceElement> .</span><span class="sxs-lookup"><span data-stu-id="0fb81-124">This element is of type <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span></span>|  
|[\<windowsAuthentication>](windowsauthentication-of-servicecredentials.md)|<span data-ttu-id="0fb81-125">Określa ustawienia weryfikacji poświadczeń systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="0fb81-125">Specifies the settings for Windows credential validation.</span></span> <span data-ttu-id="0fb81-126">Ten element jest typu <xref:System.ServiceModel.Configuration.WindowsServiceElement> .</span><span class="sxs-lookup"><span data-stu-id="0fb81-126">This element is of type <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0fb81-127">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="0fb81-127">Parent Elements</span></span>  
  
|<span data-ttu-id="0fb81-128">Element</span><span class="sxs-lookup"><span data-stu-id="0fb81-128">Element</span></span>|<span data-ttu-id="0fb81-129">Opis</span><span class="sxs-lookup"><span data-stu-id="0fb81-129">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="0fb81-130">Określa zachowanie elementu.</span><span class="sxs-lookup"><span data-stu-id="0fb81-130">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0fb81-131">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="0fb81-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement>
- <xref:System.ServiceModel.Description.ServiceCredentials>
- [<span data-ttu-id="0fb81-132">Zachowania zabezpieczeń</span><span class="sxs-lookup"><span data-stu-id="0fb81-132">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
