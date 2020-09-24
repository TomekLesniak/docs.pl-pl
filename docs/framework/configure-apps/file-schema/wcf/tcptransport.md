---
title: <tcpTransport>
ms.date: 03/30/2017
ms.assetid: 8fcd18c1-9958-42e7-b442-7903f7bdb563
ms.openlocfilehash: 6d4302e1840f58e2daad855942493cc96b7d5e34
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158672"
---
# \<tcpTransport>

<span data-ttu-id="8f854-101">Definiuje transport TCP, który może być używany przez kanał do przesyłania komunikatów dla niestandardowego powiązania.</span><span class="sxs-lookup"><span data-stu-id="8f854-101">Defines a TCP transport that can be used by a channel to transfers messages for a custom binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<tcpTransport>**  
  
## <a name="syntax"></a><span data-ttu-id="8f854-102">Składnia</span><span class="sxs-lookup"><span data-stu-id="8f854-102">Syntax</span></span>  
  
```xml  
<tcpTransport channelInitializationTimeout="TimeSpan"
              connectionBufferSize="Integer"
              hostNameComparisonMode="StrongWildcard/Exact/WeakWildcard"
              listenBacklog="Integer"
              manualAddressing="Boolean"
              maxBufferPoolSize="Integer"
              maxBufferSize="Integer"
              maxOutputDelay="TimeSpan"
              maxPendingAccepts="Integer"
              maxPendingConnections="Integer"
              maxReceivedMessageSize="Integer"
              portSharingEnabled="Boolean"
              teredoEnabled="Boolean"
              transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse" >
  <connectionPoolSettings groupName="String"
                          idleTimeout="TimeSpan"
                          leaseTimeout="TimeSpan"
                          maxOutboundConnectionsPerEndpoint="Integer" />
</tcpTransport>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8f854-103">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="8f854-103">Attributes and Elements</span></span>  

 <span data-ttu-id="8f854-104">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="8f854-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8f854-105">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="8f854-105">Attributes</span></span>  
  
|<span data-ttu-id="8f854-106">Atrybut</span><span class="sxs-lookup"><span data-stu-id="8f854-106">Attribute</span></span>|<span data-ttu-id="8f854-107">Opis</span><span class="sxs-lookup"><span data-stu-id="8f854-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8f854-108">channelInitializationTimeout</span><span class="sxs-lookup"><span data-stu-id="8f854-108">channelInitializationTimeout</span></span>|<span data-ttu-id="8f854-109">Pobiera lub ustawia limit czasu inicjowania kanału, który ma zostać zaakceptowany.</span><span class="sxs-lookup"><span data-stu-id="8f854-109">Gets or sets the time limit for initializing a channel to be accepted.</span></span>  <span data-ttu-id="8f854-110">Maksymalny czas, w którym kanał może być w stanie inicjowania przed rozłączeniem w sekundach.</span><span class="sxs-lookup"><span data-stu-id="8f854-110">The maximum time a channel can be in the initialization state before being disconnected in seconds.</span></span> <span data-ttu-id="8f854-111">Ten limit przydziału obejmuje czas, przez jaki połączenie TCP może być wykonywane w celu samodzielnego uwierzytelnienia przy użyciu protokołu ramki komunikatów .NET.</span><span class="sxs-lookup"><span data-stu-id="8f854-111">This quota includes the time a TCP connection can take to authenticate itself using the .NET Message Framing protocol.</span></span> <span data-ttu-id="8f854-112">Klient musi wysłać pewne dane początkowe, zanim serwer będzie miał wystarczającą ilość informacji do przeprowadzenia uwierzytelniania.</span><span class="sxs-lookup"><span data-stu-id="8f854-112">A client needs to send some initial data before the server has enough information to perform authentication.</span></span> <span data-ttu-id="8f854-113">Wartość domyślna to 30 sekund.</span><span class="sxs-lookup"><span data-stu-id="8f854-113">The default is 30 seconds.</span></span>|  
|<span data-ttu-id="8f854-114">connectionBufferSize</span><span class="sxs-lookup"><span data-stu-id="8f854-114">connectionBufferSize</span></span>|<span data-ttu-id="8f854-115">Pobiera lub ustawia rozmiar buforu używany do przesyłania fragmentu serializowanego komunikatu w locie z klienta lub usługi.</span><span class="sxs-lookup"><span data-stu-id="8f854-115">Gets or sets the size of the buffer used to transmit a chunk of the serialized message on the wire from the client or service.</span></span>|  
|<span data-ttu-id="8f854-116">hostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="8f854-116">hostNameComparisonMode</span></span>|<span data-ttu-id="8f854-117">Pobiera lub ustawia wartość wskazującą, czy nazwa hosta jest używana do uzyskiwania dostępu do usługi podczas dopasowywania identyfikatora URI.</span><span class="sxs-lookup"><span data-stu-id="8f854-117">Gets or sets a value that indicates whether the hostname is used to reach the service when matching on the URI.</span></span>|  
|<span data-ttu-id="8f854-118">listenBacklog</span><span class="sxs-lookup"><span data-stu-id="8f854-118">listenBacklog</span></span>|<span data-ttu-id="8f854-119">Maksymalna liczba żądań połączeń umieszczonych w kolejce, które mogą być oczekujące dla usługi sieci Web.</span><span class="sxs-lookup"><span data-stu-id="8f854-119">The maximum number of queued connection requests that can be pending for a Web service.</span></span> <span data-ttu-id="8f854-120">Ten `connectionLeaseTimeout` atrybut ogranicza czas, przez jaki klient będzie oczekiwał na połączenie przed wygenerowaniem wyjątku połączenia.</span><span class="sxs-lookup"><span data-stu-id="8f854-120">The `connectionLeaseTimeout` attribute limits the duration the client will wait to be connected before throwing a connection exception.</span></span> <span data-ttu-id="8f854-121">Jest to właściwość poziomu gniazda, która kontroluje maksymalną liczbę oczekujących żądań połączeń w usłudze sieci Web.</span><span class="sxs-lookup"><span data-stu-id="8f854-121">This is a socket level property which controls the maximum number of queued connection requests that can be pending for a Web service.</span></span> <span data-ttu-id="8f854-122">Gdy ListenBacklog jest zbyt niska, usługa WCF nie akceptuje żądań i w związku z tym porzuca nowe połączenia, dopóki serwer nie potwierdzi niektórych istniejących połączeń umieszczonych w kolejce.</span><span class="sxs-lookup"><span data-stu-id="8f854-122">When ListenBacklog is too low, WCF will stop accepting requests and therefore drop new connections until the server acknowledges some of the existing queued connections.</span></span> <span data-ttu-id="8f854-123">Wartość domyślna to 16 \* liczba procesorów.</span><span class="sxs-lookup"><span data-stu-id="8f854-123">The default is 16 \* number of processors.</span></span>|  
|<span data-ttu-id="8f854-124">Opcję ManualAddressing</span><span class="sxs-lookup"><span data-stu-id="8f854-124">manualAddressing</span></span>|<span data-ttu-id="8f854-125">Pobiera lub ustawia wartość wskazującą, czy ręczne adresowanie wiadomości jest wymagane.</span><span class="sxs-lookup"><span data-stu-id="8f854-125">Gets or sets a value that indicates whether manual addressing of the message is required.</span></span>|  
|<span data-ttu-id="8f854-126">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="8f854-126">maxBufferPoolSize</span></span>|<span data-ttu-id="8f854-127">Pobiera lub ustawia maksymalny rozmiar wszystkich pul buforów używanych przez transport.</span><span class="sxs-lookup"><span data-stu-id="8f854-127">Gets or sets the maximum size of any buffer pools used by the transport.</span></span>|  
|<span data-ttu-id="8f854-128">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="8f854-128">maxBufferSize</span></span>|<span data-ttu-id="8f854-129">Pobiera lub ustawia maksymalny rozmiar buforu do użycia.</span><span class="sxs-lookup"><span data-stu-id="8f854-129">Gets or sets the maximum size of the buffer to use.</span></span> <span data-ttu-id="8f854-130">W przypadku komunikatów przesyłanych strumieniowo ta wartość powinna mieć co najmniej maksymalny możliwy rozmiar nagłówków komunikatów, które są odczytywane w trybie buforowanym.</span><span class="sxs-lookup"><span data-stu-id="8f854-130">For streamed messages, this value should be at least the maximum possible size of the message headers, which are read in buffered mode.</span></span>|  
|<span data-ttu-id="8f854-131">maxOutputDelay</span><span class="sxs-lookup"><span data-stu-id="8f854-131">maxOutputDelay</span></span>|<span data-ttu-id="8f854-132">Pobiera lub ustawia maksymalny przedział czasu, przez który fragment komunikatu lub pełny komunikat może pozostawać w pamięci przed wysłaniem.</span><span class="sxs-lookup"><span data-stu-id="8f854-132">Gets or sets the maximum interval of time that a chunk of a message or a full message can remain buffered in memory before being sent out.</span></span>|  
|<span data-ttu-id="8f854-133">maxPendingAccepts</span><span class="sxs-lookup"><span data-stu-id="8f854-133">maxPendingAccepts</span></span>|<span data-ttu-id="8f854-134">Pobiera lub ustawia maksymalną liczbę oczekujących asynchronicznych operacji akceptujących, które są dostępne do przetwarzania przychodzących połączeń do usługi.</span><span class="sxs-lookup"><span data-stu-id="8f854-134">Gets or sets the maximum number of pending asynchronous accept operations that are available for processing incoming connections to the service.</span></span>|  
|<span data-ttu-id="8f854-135">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="8f854-135">maxPendingConnections</span></span>|<span data-ttu-id="8f854-136">Pobiera lub ustawia maksymalną liczbę połączeń oczekujących na wysłanie usługi.</span><span class="sxs-lookup"><span data-stu-id="8f854-136">Gets or sets the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="8f854-137">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="8f854-137">maxReceivedMessageSize</span></span>|<span data-ttu-id="8f854-138">Pobiera i ustawia maksymalny dopuszczalny rozmiar komunikatu, który można odbierać.</span><span class="sxs-lookup"><span data-stu-id="8f854-138">Gets and sets the maximum allowable message size that can be received.</span></span>|  
|<span data-ttu-id="8f854-139">portSharingEnabled</span><span class="sxs-lookup"><span data-stu-id="8f854-139">portSharingEnabled</span></span>|<span data-ttu-id="8f854-140">Wartość logiczna określająca, czy włączone jest Udostępnianie portów TCP dla tego połączenia.</span><span class="sxs-lookup"><span data-stu-id="8f854-140">A Boolean value that specifies if TCP port sharing is enabled for this connection.</span></span> <span data-ttu-id="8f854-141">W takim przypadku `false` każde powiązanie będzie używać własnego portu wyłącznego.</span><span class="sxs-lookup"><span data-stu-id="8f854-141">If this is `false`, each binding will use its own exclusive port.</span></span> <span data-ttu-id="8f854-142">Wartość domyślna to `false`.</span><span class="sxs-lookup"><span data-stu-id="8f854-142">The default is `false`.</span></span><br /><br /> <span data-ttu-id="8f854-143">To ustawienie dotyczy tylko usług.</span><span class="sxs-lookup"><span data-stu-id="8f854-143">This setting is relevant only to services.</span></span> <span data-ttu-id="8f854-144">Nie dotyczy to klientów.</span><span class="sxs-lookup"><span data-stu-id="8f854-144">Clients are not affected.</span></span><br /><br /> <span data-ttu-id="8f854-145">Użycie tego ustawienia wymaga włączenia usługi udostępniania portów TCP Windows Communication Foundation (WCF), zmieniając jej typ uruchamiania na ręczny lub automatyczny.</span><span class="sxs-lookup"><span data-stu-id="8f854-145">Using this setting requires enabling the Windows Communication Foundation (WCF) TCP Port Sharing Service by changing its Startup Type to Manual or Automatic</span></span>|  
|<span data-ttu-id="8f854-146">teredoEnabled</span><span class="sxs-lookup"><span data-stu-id="8f854-146">teredoEnabled</span></span>|<span data-ttu-id="8f854-147">Wartość logiczna określająca, czy jest włączona funkcja Teredo (technologia do adresowania klientów znajdujących się za zaporą).</span><span class="sxs-lookup"><span data-stu-id="8f854-147">A Boolean value that specifies whether Teredo (a technology for addressing clients that are behind firewalls) is enabled.</span></span> <span data-ttu-id="8f854-148">Wartość domyślna to `false`.</span><span class="sxs-lookup"><span data-stu-id="8f854-148">The default is `false`.</span></span><br /><br /> <span data-ttu-id="8f854-149">Ta właściwość włącza protokół Teredo dla bazowego gniazda TCP.</span><span class="sxs-lookup"><span data-stu-id="8f854-149">This property enables Teredo for the underlying TCP socket.</span></span> <span data-ttu-id="8f854-150">Aby uzyskać więcej informacji, zobacz [Omówienie protokołu Teredo](/previous-versions/windows/it-pro/windows-xp/bb457011(v=technet.10)).</span><span class="sxs-lookup"><span data-stu-id="8f854-150">For more information, see [Teredo Overview](/previous-versions/windows/it-pro/windows-xp/bb457011(v=technet.10)).</span></span><br /><br /> <span data-ttu-id="8f854-151">Ta właściwość ma zastosowanie tylko w systemach Windows XP z dodatkiem SP2 i Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="8f854-151">This property is applicable only on Windows XP SP2 and Windows Server 2003.</span></span> <span data-ttu-id="8f854-152">W systemie Windows Vista jest używana opcja konfiguracji całego komputera dla protokołu Teredo, więc w przypadku korzystania z systemu Vista Ta właściwość jest ignorowana.</span><span class="sxs-lookup"><span data-stu-id="8f854-152">Windows Vista has a machine-wide configuration option for Teredo, so when running Vista, this property is ignored.</span></span> <span data-ttu-id="8f854-153">Protokół Teredo wymaga, aby komputery klienckie i usługi miały zainstalowany stos IPv6 firmy Microsoft i prawidłowo skonfigurowany do użycia w protokole Teredo.</span><span class="sxs-lookup"><span data-stu-id="8f854-153">Teredo requires that the client and service machines both have the Microsoft IPv6 stack installed and correctly configured for Teredo usage.</span></span>|  
|<span data-ttu-id="8f854-154">Elementy TransferMode</span><span class="sxs-lookup"><span data-stu-id="8f854-154">transferMode</span></span>|<span data-ttu-id="8f854-155">Pobiera lub ustawia wartość wskazującą, czy komunikaty są buforowane, czy przesyłane strumieniowo przy użyciu transportu zorientowanego na połączenia.</span><span class="sxs-lookup"><span data-stu-id="8f854-155">Gets or sets a value that indicates whether the messages are buffered or streamed with the connection-oriented transport.</span></span>|  
|<span data-ttu-id="8f854-156">connectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="8f854-156">connectionPoolSettings</span></span>|<span data-ttu-id="8f854-157">Określa dodatkowe ustawienia puli połączeń dla powiązania nazwanego potoku.</span><span class="sxs-lookup"><span data-stu-id="8f854-157">Specifies additional connection pool settings for a Named Pipe binding.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8f854-158">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="8f854-158">Child Elements</span></span>  

 <span data-ttu-id="8f854-159">Brak</span><span class="sxs-lookup"><span data-stu-id="8f854-159">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8f854-160">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="8f854-160">Parent Elements</span></span>  
  
|<span data-ttu-id="8f854-161">Element</span><span class="sxs-lookup"><span data-stu-id="8f854-161">Element</span></span>|<span data-ttu-id="8f854-162">Opis</span><span class="sxs-lookup"><span data-stu-id="8f854-162">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="8f854-163">Definiuje wszystkie możliwości powiązań niestandardowego powiązania.</span><span class="sxs-lookup"><span data-stu-id="8f854-163">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8f854-164">Uwagi</span><span class="sxs-lookup"><span data-stu-id="8f854-164">Remarks</span></span>  

 <span data-ttu-id="8f854-165">Ten transport używa identyfikatorów URI w postaci "net. TCP://NazwaHosta: Port/Path".</span><span class="sxs-lookup"><span data-stu-id="8f854-165">This transport uses URIs of the form "net.tcp://hostname:port/path".</span></span> <span data-ttu-id="8f854-166">Inne składniki URI są opcjonalne.</span><span class="sxs-lookup"><span data-stu-id="8f854-166">Other URI components are optional.</span></span>  
  
 <span data-ttu-id="8f854-167">`tcpTransport`Element jest punktem początkowym do tworzenia niestandardowego powiązania, które implementuje protokół transportowy TCP.</span><span class="sxs-lookup"><span data-stu-id="8f854-167">The `tcpTransport` element is the starting point for creating a custom binding that implements the TCP transport protocol.</span></span> <span data-ttu-id="8f854-168">Ten transport jest zoptymalizowany pod kątem komunikacji między WCF i WCF.</span><span class="sxs-lookup"><span data-stu-id="8f854-168">This transport is optimized for WCF-to-WCF communication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f854-169">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="8f854-169">See also</span></span>

- <xref:System.ServiceModel.Configuration.TcpTransportElement>
- <xref:System.ServiceModel.Channels.TcpTransportBindingElement>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="8f854-170">Transporty</span><span class="sxs-lookup"><span data-stu-id="8f854-170">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="8f854-171">Wybieranie transportu</span><span class="sxs-lookup"><span data-stu-id="8f854-171">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="8f854-172">Powiązania</span><span class="sxs-lookup"><span data-stu-id="8f854-172">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="8f854-173">Rozszerzanie powiązań</span><span class="sxs-lookup"><span data-stu-id="8f854-173">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="8f854-174">Powiązania niestandardowe</span><span class="sxs-lookup"><span data-stu-id="8f854-174">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
