---
title: Programowanie na poziomie kanału usługi
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8d8dcd85-0a05-4c44-8861-4a0b3b90cca9
ms.openlocfilehash: db50d385bd396ba4de74e08fc1c6d93a67f320b7
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96290221"
---
# <a name="service-channel-level-programming"></a>Programowanie na poziomie kanału usługi

W tym temacie opisano sposób pisania aplikacji usługi Windows Communication Foundation (WCF) bez użycia <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType> i skojarzonego z nią modelu obiektów.  
  
## <a name="receiving-messages"></a>Otrzymywanie komunikatów  

 Aby zapewnić gotowość do odbierania i przetwarzania komunikatów, wymagane są następujące kroki:  
  
1. Utwórz powiązanie.  
  
2. Kompiluj odbiornik kanału.  
  
3. Otwórz odbiornik kanału.  
  
4. Przeczytaj żądanie i Wyślij odpowiedź.  
  
5. Zamknij wszystkie obiekty kanału.  
  
#### <a name="creating-a-binding"></a>Tworzenie powiązania  

 Pierwszym krokiem w nasłuchiwaniu i odbieraniu komunikatów jest utworzenie powiązania. Usługa WCF jest dostarczana z kilkoma wbudowanymi lub dostarczonymi w systemie powiązaniami, które mogą być używane bezpośrednio przez utworzenie wystąpienia jednego z nich. Ponadto można również utworzyć własne niestandardowe powiązanie, tworząc wystąpienie klasy CustomBinding, która jest kodem na liście 1.  
  
 Poniższy przykład kodu tworzy wystąpienie klasy <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType> i dodaje <xref:System.ServiceModel.Channels.HttpTransportBindingElement?displayProperty=nameWithType> do jej kolekcji elementów, która jest kolekcją elementów powiązania, które są używane do tworzenia stosu kanału. W tym przykładzie, ponieważ kolekcja elementów ma tylko ten <xref:System.ServiceModel.Channels.HttpTransportBindingElement> , utworzony stos kanałów ma tylko kanał transportu HTTP.  
  
#### <a name="building-a-channellistener"></a>Kompilowanie elementu ChannelListener  

 Po utworzeniu powiązania wywoływana jest <xref:System.ServiceModel.Channels.Binding.BuildChannelListener%2A?displayProperty=nameWithType> kompilacja odbiornika kanału, gdzie parametr typu jest kształtem kanału do utworzenia. W tym przykładzie używamy metody <xref:System.ServiceModel.Channels.IReplyChannel?displayProperty=nameWithType> , ponieważ chcemy słuchać komunikatów przychodzących w wzorcu wymiany komunikatów żądania/odpowiedzi.  
  
 <xref:System.ServiceModel.Channels.IReplyChannel> służy do otrzymywania komunikatów żądań i wysyłania komunikatów odpowiedzi. Wywołanie <xref:System.ServiceModel.Channels.IReplyChannel.ReceiveRequest%2A?displayProperty=nameWithType> zwraca metodę <xref:System.ServiceModel.Channels.IRequestChannel?displayProperty=nameWithType> , która może zostać użyta do odebrania komunikatu żądania i wysłania wiadomości odpowiedzi.  
  
 Podczas tworzenia odbiornika przekazujemy adres sieciowy, na którym nasłuchuje, w tym przypadku `http://localhost:8080/channelapp` . Ogólnie rzecz biorąc każdy kanał transportowy obsługuje jeden lub prawdopodobnie kilka schematów adresów, na przykład transport HTTP obsługuje schematy http i https.  
  
 Podczas tworzenia odbiornika przeszedł również pustą <xref:System.ServiceModel.Channels.BindingParameterCollection?displayProperty=nameWithType> wartość. Parametr powiązania jest mechanizmem do przekazywania parametrów, które kontrolują sposób kompilowania odbiornika. W naszym przykładzie nie używamy żadnych parametrów, więc przejdziemy do pustej kolekcji.  
  
#### <a name="listening-for-incoming-messages"></a>Nasłuchiwanie wiadomości przychodzących  

 Następnie wywołajmy <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> na odbiorniku i zaczniemy akceptować kanały. Zachowanie zależy od tego <xref:System.ServiceModel.Channels.IChannelListener%601.AcceptChannel%2A?displayProperty=nameWithType> , czy transport jest zorientowany na połączenia, czy też bez połączenia. W przypadku transportów ukierunkowanych na połączenia <xref:System.ServiceModel.Channels.IChannelListener%601.AcceptChannel%2A> bloki do momentu, w którym zostanie wysłane nowe żądanie połączenia, w tym momencie zwraca nowy kanał reprezentujący nowe połączenie. W przypadku transportów bez połączenia, takich jak HTTP, <xref:System.ServiceModel.Channels.IChannelListener%601.AcceptChannel%2A> zwraca natychmiast z jedynym kanałem, który tworzy odbiornik transportowy.  
  
 W tym przykładzie odbiornik zwraca kanał, który implementuje <xref:System.ServiceModel.Channels.IReplyChannel> . Aby odbierać komunikaty w tym kanale, najpierw dzwonimy <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> do niego w stanie gotowym do komunikacji. Następnie nazywamy <xref:System.ServiceModel.Channels.IReplyChannel.ReceiveRequest%2A> bloki do momentu odebrania komunikatu.  
  
#### <a name="reading-the-request-and-sending-a-reply"></a>Odczytywanie żądania i wysyłanie odpowiedzi  

 Gdy <xref:System.ServiceModel.Channels.IReplyChannel.ReceiveRequest%2A> zwraca <xref:System.ServiceModel.Channels.RequestContext> , otrzymamy odebrany komunikat przy użyciu jego <xref:System.ServiceModel.Channels.RequestContext.RequestMessage%2A> właściwości. Zapisujemy treść wiadomości i zawartość treści (Załóżmy, że jest to ciąg).  
  
 Aby wysłać odpowiedź, w tym przypadku tworzymy nowy komunikat odpowiedzi z powrotem do danych ciągu otrzymanego w żądaniu. Następnie wywołajmy <xref:System.ServiceModel.Channels.RequestContext.Reply%2A> , aby wysłać wiadomość odpowiedzi.  
  
#### <a name="closing-objects"></a>Zamykanie obiektów  

 Aby uniknąć przecieków zasobów, bardzo ważne jest, aby zamknąć obiekty używane w komunikacji, gdy nie są już wymagane. W tym przykładzie zamknie komunikat żądania, kontekst żądania, kanał i odbiornik.  
  
 Poniższy przykład kodu przedstawia podstawową usługę, w której odbiornik kanału odbiera tylko jeden komunikat. Rzeczywista usługa przechowuje kanały i odbiera komunikaty do momentu zakończenia usługi.  
  
 [!code-csharp[ChannelProgrammingBasic#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/channelprogrammingbasic/cs/serviceprogram.cs#1)]
 [!code-vb[ChannelProgrammingBasic#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/channelprogrammingbasic/vb/serviceprogram.vb#1)]
