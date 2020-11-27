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
# <a name="encoding-binary-objects-with-bytestream-encoder"></a><span data-ttu-id="2ae76-102">Kodowanie obiektów binarnych za pomocą kodera elementu ByteStream</span><span class="sxs-lookup"><span data-stu-id="2ae76-102">Encoding Binary Objects with ByteStream Encoder</span></span>

<span data-ttu-id="2ae76-103">Wysyłanie i otrzymywanie nieprzetworzonych danych binarnych za pomocą Windows Communication Foundation (WCF) jest konfigurowane przy użyciu <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement> .</span><span class="sxs-lookup"><span data-stu-id="2ae76-103">Sending and receiving raw binary data with Windows Communication Foundation (WCF) is configured using <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>.</span></span>  
  
## <a name="byte-stream-message-encoder-architecture"></a><span data-ttu-id="2ae76-104">Architektura kodera komunikatów strumienia bajtów</span><span class="sxs-lookup"><span data-stu-id="2ae76-104">Byte Stream Message Encoder Architecture</span></span>  

 <span data-ttu-id="2ae76-105">Koder komunikatów binarnych używany przez funkcję WCF nie ma funkcji do przetwarzania, weryfikowania lub identyfikowania źródłowych danych binarnych w komunikacie.</span><span class="sxs-lookup"><span data-stu-id="2ae76-105">The binary message encoder used by WCF has no facility for processing, validating, or identifying the underlying binary data in the message.</span></span> <span data-ttu-id="2ae76-106">Pakiet danych został zakodowany w formacie XML, wysłany, odebrany i zdekodowany.</span><span class="sxs-lookup"><span data-stu-id="2ae76-106">The data package is encoded into XML, sent, received, and decoded.</span></span> <span data-ttu-id="2ae76-107">Koder przetwarza dane po przekazaniu ich do transportu i przed wysłaniem komunikatu do kolejki komunikatów.</span><span class="sxs-lookup"><span data-stu-id="2ae76-107">The encoder processes the data after being passed to the transport and before the message is sent to the message queue.</span></span> <span data-ttu-id="2ae76-108">Funkcjonalnie koder binarny otacza dane komunikatów w `<binary>` elementach do wysłania i usuwa elementy po odebraniu komunikatu.</span><span class="sxs-lookup"><span data-stu-id="2ae76-108">Functionally, the binary encoder wraps the message data in `<binary>` elements for sending and removes the elements after the message is received.</span></span>  
  
## <a name="using-the-byte-stream-message-encoder"></a><span data-ttu-id="2ae76-109">Używanie kodera komunikatów strumienia bajtów</span><span class="sxs-lookup"><span data-stu-id="2ae76-109">Using the Byte Stream Message Encoder</span></span>  

 <span data-ttu-id="2ae76-110">W poniższym przykładzie przedstawiono kontrakt usługi implementujący koder komunikatów strumienia bajtów.</span><span class="sxs-lookup"><span data-stu-id="2ae76-110">The following example shows a service contract that implements the byte stream message encoder.</span></span>  
  
```csharp  
[OperationContract]  
Void Myfunction(Stream stream);  
```  
  
 <span data-ttu-id="2ae76-111">Poniższy przykład pokazuje wywoływaną usługę.</span><span class="sxs-lookup"><span data-stu-id="2ae76-111">The following example shows the service being invoked.</span></span>  
  
```csharp  
proxy.MyFunction(stream);  
```  
  
 <span data-ttu-id="2ae76-112">W przypadku korzystania z usługi implementującej infrastrukturę komunikatów (na przykład router) komunikat jest przetwarzany bez inspekcji, sprawdzania poprawności lub w inny sposób z komunikatem, jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="2ae76-112">In the case of using a service that implements a message infrastructure (such as a router), the message is processed without inspecting, validating, or otherwise interacting with the message, as shown in the following example.</span></span>  
  
```csharp  
[OperationContract]  
void ProcessMessage(Message message) ;  
```  
  
## <a name="scenarios"></a><span data-ttu-id="2ae76-113">Scenariusze</span><span class="sxs-lookup"><span data-stu-id="2ae76-113">Scenarios</span></span>  

 <span data-ttu-id="2ae76-114">Koder strumienia bajtów jest przydatny w następujących scenariuszach.</span><span class="sxs-lookup"><span data-stu-id="2ae76-114">The Byte Stream Encoder is useful in the following scenarios.</span></span>  
  
- <span data-ttu-id="2ae76-115">Przenoszenie obrazu JPEG między komputerami przy użyciu programu WCF.</span><span class="sxs-lookup"><span data-stu-id="2ae76-115">Transferring a JPEG image between computers using WCF.</span></span> <span data-ttu-id="2ae76-116">W tym scenariuszu obraz zostanie przychodzący przez transport ze źródła zewnętrznego, a wysyłane dane będą nieprzetworzonymi bajtami, które tworzą obraz.</span><span class="sxs-lookup"><span data-stu-id="2ae76-116">In this scenario, the image will arrive through the transport from an outside source, and the data sent will be the raw bytes that make up the image.</span></span> <span data-ttu-id="2ae76-117">Usługa otrzyma dane binarne i wyświetli obraz.</span><span class="sxs-lookup"><span data-stu-id="2ae76-117">A service will receive the binary data and display the image.</span></span>  
  
- <span data-ttu-id="2ae76-118">Odczytywanie informacji z kolejki komunikatów i przetwarzanie jej.</span><span class="sxs-lookup"><span data-stu-id="2ae76-118">Reading information out of a message queue and processing it.</span></span> <span data-ttu-id="2ae76-119">Wiadomość zostanie odczytana z Menedżera kolejki komunikatów i przeszedł do obsługi kanału kolejki komunikatów.</span><span class="sxs-lookup"><span data-stu-id="2ae76-119">The message will be read from a message queue manager, and passed up the message queue channel to be handled.</span></span> <span data-ttu-id="2ae76-120">Kanał kolejki komunikatów będzie pełnić rolę Menedżera kolejki w stosie kanału WCF.</span><span class="sxs-lookup"><span data-stu-id="2ae76-120">The message queue channel will act as a queue manager in the WCF channel stack.</span></span>  
  
 <span data-ttu-id="2ae76-121">W przypadku wysyłania komunikatu przez kanał kolejki komunikatów nadawca nie kontroluje bajtów odebranych od Menedżera kolejki.</span><span class="sxs-lookup"><span data-stu-id="2ae76-121">In the case of sending a message over a message queue channel, the sender has no control over the bytes received from the queue manager.</span></span> <span data-ttu-id="2ae76-122">Jeśli proces odbierający nie ma możliwości odczytu nieprzetworzonych bajtów, komunikat zostanie odebrany jako niepoprawnie sformatowany i nie zostanie przetworzony. przyjęto założenie, że proces odbierający będzie miał możliwość przetłumaczenia odebranych bajtów z powrotem na przydatny format.</span><span class="sxs-lookup"><span data-stu-id="2ae76-122">If the receiving process has no capability to read raw bytes, the message will be received as badly formatted and will not be processed; it is assumed that the receiving process will have the capability of translating the received bytes back into a usable format.</span></span>
