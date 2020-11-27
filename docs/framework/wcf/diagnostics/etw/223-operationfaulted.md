---
title: 223 — OperationFaulted
ms.date: 03/30/2017
ms.assetid: 2f7d89d7-3a6a-40fe-9610-5424eb6bbf61
ms.openlocfilehash: 310e91320d27dd9817302fc14ef088d180152b73
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96263077"
---
# <a name="223---operationfaulted"></a>223 — OperationFaulted

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID (Identyfikator)|223|  
|Słowa kluczowe|EndToEndMonitoring, HealthMonitoring, rozwiązywanie problemów, ServiceModel|  
|Poziom|Ostrzeżenie|  
|Kanał|Microsoft-Windows-Application Server-Applications/Analytics|  
  
## <a name="description"></a>Opis  

 To zdarzenie jest emitowane, gdy domyślny model usługi `OperationInvoker` napotkał wyjątek wynikający z `FaultException` wywołania podczas wywoływania metody.  
  
## <a name="message"></a>Wiadomość  

 Metoda "%1" zgłosiła wyjątek FaultException w przypadku wywołania przez OperationInvoker. Czas trwania wywołania metody to "%2" MS.  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|MethodName|`xs:string`|Nazwa środowiska CLR metody, która została wywołana przez `OperationInvoker` .|  
|Czas trwania|`xs:long`|Czas (w milisekundach), przez który miało `OperationInvoker` wywołać metodę.|  
|HostReference|`xs:string`|W przypadku usług hostowanych w sieci Web to pole jednoznacznie identyfikuje usługę w hierarchii sieci Web. Jego format jest zdefiniowany jako ścieżka wirtualna aplikacji nazwa witryny sieci Web&#124;wirtualnej ścieżki usługi&#124;ServiceName '. Przykład: "Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".|  
|Wywołując|`xs:string`|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
