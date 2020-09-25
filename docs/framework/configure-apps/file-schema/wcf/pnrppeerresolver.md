---
title: <pnrpPeerResolver>
ms.date: 03/30/2017
ms.assetid: c1b34f3b-68e5-4911-a367-de49fb61dbc6
ms.openlocfilehash: 0a8cc60226b13552d47faec3a156ed1f59acacb9
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91181404"
---
# \<pnrpPeerResolver>

<span data-ttu-id="e7649-101">Określa, że program rozpoznawania nazw PNRP (Peer Name Resolution Protocol) ma być używany jako program rozpoznawania nazw.</span><span class="sxs-lookup"><span data-stu-id="e7649-101">Specifies that the PNRP (Peer Name Resolution Protocol) resolver is to be used as a resolver.</span></span> <span data-ttu-id="e7649-102">Ten element jest opcjonalny, ponieważ protokół PNRP jest domyślnym programem rozpoznawania nazw.</span><span class="sxs-lookup"><span data-stu-id="e7649-102">This element is optional because PNRP is the default resolver.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<pnrpResolver>**  
  
## <a name="syntax"></a><span data-ttu-id="e7649-103">Składnia</span><span class="sxs-lookup"><span data-stu-id="e7649-103">Syntax</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e7649-104">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="e7649-104">Attributes and Elements</span></span>  

 <span data-ttu-id="e7649-105">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="e7649-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e7649-106">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="e7649-106">Attributes</span></span>  
  
|<span data-ttu-id="e7649-107">Atrybut</span><span class="sxs-lookup"><span data-stu-id="e7649-107">Attribute</span></span>|<span data-ttu-id="e7649-108">Opis</span><span class="sxs-lookup"><span data-stu-id="e7649-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e7649-109">program rozpoznawania nazw</span><span class="sxs-lookup"><span data-stu-id="e7649-109">resolverType</span></span>|<span data-ttu-id="e7649-110">Ciąg określający, który mechanizm rozwiązywania konfliktów ma być używany.</span><span class="sxs-lookup"><span data-stu-id="e7649-110">A string that specifies the resolver to be used.</span></span> <span data-ttu-id="e7649-111">Ten atrybut jest opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="e7649-111">This attribute is optional.</span></span> <span data-ttu-id="e7649-112">Jeśli nie jest ustawiona, lub jeśli jest ustawiona na pusty ciąg, używany jest protokół PNRP.</span><span class="sxs-lookup"><span data-stu-id="e7649-112">If it is not set, or if it is set to an empty string, PNRP is used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e7649-113">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="e7649-113">Child Elements</span></span>  

 <span data-ttu-id="e7649-114">Brak</span><span class="sxs-lookup"><span data-stu-id="e7649-114">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e7649-115">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="e7649-115">Parent Elements</span></span>  
  
|<span data-ttu-id="e7649-116">Element</span><span class="sxs-lookup"><span data-stu-id="e7649-116">Element</span></span>|<span data-ttu-id="e7649-117">Opis</span><span class="sxs-lookup"><span data-stu-id="e7649-117">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="e7649-118">Definiuje wszystkie możliwości powiązań niestandardowego powiązania.</span><span class="sxs-lookup"><span data-stu-id="e7649-118">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e7649-119">Przykład</span><span class="sxs-lookup"><span data-stu-id="e7649-119">Example</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="see-also"></a><span data-ttu-id="e7649-120">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="e7649-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>
- <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="e7649-121">Powiązania</span><span class="sxs-lookup"><span data-stu-id="e7649-121">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="e7649-122">Rozszerzanie powiązań</span><span class="sxs-lookup"><span data-stu-id="e7649-122">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="e7649-123">Powiązania niestandardowe</span><span class="sxs-lookup"><span data-stu-id="e7649-123">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [<span data-ttu-id="e7649-124">Mechanizmy rozpoznawania elementów równorzędnych</span><span class="sxs-lookup"><span data-stu-id="e7649-124">Peer Resolvers</span></span>](../../../wcf/feature-details/peer-resolvers.md)
