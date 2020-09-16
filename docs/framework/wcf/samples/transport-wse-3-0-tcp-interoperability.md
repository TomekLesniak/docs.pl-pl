---
title: 'Transport: Współdziałanie protokołu TCP z usługami WSE 3.0'
ms.date: 03/30/2017
ms.assetid: 5f7c3708-acad-4eb3-acb9-d232c77d1486
ms.openlocfilehash: f61d5037af0be6579d5110152ca070bec586fe87
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90558969"
---
# <a name="transport-wse-30-tcp-interoperability"></a><span data-ttu-id="e82f5-102">Transport: Współdziałanie protokołu TCP z usługami WSE 3.0</span><span class="sxs-lookup"><span data-stu-id="e82f5-102">Transport: WSE 3.0 TCP Interoperability</span></span>
<span data-ttu-id="e82f5-103">Przykład transportu współdziałania TCP w programie WSE 3,0 demonstruje sposób implementacji sesji dwustronnej TCP jako transportu niestandardowego Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="e82f5-103">The WSE 3.0 TCP Interoperability Transport sample demonstrates how to implement a TCP duplex session as a custom Windows Communication Foundation (WCF) transport.</span></span> <span data-ttu-id="e82f5-104">Przedstawiono w nim również, jak można użyć rozszerzalności warstwy kanału do interfejsu przez sieć z istniejącymi wdrożonymi systemami.</span><span class="sxs-lookup"><span data-stu-id="e82f5-104">It also demonstrates how you can use the extensibility of the channel layer to interface over the wire with existing deployed systems.</span></span> <span data-ttu-id="e82f5-105">Poniższe kroki pokazują, jak utworzyć niestandardowy transport WCF:</span><span class="sxs-lookup"><span data-stu-id="e82f5-105">The following steps show how to build this custom WCF transport:</span></span>  
  
1. <span data-ttu-id="e82f5-106">Rozpoczynając od gniazda TCP, Utwórz implementacje klienta i serwera <xref:System.ServiceModel.Channels.IDuplexSessionChannel> , które używają ramki Dime do odróżnić granic komunikatów.</span><span class="sxs-lookup"><span data-stu-id="e82f5-106">Starting with a TCP socket, create client and server implementations of <xref:System.ServiceModel.Channels.IDuplexSessionChannel> that use DIME Framing to delineate message boundaries.</span></span>  
  
2. <span data-ttu-id="e82f5-107">Utwórz fabrykę kanałów, która łączy się z usługą WSE TCP i wysyła komunikaty z ramkami za pośrednictwem klienta <xref:System.ServiceModel.Channels.IDuplexSessionChannel> s.</span><span class="sxs-lookup"><span data-stu-id="e82f5-107">Create a channel factory that connects to a WSE TCP service and sends framed messages over the client <xref:System.ServiceModel.Channels.IDuplexSessionChannel>s.</span></span>  
  
3. <span data-ttu-id="e82f5-108">Utwórz odbiornik kanału, aby akceptować przychodzące połączenia TCP i generować odpowiednie kanały.</span><span class="sxs-lookup"><span data-stu-id="e82f5-108">Create a channel listener to accept incoming TCP connections and produce corresponding channels.</span></span>  
  
4. <span data-ttu-id="e82f5-109">Upewnij się, że wszystkie wyjątki specyficzne dla sieci są znormalizowane do odpowiedniej klasy pochodnej <xref:System.ServiceModel.CommunicationException> .</span><span class="sxs-lookup"><span data-stu-id="e82f5-109">Ensure that any network-specific exceptions are normalized to the appropriate derived class of <xref:System.ServiceModel.CommunicationException>.</span></span>  
  
5. <span data-ttu-id="e82f5-110">Dodaj element powiązania, który dodaje niestandardowy transport do stosu kanału.</span><span class="sxs-lookup"><span data-stu-id="e82f5-110">Add a binding element that adds the custom transport to a channel stack.</span></span> <span data-ttu-id="e82f5-111">Aby uzyskać więcej informacji, zobacz [Dodawanie elementu powiązania].</span><span class="sxs-lookup"><span data-stu-id="e82f5-111">For more information, see [Adding a Binding Element].</span></span>  
  
