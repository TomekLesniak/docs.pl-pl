---
title: <security> dla <peerTransport>
ms.date: 03/30/2017
ms.assetid: f73634ed-f896-4968-bf74-5e5ac52d3b6b
ms.openlocfilehash: f37c336b0e42993e1eef3f06e2f919705f425a2e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91169963"
---
# <a name="security-of-peertransport"></a><span data-ttu-id="13f69-102">\<security> dla \<peerTransport></span><span class="sxs-lookup"><span data-stu-id="13f69-102">\<security> of \<peerTransport></span></span>

<span data-ttu-id="13f69-103">Zawiera ustawienia zabezpieczeń skojarzone z kanałem równorzędnym, w tym typ używanego uwierzytelniania i zabezpieczenia używane do transportu wiadomości.</span><span class="sxs-lookup"><span data-stu-id="13f69-103">Contains the security settings associated with a peer channel, including the type of authentication used and the security used for the message transport.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peerTransport>**](peertransport.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="13f69-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="13f69-104">Syntax</span></span>  
  
```xml  
<security mode="None/Transport/Message/TransportWithMessageCredential">
  <transport clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />
</security
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="13f69-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="13f69-105">Attributes and Elements</span></span>  

 <span data-ttu-id="13f69-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="13f69-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="13f69-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="13f69-107">Attributes</span></span>  
  
|<span data-ttu-id="13f69-108">Atrybut</span><span class="sxs-lookup"><span data-stu-id="13f69-108">Attribute</span></span>|<span data-ttu-id="13f69-109">Opis</span><span class="sxs-lookup"><span data-stu-id="13f69-109">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="13f69-110">Określa typ zabezpieczenia do zastosowania.</span><span class="sxs-lookup"><span data-stu-id="13f69-110">Specifies the type of security to be applied.</span></span> <span data-ttu-id="13f69-111">Wartość domyślna to Message.</span><span class="sxs-lookup"><span data-stu-id="13f69-111">The default value is Message.</span></span> <span data-ttu-id="13f69-112">Ten atrybut jest typu <xref:System.ServiceModel.SecurityMode> .</span><span class="sxs-lookup"><span data-stu-id="13f69-112">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="13f69-113">Atrybut Mode</span><span class="sxs-lookup"><span data-stu-id="13f69-113">mode Attribute</span></span>  
  
|<span data-ttu-id="13f69-114">Wartość</span><span class="sxs-lookup"><span data-stu-id="13f69-114">Value</span></span>|<span data-ttu-id="13f69-115">Opis</span><span class="sxs-lookup"><span data-stu-id="13f69-115">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="13f69-116">Zabezpieczenia są wyłączone.</span><span class="sxs-lookup"><span data-stu-id="13f69-116">Security is disabled.</span></span>|  
|`Transport`|<span data-ttu-id="13f69-117">Zabezpieczenia są udostępniane przy użyciu protokołu HTTPS.</span><span class="sxs-lookup"><span data-stu-id="13f69-117">Security is provided using HTTPS.</span></span>|  
|`Message`|<span data-ttu-id="13f69-118">Zabezpieczenia protokołu SOAP zapewniają uwierzytelnianie, integralność i poufność.</span><span class="sxs-lookup"><span data-stu-id="13f69-118">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|`TransportWithMessageCredential`|<span data-ttu-id="13f69-119">Protokół HTTPS zapewnia uwierzytelnianie i poufność.</span><span class="sxs-lookup"><span data-stu-id="13f69-119">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="13f69-120">Komunikaty protokołu SOAP zapewniają zaawansowane typy poświadczeń.</span><span class="sxs-lookup"><span data-stu-id="13f69-120">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="13f69-121">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="13f69-121">Child Elements</span></span>  
  
|<span data-ttu-id="13f69-122">Element</span><span class="sxs-lookup"><span data-stu-id="13f69-122">Element</span></span>|<span data-ttu-id="13f69-123">Opis</span><span class="sxs-lookup"><span data-stu-id="13f69-123">Description</span></span>|  
|-------------|-----------------|  
|[\<transport>](transport-of-peertransport.md)|<span data-ttu-id="13f69-124">Definiuje transport równorzędny dla niestandardowego powiązania.</span><span class="sxs-lookup"><span data-stu-id="13f69-124">Defines a peer transport for a custom binding.</span></span> <span data-ttu-id="13f69-125">Ten element ma `clientCredentialType` atrybut, który określa poświadczenia, które mają być używane podczas korzystania z usługi.</span><span class="sxs-lookup"><span data-stu-id="13f69-125">This element has a `clientCredentialType` attribute that specifies the credentials to be used when interacting with a service.</span></span> <span data-ttu-id="13f69-126">Ten atrybut jest typu <xref:System.ServiceModel.PeerTransportCredentialType> .</span><span class="sxs-lookup"><span data-stu-id="13f69-126">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span><br /><br /> <span data-ttu-id="13f69-127">Ten element jest typu <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement> .</span><span class="sxs-lookup"><span data-stu-id="13f69-127">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="13f69-128">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="13f69-128">Parent Elements</span></span>  
  
|<span data-ttu-id="13f69-129">Element</span><span class="sxs-lookup"><span data-stu-id="13f69-129">Element</span></span>|<span data-ttu-id="13f69-130">Opis</span><span class="sxs-lookup"><span data-stu-id="13f69-130">Description</span></span>|  
|-------------|-----------------|  
|[\<peerTransport>](peertransport.md)|<span data-ttu-id="13f69-131">Definiuje transport równorzędny dla niestandardowego powiązania.</span><span class="sxs-lookup"><span data-stu-id="13f69-131">Defines a peer transport for a custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="13f69-132">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="13f69-132">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="13f69-133">Zabezpieczenia transportu</span><span class="sxs-lookup"><span data-stu-id="13f69-133">Transport Security</span></span>](../../../wcf/feature-details/transport-security.md)
- [<span data-ttu-id="13f69-134">Transporty</span><span class="sxs-lookup"><span data-stu-id="13f69-134">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="13f69-135">Wybieranie transportu</span><span class="sxs-lookup"><span data-stu-id="13f69-135">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="13f69-136">Powiązania</span><span class="sxs-lookup"><span data-stu-id="13f69-136">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="13f69-137">Rozszerzanie powiązań</span><span class="sxs-lookup"><span data-stu-id="13f69-137">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="13f69-138">Powiązania niestandardowe</span><span class="sxs-lookup"><span data-stu-id="13f69-138">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
