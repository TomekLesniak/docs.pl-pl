---
title: <peer> dla <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: b134e21d-e5b5-458e-9309-626dbf8db4ed
ms.openlocfilehash: 7f6669d3f53a6ee0d189786fa9ca3625fdedd127
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91162481"
---
# <a name="peer-of-servicecredentials"></a><span data-ttu-id="401a6-102">\<peer> dla \<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="401a6-102">\<peer> of \<serviceCredentials></span></span>

<span data-ttu-id="401a6-103">Określa bieżące poświadczenia dla węzła równorzędnego.</span><span class="sxs-lookup"><span data-stu-id="401a6-103">Specifies the current credentials for a peer node.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<peer>**  
  
## <a name="syntax"></a><span data-ttu-id="401a6-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="401a6-104">Syntax</span></span>  
  
```xml  
<peer>
  <certificate />
  <peerAuthentication />
  <messageSenderAuthentication />
</peer>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="401a6-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="401a6-105">Attributes and Elements</span></span>  

 <span data-ttu-id="401a6-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="401a6-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="401a6-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="401a6-107">Attributes</span></span>  

 <span data-ttu-id="401a6-108">Brak.</span><span class="sxs-lookup"><span data-stu-id="401a6-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="401a6-109">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="401a6-109">Child Elements</span></span>  
  
|<span data-ttu-id="401a6-110">Element</span><span class="sxs-lookup"><span data-stu-id="401a6-110">Element</span></span>|<span data-ttu-id="401a6-111">Opis</span><span class="sxs-lookup"><span data-stu-id="401a6-111">Description</span></span>|  
|-------------|-----------------|  
|[\<certificate>](certificate-of-peer.md)|<span data-ttu-id="401a6-112">Określa certyfikat X. 509 używany do podpisywania i szyfrowania komunikatów dla usług peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="401a6-112">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer services.</span></span> <span data-ttu-id="401a6-113">.</span><span class="sxs-lookup"><span data-stu-id="401a6-113">.</span></span>|  
|[\<messageSenderAuthentication>](messagesenderauthentication.md)|<span data-ttu-id="401a6-114">Określa opcje uwierzytelniania dla nadawców wiadomości.</span><span class="sxs-lookup"><span data-stu-id="401a6-114">Specifies authentication options for message senders.</span></span>|  
|[\<peerAuthentication>](peerauthentication.md)|<span data-ttu-id="401a6-115">Określa opcje uwierzytelniania dla usług równorzędnych.</span><span class="sxs-lookup"><span data-stu-id="401a6-115">Specifies authentication options for peer services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="401a6-116">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="401a6-116">Parent Elements</span></span>  
  
|<span data-ttu-id="401a6-117">Element</span><span class="sxs-lookup"><span data-stu-id="401a6-117">Element</span></span>|<span data-ttu-id="401a6-118">Opis</span><span class="sxs-lookup"><span data-stu-id="401a6-118">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCredentials>](servicecredentials.md)|<span data-ttu-id="401a6-119">Określa poświadczenie, które ma być używane w uwierzytelnianiu usługi i ustawień związanych z walidacją poświadczeń klienta.</span><span class="sxs-lookup"><span data-stu-id="401a6-119">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="401a6-120">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="401a6-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.Peer%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.Peer%2A>
- <xref:System.ServiceModel.Security.PeerCredential>
- [<span data-ttu-id="401a6-121">Sieci równorzędne</span><span class="sxs-lookup"><span data-stu-id="401a6-121">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="401a6-122">[Uwierzytelnianie komunikatów kanału równorzędnego](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="401a6-122">[Peer Channel Message Authentication](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="401a6-123">[Uwierzytelnianie niestandardowe kanału równorzędnego](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="401a6-123">[Peer Channel Custom Authentication](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="401a6-124">Zabezpieczanie aplikacji kanałów równorzędnych</span><span class="sxs-lookup"><span data-stu-id="401a6-124">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
- [<span data-ttu-id="401a6-125">Zabezpieczanie usług i klientów</span><span class="sxs-lookup"><span data-stu-id="401a6-125">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