## <a name="creating-iduplexsessionchannel"></a><span data-ttu-id="e82f5-112">Tworzenie IDuplexSessionChannel</span><span class="sxs-lookup"><span data-stu-id="e82f5-112">Creating IDuplexSessionChannel</span></span>  
 <span data-ttu-id="e82f5-113">Pierwszym krokiem w przypadku transportu współdziałania TCP w systemie WSE 3,0 jest utworzenie implementacji <xref:System.ServiceModel.Channels.IDuplexSessionChannel> na podstawie <xref:System.Net.Sockets.Socket> .</span><span class="sxs-lookup"><span data-stu-id="e82f5-113">The first step in writing the WSE 3.0 TCP Interoperability Transport is to create an implementation of <xref:System.ServiceModel.Channels.IDuplexSessionChannel> on top of a <xref:System.Net.Sockets.Socket>.</span></span> <span data-ttu-id="e82f5-114">`WseTcpDuplexSessionChannel` pochodzi od <xref:System.ServiceModel.Channels.ChannelBase> .</span><span class="sxs-lookup"><span data-stu-id="e82f5-114">`WseTcpDuplexSessionChannel` derives from <xref:System.ServiceModel.Channels.ChannelBase>.</span></span> <span data-ttu-id="e82f5-115">Logika wysyłania wiadomości składa się z dwóch głównych elementów: (1) kodowanie wiadomości do bajtów i (2) umieszczanie tych bajtów i wysyłanie ich do sieci.</span><span class="sxs-lookup"><span data-stu-id="e82f5-115">The logic of sending a message consists of two main pieces: (1) Encoding the message into bytes, and (2) framing those bytes and sending them on the wire.</span></span>  
  
 `ArraySegment<byte> encodedBytes = EncodeMessage(message);`  
  
 `WriteData(encodedBytes);`  
  
 <span data-ttu-id="e82f5-116">Ponadto jest wykonywana blokada, dzięki czemu wywołania Send () zachowują gwarancję IDuplexSessionChannel w kolejności i tak, aby wywołania bazowego gniazda były prawidłowo synchronizowane.</span><span class="sxs-lookup"><span data-stu-id="e82f5-116">In addition, a lock is taken so that the Send() calls preserve the IDuplexSessionChannel in-order guarantee, and so that calls to the underlying socket are synchronized correctly.</span></span>  
  
 <span data-ttu-id="e82f5-117">`WseTcpDuplexSessionChannel` używa <xref:System.ServiceModel.Channels.MessageEncoder> do tłumaczenia typu <xref:System.ServiceModel.Channels.Message> do i z bajtu [].</span><span class="sxs-lookup"><span data-stu-id="e82f5-117">`WseTcpDuplexSessionChannel` uses a <xref:System.ServiceModel.Channels.MessageEncoder> for translating a <xref:System.ServiceModel.Channels.Message> to and from byte[].</span></span> <span data-ttu-id="e82f5-118">Ponieważ jest to transport, `WseTcpDuplexSessionChannel` jest również odpowiedzialny za zastosowanie zdalnego adresu, z którym kanał został skonfigurowany.</span><span class="sxs-lookup"><span data-stu-id="e82f5-118">Because it is a transport, `WseTcpDuplexSessionChannel` is also responsible for applying the remote address that the channel was configured with.</span></span> <span data-ttu-id="e82f5-119">`EncodeMessage` hermetyzuje logikę dla tej konwersji.</span><span class="sxs-lookup"><span data-stu-id="e82f5-119">`EncodeMessage` encapsulates the logic for this conversion.</span></span>  
  
 `this.RemoteAddress.ApplyTo(message);`  
  
 `return encoder.WriteMessage(message, maxBufferSize, bufferManager);`  
  
 <span data-ttu-id="e82f5-120">Gdy <xref:System.ServiceModel.Channels.Message> program zostanie zakodowany w bajtach, musi być przesyłany w sieci.</span><span class="sxs-lookup"><span data-stu-id="e82f5-120">Once the <xref:System.ServiceModel.Channels.Message> is encoded into bytes, it must be transmitted on the wire.</span></span> <span data-ttu-id="e82f5-121">Wymaga to systemu do definiowania granic komunikatów.</span><span class="sxs-lookup"><span data-stu-id="e82f5-121">This requires a system for defining message boundaries.</span></span> <span data-ttu-id="e82f5-122">WSE 3,0 używa wersji [Dime](/archive/msdn-magazine/2002/december/sending-files-attachments-and-soap-messages-via-dime) jako protokołu szkieletu.</span><span class="sxs-lookup"><span data-stu-id="e82f5-122">WSE 3.0 uses a version of [DIME](/archive/msdn-magazine/2002/december/sending-files-attachments-and-soap-messages-via-dime) as its framing protocol.</span></span> <span data-ttu-id="e82f5-123">`WriteData` hermetyzuje logikę ramek, aby otoczyć bajt [] do zestawu rekordów DIME.</span><span class="sxs-lookup"><span data-stu-id="e82f5-123">`WriteData` encapsulates the framing logic to wrap a byte[] into a set of DIME records.</span></span>  
  
 <span data-ttu-id="e82f5-124">Logika wysyłania komunikatów jest podobna.</span><span class="sxs-lookup"><span data-stu-id="e82f5-124">The logic for receiving messages is similar.</span></span> <span data-ttu-id="e82f5-125">Główna złożoność obsługuje fakt, że odczytany przez gniazdo może zwrócić mniejszą liczbę bajtów niż zażądano.</span><span class="sxs-lookup"><span data-stu-id="e82f5-125">The main complexity is handling the fact that a socket read can return fewer bytes than were requested.</span></span> <span data-ttu-id="e82f5-126">Aby odebrać komunikat, program `WseTcpDuplexSessionChannel` odczytuje bajty z sieci, dekoduje ramkę Dime, a następnie używa w <xref:System.ServiceModel.Channels.MessageEncoder> celu wyłączania bajtu [] do <xref:System.ServiceModel.Channels.Message> .</span><span class="sxs-lookup"><span data-stu-id="e82f5-126">To receive a message, `WseTcpDuplexSessionChannel` reads bytes off the wire, decodes the DIME framing, and then uses the <xref:System.ServiceModel.Channels.MessageEncoder> for turning the byte[] into a <xref:System.ServiceModel.Channels.Message>.</span></span>  
  
 <span data-ttu-id="e82f5-127">Podstawą jest `WseTcpDuplexSessionChannel` założenie, że odbierze połączone gniazdo.</span><span class="sxs-lookup"><span data-stu-id="e82f5-127">The base `WseTcpDuplexSessionChannel` assumes that it receives a connected socket.</span></span> <span data-ttu-id="e82f5-128">Klasa bazowa obsługuje zamknięcie gniazda.</span><span class="sxs-lookup"><span data-stu-id="e82f5-128">The base class handles socket shutdown.</span></span> <span data-ttu-id="e82f5-129">Istnieją trzy miejsca, w których interfejs ma zamknięcie gniazda:</span><span class="sxs-lookup"><span data-stu-id="e82f5-129">There are three places that interface with socket closure:</span></span>  
  
