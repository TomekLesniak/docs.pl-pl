---
title: 216 — MessageSentByTransport
ms.date: 03/30/2017
ms.assetid: 150c3167-4154-4225-8d94-57cc94341233
ms.openlocfilehash: b3e9e1a48951ad5a2e5e7820dc1828c20e310635
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96278911"
---
# <a name="216---messagesentbytransport"></a>216 — MessageSentByTransport

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID (Identyfikator)|216|  
|Słowa kluczowe|Rozwiązywanie problemów, ServiceModel|  
|Poziom|Informacje|  
|Kanał|Microsoft-Windows-Application Server-Applications/Analytics|  
  
## <a name="description"></a>Opis  

 To zdarzenie występuje, gdy transport oparty na protokole TCP wysyła komunikat. Należy pamiętać, że na poziomie transportu wiele komunikatów może być wymienianych między klientami i usługami w ramach jednej operacji. Może to być spowodowane zachowaniem infrastruktury, dobrym przykładem. W związku z tym liczba zdarzeń **MessageSentByTransport** , które są emitowane, różni się w zależności od powiązania i konfiguracji usługi.  
  
## <a name="message"></a>Wiadomość  

 Transport wysłał komunikat do "%1".  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|DestinationAddress|`xs:string`|Adres, na który jest wysyłany komunikat żądania.|  
|HostReference|XS: ciąg|W przypadku usług hostowanych w sieci Web to pole jednoznacznie identyfikuje usługę w hierarchii sieci Web. Jego format jest zdefiniowany jako ścieżka wirtualna aplikacji nazwa witryny sieci Web&#124;wirtualnej ścieżki usługi&#124;ServiceName '. Przykład: "Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".|  
|Wywołując|`xs:string`|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
