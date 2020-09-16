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
# <a name="transport-wse-30-tcp-interoperability"></a>Transport: Współdziałanie protokołu TCP z usługami WSE 3.0
Przykład transportu współdziałania TCP w programie WSE 3,0 demonstruje sposób implementacji sesji dwustronnej TCP jako transportu niestandardowego Windows Communication Foundation (WCF). Przedstawiono w nim również, jak można użyć rozszerzalności warstwy kanału do interfejsu przez sieć z istniejącymi wdrożonymi systemami. Poniższe kroki pokazują, jak utworzyć niestandardowy transport WCF:  
  
1. Rozpoczynając od gniazda TCP, Utwórz implementacje klienta i serwera <xref:System.ServiceModel.Channels.IDuplexSessionChannel> , które używają ramki Dime do odróżnić granic komunikatów.  
  
2. Utwórz fabrykę kanałów, która łączy się z usługą WSE TCP i wysyła komunikaty z ramkami za pośrednictwem klienta <xref:System.ServiceModel.Channels.IDuplexSessionChannel> s.  
  
3. Utwórz odbiornik kanału, aby akceptować przychodzące połączenia TCP i generować odpowiednie kanały.  
  
4. Upewnij się, że wszystkie wyjątki specyficzne dla sieci są znormalizowane do odpowiedniej klasy pochodnej <xref:System.ServiceModel.CommunicationException> .  
  
5. Dodaj element powiązania, który dodaje niestandardowy transport do stosu kanału. Aby uzyskać więcej informacji, zobacz [Dodawanie elementu powiązania].  
  
## <a name="creating-iduplexsessionchannel"></a>Tworzenie IDuplexSessionChannel  
 Pierwszym krokiem w przypadku transportu współdziałania TCP w systemie WSE 3,0 jest utworzenie implementacji <xref:System.ServiceModel.Channels.IDuplexSessionChannel> na podstawie <xref:System.Net.Sockets.Socket> . `WseTcpDuplexSessionChannel` pochodzi od <xref:System.ServiceModel.Channels.ChannelBase> . Logika wysyłania wiadomości składa się z dwóch głównych elementów: (1) kodowanie wiadomości do bajtów i (2) umieszczanie tych bajtów i wysyłanie ich do sieci.  
  
 `ArraySegment<byte> encodedBytes = EncodeMessage(message);`  
  
 `WriteData(encodedBytes);`  
  
 Ponadto jest wykonywana blokada, dzięki czemu wywołania Send () zachowują gwarancję IDuplexSessionChannel w kolejności i tak, aby wywołania bazowego gniazda były prawidłowo synchronizowane.  
  
 `WseTcpDuplexSessionChannel` używa <xref:System.ServiceModel.Channels.MessageEncoder> do tłumaczenia typu <xref:System.ServiceModel.Channels.Message> do i z bajtu []. Ponieważ jest to transport, `WseTcpDuplexSessionChannel` jest również odpowiedzialny za zastosowanie zdalnego adresu, z którym kanał został skonfigurowany. `EncodeMessage` hermetyzuje logikę dla tej konwersji.  
  
 `this.RemoteAddress.ApplyTo(message);`  
  
 `return encoder.WriteMessage(message, maxBufferSize, bufferManager);`  
  
 Gdy <xref:System.ServiceModel.Channels.Message> program zostanie zakodowany w bajtach, musi być przesyłany w sieci. Wymaga to systemu do definiowania granic komunikatów. WSE 3,0 używa wersji [Dime](/archive/msdn-magazine/2002/december/sending-files-attachments-and-soap-messages-via-dime) jako protokołu szkieletu. `WriteData` hermetyzuje logikę ramek, aby otoczyć bajt [] do zestawu rekordów DIME.  
  
 Logika wysyłania komunikatów jest podobna. Główna złożoność obsługuje fakt, że odczytany przez gniazdo może zwrócić mniejszą liczbę bajtów niż zażądano. Aby odebrać komunikat, program `WseTcpDuplexSessionChannel` odczytuje bajty z sieci, dekoduje ramkę Dime, a następnie używa w <xref:System.ServiceModel.Channels.MessageEncoder> celu wyłączania bajtu [] do <xref:System.ServiceModel.Channels.Message> .  
  
 Podstawą jest `WseTcpDuplexSessionChannel` założenie, że odbierze połączone gniazdo. Klasa bazowa obsługuje zamknięcie gniazda. Istnieją trzy miejsca, w których interfejs ma zamknięcie gniazda:  
  