- <span data-ttu-id="e82f5-130">OnAbort — Zamknij gniazdo niebezpiecznie (twarde).</span><span class="sxs-lookup"><span data-stu-id="e82f5-130">OnAbort -- close the socket ungracefully (hard close).</span></span>  
  
- <span data-ttu-id="e82f5-131">Na [BEGIN] Zamknij--zamykaj gniazdo w sposób łagodny (zamknięcie miękkie).</span><span class="sxs-lookup"><span data-stu-id="e82f5-131">On[Begin]Close -- close the socket gracefully (soft close).</span></span>  
  
- <span data-ttu-id="e82f5-132">obrad. Wywołaniu metody CloseOutputSession — Zamknij strumień danych wychodzących (połowa Close).</span><span class="sxs-lookup"><span data-stu-id="e82f5-132">session.CloseOutputSession -- shut down the outbound data stream (half close).</span></span>  
  
## <a name="channel-factory"></a><span data-ttu-id="e82f5-133">Fabryka kanałów</span><span class="sxs-lookup"><span data-stu-id="e82f5-133">Channel Factory</span></span>  
 <span data-ttu-id="e82f5-134">Następnym krokiem podczas pisania transportu TCP jest utworzenie implementacji <xref:System.ServiceModel.Channels.IChannelFactory> dla kanałów klienta.</span><span class="sxs-lookup"><span data-stu-id="e82f5-134">The next step in writing the TCP transport is to create an implementation of <xref:System.ServiceModel.Channels.IChannelFactory> for client channels.</span></span>  
  
