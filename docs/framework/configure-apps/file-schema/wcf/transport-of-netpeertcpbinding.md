---
title: <transport> dla <netPeerTcpBinding>
ms.date: 03/30/2017
ms.assetid: c44d86d2-1160-44d7-9c7a-297b12eccc7f
ms.openlocfilehash: 5df47b1bfc149b524fc9b90eacffa832817f653c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91172869"
---
# <a name="transport-of-netpeertcpbinding"></a><span data-ttu-id="7f5eb-102">\<transport> dla \<netPeerTcpBinding></span><span class="sxs-lookup"><span data-stu-id="7f5eb-102">\<transport> of \<netPeerTcpBinding></span></span>

<span data-ttu-id="7f5eb-103">Określa ustawienia zabezpieczeń na poziomie transportu podczas korzystania z [\<netPeerTcpBinding>](netpeertcpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="7f5eb-103">Specifies settings for transport level security when using the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netpeerbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="7f5eb-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="7f5eb-104">Syntax</span></span>  
  
```xml  
<netPeerTcpBinding>
  <binding>
    <security>
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerTcpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7f5eb-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="7f5eb-105">Attributes and Elements</span></span>  

 <span data-ttu-id="7f5eb-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="7f5eb-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7f5eb-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="7f5eb-107">Attributes</span></span>  
  
|<span data-ttu-id="7f5eb-108">Atrybut</span><span class="sxs-lookup"><span data-stu-id="7f5eb-108">Attribute</span></span>|<span data-ttu-id="7f5eb-109">Opis</span><span class="sxs-lookup"><span data-stu-id="7f5eb-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7f5eb-110">CredentialType</span><span class="sxs-lookup"><span data-stu-id="7f5eb-110">credentialType</span></span>|<span data-ttu-id="7f5eb-111">Opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="7f5eb-111">Optional.</span></span> <span data-ttu-id="7f5eb-112">Określa typ poświadczeń używanych do weryfikowania komunikatów wysyłanych z transportem równorzędnym.</span><span class="sxs-lookup"><span data-stu-id="7f5eb-112">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="7f5eb-113">Ten atrybut jest typu <xref:System.ServiceModel.PeerTransportCredentialType> .</span><span class="sxs-lookup"><span data-stu-id="7f5eb-113">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="7f5eb-114">CredentialType — atrybut</span><span class="sxs-lookup"><span data-stu-id="7f5eb-114">credentialType Attribute</span></span>  
  
|<span data-ttu-id="7f5eb-115">Wartość</span><span class="sxs-lookup"><span data-stu-id="7f5eb-115">Value</span></span>|<span data-ttu-id="7f5eb-116">Opis</span><span class="sxs-lookup"><span data-stu-id="7f5eb-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7f5eb-117">Certyfikat</span><span class="sxs-lookup"><span data-stu-id="7f5eb-117">Certificate</span></span>|<span data-ttu-id="7f5eb-118">Uwierzytelnianie w ramach transportu kanału równorzędnego wymaga certyfikatu x509.</span><span class="sxs-lookup"><span data-stu-id="7f5eb-118">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="7f5eb-119">Hasło</span><span class="sxs-lookup"><span data-stu-id="7f5eb-119">Password</span></span>|<span data-ttu-id="7f5eb-120">Uwierzytelnianie transportu kanału równorzędnego wymaga poprawnego hasła.</span><span class="sxs-lookup"><span data-stu-id="7f5eb-120">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7f5eb-121">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="7f5eb-121">Child Elements</span></span>  

 <span data-ttu-id="7f5eb-122">Brak</span><span class="sxs-lookup"><span data-stu-id="7f5eb-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7f5eb-123">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="7f5eb-123">Parent Elements</span></span>  
  
|<span data-ttu-id="7f5eb-124">Element</span><span class="sxs-lookup"><span data-stu-id="7f5eb-124">Element</span></span>|<span data-ttu-id="7f5eb-125">Opis</span><span class="sxs-lookup"><span data-stu-id="7f5eb-125">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-netpeerbinding.md)|<span data-ttu-id="7f5eb-126">Definiuje ustawienia zabezpieczeń dla [\<netPeerTcpBinding>](netpeertcpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="7f5eb-126">Defines the security settings for the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7f5eb-127">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="7f5eb-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.Configuration.PeerSecurityElement.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- [<span data-ttu-id="7f5eb-128">Zabezpieczanie usług i klientów</span><span class="sxs-lookup"><span data-stu-id="7f5eb-128">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="7f5eb-129">Powiązania</span><span class="sxs-lookup"><span data-stu-id="7f5eb-129">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="7f5eb-130">Konfigurowanie powiązań dostarczanych przez system</span><span class="sxs-lookup"><span data-stu-id="7f5eb-130">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="7f5eb-131">Konfigurowanie usług i klientów za pomocą wiązań</span><span class="sxs-lookup"><span data-stu-id="7f5eb-131">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
