---
title: Dane struktury usługi
ms.date: 03/30/2017
ms.assetid: 2a2c8ddc-4e82-4e7f-a79f-97085c469517
ms.openlocfilehash: 8bb6e9df6a77eda5875981a0bf7783f50671a589
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96255783"
---
# <a name="service-framework-data"></a>Dane struktury usługi

W tym temacie wymieniono wszystkie wyjątki wygenerowane przez dane struktury usługi.  
  
## <a name="exception-list"></a>Lista wyjątków  
  
|Kod zasobu|Ciąg zasobu|  
|-------------------|---------------------|  
|AddressingExtensionInBadNS|Określony element w określonej przestrzeni nazw jest nieprawidłowy. Oznacza to, że określony element jest duplikatem elementu lub że nie jest to dozwolone rozszerzenie, ponieważ elementy rozszerzenia nie mogą znajdować się w przestrzeni nazw adresowania.|  
|BinaryEncoderSessionInvalid|Sesja kodera binarnego jest nieprawidłowa, ponieważ wystąpił błąd podczas dekodowania poprzedniego komunikatu.|  
|CannotDetectAddressingVersion|Nie można wykryć wersji WS-Addressing. Element EndpointAddress nie zaczyna się od elementu.|  
|CouldNotFindNamespaceForPrefix|Określony prefiks nie ma powiązania przestrzeni nazw w zakresie.|  
|EncoderBadContentType|Nie można przetworzyć do ContentType.|  
|EncoderEnvelopeVersionMismatch|Wersja koperty określonego komunikatu przychodzącego nie jest zgodna z określonym koderem. Upewnij się, że powiązanie ma skonfigurowaną taką samą wersję jak oczekiwane komunikaty.|  
|EncoderMessageVersionMismatch|Wersja komunikatu określonego komunikatu wychodzącego nie jest zgodna z określonym koderem. Upewnij się, że powiązanie ma skonfigurowaną taką samą wersję, jak komunikat.|  
|ExtraContentIsPresentInFaultDetail|Dodatkowa zawartość XML jest obecna w elemencie szczegóły błędu. Dozwolony jest tylko jeden element.|  
|FilterBadTableType|IMessageFilterTable utworzony dla filtru nie może być elementem obiektem ani pochodzącym z obiektem.|  
|FilterTableInvalidForLookup|Stan obiektem jest uszkodzony. Nie można wykonać żądanego wyszukiwania.|  
|MandatoryHeaderNotUnderstood|Co najmniej jeden wymagany blok nagłówka prostego dostępu do obiektów jest niezrozumiały.|  
|MessageBodyIsStream|Treść komunikatu jest strumieniem.|  
|MessageBodyIsUnknown|Format treści komunikatu jest nieznany.|  
|MessageBodyReaderInvalidReadState|Określony stanie ReadState czytnika treści wiadomości nie może zostać użyty.|  
|MessageTextEncodingNotSupported|Określone kodowanie tekstu używane w formacie wiadomości tekstowej nie jest obsługiwane.|  
|MissingMessageID|W komunikacie żądania brakuje nagłówka MessageID. Nagłówek MessageID jest wymagany do skorelowania odpowiedzi.|  
|MultipleMessageHeaders|Znaleziono więcej niż jeden nagłówek o określonej nazwie i przestrzeni nazw.|  
|MultipleMessageHeadersWithActor|Znaleziono więcej niż jeden nagłówek o określonej nazwie, przestrzeni nazw i roli.|  
|MultipleRelatesToHeaders|Znaleziono więcej niż jeden nagłówek RelatesTo z określoną relacją. Dla każdej relacji jest dozwolony tylko jeden.|  
|QueryFunctionTypeNotSupported|Określony typ zwracany dla IXsltContextFunction nie jest obsługiwany.|  
|QueryIteratorOutOfScope|XPathNodeIterator zostało unieważnione. XPathNodeIterators, które są przekazane jako argumenty do IXsltContextFunctions, są prawidłowe tylko w obrębie funkcji. Nie mogą być buforowane do późniejszego użycia lub zwracane przez funkcję.|  
|QueryVariableNull|Metody IXsltContextVariable nie mogą zwracać wartości null.|  
|QueryVariableTypeNotSupported|Określony typ pochodny IXsltContextVariable nie jest obsługiwany.|  
|ReceiveShutdownReturnedMessage|W kanale Odebrano nieoczekiwany komunikat wejściowy z określoną akcją podczas zamykania. Zamknij kanał, gdy nie oczekujesz więcej komunikatów wejściowych.|  
|XmlBufferInInvalidState|Wystąpił błąd wewnętrzny. Nie można wykonać operacji ze względu na stan buforu XML.|  
|XmlBufferQuotaExceeded|Rozmiar wymagany do buforowania zawartości XML przekroczył limit przydziału buforu.|
