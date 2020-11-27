---
title: 213 — ServiceHostStarted
ms.date: 03/30/2017
ms.assetid: a6f7facc-342f-46bb-9d52-a470178ba6bb
ms.openlocfilehash: 87a98d30f5ecde6f81580a95e337df22341c23d4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96279028"
---
# <a name="213---servicehoststarted"></a>213 — ServiceHostStarted

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID (Identyfikator)|213|  
|Słowa kluczowe|EndToEndMonitoring, HealthMonitoring, rozwiązywanie problemów, ServiceHost|  
|Poziom|LogAlways|  
|Kanał|Microsoft-Windows-Application Server-Applications/Analytics|  
  
## <a name="description"></a>Opis  

 To zdarzenie jest emitowane po uruchomieniu hosta usługi hostowanej w sieci Web. Zwykle dzieje się tak, gdy usługa jest aktywowana przez komunikat. Może się tak zdarzyć, jeśli usługa jest skonfigurowana do automatycznego uruchamiania.  
  
## <a name="message"></a>Wiadomość  

 Uruchomiono ServiceHost: ' %1 '.  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|Nazwa typu usługi|`xs:string`|FullName CLR typu implementacji usługi.|  
|HostReference|`xs:string`|W przypadku usług hostowanych w sieci Web to pole jednoznacznie identyfikuje usługę w hierarchii sieci Web. Jego format jest zdefiniowany jako ścieżka wirtualna aplikacji nazwa witryny sieci Web&#124;wirtualnej ścieżki usługi&#124;ServiceName '. Przykład: "Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".|  
|Wywołując|`xs:string`|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
