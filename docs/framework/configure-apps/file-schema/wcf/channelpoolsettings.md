---
title: <channelPoolSettings>
ms.date: 03/30/2017
ms.assetid: 4755f3d3-4213-4c68-ae7f-45b67d744459
ms.openlocfilehash: 8638d56ccb4aaa1c5ac735aa268823af2b1fbc6d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176074"
---
# \<channelPoolSettings>

<span data-ttu-id="2f3ad-101">Określa ustawienia puli kanałów dla niestandardowego powiązania.</span><span class="sxs-lookup"><span data-stu-id="2f3ad-101">Specifies the channel pool settings for a custom binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oneWay>**](oneway.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<channelPoolSettings>**  
  
## <a name="syntax"></a><span data-ttu-id="2f3ad-102">Składnia</span><span class="sxs-lookup"><span data-stu-id="2f3ad-102">Syntax</span></span>  
  
```xml  
<channelPoolSettings idleTimeout="TimeSpan"
                     leaseTimeout="TimeSpan"
                     maxOutboundConnectionsPerEndpoint="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2f3ad-103">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="2f3ad-103">Attributes and Elements</span></span>  

 <span data-ttu-id="2f3ad-104">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="2f3ad-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2f3ad-105">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="2f3ad-105">Attributes</span></span>  
  
|<span data-ttu-id="2f3ad-106">Atrybut</span><span class="sxs-lookup"><span data-stu-id="2f3ad-106">Attribute</span></span>|<span data-ttu-id="2f3ad-107">Opis</span><span class="sxs-lookup"><span data-stu-id="2f3ad-107">Description</span></span>|  
|---------------|-----------------|  
|`idleTimeout`|<span data-ttu-id="2f3ad-108">Wartość dodatnia <xref:System.TimeSpan> , która określa maksymalny czas bezczynności kanałów w puli przed rozłączeniem.</span><span class="sxs-lookup"><span data-stu-id="2f3ad-108">A positive <xref:System.TimeSpan> that specifies the maximum time the channels in the pool can be idle before being disconnected.</span></span> <span data-ttu-id="2f3ad-109">Wartość domyślna to 00:02:00.</span><span class="sxs-lookup"><span data-stu-id="2f3ad-109">The default is 00:02:00.</span></span>|  
|`leaseTimeout`|<span data-ttu-id="2f3ad-110">A <xref:System.TimeSpan> , który określa przedział czasu, po którym kanał, gdy jest zwracany do puli, jest zamknięty.</span><span class="sxs-lookup"><span data-stu-id="2f3ad-110">A <xref:System.TimeSpan> that specifies the interval of time after which a channel, when returned to the pool, is closed.</span></span> <span data-ttu-id="2f3ad-111">Wartość domyślna to 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="2f3ad-111">The default is 00:10:00.</span></span>|  
|`maxOutboundChannelsPerEndpoint`|<span data-ttu-id="2f3ad-112">Dodatnia liczba całkowita, która określa maksymalną liczbę kanałów, które mogą być przechowywane w puli dla każdego zdalnego punktu końcowego.</span><span class="sxs-lookup"><span data-stu-id="2f3ad-112">A positive integer that specifies the maximum number of channels that can be stored in the pool for each remote endpoint.</span></span> <span data-ttu-id="2f3ad-113">Wartość domyślna to 10.</span><span class="sxs-lookup"><span data-stu-id="2f3ad-113">The default is 10.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2f3ad-114">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="2f3ad-114">Child Elements</span></span>  

 <span data-ttu-id="2f3ad-115">Brak.</span><span class="sxs-lookup"><span data-stu-id="2f3ad-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2f3ad-116">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="2f3ad-116">Parent Elements</span></span>  
  
|<span data-ttu-id="2f3ad-117">Element</span><span class="sxs-lookup"><span data-stu-id="2f3ad-117">Element</span></span>|<span data-ttu-id="2f3ad-118">Opis</span><span class="sxs-lookup"><span data-stu-id="2f3ad-118">Description</span></span>|  
|-------------|-----------------|  
|[\<oneWay>](oneway.md)|<span data-ttu-id="2f3ad-119">Włącza routing pakietów dla niestandardowego powiązania.</span><span class="sxs-lookup"><span data-stu-id="2f3ad-119">Enables packet routing for a custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2f3ad-120">Uwagi</span><span class="sxs-lookup"><span data-stu-id="2f3ad-120">Remarks</span></span>  

 <span data-ttu-id="2f3ad-121">Przydziały są używane jako mechanizm zasad, aby zapobiec zużyciu nadmiernych zasobów.</span><span class="sxs-lookup"><span data-stu-id="2f3ad-121">Quotas are used as a policy mechanism to prevent the consumption of excessive resources.</span></span> <span data-ttu-id="2f3ad-122">Uniemożliwiają one ataki typu "odmowa usługi" (DOS), które są złośliwe lub niezamierzone.</span><span class="sxs-lookup"><span data-stu-id="2f3ad-122">They prevent Denial of Service (DOS) attacks that are either malicious or unintentional.</span></span> <span data-ttu-id="2f3ad-123">Użyj tego elementu, gdy ustawiasz limity przydziału kanałów w niestandardowym kanale.</span><span class="sxs-lookup"><span data-stu-id="2f3ad-123">Use this element when setting channel quotas on a custom channel.</span></span>  
  
 <span data-ttu-id="2f3ad-124">`ChannelPoolSettings` określa trzy przydziały:</span><span class="sxs-lookup"><span data-stu-id="2f3ad-124">`ChannelPoolSettings` specifies three quotas:</span></span>  
  
- <span data-ttu-id="2f3ad-125">`idleTimeout`Przydział służy do zapobiegania atakom typu "odmowa usługi" (DOS) na serwerze, który polega na rozdzieleniu zasobów przez dłuższy czas.</span><span class="sxs-lookup"><span data-stu-id="2f3ad-125">The `idleTimeout` quota is used to mitigate Denial of Service (DOS) attacks on the server that rely on tying up resources for an extended period of time.</span></span> <span data-ttu-id="2f3ad-126">Ustawienie poprawnej wartości na kliencie może zwiększyć niezawodność połączenia z usługą.</span><span class="sxs-lookup"><span data-stu-id="2f3ad-126">On the client, setting the correct value can increase the reliability of connecting with the service.</span></span> <span data-ttu-id="2f3ad-127">Wartość domyślna jest oparta na nieumiarkowanie niedostatecznej alokacji zasobów.</span><span class="sxs-lookup"><span data-stu-id="2f3ad-127">The default value is based on a conservatively modest allocation of resources.</span></span> <span data-ttu-id="2f3ad-128">Jest to odpowiednie dla środowiska programistycznego i małych scenariuszy instalacji.</span><span class="sxs-lookup"><span data-stu-id="2f3ad-128">It is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="2f3ad-129">Administratorzy usługi powinni sprawdzić wartość w przypadku braku zasobów w ramach instalacji lub w przypadku ograniczonej liczby połączeń poza dostępnością dodatkowych zasobów.</span><span class="sxs-lookup"><span data-stu-id="2f3ad-129">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
- <span data-ttu-id="2f3ad-130">`leaseTimeout`Przydział służy do integracji z usługami równoważenia obciążenia i zwiększania niezawodności.</span><span class="sxs-lookup"><span data-stu-id="2f3ad-130">The `leaseTimeout` quota is used to for integration with load balancers and for improving reliability.</span></span> <span data-ttu-id="2f3ad-131">Wartość domyślna jest określana na podstawie ostrożnej alokacji zasobów.</span><span class="sxs-lookup"><span data-stu-id="2f3ad-131">The default value is based on a conservative allocation of resources.</span></span> <span data-ttu-id="2f3ad-132">Jest to odpowiednie dla środowiska programistycznego i małych scenariuszy instalacji.</span><span class="sxs-lookup"><span data-stu-id="2f3ad-132">It is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="2f3ad-133">Administratorzy usługi powinni sprawdzić wartość w przypadku braku zasobów w ramach instalacji lub w przypadku ograniczonej liczby połączeń poza dostępnością dodatkowych zasobów.</span><span class="sxs-lookup"><span data-stu-id="2f3ad-133">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
- <span data-ttu-id="2f3ad-134">`maxOutboundChannelsPerEndpoint`Limity przydziału są ustawiane w pamięci podręcznej zarówno na serwerze, jak i na kliencie i są używane w celu zwiększenia niezawodności.</span><span class="sxs-lookup"><span data-stu-id="2f3ad-134">The `maxOutboundChannelsPerEndpoint` quota sets cache limits on both the server and the client and is used to improve reliability.</span></span> <span data-ttu-id="2f3ad-135">Wartość domyślna jest oparta na niewielkiej ilości alokacji zasobów, która jest odpowiednia dla środowiska programistycznego i małych scenariuszy instalacji.</span><span class="sxs-lookup"><span data-stu-id="2f3ad-135">The default value is based on a conservatively modest allocation of resources that is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="2f3ad-136">Administratorzy usługi powinni sprawdzić wartość w przypadku braku zasobów w ramach instalacji lub w przypadku ograniczonej liczby połączeń poza dostępnością dodatkowych zasobów.</span><span class="sxs-lookup"><span data-stu-id="2f3ad-136">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f3ad-137">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="2f3ad-137">See also</span></span>

- <xref:System.ServiceModel.Channels.OneWayBindingElement.ChannelPoolSettings%2A>
- <xref:System.ServiceModel.Channels.ChannelPoolSettings>
- <xref:System.ServiceModel.Configuration.OneWayElement.ChannelPoolSettings%2A>
- <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [\<oneWay>](oneway.md)
- [<span data-ttu-id="2f3ad-138">Powiązania</span><span class="sxs-lookup"><span data-stu-id="2f3ad-138">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="2f3ad-139">Rozszerzanie powiązań</span><span class="sxs-lookup"><span data-stu-id="2f3ad-139">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="2f3ad-140">Powiązania niestandardowe</span><span class="sxs-lookup"><span data-stu-id="2f3ad-140">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
