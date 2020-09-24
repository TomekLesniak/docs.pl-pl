---
title: <security> dla <msmqIntegrationBinding>
ms.date: 03/30/2017
ms.assetid: ae5c68a8-14a2-4c6e-b9e0-3e94e3e9135e
ms.openlocfilehash: be2f48f7d9c3be4ea0a5fe95436930b3f23c7551
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91170067"
---
# <a name="security-of-msmqintegrationbinding"></a><span data-ttu-id="08d94-102">\<security> dla \<msmqIntegrationBinding></span><span class="sxs-lookup"><span data-stu-id="08d94-102">\<security> of \<msmqIntegrationBinding></span></span>

<span data-ttu-id="08d94-103">Definiuje ustawienia zabezpieczeń transportu dla kanału integracji usługi kolejkowania komunikatów (MSMQ).</span><span class="sxs-lookup"><span data-stu-id="08d94-103">Defines the transport security settings for the Message Queuing (MSMQ) integration channel.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<msmqIntegrationBinding>**](msmqintegrationbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="08d94-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="08d94-104">Syntax</span></span>  
  
```xml  
<msmqIntegrationBinding>
  <binding>
    <security mode="None/Transport">
      <transport msmqAuthenticationMode="None/Windows/Certificate"
                 msmqEncryptionAlgorithm="RC4Stream/AES"
                 msmqProtectionLevel="None/Sign/EncryptAndSign"
                 msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
      <message algorithmSuite="Aes128/Aes192/Aes256/Rsa15Aes128/ Rsa15Aes256/TripleDes"
               clientCredentialType="None/Windows/UserName/Certificate/CardSpace"
               defaultProtectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</msmqIntegrationBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="08d94-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="08d94-105">Attributes and Elements</span></span>  

 <span data-ttu-id="08d94-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="08d94-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="08d94-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="08d94-107">Attributes</span></span>  
  
|<span data-ttu-id="08d94-108">Atrybut</span><span class="sxs-lookup"><span data-stu-id="08d94-108">Attribute</span></span>|<span data-ttu-id="08d94-109">Opis</span><span class="sxs-lookup"><span data-stu-id="08d94-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="08d94-110">tryb</span><span class="sxs-lookup"><span data-stu-id="08d94-110">mode</span></span>|<span data-ttu-id="08d94-111">Określa typ zabezpieczeń, który kontroluje integralność, poufność i uwierzytelnianie przy użyciu kanału integracji usługi kolejkowania komunikatów.</span><span class="sxs-lookup"><span data-stu-id="08d94-111">Specifies the type of security that controls integrity, confidentiality and authentication with the Message Queuing integration channel.</span></span> <span data-ttu-id="08d94-112">Prawidłowe wartości to:</span><span class="sxs-lookup"><span data-stu-id="08d94-112">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="08d94-113">-Brak: spowoduje to wyłączenie zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="08d94-113">-   None: This disables security.</span></span><br /><span data-ttu-id="08d94-114">-Transport: Ochrona i uwierzytelnianie są oferowane przez transport.</span><span class="sxs-lookup"><span data-stu-id="08d94-114">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="08d94-115">Ma to zastosowanie do zabezpieczeń komunikatów między dwoma menedżerami kolejki.</span><span class="sxs-lookup"><span data-stu-id="08d94-115">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="08d94-116">Nie ma żadnych zabezpieczeń oferowanych między aplikacją a menedżerem kolejki.</span><span class="sxs-lookup"><span data-stu-id="08d94-116">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="08d94-117">Istniejące aplikacje MSMQ są funkcjonalnie równoważne z tego typu trybem zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="08d94-117">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><br /> <span data-ttu-id="08d94-118">Wartość domyślna to `Transport`.</span><span class="sxs-lookup"><span data-stu-id="08d94-118">The default value is `Transport`.</span></span> <span data-ttu-id="08d94-119">Ten atrybut jest typu <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode> .</span><span class="sxs-lookup"><span data-stu-id="08d94-119">This attribute is of type <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="08d94-120">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="08d94-120">Child Elements</span></span>  
  
|<span data-ttu-id="08d94-121">Element</span><span class="sxs-lookup"><span data-stu-id="08d94-121">Element</span></span>|<span data-ttu-id="08d94-122">Opis</span><span class="sxs-lookup"><span data-stu-id="08d94-122">Description</span></span>|  
|-------------|-----------------|  
|[\<transport>](transport-of-msmqintegrationbinding.md)|<span data-ttu-id="08d94-123">Definiuje ustawienia zabezpieczeń dla transportu integracji usługi kolejkowania komunikatów.</span><span class="sxs-lookup"><span data-stu-id="08d94-123">Defines the security settings for the Message Queuing integration transport.</span></span> <span data-ttu-id="08d94-124">Ten element jest typu <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement> .</span><span class="sxs-lookup"><span data-stu-id="08d94-124">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="08d94-125">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="08d94-125">Parent Elements</span></span>  
  
|<span data-ttu-id="08d94-126">Element</span><span class="sxs-lookup"><span data-stu-id="08d94-126">Element</span></span>|<span data-ttu-id="08d94-127">Opis</span><span class="sxs-lookup"><span data-stu-id="08d94-127">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="08d94-128">Element Binding elementu [\<msmqIntegrationBinding>](msmqintegrationbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="08d94-128">The binding element of the [\<msmqIntegrationBinding>](msmqintegrationbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="08d94-129">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="08d94-129">See also</span></span>

- <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.MsmqIntegrationBindingElement.Security%2A>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>
- [<span data-ttu-id="08d94-130">Kolejki programu WCF</span><span class="sxs-lookup"><span data-stu-id="08d94-130">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="08d94-131">Zabezpieczanie usług i klientów</span><span class="sxs-lookup"><span data-stu-id="08d94-131">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="08d94-132">Powiązania</span><span class="sxs-lookup"><span data-stu-id="08d94-132">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="08d94-133">Konfigurowanie powiązań dostarczanych przez system</span><span class="sxs-lookup"><span data-stu-id="08d94-133">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="08d94-134">Konfigurowanie usług i klientów za pomocą wiązań</span><span class="sxs-lookup"><span data-stu-id="08d94-134">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
- [\<msmqIntegrationBinding>](msmqintegrationbinding.md)
