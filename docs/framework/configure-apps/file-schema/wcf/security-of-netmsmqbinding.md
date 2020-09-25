---
title: <security> dla <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 001d11a9-7439-498c-b09d-fca20eaf8cd3
ms.openlocfilehash: 32b066fdf4d8edbbd36fdff7b14bdec87ddc970d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91170080"
---
# <a name="security-of-netmsmqbinding"></a><span data-ttu-id="c6078-102">\<security> dla \<netMsmqBinding></span><span class="sxs-lookup"><span data-stu-id="c6078-102">\<security> of \<netMsmqBinding></span></span>

<span data-ttu-id="c6078-103">Definiuje ustawienia zabezpieczeń dla powiązania usługi MSMQ.</span><span class="sxs-lookup"><span data-stu-id="c6078-103">Defines the security settings for a MSMQ binding.</span></span> <span data-ttu-id="c6078-104">Określa, czy zabezpieczenia transportu lub protokołu SOAP są włączone i, jeśli tak, jakiego trybu uwierzytelniania i poziomów ochrony są używane.</span><span class="sxs-lookup"><span data-stu-id="c6078-104">It specifies whether transport or SOAP security is enabled and, if so, what authentication mode and protection levels are in use.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netMsmqBinding>**](netmsmqbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="c6078-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="c6078-105">Syntax</span></span>  
  
```xml  
<security mode="None/Transport/Message/Both">
  <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"
             msmqEncryptionAlgorithm="RC4Stream/AES"
             msmqProtectionLevel="None/Sign/EncryptAndSign"
             msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
    <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
             clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c6078-106">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="c6078-106">Attributes and Elements</span></span>  

 <span data-ttu-id="c6078-107">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="c6078-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c6078-108">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="c6078-108">Attributes</span></span>  
  
|<span data-ttu-id="c6078-109">Atrybut</span><span class="sxs-lookup"><span data-stu-id="c6078-109">Attribute</span></span>|<span data-ttu-id="c6078-110">Opis</span><span class="sxs-lookup"><span data-stu-id="c6078-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c6078-111">tryb</span><span class="sxs-lookup"><span data-stu-id="c6078-111">mode</span></span>|<span data-ttu-id="c6078-112">Określa typ zabezpieczeń, który kontroluje integralność, poufność i uwierzytelnianie.</span><span class="sxs-lookup"><span data-stu-id="c6078-112">Specifies the type of security that controls integrity, confidentiality and authentication.</span></span> <span data-ttu-id="c6078-113">Prawidłowe wartości to:</span><span class="sxs-lookup"><span data-stu-id="c6078-113">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="c6078-114">-Brak: spowoduje to wyłączenie zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="c6078-114">-   None: This disables security.</span></span><br /><span data-ttu-id="c6078-115">-Transport: Ochrona i uwierzytelnianie są oferowane przez transport.</span><span class="sxs-lookup"><span data-stu-id="c6078-115">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="c6078-116">Ma to zastosowanie do zabezpieczeń komunikatów między dwoma menedżerami kolejki.</span><span class="sxs-lookup"><span data-stu-id="c6078-116">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="c6078-117">Nie ma żadnych zabezpieczeń oferowanych między aplikacją a menedżerem kolejki.</span><span class="sxs-lookup"><span data-stu-id="c6078-117">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="c6078-118">Istniejące aplikacje MSMQ są funkcjonalnie równoważne z tego typu trybem zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="c6078-118">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><span data-ttu-id="c6078-119">-Message: Określa zabezpieczenia aplikacji końcowej.</span><span class="sxs-lookup"><span data-stu-id="c6078-119">-   Message: Specifies end-end application security.</span></span> <span data-ttu-id="c6078-120">Warstwa transportu nie oferuje żadnych zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="c6078-120">There is no security offered at the transport layer.</span></span> <span data-ttu-id="c6078-121">Jest to podobne do zabezpieczeń oferowanych przez inne powiązania standardowe.</span><span class="sxs-lookup"><span data-stu-id="c6078-121">This is similar to the security offered by other standard bindings.</span></span><br /><span data-ttu-id="c6078-122">-Both: oferuje zabezpieczenia zarówno dla warstwy transportu, jak i protokołu SOAP.</span><span class="sxs-lookup"><span data-stu-id="c6078-122">-   Both: Offers security at both the transport and SOAP messaging layer.</span></span> <span data-ttu-id="c6078-123">To samo poświadczenie jest wymagane na poziomie.</span><span class="sxs-lookup"><span data-stu-id="c6078-123">The same credential is required at both the levels.</span></span><br /><br /> <span data-ttu-id="c6078-124">Wartością domyślną jest transport.</span><span class="sxs-lookup"><span data-stu-id="c6078-124">The default value is Transport.</span></span> <span data-ttu-id="c6078-125">Ten atrybut jest typu <xref:System.ServiceModel.NetMsmqSecurityMode> .</span><span class="sxs-lookup"><span data-stu-id="c6078-125">This attribute is of type <xref:System.ServiceModel.NetMsmqSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c6078-126">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="c6078-126">Child Elements</span></span>  
  
|<span data-ttu-id="c6078-127">Element</span><span class="sxs-lookup"><span data-stu-id="c6078-127">Element</span></span>|<span data-ttu-id="c6078-128">Opis</span><span class="sxs-lookup"><span data-stu-id="c6078-128">Description</span></span>|  
|-------------|-----------------|  
|[\<message>](message-of-netmsmqbinding.md)|<span data-ttu-id="c6078-129">Definiuje ustawienia zabezpieczeń wiadomości protokołu SOAP.</span><span class="sxs-lookup"><span data-stu-id="c6078-129">Defines the SOAP message security settings.</span></span> <span data-ttu-id="c6078-130">Ten element jest typu <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement> .</span><span class="sxs-lookup"><span data-stu-id="c6078-130">This element is of type <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>.</span></span>|  
|[\<transport>](transport-of-netmsmqbinding.md)|<span data-ttu-id="c6078-131">Definiuje ustawienia zabezpieczeń dla transportu MSMQ.</span><span class="sxs-lookup"><span data-stu-id="c6078-131">Defines the security settings for the MSMQ transport.</span></span> <span data-ttu-id="c6078-132">Ten element jest typu <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement> .</span><span class="sxs-lookup"><span data-stu-id="c6078-132">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c6078-133">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="c6078-133">Parent Elements</span></span>  
  
|<span data-ttu-id="c6078-134">Element</span><span class="sxs-lookup"><span data-stu-id="c6078-134">Element</span></span>|<span data-ttu-id="c6078-135">Opis</span><span class="sxs-lookup"><span data-stu-id="c6078-135">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c6078-136">powiązanie</span><span class="sxs-lookup"><span data-stu-id="c6078-136">binding</span></span>|<span data-ttu-id="c6078-137">Element Binding elementu [\<netMsmqBinding>](netmsmqbinding.md)</span><span class="sxs-lookup"><span data-stu-id="c6078-137">The binding element of the [\<netMsmqBinding>](netmsmqbinding.md)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c6078-138">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="c6078-138">See also</span></span>

- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement>
- <xref:System.ServiceModel.NetMsmqBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetMsmqBindingElement.Security%2A>
- <xref:System.ServiceModel.NetMsmqSecurity>
- [<span data-ttu-id="c6078-139">Zabezpieczanie usług i klientów</span><span class="sxs-lookup"><span data-stu-id="c6078-139">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="c6078-140">Powiązania</span><span class="sxs-lookup"><span data-stu-id="c6078-140">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="c6078-141">Konfigurowanie powiązań dostarczanych przez system</span><span class="sxs-lookup"><span data-stu-id="c6078-141">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="c6078-142">Konfigurowanie usług i klientów za pomocą wiązań</span><span class="sxs-lookup"><span data-stu-id="c6078-142">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
- [<span data-ttu-id="c6078-143">Kolejki programu WCF</span><span class="sxs-lookup"><span data-stu-id="c6078-143">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
