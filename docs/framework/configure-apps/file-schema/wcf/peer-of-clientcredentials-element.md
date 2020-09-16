---
title: <peer><clientCredentials>elementu
ms.date: 03/30/2017
ms.assetid: 505bd987-0042-4622-b68e-94f439729d53
ms.openlocfilehash: a8144ca7bad5654bf8f77259ea1717442665fc81
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555461"
---
# <a name="peer-of-clientcredentials-element"></a><span data-ttu-id="6de57-102">\<peer>\<clientCredentials>elementu</span><span class="sxs-lookup"><span data-stu-id="6de57-102">\<peer> of \<clientCredentials> Element</span></span>
<span data-ttu-id="6de57-103">Określa poświadczenia używane podczas uwierzytelniania klientów równorzędnych.</span><span class="sxs-lookup"><span data-stu-id="6de57-103">Specifies credentials used when authenticating peer-to-peer clients.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<peer>**  
  
## <a name="syntax"></a><span data-ttu-id="6de57-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="6de57-104">Syntax</span></span>  
  
```xml  
<peer>
  <certificate />
  <peerAuthentication />
  <messageSenderAuthentication />
</peer>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6de57-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="6de57-105">Attributes and Elements</span></span>  
 <span data-ttu-id="6de57-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="6de57-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6de57-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="6de57-107">Attributes</span></span>  
 <span data-ttu-id="6de57-108">Brak.</span><span class="sxs-lookup"><span data-stu-id="6de57-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6de57-109">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="6de57-109">Child Elements</span></span>  
  
|<span data-ttu-id="6de57-110">Element</span><span class="sxs-lookup"><span data-stu-id="6de57-110">Element</span></span>|<span data-ttu-id="6de57-111">Opis</span><span class="sxs-lookup"><span data-stu-id="6de57-111">Description</span></span>|  
|-------------|-----------------|  
|[\<certificate>](certificate-element.md)|<span data-ttu-id="6de57-112">Określa certyfikat X. 509 używany do podpisywania i szyfrowania komunikatów dla klientów równorzędnych.</span><span class="sxs-lookup"><span data-stu-id="6de57-112">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span> <span data-ttu-id="6de57-113">.</span><span class="sxs-lookup"><span data-stu-id="6de57-113">.</span></span>|  
|[\<peerAuthentication>](peerauthentication-element.md)|<span data-ttu-id="6de57-114">Określa opcje uwierzytelniania dla klientów równorzędnych.</span><span class="sxs-lookup"><span data-stu-id="6de57-114">Specifies authentication options for peer clients.</span></span>|  
|[\<messageSenderAuthentication>](messagesenderauthentication-element.md)|<span data-ttu-id="6de57-115">Określa opcje uwierzytelniania dla nadawców wiadomości.</span><span class="sxs-lookup"><span data-stu-id="6de57-115">Specifies authentication options for message senders.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6de57-116">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="6de57-116">Parent Elements</span></span>  
  
|<span data-ttu-id="6de57-117">Element</span><span class="sxs-lookup"><span data-stu-id="6de57-117">Element</span></span>|<span data-ttu-id="6de57-118">Opis</span><span class="sxs-lookup"><span data-stu-id="6de57-118">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|<span data-ttu-id="6de57-119">Określa poświadczenia używane do uwierzytelniania klienta w usłudze.</span><span class="sxs-lookup"><span data-stu-id="6de57-119">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6de57-120">Uwagi</span><span class="sxs-lookup"><span data-stu-id="6de57-120">Remarks</span></span>  
 <span data-ttu-id="6de57-121">Ten element konfiguracji określa poświadczenia używane przez węzeł równorzędny do samodzielnego uwierzytelnienia w innych węzłach w sieci, a także ustawień uwierzytelniania używanych przez węzeł równorzędny do uwierzytelniania innych węzłów równorzędnych.</span><span class="sxs-lookup"><span data-stu-id="6de57-121">This configuration element specifies the credentials that a peer node uses to authenticate itself to other nodes in the mesh, as well as authentication settings that a peer node uses to authenticate other peer nodes.</span></span> <span data-ttu-id="6de57-122">Aby uzyskać więcej informacji, zobacz [uwierzytelnianie komunikatów kanału równorzędnego](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90)) i [Zabezpieczanie aplikacji kanału równorzędnego](../../../wcf/feature-details/securing-peer-channel-applications.md).</span><span class="sxs-lookup"><span data-stu-id="6de57-122">For more information, see [Peer Channel Message Authentication](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90)) and [Securing Peer Channel Applications](../../../wcf/feature-details/securing-peer-channel-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6de57-123">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="6de57-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Peer%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.Peer%2A>
- <xref:System.ServiceModel.Security.PeerCredential>
- [<span data-ttu-id="6de57-124">Sieci równorzędne</span><span class="sxs-lookup"><span data-stu-id="6de57-124">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="6de57-125">[Zabezpieczanie klientów [WCF]](../../../wcf/securing-clients.md)</span><span class="sxs-lookup"><span data-stu-id="6de57-125">[Securing Clients](../../../wcf/securing-clients.md)</span></span>
- <span data-ttu-id="6de57-126">[Uwierzytelnianie komunikatów kanału równorzędnego](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="6de57-126">[Peer Channel Message Authentication](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="6de57-127">[Uwierzytelnianie niestandardowe kanału równorzędnego](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="6de57-127">[Peer Channel Custom Authentication](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="6de57-128">Zabezpieczanie aplikacji kanałów równorzędnych</span><span class="sxs-lookup"><span data-stu-id="6de57-128">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
- [<span data-ttu-id="6de57-129">Zabezpieczanie usług i klientów</span><span class="sxs-lookup"><span data-stu-id="6de57-129">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