- <span data-ttu-id="e82f5-135">`WseTcpChannelFactory`pochodzi od <xref:System.ServiceModel.Channels.ChannelFactoryBase> \<IDuplexSessionChannel> .</span><span class="sxs-lookup"><span data-stu-id="e82f5-135">`WseTcpChannelFactory` derives from <xref:System.ServiceModel.Channels.ChannelFactoryBase>\<IDuplexSessionChannel>.</span></span> <span data-ttu-id="e82f5-136">Jest to fabryka, która zastępuje `OnCreateChannel` generowanie kanałów klientów.</span><span class="sxs-lookup"><span data-stu-id="e82f5-136">It is a factory that overrides `OnCreateChannel` to produce client channels.</span></span>  
  
 `protected override IDuplexSessionChannel OnCreateChannel(EndpointAddress remoteAddress, Uri via)`  
  
 `{`  
  
 `return new ClientWseTcpDuplexSessionChannel(encoderFactory, bufferManager, remoteAddress, via, this);`  
  
 `}`  
  
- <span data-ttu-id="e82f5-137">`ClientWseTcpDuplexSessionChannel` dodaje logikę do podstawy, `WseTcpDuplexSessionChannel` Aby połączyć się z serwerem TCP w `channel.Open` czasie.</span><span class="sxs-lookup"><span data-stu-id="e82f5-137">`ClientWseTcpDuplexSessionChannel` adds logic to the base `WseTcpDuplexSessionChannel` to connect to a TCP server at `channel.Open` time.</span></span> <span data-ttu-id="e82f5-138">Najpierw nazwa hosta jest rozpoznawana jako adres IP, jak pokazano w poniższym kodzie.</span><span class="sxs-lookup"><span data-stu-id="e82f5-138">First the hostname is resolved to an IP address, as shown in the following code.</span></span>  
  
 `hostEntry = Dns.GetHostEntry(Via.Host);`  
  
- <span data-ttu-id="e82f5-139">Następnie nazwa hosta jest połączona z pierwszym dostępnym adresem IP w pętli, jak pokazano w poniższym kodzie.</span><span class="sxs-lookup"><span data-stu-id="e82f5-139">Then the hostname is connected to the first available IP address in a loop, as shown in the following code.</span></span>  
  
 `IPAddress address = hostEntry.AddressList[i];`  
  
 `socket = new Socket(address.AddressFamily, SocketType.Stream, ProtocolType.Tcp);`  
  
 `socket.Connect(new IPEndPoint(address, port));`  
  
- <span data-ttu-id="e82f5-140">W ramach kontraktu kanału wszystkie wyjątki specyficzne dla domeny są opakowane, na przykład `SocketException` w <xref:System.ServiceModel.CommunicationException> .</span><span class="sxs-lookup"><span data-stu-id="e82f5-140">As part of the channel contract, any domain-specific exceptions are wrapped, such as `SocketException` in <xref:System.ServiceModel.CommunicationException>.</span></span>  
  
