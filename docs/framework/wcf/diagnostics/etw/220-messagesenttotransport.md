---
title: 220 — MessageSentToTransport
ms.date: 03/30/2017
ms.assetid: aef4e781-240b-45bc-bff8-400053037e71
ms.openlocfilehash: 1b63877998ea7942886c83d8795fe5ee49fdf053
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96241931"
---
# <a name="220---messagesenttotransport"></a>220 — MessageSentToTransport

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|Id|220|  
|Słowa kluczowe|EndToEndMonitoring, rozwiązywanie problemów, ServiceModel|  
|Poziom|Informacje|  
|Kanał|Microsoft-Windows-Application Server-Applications/Analytics|  
  
## <a name="description"></a>Opis  

 To zdarzenie jest emitowane, gdy model usługi wysyła komunikat do transportu.  
  
> [!NOTE]
> To zdarzenie nie będzie emitowane w przypadku transportów jednokierunkowych.  
  
## <a name="message"></a>Wiadomość  

 Dyspozytor wysłał komunikat do transportu. Identyfikator korelacji = = ' %1 '.  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|Identyfikator korelacji|`xs:GUID`|Identyfikator działania służący do skorelowania `MessageSentToTransport` zdarzenia z usługi lub klienta do jego odpowiadającego `MessageReceivedFromTransport` na drugim końcu.|  
|HostReference|`xs:string`|W przypadku usług hostowanych w sieci Web to pole jednoznacznie identyfikuje usługę w hierarchii sieci Web. Jego format jest zdefiniowany jako ścieżka wirtualna aplikacji nazwa witryny sieci Web&#124;wirtualnej ścieżki usługi&#124;ServiceName '. Przykład: "Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".|  
|Wywołując|`xs:string`|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
