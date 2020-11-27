---
title: 'Klient: Fabryki kanałów i kanały'
ms.date: 03/30/2017
ms.assetid: ef245191-fdab-4468-a0da-7c6f25d2110f
ms.openlocfilehash: 2476147d20b1aec27986a01773c3d16fb764c665
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275635"
---
# <a name="client-channel-factories-and-channels"></a>Klient: Fabryki kanałów i kanały

W tym temacie omówiono tworzenie fabryk kanałów i kanałów.  
  
## <a name="channel-factories-and-channels"></a>Fabryki kanałów i kanały  

 Fabryki kanałów są odpowiedzialne za tworzenie kanałów. Kanały utworzone za pomocą fabryk kanałów są używane do wysyłania komunikatów. Kanały te są odpowiedzialne za pobieranie wiadomości z warstwy powyżej, wykonując niezależnie od tego, co jest konieczne, a następnie wysyłając komunikat do poniższej warstwy. Poniższy rysunek ilustruje ten proces.  
  
 ![Fabryki i kanały klienta](./media/wcfc-wcfchannelsigure2highlevelfactgoriesc.gif "wcfc_WCFChannelsigure2HIghLevelFactgoriesc")  
Fabryka kanałów tworzy kanały.  
  
 Po zamknięciu fabryki kanałów są odpowiedzialne za zamknięcie wszelkich utworzonych przez siebie kanałów, które nie zostały jeszcze zamknięte. Należy zauważyć, że model jest asymetryczny w tym miejscu, ponieważ gdy odbiornik kanału jest zamknięty, nie akceptuje tylko nowych kanałów, ale pozostawia otwarte kanały, aby mogły nadal otrzymywać komunikaty.  
  
 Funkcja WCF udostępnia pomocników klasy bazowej dla tego procesu. (Aby zapoznać się z diagramem klas pomocnika kanału omawianych w tym temacie, zobacz temat [model kanału — Omówienie](channel-model-overview.md)).  
  
- <xref:System.ServiceModel.Channels.CommunicationObject>Klasa implementuje <xref:System.ServiceModel.ICommunicationObject> i wymusza komputer stanu opisany w kroku 2 [tworzenia kanałów](developing-channels.md).  
  
- <xref:System.ServiceModel.Channels.ChannelManagerBase>Klasa implementuje <xref:System.ServiceModel.Channels.CommunicationObject> i udostępnia ujednoliconą klasę bazową dla <xref:System.ServiceModel.Channels.ChannelFactoryBase?displayProperty=nameWithType> i <xref:System.ServiceModel.Channels.ChannelListenerBase?displayProperty=nameWithType> . <xref:System.ServiceModel.Channels.ChannelManagerBase>Klasa działa w połączeniu z <xref:System.ServiceModel.Channels.ChannelBase> , która jest klasą bazową implementującą <xref:System.ServiceModel.Channels.IChannel> .
  
- <xref:System.ServiceModel.Channels.ChannelFactoryBase>Klasa implementuje <xref:System.ServiceModel.Channels.ChannelManagerBase> i <xref:System.ServiceModel.Channels.IChannelFactory> konsoliduje `CreateChannel` przeciążenia w jedną `OnCreateChannel` metodę abstrakcyjną.
  
- <xref:System.ServiceModel.Channels.ChannelListenerBase>Klasa implementuje <xref:System.ServiceModel.Channels.IChannelListener> . Dział IT zajmuje się podstawowym zarządzaniem stanem.
  
 Następująca dyskusja jest oparta na przykładowej [transportowej: UDP](../samples/transport-udp.md) .  
  
### <a name="creating-a-channel-factory"></a>Tworzenie fabryki kanałów  

 `UdpChannelFactory`Pochodzi od <xref:System.ServiceModel.Channels.ChannelFactoryBase> . Przykłady zastąpień <xref:System.ServiceModel.Channels.ChannelFactoryBase.GetProperty%2A> w celu zapewnienia dostępu do wersji komunikatu kodera wiadomości. Przykład przesłonił również, aby wypróbować <xref:System.ServiceModel.Channels.ChannelFactoryBase.OnClose%2A> nasze wystąpienie po przeniesieniu <xref:System.ServiceModel.Channels.BufferManager> automatu Stanów.  
  
#### <a name="the-udp-output-channel"></a>Kanał wyjściowy UDP  

 `UdpOutputChannel`Implementacja <xref:System.ServiceModel.Channels.IOutputChannel> . Konstruktor sprawdza poprawność argumentów i konstruuje <xref:System.Net.EndPoint> obiekt docelowy na podstawie <xref:System.ServiceModel.EndpointAddress> przekazanego elementu.  
  
 Przesłonięcie <xref:System.ServiceModel.Channels.CommunicationObject.OnOpen%2A> tworzenia gniazda, które jest używane do wysyłania komunikatów do tego obiektu <xref:System.Net.EndPoint> .  
  
 ```csharp
this.socket = new Socket(  
this.remoteEndPoint.AddressFamily,
   SocketType.Dgram,
   ProtocolType.Udp
);  
```  

 Kanał może być zamknięty bezpiecznie lub bezproblemowo. Jeśli kanał zostanie zamknięty bezpiecznie, gniazdo jest zamknięte i zostanie wykonane wywołanie metody klasy bazowej `OnClose` . W przypadku zgłaszania wyjątku, infrastruktura wywołuje, `Abort` Aby upewnić się, że kanał jest czyszczony.  
  
```csharp  
this.socket.Close();  
base.OnClose(timeout);  
```  
  
 Implementuj `Send()` i `BeginSend()` / `EndSend()` . Ten podział jest podzielony na dwie główne sekcje. Najpierw serializować komunikat do tablicy bajtowej:  
  
```csharp  
ArraySegment<byte> messageBuffer = EncodeMessage(message);  
```  
  
 Następnie Wyślij dane uzyskane z sieci:  
  
```csharp  
this.socket.SendTo(  
  messageBuffer.Array,
  messageBuffer.Offset,
  messageBuffer.Count,
  SocketFlags.None,
  this.remoteEndPoint  
);  
```  
  
## <a name="see-also"></a>Zobacz też

- [Opracowywanie kanałów](developing-channels.md)