## <a name="channel-listener"></a><span data-ttu-id="e82f5-141">Odbiornik kanału</span><span class="sxs-lookup"><span data-stu-id="e82f5-141">Channel Listener</span></span>  
 <span data-ttu-id="e82f5-142">Następnym krokiem podczas pisania transportu TCP jest utworzenie implementacji <xref:System.ServiceModel.Channels.IChannelListener> dla akceptowania kanałów serwera.</span><span class="sxs-lookup"><span data-stu-id="e82f5-142">The next step in writing the TCP transport is to create an implementation of <xref:System.ServiceModel.Channels.IChannelListener> for accepting server channels.</span></span>  
  
- <span data-ttu-id="e82f5-143">`WseTcpChannelListener`pochodzi od <xref:System.ServiceModel.Channels.ChannelListenerBase> \<IDuplexSessionChannel> i przesłonięcia na [BEGIN] Otwórz i na [BEGIN] Zamknij, aby kontrolować okres istnienia gniazda nasłuchiwania.</span><span class="sxs-lookup"><span data-stu-id="e82f5-143">`WseTcpChannelListener` derives from <xref:System.ServiceModel.Channels.ChannelListenerBase>\<IDuplexSessionChannel> and overrides On[Begin]Open and On[Begin]Close to control the lifetime of its listen socket.</span></span> <span data-ttu-id="e82f5-144">W obszarze OnOpen gniazdo jest tworzone w celu nasłuchiwania na IP_ANY.</span><span class="sxs-lookup"><span data-stu-id="e82f5-144">In OnOpen, a socket is created to listen on IP_ANY.</span></span> <span data-ttu-id="e82f5-145">Bardziej zaawansowane implementacje mogą również utworzyć drugie gniazdo do nasłuchiwania na protokole IPv6.</span><span class="sxs-lookup"><span data-stu-id="e82f5-145">More advanced implementations can create a second socket to listen on IPv6 as well.</span></span> <span data-ttu-id="e82f5-146">Mogą również zezwalać na określenie adresu IP w nazwie hosta.</span><span class="sxs-lookup"><span data-stu-id="e82f5-146">They can also allow the IP address to be specified in the hostname.</span></span>  
  
 `IPEndPoint localEndpoint = new IPEndPoint(IPAddress.Any, uri.Port);`  
  
 `this.listenSocket = new Socket(localEndpoint.AddressFamily, SocketType.Stream, ProtocolType.Tcp);`  
  
 `this.listenSocket.Bind(localEndpoint);`  
  
 `this.listenSocket.Listen(10);`  
  
 <span data-ttu-id="e82f5-147">Po zaakceptowaniu nowego gniazda kanał serwera jest inicjowany za pomocą tego gniazda.</span><span class="sxs-lookup"><span data-stu-id="e82f5-147">When a new socket is accepted, a server channel is initialized with this socket.</span></span> <span data-ttu-id="e82f5-148">Wszystkie dane wejściowe i wyjściowe są już zaimplementowane w klasie bazowej, więc ten kanał jest odpowiedzialny za Inicjowanie gniazda.</span><span class="sxs-lookup"><span data-stu-id="e82f5-148">All the input and output is already implemented in the base class, so this channel is responsible for initializing the socket.</span></span>  
  
