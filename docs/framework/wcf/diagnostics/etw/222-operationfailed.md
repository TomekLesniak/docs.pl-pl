---
title: 222 — OperationFailed
ms.date: 03/30/2017
ms.assetid: 6b530ded-8f20-4d78-8bfe-1875276df6ba
ms.openlocfilehash: 64b41ee78e943ca16eaa791133454ec62ccf6ed8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96263090"
---
# <a name="222---operationfailed"></a>222 — OperationFailed

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID (Identyfikator)|222|  
|Słowa kluczowe|EndToEndMonitoring, HealthMonitoring, rozwiązywanie problemów, ServiceModel|  
|Poziom|Ostrzeżenie|  
|Kanał|Microsoft-Windows-Application Server-Applications/Analytics|  
  
## <a name="description"></a>Opis  

 To zdarzenie jest emitowane, gdy domyślny model usługi `OperationInvoker` napotkał wyjątek podczas wywoływania jego metody. Należy zauważyć, że wyjątki, które wynikają z `FaultException` spowodowania tego zdarzenia, nie są emitowane.  
  
## <a name="message"></a>Wiadomość  

 Metoda "%1" zgłosiła nieobsługiwany wyjątek podczas wywoływania przez OperationInvoker. Czas trwania wywołania metody to "%2" MS.  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|Nazwa metody|`xs:string`|Nazwa środowiska CLR metody, która została wywołana przez `OperationInvoker` .|  
|Czas trwania|`xs:long`|Czas (w milisekundach), przez który miało `OperationInvoker` wywołać metodę.|  
|HostReference|`xs:string`|W przypadku usług hostowanych w sieci Web to pole jednoznacznie identyfikuje usługę w hierarchii sieci Web. Jego format jest zdefiniowany jako ścieżka wirtualna aplikacji nazwa witryny sieci Web&#124;wirtualnej ścieżki usługi&#124;ServiceName '. Przykład: "Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".|  
|Wywołując|`xs:string`|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
