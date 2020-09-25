---
title: <connectionPoolSettings> dla <tcpTransport>
ms.date: 03/30/2017
ms.assetid: 2fbc3aa7-fcc9-4193-99a3-85d31d60d3f7
ms.openlocfilehash: 53523fd550ecad931bfb2af5eb9beb71c60d44f8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176009"
---
# <a name="connectionpoolsettings-of-tcptransport"></a><span data-ttu-id="e7bdf-102">\<connectionPoolSettings> dla \<tcpTransport></span><span class="sxs-lookup"><span data-stu-id="e7bdf-102">\<connectionPoolSettings> of \<tcpTransport></span></span>

<span data-ttu-id="e7bdf-103">Określa dodatkowe ustawienia puli połączeń dla transportu TCP.</span><span class="sxs-lookup"><span data-stu-id="e7bdf-103">Specifies additional connection pool settings for a TCP transport.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<tcpTransport>**](tcptransport.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<connectionPoolSettings>**  
  
## <a name="syntax"></a><span data-ttu-id="e7bdf-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="e7bdf-104">Syntax</span></span>  
  
```xml  
<connectionPoolSettings groupName="String"
                        idleTimeout="TimeSpan"
                        leaseTimeout="TimeSpan"
                        maxOutboundConnectionsPerEndpoint="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e7bdf-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="e7bdf-105">Attributes and Elements</span></span>  

 <span data-ttu-id="e7bdf-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="e7bdf-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e7bdf-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="e7bdf-107">Attributes</span></span>  
  
|<span data-ttu-id="e7bdf-108">Atrybut</span><span class="sxs-lookup"><span data-stu-id="e7bdf-108">Attribute</span></span>|<span data-ttu-id="e7bdf-109">Opis</span><span class="sxs-lookup"><span data-stu-id="e7bdf-109">Description</span></span>|  
|---------------|-----------------|  
|`groupName`|<span data-ttu-id="e7bdf-110">Ciąg określający nazwę puli połączeń używanej dla kanałów wychodzących.</span><span class="sxs-lookup"><span data-stu-id="e7bdf-110">A string that defines the name of the connection pool used for outgoing channels.</span></span> <span data-ttu-id="e7bdf-111">W trybie przesyłania strumieniowego połączenia nie są udostępniane, co oznacza, że buforowanie połączeń jest wyłączone.</span><span class="sxs-lookup"><span data-stu-id="e7bdf-111">In streamed mode, connections are not shared, meaning that connection pooling is disabled.</span></span> <span data-ttu-id="e7bdf-112">Wartość domyślna to ciąg "default".</span><span class="sxs-lookup"><span data-stu-id="e7bdf-112">The default is a "default" string.</span></span> <span data-ttu-id="e7bdf-113">Możesz zmodyfikować tę wartość, aby wyizolować połączenia dla określonego klienta w oddzielnych grupach.</span><span class="sxs-lookup"><span data-stu-id="e7bdf-113">You can modify this value to isolate the connections for a particular client into separate groups.</span></span>|  
|`idleTimeout`|<span data-ttu-id="e7bdf-114">Wartość dodatnia <xref:System.TimeSpan> , która określa maksymalny czas bezczynności połączenia przed jego rozłączeniem.</span><span class="sxs-lookup"><span data-stu-id="e7bdf-114">A positive <xref:System.TimeSpan> that specifies the maximum time the connection can be idle before being disconnected.</span></span> <span data-ttu-id="e7bdf-115">Wartość domyślna to 00:02:00.</span><span class="sxs-lookup"><span data-stu-id="e7bdf-115">The default is 00:02:00.</span></span>|  
|`leaseTimeout`|<span data-ttu-id="e7bdf-116">A <xref:System.TimeSpan> , który określa czas, po którym zamknięte jest aktywne połączenie.</span><span class="sxs-lookup"><span data-stu-id="e7bdf-116">A <xref:System.TimeSpan> that specifies the time after which an active connection is closed.</span></span> <span data-ttu-id="e7bdf-117">Wartość domyślna to 00:05:00.</span><span class="sxs-lookup"><span data-stu-id="e7bdf-117">The default is 00:05:00.</span></span><br /><br /> <span data-ttu-id="e7bdf-118">Połączenie jest zamykane, gdy zostało zwrócone do pamięci podręcznej połączenia, a nie podczas aktywnej transmisji.</span><span class="sxs-lookup"><span data-stu-id="e7bdf-118">A connection is closed after it has been returned to the connection cache and not during active transmission.</span></span> <span data-ttu-id="e7bdf-119">Pamięć podręczna połączeń używana przez transport TCP tworzy nowe połączenia zgodnie z wymaganiami dla każdego punktu końcowego, do limitu pamięci podręcznej, który jest ustawiony przez `maxOutboundConnectionsPerEndpoint.`</span><span class="sxs-lookup"><span data-stu-id="e7bdf-119">The connection cache used by the TCP transport creates new connections as required for each endpoint, up to the cache limit that is set by `maxOutboundConnectionsPerEndpoint.`</span></span>|  
|`maxOutboundConnectionsPerEndpoint`|<span data-ttu-id="e7bdf-120">Dodatnia liczba całkowita, która określa maksymalną liczbę połączeń ze zdalnym punktem końcowym inicjowanym przez usługę.</span><span class="sxs-lookup"><span data-stu-id="e7bdf-120">A positive integer that specifies the maximum number of connections to a remote endpoint initiated by the service.</span></span> <span data-ttu-id="e7bdf-121">Połączenia przekraczające limit są umieszczane w kolejce do momentu udostępnienia odstępu poniżej limitu.</span><span class="sxs-lookup"><span data-stu-id="e7bdf-121">Connections in excess of the limit are queued until a space below the limit becomes available.</span></span> <span data-ttu-id="e7bdf-122">`idleTimeout`Ogranicza czas, w którym połączenia pozostają w kolejce przed zgłoszeniem wyjątku.</span><span class="sxs-lookup"><span data-stu-id="e7bdf-122">The `idleTimeout` limits the duration in which connections remain queued before an exception is thrown.</span></span> <span data-ttu-id="e7bdf-123">Wartość domyślna to 10.</span><span class="sxs-lookup"><span data-stu-id="e7bdf-123">The default is 10.</span></span><br /><br /> <span data-ttu-id="e7bdf-124">Ten atrybut ogranicza liczbę jednoczesnych aktywnych połączeń z klienta do określonego punktu końcowego usługi.</span><span class="sxs-lookup"><span data-stu-id="e7bdf-124">This attribute limits the number of simultaneous active connections from the client to a particular service endpoint.</span></span> <span data-ttu-id="e7bdf-125">W przypadku przekroczenia tej wartości przy użyciu większej liczby aktywnych połączeń z klientem usługa może nie odpowiadać na klienta.</span><span class="sxs-lookup"><span data-stu-id="e7bdf-125">If this value is exceeded by having more active client connections, the service may appear unresponsive to the client.</span></span> <span data-ttu-id="e7bdf-126">W takim przypadku ta wartość powinna zostać zmieniona, aby przekroczyć maksymalną dozwoloną liczbę równoczesnych połączeń klienta do określonego punktu końcowego.</span><span class="sxs-lookup"><span data-stu-id="e7bdf-126">In this case, this value should be adjusted to exceed the maximum number of expected simultaneous client connections to a specific endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e7bdf-127">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="e7bdf-127">Child Elements</span></span>  

 <span data-ttu-id="e7bdf-128">Brak.</span><span class="sxs-lookup"><span data-stu-id="e7bdf-128">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e7bdf-129">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="e7bdf-129">Parent Elements</span></span>  
  
|<span data-ttu-id="e7bdf-130">Element</span><span class="sxs-lookup"><span data-stu-id="e7bdf-130">Element</span></span>|<span data-ttu-id="e7bdf-131">Opis</span><span class="sxs-lookup"><span data-stu-id="e7bdf-131">Description</span></span>|  
|-------------|-----------------|  
|[\<namedPipeTransport>](namedpipetransport.md)|<span data-ttu-id="e7bdf-132">Definiuje transport, który powoduje, że kanał przesyła komunikaty przy użyciu nazwanych potoków.</span><span class="sxs-lookup"><span data-stu-id="e7bdf-132">Defines a transport that causes a channel to transfer messages using named pipes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e7bdf-133">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="e7bdf-133">See also</span></span>

- <xref:System.ServiceModel.Configuration.TcpConnectionPoolSettingsElement>
- <xref:System.ServiceModel.Channels.TcpTransportBindingElement.ConnectionPoolSettings%2A>
- <xref:System.ServiceModel.Channels.TcpConnectionPoolSettings>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="e7bdf-134">Transporty</span><span class="sxs-lookup"><span data-stu-id="e7bdf-134">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="e7bdf-135">Wybieranie transportu</span><span class="sxs-lookup"><span data-stu-id="e7bdf-135">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="e7bdf-136">Powiązania</span><span class="sxs-lookup"><span data-stu-id="e7bdf-136">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="e7bdf-137">Rozszerzanie powiązań</span><span class="sxs-lookup"><span data-stu-id="e7bdf-137">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="e7bdf-138">Powiązania niestandardowe</span><span class="sxs-lookup"><span data-stu-id="e7bdf-138">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
