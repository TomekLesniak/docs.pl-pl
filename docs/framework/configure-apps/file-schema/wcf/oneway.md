---
title: <oneWay>
ms.date: 03/30/2017
ms.assetid: 00e67e0e-77c0-4695-9138-c0997b0e5f3c
ms.openlocfilehash: 92cd6b280305c223ee125a45724691c5205ce3c1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91195015"
---
# \<oneWay>

<span data-ttu-id="d0577-101">Umożliwia routing pakietów i stosowanie jednokierunkowych metod dla niestandardowego powiązania.</span><span class="sxs-lookup"><span data-stu-id="d0577-101">Enables packet routing and the use of one-way methods for a custom binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<oneWay>**  
  
## <a name="syntax"></a><span data-ttu-id="d0577-102">Składnia</span><span class="sxs-lookup"><span data-stu-id="d0577-102">Syntax</span></span>  
  
```xml  
<oneWay packetRoutable="Boolean">
  <channelPoolSettings idleTimeout="TimeSpan"
                       leaseTimeout="TimeSpan"
                       maxOutboundConnectionsPerEndpoint="Integer" />
</oneWay>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d0577-103">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="d0577-103">Attributes and Elements</span></span>  

 <span data-ttu-id="d0577-104">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="d0577-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d0577-105">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="d0577-105">Attributes</span></span>  
  
|<span data-ttu-id="d0577-106">Atrybut</span><span class="sxs-lookup"><span data-stu-id="d0577-106">Attribute</span></span>|<span data-ttu-id="d0577-107">Opis</span><span class="sxs-lookup"><span data-stu-id="d0577-107">Description</span></span>|  
|---------------|-----------------|  
|`packetRoutable`|<span data-ttu-id="d0577-108">Wartość logiczna określająca, czy jest włączona funkcja routingu pakietów.</span><span class="sxs-lookup"><span data-stu-id="d0577-108">A Boolean value that specifies whether packet routing is enabled.</span></span> <span data-ttu-id="d0577-109">Wartość domyślna to `false`.</span><span class="sxs-lookup"><span data-stu-id="d0577-109">The default is `false`.</span></span>|  
|`MaxAcceptedChannels`|<span data-ttu-id="d0577-110">Liczba całkowita określająca maksymalną liczbę kanałów, które mogą być akceptowane.</span><span class="sxs-lookup"><span data-stu-id="d0577-110">An integer that specifies the maximum number of channels that can be accepted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d0577-111">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="d0577-111">Child Elements</span></span>  
  
|<span data-ttu-id="d0577-112">Element</span><span class="sxs-lookup"><span data-stu-id="d0577-112">Element</span></span>|<span data-ttu-id="d0577-113">Opis</span><span class="sxs-lookup"><span data-stu-id="d0577-113">Description</span></span>|  
|-------------|-----------------|  
|[\<channelPoolSettings>](channelpoolsettings.md)|<span data-ttu-id="d0577-114"><xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement>Obiekt, który zawiera właściwości puli kanałów dla bieżącego kanału.</span><span class="sxs-lookup"><span data-stu-id="d0577-114">A <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> object that contains properties of the channel pool for the current channel.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d0577-115">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="d0577-115">Parent Elements</span></span>  
  
|<span data-ttu-id="d0577-116">Element</span><span class="sxs-lookup"><span data-stu-id="d0577-116">Element</span></span>|<span data-ttu-id="d0577-117">Opis</span><span class="sxs-lookup"><span data-stu-id="d0577-117">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="d0577-118">Definiuje wszystkie możliwości powiązań niestandardowego powiązania.</span><span class="sxs-lookup"><span data-stu-id="d0577-118">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d0577-119">Uwagi</span><span class="sxs-lookup"><span data-stu-id="d0577-119">Remarks</span></span>  

 <span data-ttu-id="d0577-120">Aby włączyć routing pakietów, wymagana jest jednokierunkowa warstwa konwersji, która zawiera ten element.</span><span class="sxs-lookup"><span data-stu-id="d0577-120">To enable packet routing, a one-way conversion layer is required, which this element provides.</span></span> <span data-ttu-id="d0577-121">Użytkownik może utworzyć niestandardowe powiązanie, które tworzy warstwy tego powiązania przez transport obsługujący sesję lub żądanie-odpowiedź, aby umożliwić jej Routing.</span><span class="sxs-lookup"><span data-stu-id="d0577-121">A user can create a custom binding that layers this binding over a session-aware or request-reply transport to make it packet routable.</span></span> <span data-ttu-id="d0577-122">Ten element jest również przydatny, gdy chcesz uwidocznić jednokierunkowe metody w bardziej natywny sposób.</span><span class="sxs-lookup"><span data-stu-id="d0577-122">This element is also useful when you want to expose one-way methods in a more native fashion.</span></span> <span data-ttu-id="d0577-123">Więcej przekształceń można zastosować do tej warstwy, na przykład złożonego dupleksu i niezawodnej obsługi komunikatów.</span><span class="sxs-lookup"><span data-stu-id="d0577-123">More transformations can be applied over this layer, such as Composite Duplex and Reliable Messaging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0577-124">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="d0577-124">See also</span></span>

- <xref:System.ServiceModel.Channels.OneWayBindingElement>
- <xref:System.ServiceModel.Configuration.OneWayElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="d0577-125">Powiązania</span><span class="sxs-lookup"><span data-stu-id="d0577-125">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="d0577-126">Rozszerzanie powiązań</span><span class="sxs-lookup"><span data-stu-id="d0577-126">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="d0577-127">Powiązania niestandardowe</span><span class="sxs-lookup"><span data-stu-id="d0577-127">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