## <a name="adding-a-binding-element"></a><span data-ttu-id="e82f5-149">Dodawanie elementu powiązania</span><span class="sxs-lookup"><span data-stu-id="e82f5-149">Adding a Binding Element</span></span>  
 <span data-ttu-id="e82f5-150">Teraz, gdy fabryki i kanały są kompilowane, muszą one być uwidocznione w środowisku uruchomieniowym ServiceModel za pomocą powiązania.</span><span class="sxs-lookup"><span data-stu-id="e82f5-150">Now that the factories and channels are built, they must be exposed to the ServiceModel runtime through a binding.</span></span> <span data-ttu-id="e82f5-151">Powiązanie to kolekcja elementów powiązania, które reprezentują stos komunikacji skojarzony z adresem usługi.</span><span class="sxs-lookup"><span data-stu-id="e82f5-151">A binding is a collection of binding elements that represents the communication stack associated with a service address.</span></span> <span data-ttu-id="e82f5-152">Każdy element w stosie jest reprezentowany przez element powiązania.</span><span class="sxs-lookup"><span data-stu-id="e82f5-152">Each element in the stack is represented by a binding element.</span></span>  
  
 <span data-ttu-id="e82f5-153">W przykładzie element Binding ma wartość `WseTcpTransportBindingElement` , która pochodzi od <xref:System.ServiceModel.Channels.TransportBindingElement> .</span><span class="sxs-lookup"><span data-stu-id="e82f5-153">In the sample, the binding element is `WseTcpTransportBindingElement`, which derives from <xref:System.ServiceModel.Channels.TransportBindingElement>.</span></span> <span data-ttu-id="e82f5-154">Obsługuje <xref:System.ServiceModel.Channels.IDuplexSessionChannel> i zastępuje następujące metody tworzenia fabryk skojarzonych z naszymi powiązaniami.</span><span class="sxs-lookup"><span data-stu-id="e82f5-154">It supports <xref:System.ServiceModel.Channels.IDuplexSessionChannel> and overrides the following methods to build the factories associated with our binding.</span></span>  
  
 `public IChannelFactory<TChannel> BuildChannelFactory<TChannel>(BindingContext context)`  
  
 `{`  
  
 `return (IChannelFactory<TChannel>)(object)new WseTcpChannelFactory(this, context);`  
  
 `}`  
  
 `public IChannelListener<TChannel> BuildChannelListener<TChannel>(BindingContext context)`  
  
 `{`  
  
 `return (IChannelListener<TChannel>)(object)new WseTcpChannelListener(this, context);`  
  
 `}`  
  
 <span data-ttu-id="e82f5-155">Zawiera również elementy członkowskie do klonowania `BindingElement` i zwracania naszego schematu (WSE. TCP).</span><span class="sxs-lookup"><span data-stu-id="e82f5-155">It also contains members for cloning the `BindingElement` and returning our scheme (wse.tcp).</span></span>  
  
