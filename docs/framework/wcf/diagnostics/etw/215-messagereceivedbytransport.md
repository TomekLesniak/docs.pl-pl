---
title: 215 — MessageReceivedByTransport
ms.date: 03/30/2017
ms.assetid: bb32aa60-5207-4711-9f08-110e8ac327e5
ms.openlocfilehash: 2f247e751a0690f13d059eff29d633c6d047775d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96279080"
---
# <a name="215---messagereceivedbytransport"></a>215 — MessageReceivedByTransport

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID (Identyfikator)|215|  
|Słowa kluczowe|Rozwiązywanie problemów, ServiceModel|  
|Poziom|Informacje|  
|Kanał|Microsoft-Windows-Application Server-Applications/Analytics|  
  
## <a name="description"></a>Opis  

 To zdarzenie występuje, gdy transport oparty na protokole TCP odbierze komunikat. Należy pamiętać, że na poziomie transportu wiele komunikatów może być wymienianych między klientami i usługami w ramach jednej operacji. Może to być spowodowane zachowaniem infrastruktury, tym dobrym przykładem. W związku z tym liczba `MessageReceivedByTransport` wyemitowanych zdarzeń zależy od powiązania usługi i jego konfiguracji.  
  
> [!NOTE]
> To zdarzenie nie jest emitowane w przypadku transportów jednokierunkowych.  
  
## <a name="message"></a>Wiadomość  

 Transport odebrał komunikat z ' %1 '.  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|Adres nasłuchiwania|`xs:string`|Adres, który odebrał wiadomość.|  
|HostReference|`xs:string`|W przypadku usług hostowanych w sieci Web to pole jednoznacznie identyfikuje usługę w hierarchii sieci Web. Jego format jest zdefiniowany jako ścieżka wirtualna aplikacji nazwa witryny sieci Web&#124;wirtualnej ścieżki usługi&#124;ServiceName '. Przykład: "Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".|  
|Wywołując|`xs:string`|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