- OnAbort — Zamknij gniazdo niebezpiecznie (twarde).  
  
- Na [BEGIN] Zamknij--zamykaj gniazdo w sposób łagodny (zamknięcie miękkie).  
  
- obrad. Wywołaniu metody CloseOutputSession — Zamknij strumień danych wychodzących (połowa Close).  
  
## <a name="channel-factory"></a>Fabryka kanałów  
 Następnym krokiem podczas pisania transportu TCP jest utworzenie implementacji <xref:System.ServiceModel.Channels.IChannelFactory> dla kanałów klienta.  
  
- `WseTcpChannelFactory`pochodzi od <xref:System.ServiceModel.Channels.ChannelFactoryBase> \<IDuplexSessionChannel> . Jest to fabryka, która zastępuje `OnCreateChannel` generowanie kanałów klientów.  
  
 `protected override IDuplexSessionChannel OnCreateChannel(EndpointAddress remoteAddress, Uri via)`  
  
 `{`  
  
 `return new ClientWseTcpDuplexSessionChannel(encoderFactory, bufferManager, remoteAddress, via, this);`  
  
 `}`  
  
- `ClientWseTcpDuplexSessionChannel` dodaje logikę do podstawy, `WseTcpDuplexSessionChannel` Aby połączyć się z serwerem TCP w `channel.Open` czasie. Najpierw nazwa hosta jest rozpoznawana jako adres IP, jak pokazano w poniższym kodzie.  
  
 `hostEntry = Dns.GetHostEntry(Via.Host);`  
  
- Następnie nazwa hosta jest połączona z pierwszym dostępnym adresem IP w pętli, jak pokazano w poniższym kodzie.  
  
 `IPAddress address = hostEntry.AddressList[i];`  
  
 `socket = new Socket(address.AddressFamily, SocketType.Stream, ProtocolType.Tcp);`  
  
 `socket.Connect(new IPEndPoint(address, port));`  
  
- W ramach kontraktu kanału wszystkie wyjątki specyficzne dla domeny są opakowane, na przykład `SocketException` w <xref:System.ServiceModel.CommunicationException> .  
  
## <a name="channel-listener"></a>Odbiornik kanału  
 Następnym krokiem podczas pisania transportu TCP jest utworzenie implementacji <xref:System.ServiceModel.Channels.IChannelListener> dla akceptowania kanałów serwera.  
  
- `WseTcpChannelListener`pochodzi od <xref:System.ServiceModel.Channels.ChannelListenerBase> \<IDuplexSessionChannel> i przesłonięcia na [BEGIN] Otwórz i na [BEGIN] Zamknij, aby kontrolować okres istnienia gniazda nasłuchiwania. W obszarze OnOpen gniazdo jest tworzone w celu nasłuchiwania na IP_ANY. Bardziej zaawansowane implementacje mogą również utworzyć drugie gniazdo do nasłuchiwania na protokole IPv6. Mogą również zezwalać na określenie adresu IP w nazwie hosta.  
  
 `IPEndPoint localEndpoint = new IPEndPoint(IPAddress.Any, uri.Port);`  
  
 `this.listenSocket = new Socket(localEndpoint.AddressFamily, SocketType.Stream, ProtocolType.Tcp);`  
  
 `this.listenSocket.Bind(localEndpoint);`  
  
 `this.listenSocket.Listen(10);`  
  
 Po zaakceptowaniu nowego gniazda kanał serwera jest inicjowany za pomocą tego gniazda. Wszystkie dane wejściowe i wyjściowe są już zaimplementowane w klasie bazowej, więc ten kanał jest odpowiedzialny za Inicjowanie gniazda.  
  
## <a name="adding-a-binding-element"></a>Dodawanie elementu powiązania  
 Teraz, gdy fabryki i kanały są kompilowane, muszą one być uwidocznione w środowisku uruchomieniowym ServiceModel za pomocą powiązania. Powiązanie to kolekcja elementów powiązania, które reprezentują stos komunikacji skojarzony z adresem usługi. Każdy element w stosie jest reprezentowany przez element powiązania.  
  
 W przykładzie element Binding ma wartość `WseTcpTransportBindingElement` , która pochodzi od <xref:System.ServiceModel.Channels.TransportBindingElement> . Obsługuje <xref:System.ServiceModel.Channels.IDuplexSessionChannel> i zastępuje następujące metody tworzenia fabryk skojarzonych z naszymi powiązaniami.  
  
 `public IChannelFactory<TChannel> BuildChannelFactory<TChannel>(BindingContext context)`  
  
 `{`  
  
 `return (IChannelFactory<TChannel>)(object)new WseTcpChannelFactory(this, context);`  
  
 `}`  
  
 `public IChannelListener<TChannel> BuildChannelListener<TChannel>(BindingContext context)`  
  
 `{`  
  
 `return (IChannelListener<TChannel>)(object)new WseTcpChannelListener(this, context);`  
  
 `}`  
  
 Zawiera również elementy członkowskie do klonowania `BindingElement` i zwracania naszego schematu (WSE. TCP).  
  
