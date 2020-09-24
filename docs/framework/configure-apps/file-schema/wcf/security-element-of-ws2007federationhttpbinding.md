---
title: <security> elementu <ws2007FederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 826219b4-3a16-45fc-832d-0cd7cbbd3b84
ms.openlocfilehash: 943ccc241aef15b58661699408b085d98cf86c3b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183705"
---
# <a name="security-element-of-ws2007federationhttpbinding"></a><span data-ttu-id="304db-102">\<security> elementu \<ws2007FederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="304db-102">\<security> element of \<ws2007FederationHttpBinding></span></span>

<span data-ttu-id="304db-103">Definiuje ustawienia zabezpieczeń [\<ws2007FederationHttpBinding>](ws2007federationhttpbinding.md) elementu.</span><span class="sxs-lookup"><span data-stu-id="304db-103">Defines the security settings of the [\<ws2007FederationHttpBinding>](ws2007federationhttpbinding.md) element.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007FederationHttpBinding>**](ws2007federationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="304db-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="304db-104">Syntax</span></span>  
  
```xml  
<ws2007FederationBinding>
  <binding>
    <security mode="None/Message/TransportWithMessageCredential">
      <message negotiateServiceCredential="Boolean"
               algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/  Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               defaultProtectionLevel="none/sign/EncryptAndSign"
               issuedTokenType="string"
               issuedKeyType="SymmetricKey/PublicKey">
      </message>
    </security>
  </binding>
</ws2007FederationBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="304db-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="304db-105">Attributes and Elements</span></span>  

 <span data-ttu-id="304db-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="304db-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="304db-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="304db-107">Attributes</span></span>  
  
|<span data-ttu-id="304db-108">Atrybut</span><span class="sxs-lookup"><span data-stu-id="304db-108">Attribute</span></span>|<span data-ttu-id="304db-109">Opis</span><span class="sxs-lookup"><span data-stu-id="304db-109">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="304db-110">Opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="304db-110">Optional.</span></span> <span data-ttu-id="304db-111">Określa typ stosowanego zabezpieczenia.</span><span class="sxs-lookup"><span data-stu-id="304db-111">Specifies the type of security that is applied.</span></span> <span data-ttu-id="304db-112">Wartość domyślna to `Message`.</span><span class="sxs-lookup"><span data-stu-id="304db-112">The default value is `Message`.</span></span> <span data-ttu-id="304db-113">Ten atrybut jest typu <xref:System.ServiceModel.WSFederationHttpSecurityMode> .</span><span class="sxs-lookup"><span data-stu-id="304db-113">This attribute is of type <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="304db-114">Atrybut Mode</span><span class="sxs-lookup"><span data-stu-id="304db-114">mode Attribute</span></span>  
  
|<span data-ttu-id="304db-115">Wartość</span><span class="sxs-lookup"><span data-stu-id="304db-115">Value</span></span>|<span data-ttu-id="304db-116">Opis</span><span class="sxs-lookup"><span data-stu-id="304db-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="304db-117">Brak</span><span class="sxs-lookup"><span data-stu-id="304db-117">None</span></span>|<span data-ttu-id="304db-118">Komunikat protokołu SOAP nie jest zabezpieczony podczas transferu.</span><span class="sxs-lookup"><span data-stu-id="304db-118">The SOAP message is not secure during transfer.</span></span>|  
|<span data-ttu-id="304db-119">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="304db-119">Message</span></span>|<span data-ttu-id="304db-120">Integralność, poufność, uwierzytelnianie serwera i uwierzytelnianie klienta są udostępniane przy użyciu zabezpieczeń komunikatów protokołu SOAP.</span><span class="sxs-lookup"><span data-stu-id="304db-120">Integrity, confidentiality, server authentication and client authentication are provided using SOAP message security.</span></span> <span data-ttu-id="304db-121">Domyślnie treść jest zaszyfrowana i podpisana.</span><span class="sxs-lookup"><span data-stu-id="304db-121">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="304db-122">Usługa musi być skonfigurowana przy użyciu certyfikatu.</span><span class="sxs-lookup"><span data-stu-id="304db-122">The service must be configured with a certificate.</span></span> <span data-ttu-id="304db-123">Uwierzytelnianie klienta opiera się na tokenie wystawionym dla klienta przez usługę tokenu zabezpieczającego.</span><span class="sxs-lookup"><span data-stu-id="304db-123">Client authentication is based on the token issued to the client by a security token service.</span></span>|  
|<span data-ttu-id="304db-124">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="304db-124">TransportWithMessageCredential</span></span>|<span data-ttu-id="304db-125">Uwierzytelnianie za pomocą protokołu HTTPS zapewnia integralność, poufność i serwer.</span><span class="sxs-lookup"><span data-stu-id="304db-125">Integrity, confidentiality and server authentication are provided by HTTPS.</span></span> <span data-ttu-id="304db-126">Usługa musi być skonfigurowana przy użyciu certyfikatu.</span><span class="sxs-lookup"><span data-stu-id="304db-126">The service must be configured with a certificate.</span></span> <span data-ttu-id="304db-127">Uwierzytelnianie klienta jest zapewniane przez zabezpieczenia komunikatów protokołu SOAP i opiera się na tokenie wystawionym dla klienta przez usługę tokenu zabezpieczającego.</span><span class="sxs-lookup"><span data-stu-id="304db-127">Client authentication is provided by means of SOAP message security and is based on the token issued to the client by a security token service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="304db-128">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="304db-128">Child Elements</span></span>  
  
|<span data-ttu-id="304db-129">Element</span><span class="sxs-lookup"><span data-stu-id="304db-129">Element</span></span>|<span data-ttu-id="304db-130">Opis</span><span class="sxs-lookup"><span data-stu-id="304db-130">Description</span></span>|  
|-------------|-----------------|  
|[\<message>](message-of-ws2007httpbinding.md)|<span data-ttu-id="304db-131">Definiuje ustawienia zabezpieczeń na poziomie wiadomości.</span><span class="sxs-lookup"><span data-stu-id="304db-131">Defines the settings for the message-level security.</span></span> <span data-ttu-id="304db-132">Ten element jest typu <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement> .</span><span class="sxs-lookup"><span data-stu-id="304db-132">This element is of type <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="304db-133">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="304db-133">Parent Elements</span></span>  
  
|<span data-ttu-id="304db-134">Element</span><span class="sxs-lookup"><span data-stu-id="304db-134">Element</span></span>|<span data-ttu-id="304db-135">Opis</span><span class="sxs-lookup"><span data-stu-id="304db-135">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="304db-136">Definiuje wszystkie możliwości powiązań [\<wsDualHttpBinding>](wsdualhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="304db-136">Defines all binding capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="304db-137">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="304db-137">See also</span></span>

- <xref:System.ServiceModel.WSFederationHttpSecurity>
- <xref:System.ServiceModel.WSFederationHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>
- [<span data-ttu-id="304db-138">Instrukcje: tworzenie elementu WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="304db-138">How to: Create a WSFederationHttpBinding</span></span>](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
- [<span data-ttu-id="304db-139">Zabezpieczanie usług i klientów</span><span class="sxs-lookup"><span data-stu-id="304db-139">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="304db-140">Wybieranie typu poświadczeń</span><span class="sxs-lookup"><span data-stu-id="304db-140">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="304db-141">Powiązania</span><span class="sxs-lookup"><span data-stu-id="304db-141">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="304db-142">Konfigurowanie powiązań dostarczanych przez system</span><span class="sxs-lookup"><span data-stu-id="304db-142">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="304db-143">Konfigurowanie usług i klientów za pomocą wiązań</span><span class="sxs-lookup"><span data-stu-id="304db-143">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
