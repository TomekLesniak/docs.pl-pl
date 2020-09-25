---
title: <connectionPoolSettings>
ms.date: 03/30/2017
ms.assetid: 6fa7fa65-2c6e-4eab-b8cf-7690112c0be5
ms.openlocfilehash: d8787bc2ef8da4fdc01237ac9b041dfdd66fce03
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91175996"
---
# \<connectionPoolSettings>

<span data-ttu-id="3a8ad-101">Określa dodatkowe ustawienia puli połączeń dla powiązania nazwanego potoku.</span><span class="sxs-lookup"><span data-stu-id="3a8ad-101">Specifies additional connection pool settings for a Named Pipe binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedPipeTransport>**](namedpipetransport.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<connectionPoolSettings>**  
  
## <a name="syntax"></a><span data-ttu-id="3a8ad-102">Składnia</span><span class="sxs-lookup"><span data-stu-id="3a8ad-102">Syntax</span></span>  
  
```xml  
<connectionPoolSettings groupName="String"
                        idleTimeout="TimeSpan"
                        maxOutboundConnectionsPerEndpoint="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3a8ad-103">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="3a8ad-103">Attributes and Elements</span></span>  

 <span data-ttu-id="3a8ad-104">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="3a8ad-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3a8ad-105">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="3a8ad-105">Attributes</span></span>  
  
|<span data-ttu-id="3a8ad-106">Atrybut</span><span class="sxs-lookup"><span data-stu-id="3a8ad-106">Attribute</span></span>|<span data-ttu-id="3a8ad-107">Opis</span><span class="sxs-lookup"><span data-stu-id="3a8ad-107">Description</span></span>|  
|---------------|-----------------|  
|`groupName`|<span data-ttu-id="3a8ad-108">Ciąg określający nazwę puli połączeń używanej dla kanałów wychodzących.</span><span class="sxs-lookup"><span data-stu-id="3a8ad-108">A string that defines the name of the connection pool used for outgoing channels.</span></span> <span data-ttu-id="3a8ad-109">W trybie przesyłania strumieniowego połączenia nie są udostępniane, co oznacza, że buforowanie połączeń jest wyłączone.</span><span class="sxs-lookup"><span data-stu-id="3a8ad-109">In streamed mode, connections are not shared, meaning that connection pooling is disabled.</span></span> <span data-ttu-id="3a8ad-110">Wartość domyślna to ciąg "default".</span><span class="sxs-lookup"><span data-stu-id="3a8ad-110">The default is a "default" string.</span></span> <span data-ttu-id="3a8ad-111">Możesz zmodyfikować tę wartość, aby wyizolować połączenia dla określonego klienta w oddzielnych grupach.</span><span class="sxs-lookup"><span data-stu-id="3a8ad-111">You can modify this value to isolate the connections for a particular client into separate groups.</span></span>|  
|`idleTimeout`|<span data-ttu-id="3a8ad-112">Wartość dodatnia <xref:System.TimeSpan> , która określa maksymalny czas bezczynności połączenia przed jego rozłączeniem.</span><span class="sxs-lookup"><span data-stu-id="3a8ad-112">A positive <xref:System.TimeSpan> that specifies the maximum time the connection can be idle before being disconnected.</span></span> <span data-ttu-id="3a8ad-113">Wartość domyślna to 00:02:00.</span><span class="sxs-lookup"><span data-stu-id="3a8ad-113">The default is 00:02:00.</span></span>|  
|`maxOutboundConnectionsPerEndpoint`|<span data-ttu-id="3a8ad-114">Dodatnia liczba całkowita, która określa maksymalną liczbę połączeń ze zdalnym punktem końcowym inicjowanym przez usługę.</span><span class="sxs-lookup"><span data-stu-id="3a8ad-114">A positive integer that specifies the maximum number of connections to a remote endpoint initiated by the service.</span></span> <span data-ttu-id="3a8ad-115">Połączenia przekraczające limit są umieszczane w kolejce do momentu udostępnienia odstępu poniżej limitu.</span><span class="sxs-lookup"><span data-stu-id="3a8ad-115">Connections in excess of the limit are queued until a space below the limit becomes available.</span></span> <span data-ttu-id="3a8ad-116">`idleTimeout`Ogranicza czas, w którym połączenia pozostają w kolejce przed zgłoszeniem wyjątku.</span><span class="sxs-lookup"><span data-stu-id="3a8ad-116">The `idleTimeout` limits the duration in which connections remain queued before an exception is thrown.</span></span> <span data-ttu-id="3a8ad-117">Wartość domyślna to 10.</span><span class="sxs-lookup"><span data-stu-id="3a8ad-117">The default is 10.</span></span><br /><br /> <span data-ttu-id="3a8ad-118">Ten atrybut ogranicza liczbę jednoczesnych aktywnych połączeń z klienta do określonego punktu końcowego usługi.</span><span class="sxs-lookup"><span data-stu-id="3a8ad-118">This attribute limits the number of simultaneous active connections from the client to a particular service endpoint.</span></span> <span data-ttu-id="3a8ad-119">W przypadku przekroczenia tej wartości przy użyciu większej liczby aktywnych połączeń z klientem usługa może nie odpowiadać na klienta.</span><span class="sxs-lookup"><span data-stu-id="3a8ad-119">If this value is exceeded by having more active client connections, the service may appear unresponsive to the client.</span></span> <span data-ttu-id="3a8ad-120">W takim przypadku ta wartość powinna zostać zmieniona, aby przekroczyć maksymalną dozwoloną liczbę równoczesnych połączeń klienta do określonego punktu końcowego.</span><span class="sxs-lookup"><span data-stu-id="3a8ad-120">In this case, this value should be adjusted to exceed the maximum number of expected simultaneous client connections to a specific endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3a8ad-121">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="3a8ad-121">Child Elements</span></span>  

 <span data-ttu-id="3a8ad-122">Brak.</span><span class="sxs-lookup"><span data-stu-id="3a8ad-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3a8ad-123">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="3a8ad-123">Parent Elements</span></span>  
  
|<span data-ttu-id="3a8ad-124">Element</span><span class="sxs-lookup"><span data-stu-id="3a8ad-124">Element</span></span>|<span data-ttu-id="3a8ad-125">Opis</span><span class="sxs-lookup"><span data-stu-id="3a8ad-125">Description</span></span>|  
|-------------|-----------------|  
|[\<namedPipeTransport>](namedpipetransport.md)|<span data-ttu-id="3a8ad-126">Definiuje transport, który powoduje, że kanał przesyła komunikaty przy użyciu nazwanych potoków.</span><span class="sxs-lookup"><span data-stu-id="3a8ad-126">Defines a transport that causes a channel to transfer messages using named pipes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3a8ad-127">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="3a8ad-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.NamedPipeConnectionPoolSettingsElement>
- <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement.ConnectionPoolSettings%2A>
- <xref:System.ServiceModel.Channels.NamedPipeConnectionPoolSettings>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="3a8ad-128">Transporty</span><span class="sxs-lookup"><span data-stu-id="3a8ad-128">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="3a8ad-129">Wybieranie transportu</span><span class="sxs-lookup"><span data-stu-id="3a8ad-129">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="3a8ad-130">Powiązania</span><span class="sxs-lookup"><span data-stu-id="3a8ad-130">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="3a8ad-131">Rozszerzanie powiązań</span><span class="sxs-lookup"><span data-stu-id="3a8ad-131">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="3a8ad-132">Powiązania niestandardowe</span><span class="sxs-lookup"><span data-stu-id="3a8ad-132">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
