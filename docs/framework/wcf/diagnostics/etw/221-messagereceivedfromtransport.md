---
title: 221 — MessageReceivedFromTransport
ms.date: 03/30/2017
ms.assetid: 4995f0d5-c182-4d97-981f-6951da6df1fb
ms.openlocfilehash: 47e871b70e3ef2419543b4710c2988736665cb46
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96263103"
---
# <a name="221---messagereceivedfromtransport"></a>221 — MessageReceivedFromTransport

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID (Identyfikator)|221|  
|Słowa kluczowe|EndToEndMonitoring, rozwiązywanie problemów, ServiceModel|  
|Poziom|Informacje|  
|Kanał|Microsoft-Windows-Application Server-Applications/Analytics|  
  
## <a name="description"></a>Opis  

 To zdarzenie jest emitowane, gdy model usługi odbiera komunikat z transportu.  
  
## <a name="message"></a>Wiadomość  

 Dyspozytor odebrał komunikat z transportu. Identyfikator korelacji = = ' %1 '.  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|Identyfikator korelacji|`xs:GUID`|Identyfikator działania służący do skorelowania `MessageSentToTransport` zdarzenia z usługi lub klienta do jego odpowiadającego `MessageReceivedFromTransport` na drugim końcu.|  
|HostReference|`xs:string`|W przypadku usług hostowanych w sieci Web to pole jednoznacznie identyfikuje usługę w hierarchii sieci Web. Jego format jest zdefiniowany jako ścieżka wirtualna aplikacji nazwa witryny sieci Web&#124;wirtualnej ścieżki usługi&#124;ServiceName '. Przykład: "Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".|  
|Wywołując|`xs:string`|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
