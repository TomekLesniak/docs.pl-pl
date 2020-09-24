---
title: <transport> dla <peerTransport>
ms.date: 03/30/2017
ms.assetid: d7116240-845c-4b6f-b203-262de6b597ef
ms.openlocfilehash: 7328d67c4649010dce3e1c866238d1e0067e4990
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91157073"
---
# <a name="transport-of-peertransport"></a><span data-ttu-id="b7e72-102">\<transport> dla \<peerTransport></span><span class="sxs-lookup"><span data-stu-id="b7e72-102">\<transport> of \<peerTransport></span></span>

<span data-ttu-id="b7e72-103">Określa typ transportu zabezpieczonych komunikatów wysyłanych przez elementy równorzędne skonfigurowane przy użyciu tego powiązania.</span><span class="sxs-lookup"><span data-stu-id="b7e72-103">Specifies the transport type for secured messages sent by peers configured with this binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peerTransport>**](peertransport.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-peertransport.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="b7e72-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="b7e72-104">Syntax</span></span>  
  
```xml  
<security>
  <transport credentialType="Certificate/Password" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b7e72-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="b7e72-105">Attributes and Elements</span></span>  

 <span data-ttu-id="b7e72-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="b7e72-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b7e72-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="b7e72-107">Attributes</span></span>  
  
|<span data-ttu-id="b7e72-108">Atrybut</span><span class="sxs-lookup"><span data-stu-id="b7e72-108">Attribute</span></span>|<span data-ttu-id="b7e72-109">Opis</span><span class="sxs-lookup"><span data-stu-id="b7e72-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b7e72-110">CredentialType</span><span class="sxs-lookup"><span data-stu-id="b7e72-110">credentialType</span></span>|<span data-ttu-id="b7e72-111">Opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="b7e72-111">Optional.</span></span> <span data-ttu-id="b7e72-112">Określa typ poświadczeń używanych do weryfikowania komunikatów wysyłanych z transportem równorzędnym.</span><span class="sxs-lookup"><span data-stu-id="b7e72-112">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="b7e72-113">Ten atrybut jest typu <xref:System.ServiceModel.PeerTransportCredentialType> .</span><span class="sxs-lookup"><span data-stu-id="b7e72-113">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="b7e72-114">CredentialType — atrybut</span><span class="sxs-lookup"><span data-stu-id="b7e72-114">credentialType Attribute</span></span>  
  
|<span data-ttu-id="b7e72-115">Wartość</span><span class="sxs-lookup"><span data-stu-id="b7e72-115">Value</span></span>|<span data-ttu-id="b7e72-116">Opis</span><span class="sxs-lookup"><span data-stu-id="b7e72-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b7e72-117">Certyfikat</span><span class="sxs-lookup"><span data-stu-id="b7e72-117">Certificate</span></span>|<span data-ttu-id="b7e72-118">Uwierzytelnianie w ramach transportu kanału równorzędnego wymaga certyfikatu x509.</span><span class="sxs-lookup"><span data-stu-id="b7e72-118">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="b7e72-119">Hasło</span><span class="sxs-lookup"><span data-stu-id="b7e72-119">Password</span></span>|<span data-ttu-id="b7e72-120">Uwierzytelnianie transportu kanału równorzędnego wymaga poprawnego hasła.</span><span class="sxs-lookup"><span data-stu-id="b7e72-120">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b7e72-121">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="b7e72-121">Child Elements</span></span>  

 <span data-ttu-id="b7e72-122">Brak</span><span class="sxs-lookup"><span data-stu-id="b7e72-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b7e72-123">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="b7e72-123">Parent Elements</span></span>  
  
|<span data-ttu-id="b7e72-124">Element</span><span class="sxs-lookup"><span data-stu-id="b7e72-124">Element</span></span>|<span data-ttu-id="b7e72-125">Opis</span><span class="sxs-lookup"><span data-stu-id="b7e72-125">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-peertransport.md)|<span data-ttu-id="b7e72-126">Definiuje ustawienia zabezpieczeń dla transportu równorzędnego.</span><span class="sxs-lookup"><span data-stu-id="b7e72-126">Defines the security settings for a peer transport.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b7e72-127">Uwagi</span><span class="sxs-lookup"><span data-stu-id="b7e72-127">Remarks</span></span>  

 <span data-ttu-id="b7e72-128">Ten element jest ustawiany tylko wtedy, gdy atrybut mode [\<security>](security-of-peertransport.md) jest ustawiony na `Transport` lub `TransportWithMessageCredential` .</span><span class="sxs-lookup"><span data-stu-id="b7e72-128">This element is set only if the mode attribute of [\<security>](security-of-peertransport.md) is set to `Transport` or `TransportWithMessageCredential`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7e72-129">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b7e72-129">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="b7e72-130">Zabezpieczenia transportu</span><span class="sxs-lookup"><span data-stu-id="b7e72-130">Transport Security</span></span>](../../../wcf/feature-details/transport-security.md)
- [<span data-ttu-id="b7e72-131">Transporty</span><span class="sxs-lookup"><span data-stu-id="b7e72-131">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="b7e72-132">Wybieranie transportu</span><span class="sxs-lookup"><span data-stu-id="b7e72-132">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="b7e72-133">Powiązania</span><span class="sxs-lookup"><span data-stu-id="b7e72-133">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="b7e72-134">Rozszerzanie powiązań</span><span class="sxs-lookup"><span data-stu-id="b7e72-134">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="b7e72-135">Powiązania niestandardowe</span><span class="sxs-lookup"><span data-stu-id="b7e72-135">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