## <a name="the-wse-tcp-test-console"></a>Konsola testowa TCP WSE  
 Kod testowy służący do korzystania z tego przykładowego transportu jest dostępny w TestCode.cs. Poniższe instrukcje przedstawiają sposób konfigurowania `TcpSyncStockService` przykładu WSE.  
  
 Kod testu tworzy niestandardowe powiązanie, które używa MTOM jako kodowania i `WseTcpTransport` jako transportu. Konfiguruje również AddressingVersion, aby była zgodna z WSE 3,0, jak pokazano w poniższym kodzie.  
  
 `CustomBinding binding = new CustomBinding();`  
  
 `MtomMessageEncodingBindingElement mtomBindingElement = new MtomMessageEncodingBindingElement();`  
  
 `mtomBindingElement.MessageVersion = MessageVersion.Soap11WSAddressingAugust2004;`  
  
 `binding.Elements.Add(mtomBindingElement);`  
  
 `binding.Elements.Add(new WseTcpTransportBindingElement());`  
  
 Składa się z dwóch testów — jeden test konfiguruje klienta z określonym typem przy użyciu kodu wygenerowanego na podstawie języka WSDL WSE 3,0. Drugi test używa programu WCF jako klienta i serwera przez wysyłanie komunikatów bezpośrednio na podstawie interfejsów API kanału.  
  
 Podczas uruchamiania przykładu, oczekiwane są następujące dane wyjściowe.  
  
 Klient:  
  
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
  
 Serwer:  
  
```console  
Listening for messages at soap://stockservice.contoso.com/wse/samples/2003/06/TcpSyncStockService  
  
Press any key to exit when done...  
  
Request received.  
Symbols:  
        FABRIKAM  
        CONTOSO  
```  
  
## <a name="set-up-build-and-run-the-sample"></a>Konfigurowanie, kompilowanie i uruchamianie przykładu  
  
1. Aby uruchomić ten przykład, musisz mieć [rozszerzenia usług sieci Web (WSE) 3,0 dla Microsoft .NET](https://www.microsoft.com/download/details.aspx?id=14089) i `TcpSyncStockService` zainstalowaną przykład WSE.
  
> [!NOTE]
> Ponieważ WSE 3,0 nie jest obsługiwany w systemie Windows Server 2008, nie można zainstalować ani uruchomić `TcpSyncStockService` przykładu w tym systemie operacyjnym.  
  
1. Po zainstalowaniu `TcpSyncStockService` przykładu należy wykonać następujące czynności:  
  
    1. Otwórz `TcpSyncStockService` program w programie Visual Studio. (Przykład TcpSyncStockService jest instalowany z WSE 3,0. Nie jest częścią tego przykładowego kodu.)  
  
    2. Ustaw projekt StockService jako projekt startowy.  
  
    3. Otwórz StockService.cs w projekcie StockService i Dodaj komentarz do atrybutu [Policy] w `StockService` klasie. Spowoduje to wyłączenie zabezpieczeń z przykładu. Chociaż WCF może współdziałać z bezpiecznymi punktami końcowymi WSE 3,0, zabezpieczenia są wyłączone, aby ten przykład był skoncentrowany na niestandardowym transportie TCP.  
  
    4. Naciśnij klawisz F5, aby uruchomić `TcpSyncStockService` . Usługa jest uruchamiana w nowym oknie konsoli.  
  
    5. Otwórz ten przykład transportu TCP w programie Visual Studio.  
  
    6. Zaktualizuj zmienną "hostname" w TestCode.cs, aby odpowiadała nazwie komputera z uruchomionym programem `TcpSyncStockService` .  
  
    7. Naciśnij klawisz F5, aby uruchomić próbkę transportu TCP.  
  
    8. Klient testowy transportu TCP uruchamia się w nowej konsoli. Klient żąda notowań giełdowych z usługi, a następnie wyświetla wyniki w oknie konsoli.
