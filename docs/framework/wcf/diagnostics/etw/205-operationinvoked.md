---
title: 205 — OperationInvoked
ms.date: 03/30/2017
ms.assetid: 9c8d6c90-dfa5-4ae0-a589-96679a8fb3ba
ms.openlocfilehash: c36294a4a430c3e372e8213246e85dba45ce03c8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96286022"
---
# <a name="205---operationinvoked"></a>205 — OperationInvoked

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID (Identyfikator)|205|  
|Słowa kluczowe|Rozwiązywanie problemów, ServiceModel|  
|Poziom|Informacje|  
|Kanał|Microsoft-Windows-Application Server-Applications/Analytics|  
  
## <a name="description"></a>Opis  

 To zdarzenie jest emitowane tuż przed rozpoczęciem domyślnego modelu usługi `OperationInvoker` wywołanie metody.  
  
## <a name="message"></a>Wiadomość  

 OperationInvoker wywołała metodę ' %1 '. Informacje o wywołującym: ' %2 '.  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|Nazwa metody|`xs:string`|Nazwa środowiska CLR metody, która została wywołana przez `OperationInvoker` .|  
|Informacje o wywołującym|`xs:string`|Adres IP i numer portu klienta w formacie "IPAddress: numer_portu". Dwie wartości są pobierane z właściwości komunikatu "System. ServiceModel. Channels. RemoteEndpointMessageProperty" w ramach kontekstu operacji. Należy pamiętać, że w przypadku powiązań innych niż TCP ta wartość `null` .|  
|HostReference|`xs:string`|W przypadku usług hostowanych w sieci Web to pole jednoznacznie identyfikuje usługę w hierarchii sieci Web. Jego format jest zdefiniowany jako ścieżka wirtualna aplikacji nazwa witryny sieci Web&#124;wirtualnej ścieżki usługi&#124;ServiceName '. Przykład: "Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".|  
|Wywołując|`xs:string`|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
