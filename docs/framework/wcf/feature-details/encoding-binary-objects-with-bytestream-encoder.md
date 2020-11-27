---
title: Kodowanie obiektów binarnych za pomocą kodera elementu ByteStream
ms.date: 03/30/2017
ms.assetid: 020ee981-c889-4b12-a3ea-91823ef46444
ms.openlocfilehash: cc63cb8de1e245c3b58fb69819e59cb815b777d3
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96276740"
---
# <a name="encoding-binary-objects-with-bytestream-encoder"></a>Kodowanie obiektów binarnych za pomocą kodera elementu ByteStream

Wysyłanie i otrzymywanie nieprzetworzonych danych binarnych za pomocą Windows Communication Foundation (WCF) jest konfigurowane przy użyciu <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement> .  
  
## <a name="byte-stream-message-encoder-architecture"></a>Architektura kodera komunikatów strumienia bajtów  

 Koder komunikatów binarnych używany przez funkcję WCF nie ma funkcji do przetwarzania, weryfikowania lub identyfikowania źródłowych danych binarnych w komunikacie. Pakiet danych został zakodowany w formacie XML, wysłany, odebrany i zdekodowany. Koder przetwarza dane po przekazaniu ich do transportu i przed wysłaniem komunikatu do kolejki komunikatów. Funkcjonalnie koder binarny otacza dane komunikatów w `<binary>` elementach do wysłania i usuwa elementy po odebraniu komunikatu.  
  
## <a name="using-the-byte-stream-message-encoder"></a>Używanie kodera komunikatów strumienia bajtów  

 W poniższym przykładzie przedstawiono kontrakt usługi implementujący koder komunikatów strumienia bajtów.  
  
```csharp  
[OperationContract]  
Void Myfunction(Stream stream);  
```  
  
 Poniższy przykład pokazuje wywoływaną usługę.  
  
```csharp  
proxy.MyFunction(stream);  
```  
  
 W przypadku korzystania z usługi implementującej infrastrukturę komunikatów (na przykład router) komunikat jest przetwarzany bez inspekcji, sprawdzania poprawności lub w inny sposób z komunikatem, jak pokazano w poniższym przykładzie.  
  
```csharp  
[OperationContract]  
void ProcessMessage(Message message) ;  
```  
  
## <a name="scenarios"></a>Scenariusze  

 Koder strumienia bajtów jest przydatny w następujących scenariuszach.  
  
- Przenoszenie obrazu JPEG między komputerami przy użyciu programu WCF. W tym scenariuszu obraz zostanie przychodzący przez transport ze źródła zewnętrznego, a wysyłane dane będą nieprzetworzonymi bajtami, które tworzą obraz. Usługa otrzyma dane binarne i wyświetli obraz.  
  
- Odczytywanie informacji z kolejki komunikatów i przetwarzanie jej. Wiadomość zostanie odczytana z Menedżera kolejki komunikatów i przeszedł do obsługi kanału kolejki komunikatów. Kanał kolejki komunikatów będzie pełnić rolę Menedżera kolejki w stosie kanału WCF.  
  
 W przypadku wysyłania komunikatu przez kanał kolejki komunikatów nadawca nie kontroluje bajtów odebranych od Menedżera kolejki. Jeśli proces odbierający nie ma możliwości odczytu nieprzetworzonych bajtów, komunikat zostanie odebrany jako niepoprawnie sformatowany i nie zostanie przetworzony. przyjęto założenie, że proces odbierający będzie miał możliwość przetłumaczenia odebranych bajtów z powrotem na przydatny format.
