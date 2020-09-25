---
title: <namedPipeTransport>
ms.date: 03/30/2017
ms.assetid: 9fc3f42f-43e2-4ab1-8bc7-3c95a9220df1
ms.openlocfilehash: 4582066098feaf50b33b083de56bcb8c3e04df0f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204622"
---
# \<namedPipeTransport>

<span data-ttu-id="e2428-101">Definiuje transport, który powoduje, że kanał przesyła komunikaty przy użyciu nazwanych potoków, gdy zostanie uwzględniony w niestandardowym powiązaniu.</span><span class="sxs-lookup"><span data-stu-id="e2428-101">Defines a transport that causes a channel to transfer messages using named pipes when it is included in a custom binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<namedPipeTransport>**  
  
## <a name="syntax"></a><span data-ttu-id="e2428-102">Składnia</span><span class="sxs-lookup"><span data-stu-id="e2428-102">Syntax</span></span>  
  
```xml  
<namedPipeTransport channelInitializationTimeout="TimeSpan"
                    connectionBufferSize="Integer"
                    hostNameComparisonMode="StrongWildcard/Exact/WeakWildcard"
                    manualAddressing="Boolean"
                    maxBufferPoolSize="Integer"
                    maxBufferSize="Integer"
                    maxOutputDelay="TimeSpan"
                    maxPendingAccepts="Integer"
                    maxPendingConnections="Integer"
                    maxReceivedMessageSize="Integer"
                    transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse">
  <connectionPoolSettings groupName="String"
                          idleTimeout="TimeSpan"
                          maxOutboundConnectionsPerEndpoint="Integer" />
</namedPipeTransport>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e2428-103">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="e2428-103">Attributes and Elements</span></span>  

<span data-ttu-id="e2428-104">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="e2428-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e2428-105">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="e2428-105">Attributes</span></span>  

<span data-ttu-id="e2428-106">Brak.</span><span class="sxs-lookup"><span data-stu-id="e2428-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e2428-107">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="e2428-107">Child Elements</span></span>  
  
|<span data-ttu-id="e2428-108">Element</span><span class="sxs-lookup"><span data-stu-id="e2428-108">Element</span></span>|<span data-ttu-id="e2428-109">Opis</span><span class="sxs-lookup"><span data-stu-id="e2428-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e2428-110">ChannelInitializationTimeout</span><span class="sxs-lookup"><span data-stu-id="e2428-110">ChannelInitializationTimeout</span></span>|<span data-ttu-id="e2428-111">Pobiera lub ustawia wartość określającą <xref:System.TimeSpan> Maksymalny czas, przez który kanał może być w stanie inicjowania przed rozłączeniem.</span><span class="sxs-lookup"><span data-stu-id="e2428-111">Gets or sets a <xref:System.TimeSpan> that determines the maximum time a channel can be in the initialization status before being disconnected.</span></span>|  
|<span data-ttu-id="e2428-112">ConnectionBufferSize</span><span class="sxs-lookup"><span data-stu-id="e2428-112">ConnectionBufferSize</span></span>|<span data-ttu-id="e2428-113">Pobiera lub ustawia rozmiar buforu używany do przesyłania fragmentu serializowanego komunikatu w locie z klienta lub usługi.</span><span class="sxs-lookup"><span data-stu-id="e2428-113">Gets or sets the size of the buffer used to transmit a chunk of the serialized message on the wire from the client or service.</span></span>|  
|<span data-ttu-id="e2428-114">hostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="e2428-114">hostNameComparisonMode</span></span>|<span data-ttu-id="e2428-115">Pobiera lub ustawia wartość wskazującą, czy nazwa hosta jest używana do uzyskiwania dostępu do usługi podczas dopasowywania identyfikatora URI.</span><span class="sxs-lookup"><span data-stu-id="e2428-115">Gets or sets a value that indicates whether the hostname is used to reach the service when matching on the URI.</span></span>|  
|<span data-ttu-id="e2428-116">Opcję ManualAddressing</span><span class="sxs-lookup"><span data-stu-id="e2428-116">manualAddressing</span></span>|<span data-ttu-id="e2428-117">Pobiera lub ustawia wartość wskazującą, czy ręczne adresowanie wiadomości jest wymagane.</span><span class="sxs-lookup"><span data-stu-id="e2428-117">Gets or sets a value that indicates whether manual addressing of the message is required.</span></span>|  
|<span data-ttu-id="e2428-118">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="e2428-118">maxBufferPoolSize</span></span>|<span data-ttu-id="e2428-119">Pobiera lub ustawia maksymalny rozmiar (w bajtach) wszystkich pul buforów używanych przez transport.</span><span class="sxs-lookup"><span data-stu-id="e2428-119">Gets or sets the maximum size, in bytes, of any buffer pools used by the transport.</span></span>|  
|<span data-ttu-id="e2428-120">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="e2428-120">maxBufferSize</span></span>|<span data-ttu-id="e2428-121">Pobiera lub ustawia maksymalny rozmiar buforu do użycia.</span><span class="sxs-lookup"><span data-stu-id="e2428-121">Gets or sets the maximum size of the buffer to use.</span></span> <span data-ttu-id="e2428-122">W przypadku komunikatów przesyłanych strumieniowo ta wartość powinna mieć co najmniej maksymalny możliwy rozmiar nagłówków komunikatów, które są odczytywane w trybie buforowanym.</span><span class="sxs-lookup"><span data-stu-id="e2428-122">For streamed messages, this value should be at least the maximum possible size of the message headers, which are read in buffered mode.</span></span>|  
|<span data-ttu-id="e2428-123">maxOutputDelay</span><span class="sxs-lookup"><span data-stu-id="e2428-123">maxOutputDelay</span></span>|<span data-ttu-id="e2428-124">Pobiera lub ustawia maksymalny przedział czasu, przez który fragment komunikatu lub pełny komunikat może pozostawać w pamięci przed wysłaniem.</span><span class="sxs-lookup"><span data-stu-id="e2428-124">Gets or sets the maximum interval of time that a chunk of a message or a full message can remain buffered in memory before being sent out.</span></span>|  
|<span data-ttu-id="e2428-125">maxPendingAccepts</span><span class="sxs-lookup"><span data-stu-id="e2428-125">maxPendingAccepts</span></span>|<span data-ttu-id="e2428-126">Pobiera lub ustawia maksymalną liczbę kanałów, jaką usługa może oczekiwać na odbiorniku do przetwarzania połączeń przychodzących do usługi.</span><span class="sxs-lookup"><span data-stu-id="e2428-126">Gets or sets the maximum number of channels a service can have waiting on a listener for processing incoming connections to the service.</span></span>|  
|<span data-ttu-id="e2428-127">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="e2428-127">maxPendingConnections</span></span>|<span data-ttu-id="e2428-128">Pobiera lub ustawia maksymalną liczbę połączeń oczekujących na wysłanie usługi.</span><span class="sxs-lookup"><span data-stu-id="e2428-128">Gets or sets the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="e2428-129">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="e2428-129">maxReceivedMessageSize</span></span>|<span data-ttu-id="e2428-130">Pobiera i ustawia maksymalny dopuszczalny rozmiar wiadomości (w bajtach), która może zostać odebrana.</span><span class="sxs-lookup"><span data-stu-id="e2428-130">Gets and sets the maximum allowable message size, in bytes, that can be received.</span></span>|  
|<span data-ttu-id="e2428-131">Elementy TransferMode</span><span class="sxs-lookup"><span data-stu-id="e2428-131">transferMode</span></span>|<span data-ttu-id="e2428-132">Pobiera lub ustawia wartość wskazującą, czy komunikaty są buforowane, czy przesyłane strumieniowo przy użyciu transportu zorientowanego na połączenia.</span><span class="sxs-lookup"><span data-stu-id="e2428-132">Gets or sets a value that indicates whether the messages are buffered or streamed with the connection-oriented transport.</span></span>|  
|[<span data-ttu-id="e2428-133">\<connectionPoolSettings> z \<namedPipeTransport></span><span class="sxs-lookup"><span data-stu-id="e2428-133">\<connectionPoolSettings> of \<namedPipeTransport></span></span>](connectionpoolsettings.md)|<span data-ttu-id="e2428-134">Określa dodatkowe ustawienia puli połączeń dla powiązania nazwanego potoku.</span><span class="sxs-lookup"><span data-stu-id="e2428-134">Specifies additional connection pool settings for a Named Pipe binding.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e2428-135">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="e2428-135">Parent Elements</span></span>  
  
|<span data-ttu-id="e2428-136">Element</span><span class="sxs-lookup"><span data-stu-id="e2428-136">Element</span></span>|<span data-ttu-id="e2428-137">Opis</span><span class="sxs-lookup"><span data-stu-id="e2428-137">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="e2428-138">Definiuje wszystkie możliwości powiązań niestandardowego powiązania.</span><span class="sxs-lookup"><span data-stu-id="e2428-138">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e2428-139">Uwagi</span><span class="sxs-lookup"><span data-stu-id="e2428-139">Remarks</span></span>  

<span data-ttu-id="e2428-140">Ten transport używa identyfikatorów URI w postaci "net. pipe://hostname/Path".</span><span class="sxs-lookup"><span data-stu-id="e2428-140">This transport uses URIs of the form "net.pipe://hostname/path".</span></span> <span data-ttu-id="e2428-141">Inne składniki URI są opcjonalne.</span><span class="sxs-lookup"><span data-stu-id="e2428-141">Other URI components are optional.</span></span>  
  
<span data-ttu-id="e2428-142">`namedPipeTransport`Element jest punktem początkowym do tworzenia niestandardowego powiązania, które implementuje protokół transportu nazwanych potoków.</span><span class="sxs-lookup"><span data-stu-id="e2428-142">The `namedPipeTransport` element is the starting point for creating a custom binding that implements the named pipes transport protocol.</span></span> <span data-ttu-id="e2428-143">Ten transport jest używany w przypadku komunikacji między maszynami Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="e2428-143">This transport is used for on-machine Windows Communication Foundation (WCF)-to-WCF communication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2428-144">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="e2428-144">See also</span></span>

- <xref:System.ServiceModel.Configuration.NamedPipeTransportElement>
- <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="e2428-145">Transporty</span><span class="sxs-lookup"><span data-stu-id="e2428-145">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="e2428-146">Wybieranie transportu</span><span class="sxs-lookup"><span data-stu-id="e2428-146">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="e2428-147">Powiązania</span><span class="sxs-lookup"><span data-stu-id="e2428-147">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="e2428-148">Rozszerzanie powiązań</span><span class="sxs-lookup"><span data-stu-id="e2428-148">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="e2428-149">Powiązania niestandardowe</span><span class="sxs-lookup"><span data-stu-id="e2428-149">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