## <a name="the-wse-tcp-test-console"></a><span data-ttu-id="e82f5-156">Konsola testowa TCP WSE</span><span class="sxs-lookup"><span data-stu-id="e82f5-156">The WSE TCP Test Console</span></span>  
 <span data-ttu-id="e82f5-157">Kod testowy służący do korzystania z tego przykładowego transportu jest dostępny w TestCode.cs.</span><span class="sxs-lookup"><span data-stu-id="e82f5-157">Test code for using this sample transport is available in TestCode.cs.</span></span> <span data-ttu-id="e82f5-158">Poniższe instrukcje przedstawiają sposób konfigurowania `TcpSyncStockService` przykładu WSE.</span><span class="sxs-lookup"><span data-stu-id="e82f5-158">The following instructions show how to set up the WSE `TcpSyncStockService` sample.</span></span>  
  
 <span data-ttu-id="e82f5-159">Kod testu tworzy niestandardowe powiązanie, które używa MTOM jako kodowania i `WseTcpTransport` jako transportu.</span><span class="sxs-lookup"><span data-stu-id="e82f5-159">The test code creates a custom binding that uses MTOM as the encoding and `WseTcpTransport` as the transport.</span></span> <span data-ttu-id="e82f5-160">Konfiguruje również AddressingVersion, aby była zgodna z WSE 3,0, jak pokazano w poniższym kodzie.</span><span class="sxs-lookup"><span data-stu-id="e82f5-160">It also sets up the AddressingVersion to be conformant with WSE 3.0, as shown in the following code.</span></span>  
  
 `CustomBinding binding = new CustomBinding();`  
  
 `MtomMessageEncodingBindingElement mtomBindingElement = new MtomMessageEncodingBindingElement();`  
  
 `mtomBindingElement.MessageVersion = MessageVersion.Soap11WSAddressingAugust2004;`  
  
 `binding.Elements.Add(mtomBindingElement);`  
  
 `binding.Elements.Add(new WseTcpTransportBindingElement());`  
  
 <span data-ttu-id="e82f5-161">Składa się z dwóch testów — jeden test konfiguruje klienta z określonym typem przy użyciu kodu wygenerowanego na podstawie języka WSDL WSE 3,0.</span><span class="sxs-lookup"><span data-stu-id="e82f5-161">It consists of two tests—one test sets up a typed client using code generated from the WSE 3.0 WSDL.</span></span> <span data-ttu-id="e82f5-162">Drugi test używa programu WCF jako klienta i serwera przez wysyłanie komunikatów bezpośrednio na podstawie interfejsów API kanału.</span><span class="sxs-lookup"><span data-stu-id="e82f5-162">The second test uses WCF as both the client and the server by sending messages directly on top of the channel APIs.</span></span>  
  
 <span data-ttu-id="e82f5-163">Podczas uruchamiania przykładu, oczekiwane są następujące dane wyjściowe.</span><span class="sxs-lookup"><span data-stu-id="e82f5-163">When running the sample, the following output is expected.</span></span>  
  
 <span data-ttu-id="e82f5-164">Klient:</span><span class="sxs-lookup"><span data-stu-id="e82f5-164">Client:</span></span>  
  
```console  
Calling soap://stockservice.contoso.com/wse/samples/2003/06/TcpSyncStockService  
  
Symbol: FABRIKAM  
        Name: Fabrikam, Inc.  
        Last Price: 120  
  
Symbol: CONTOSO  
        Name: Contoso Corp.  
        Last Price: 50.07  
Press enter.  
  
Received Action: http://SayHello  
Received Body: to you.  
Hello to you.  
Press enter.  
  
Received Action: http://NotHello  
Received Body: to me.  
Press enter.  
```  
  
 <span data-ttu-id="e82f5-165">Serwer:</span><span class="sxs-lookup"><span data-stu-id="e82f5-165">Server:</span></span>  
  
```console  
Listening for messages at soap://stockservice.contoso.com/wse/samples/2003/06/TcpSyncStockService  
  
Press any key to exit when done...  
  
Request received.  
Symbols:  
        FABRIKAM  
        CONTOSO  
```  
  
## <a name="set-up-build-and-run-the-sample"></a><span data-ttu-id="e82f5-166">Konfigurowanie, kompilowanie i uruchamianie przykładu</span><span class="sxs-lookup"><span data-stu-id="e82f5-166">Set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="e82f5-167">Aby uruchomić ten przykład, musisz mieć [rozszerzenia usług sieci Web (WSE) 3,0 dla Microsoft .NET](https://www.microsoft.com/download/details.aspx?id=14089) i `TcpSyncStockService` zainstalowaną przykład WSE.</span><span class="sxs-lookup"><span data-stu-id="e82f5-167">To run this sample, you must have [Web Services Enhancements (WSE) 3.0 for Microsoft .NET](https://www.microsoft.com/download/details.aspx?id=14089) and the WSE `TcpSyncStockService` sample installed.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e82f5-168">Ponieważ WSE 3,0 nie jest obsługiwany w systemie Windows Server 2008, nie można zainstalować ani uruchomić `TcpSyncStockService` przykładu w tym systemie operacyjnym.</span><span class="sxs-lookup"><span data-stu-id="e82f5-168">Because WSE 3.0 is not supported on Windows Server 2008, you cannot install or run the `TcpSyncStockService` sample on that operating system.</span></span>  
  
