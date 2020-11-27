---
title: Niestandardowe elementy formatujące komunikaty
ms.date: 03/30/2017
ms.assetid: c07435f3-5214-4791-8961-2c2b61306d71
ms.openlocfilehash: e238eb134772c0a95934a460edda62ca9dba2518
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96254756"
---
# <a name="custom-message-formatters"></a>Niestandardowe elementy formatujące komunikaty

Zawartość komunikatu jest często w postaci pliku XML, który zwykle nie jest wygodnym formatem aplikacji. Aplikacje manipulowanie obiektami, pobieranie i Ustawianie ich właściwości. Windows Communication Foundation (WCF) używa *kontraktu danych* do konwersji <xref:System.ServiceModel.Channels.Message> obiektu do obiektu, który można łatwo obsłużyć przez aplikację. Procesy te są nazywane serializacji i deserializacji. Należy zauważyć, że te same terminy są używane do opisywania serializacji i deserializacji wykonywanej przez warstwę transportu do i z formatu transportowego, który jest procesem niepowiązanym.  
  
 Niestandardowego programu formatującego komunikaty można użyć, jeśli trzeba zaimplementować wyspecjalizowaną konwersję między komunikatami i obiektami, których nie można osiągnąć za pomocą kontraktu danych. W tym celu należy zmodyfikować lub rozszerzyć zachowanie wykonywania konkretnej operacji kontraktu na kliencie lub usłudze.  
  
## <a name="custom-message-formatters-on-the-client"></a>Niestandardowe elementy formatujące komunikaty na kliencie  

 <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter>Interfejs definiuje metody, które są używane do sterowania konwersją komunikatów do obiektów i obiektów w wiadomości dla aplikacji klienckich.  
  
 Należy zaimplementować ten interfejs. Najpierw Zastąp <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter.DeserializeReply%2A> metodę, aby deserializować komunikat. Ta metoda jest wywoływana po odebraniu komunikatu przychodzącego, ale przed wysłaniem go do operacji klienta.  
  
 Następnie zastąp <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter.SerializeRequest%2A> metodę serializacji obiektu. Ta metoda jest wywoływana przed wysłaniem komunikatu wychodzącego.  
  
 Aby wstawić niestandardowy program formatujący do aplikacji usługi, przypisz <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter> obiekt do <xref:System.ServiceModel.Dispatcher.ClientOperation.Formatter%2A> właściwości przy użyciu zachowania operacji. Aby uzyskać informacje o zachowaniach, zobacz [Konfigurowanie i rozszerzanie środowiska uruchomieniowego za pomocą zachowań](configuring-and-extending-the-runtime-with-behaviors.md).  
  
## <a name="custom-message-formatters-on-the-service"></a>Niestandardowe elementy formatujące wiadomości w usłudze  

 <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter>Interfejs definiuje metody, które konwertują <xref:System.ServiceModel.Channels.Message> obiekt na parametry dla operacji i z parametrów do <xref:System.ServiceModel.Channels.Message> obiektu w aplikacji usługi.  
  
 Należy zaimplementować ten interfejs. Najpierw Zastąp <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter.DeserializeReply%2A> metodę, aby deserializować komunikat. Ta metoda jest wywoływana po odebraniu komunikatu przychodzącego, ale przed wysłaniem go do operacji klienta.  
  
 Następnie zastąp <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter.SerializeRequest%2A> metodę serializacji obiektu. Ta metoda jest wywoływana przed wysłaniem komunikatu wychodzącego.  
  
 Aby wstawić niestandardowy program formatujący do aplikacji usługi, przypisz <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter> obiekt do <xref:System.ServiceModel.Dispatcher.DispatchOperation.Formatter%2A> właściwości przy użyciu zachowania operacji. Aby uzyskać informacje o zachowaniach, zobacz [Konfigurowanie i rozszerzanie środowiska uruchomieniowego za pomocą zachowań](configuring-and-extending-the-runtime-with-behaviors.md).  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter>
- <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter>
- [Konfigurowanie i rozszerzanie środowiska uruchomieniowego za pomocą zachowań](configuring-and-extending-the-runtime-with-behaviors.md)
