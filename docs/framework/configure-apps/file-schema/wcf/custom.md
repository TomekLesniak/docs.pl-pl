---
title: <custom>
ms.date: 03/30/2017
ms.assetid: a6f65a00-bd1a-4d4a-955a-fe009ec02ab8
ms.openlocfilehash: 4077aacab1c1c4594db76cc6663bfc0245d345d7
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555500"
---
# \<custom>
<span data-ttu-id="a62ae-101">Określa ustawienia niestandardowej usługi rozpoznawania elementów równorzędnych.</span><span class="sxs-lookup"><span data-stu-id="a62ae-101">Specifies settings for a custom peer resolver service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<resolver>**](resolver.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<custom>**  
  
## <a name="syntax"></a><span data-ttu-id="a62ae-102">Składnia</span><span class="sxs-lookup"><span data-stu-id="a62ae-102">Syntax</span></span>  
  
```xml  
<custom address="Uri"
        resolverType="String">
  <headers/>
  <identity/>
</custom>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a62ae-103">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="a62ae-103">Attributes and Elements</span></span>  
 <span data-ttu-id="a62ae-104">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="a62ae-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a62ae-105">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="a62ae-105">Attributes</span></span>  
  
|<span data-ttu-id="a62ae-106">Atrybut</span><span class="sxs-lookup"><span data-stu-id="a62ae-106">Attribute</span></span>|<span data-ttu-id="a62ae-107">Opis</span><span class="sxs-lookup"><span data-stu-id="a62ae-107">Description</span></span>|  
|---------------|-----------------|  
|`address`|<span data-ttu-id="a62ae-108">Identyfikator URI, który określa adres punktu końcowego węzła równorzędnego, który hostuje niestandardową usługę rozpoznawania elementów równorzędnych.</span><span class="sxs-lookup"><span data-stu-id="a62ae-108">A URI that specifies the endpoint address of the peer node that hosts the custom peer resolver service.</span></span>|  
|`resolverType`|<span data-ttu-id="a62ae-109">Ciąg określający typ niestandardowej usługi rozpoznawania elementów równorzędnych.</span><span class="sxs-lookup"><span data-stu-id="a62ae-109">A string that specifies the type of the custom peer resolver service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a62ae-110">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="a62ae-110">Child Elements</span></span>  
  
|<span data-ttu-id="a62ae-111">Element</span><span class="sxs-lookup"><span data-stu-id="a62ae-111">Element</span></span>|<span data-ttu-id="a62ae-112">Opis</span><span class="sxs-lookup"><span data-stu-id="a62ae-112">Description</span></span>|  
|-------------|-----------------|  
|[\<identity>](identity.md)|<span data-ttu-id="a62ae-113">Określa tożsamość niestandardowych resolverów równorzędnych skonfigurowanych przy użyciu tego elementu.</span><span class="sxs-lookup"><span data-stu-id="a62ae-113">Specifies the identity for custom peer resolvers configured with this element.</span></span> <span data-ttu-id="a62ae-114">Ten element jest typu <xref:System.ServiceModel.Configuration.IdentityElement> .</span><span class="sxs-lookup"><span data-stu-id="a62ae-114">This element is of type <xref:System.ServiceModel.Configuration.IdentityElement>.</span></span>|  
|[\<headers>](headers-element.md)|<span data-ttu-id="a62ae-115">Kolekcja nagłówka adresu używana dla komunikatów SOAP obsłużonych przez niestandardowy program rozpoznawania elementów równorzędnych.</span><span class="sxs-lookup"><span data-stu-id="a62ae-115">A collection of address header used for SOAP messages handled by the custom peer resolver.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a62ae-116">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="a62ae-116">Parent Elements</span></span>  
  
|<span data-ttu-id="a62ae-117">Element</span><span class="sxs-lookup"><span data-stu-id="a62ae-117">Element</span></span>|<span data-ttu-id="a62ae-118">Opis</span><span class="sxs-lookup"><span data-stu-id="a62ae-118">Description</span></span>|  
|-------------|-----------------|  
|[\<resolver>](resolver.md)|<span data-ttu-id="a62ae-119">Równorzędny program rozpoznawania używany do rozpoznawania identyfikatora siatki równorzędnej w zestawie adresów węzłów równorzędnych reprezentujących kilka węzłów, które uczestniczą w sieci.</span><span class="sxs-lookup"><span data-stu-id="a62ae-119">A peer resolver that is used to resolve a peer mesh ID to a set of peer node addresses that represents several nodes that participate in the mesh.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a62ae-120">Uwagi</span><span class="sxs-lookup"><span data-stu-id="a62ae-120">Remarks</span></span>  
 <span data-ttu-id="a62ae-121">Ten element definiuje podstawowe ustawienia dla niestandardowej usługi rozpoznawania elementów równorzędnych, w tym adres punktu końcowego elementu równorzędnego obsługującego usługę i wszystkie określone ustawienia powiązań.</span><span class="sxs-lookup"><span data-stu-id="a62ae-121">This element defines the basic settings for a custom peer resolver service, including the endpoint address of the peer hosting the service and any specific binding settings.</span></span> <span data-ttu-id="a62ae-122">Aby uzyskać więcej informacji na temat tworzenia niestandardowego programu rozpoznawania nazw, zobacz [Dodawanie niestandardowego programu rozpoznawania nazw do aplikacji PeerChannel](/previous-versions/ms730105(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="a62ae-122">For more information on creating a custom resolver, see [Adding a Custom Resolver to a PeerChannel Application](/previous-versions/ms730105(v=vs.90)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a62ae-123">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="a62ae-123">See also</span></span>

- <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService>
- <xref:System.ServiceModel.PeerResolvers.PeerCustomResolverSettings>
- <xref:System.ServiceModel.Configuration.PeerResolverElement.Custom%2A>
- <xref:System.ServiceModel.Configuration.PeerCustomResolverElement>
- [<span data-ttu-id="a62ae-124">Mechanizmy rozpoznawania elementów równorzędnych</span><span class="sxs-lookup"><span data-stu-id="a62ae-124">Peer Resolvers</span></span>](../../../wcf/feature-details/peer-resolvers.md)
- <span data-ttu-id="a62ae-125">[Dodawanie niestandardowego programu rozpoznawania nazw do aplikacji PeerChannel](/previous-versions/ms730105(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="a62ae-125">[Adding a Custom Resolver to a PeerChannel Application](/previous-versions/ms730105(v=vs.90))</span></span>