1. <span data-ttu-id="e82f5-169">Po zainstalowaniu `TcpSyncStockService` przykładu należy wykonać następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="e82f5-169">Once you install the `TcpSyncStockService` sample, do the following:</span></span>  
  
    1. <span data-ttu-id="e82f5-170">Otwórz `TcpSyncStockService` program w programie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e82f5-170">Open the `TcpSyncStockService` in Visual Studio.</span></span> <span data-ttu-id="e82f5-171">(Przykład TcpSyncStockService jest instalowany z WSE 3,0.</span><span class="sxs-lookup"><span data-stu-id="e82f5-171">(The TcpSyncStockService sample is installed with WSE 3.0.</span></span> <span data-ttu-id="e82f5-172">Nie jest częścią tego przykładowego kodu.)</span><span class="sxs-lookup"><span data-stu-id="e82f5-172">It is not part of this sample's code.)</span></span>  
  
    2. <span data-ttu-id="e82f5-173">Ustaw projekt StockService jako projekt startowy.</span><span class="sxs-lookup"><span data-stu-id="e82f5-173">Set the StockService project as the start-up project.</span></span>  
  
    3. <span data-ttu-id="e82f5-174">Otwórz StockService.cs w projekcie StockService i Dodaj komentarz do atrybutu [Policy] w `StockService` klasie.</span><span class="sxs-lookup"><span data-stu-id="e82f5-174">Open StockService.cs in the StockService project and comment out the [Policy] attribute on the `StockService` class.</span></span> <span data-ttu-id="e82f5-175">Spowoduje to wyłączenie zabezpieczeń z przykładu.</span><span class="sxs-lookup"><span data-stu-id="e82f5-175">This disables security from the sample.</span></span> <span data-ttu-id="e82f5-176">Chociaż WCF może współdziałać z bezpiecznymi punktami końcowymi WSE 3,0, zabezpieczenia są wyłączone, aby ten przykład był skoncentrowany na niestandardowym transportie TCP.</span><span class="sxs-lookup"><span data-stu-id="e82f5-176">While WCF can interoperate with WSE 3.0 secure endpoints, security is disabled to keep this sample focused on the custom TCP transport.</span></span>  
  
    4. <span data-ttu-id="e82f5-177">Naciśnij klawisz F5, aby uruchomić `TcpSyncStockService` .</span><span class="sxs-lookup"><span data-stu-id="e82f5-177">Press F5 to start the `TcpSyncStockService`.</span></span> <span data-ttu-id="e82f5-178">Usługa jest uruchamiana w nowym oknie konsoli.</span><span class="sxs-lookup"><span data-stu-id="e82f5-178">The service starts in a new console window.</span></span>  
  
    5. <span data-ttu-id="e82f5-179">Otwórz ten przykład transportu TCP w programie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e82f5-179">Open this TCP transport sample in Visual Studio.</span></span>  
  
    6. <span data-ttu-id="e82f5-180">Zaktualizuj zmienną "hostname" w TestCode.cs, aby odpowiadała nazwie komputera z uruchomionym programem `TcpSyncStockService` .</span><span class="sxs-lookup"><span data-stu-id="e82f5-180">Update the "hostname" variable in TestCode.cs to match the machine name running the `TcpSyncStockService`.</span></span>  
  
    7. <span data-ttu-id="e82f5-181">Naciśnij klawisz F5, aby uruchomić próbkę transportu TCP.</span><span class="sxs-lookup"><span data-stu-id="e82f5-181">Press F5 to start the TCP transport sample.</span></span>  
  
    8. <span data-ttu-id="e82f5-182">Klient testowy transportu TCP uruchamia się w nowej konsoli.</span><span class="sxs-lookup"><span data-stu-id="e82f5-182">The TCP transport test client starts in a new console.</span></span> <span data-ttu-id="e82f5-183">Klient żąda notowań giełdowych z usługi, a następnie wyświetla wyniki w oknie konsoli.</span><span class="sxs-lookup"><span data-stu-id="e82f5-183">The client requests stock quotes from the service and then displays the results in its console window.</span></span>
