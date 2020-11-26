---
title: 224 — MessageThrottleAtSeventyPercent
ms.date: 03/30/2017
ms.assetid: 82bbbfd7-10d2-41fd-805d-2443b0c1b96b
ms.openlocfilehash: 26b860b88313a971960a65b599562ef1ccb4e7da
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96243524"
---
# <a name="224---messagethrottleatseventypercent"></a>224 — MessageThrottleAtSeventyPercent

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID (Identyfikator)|224|  
|Słowa kluczowe|EndToEndMonitoring, HealthMonitoring, rozwiązywanie problemów, ServiceModel|  
|Poziom|Ostrzeżenie|  
|Kanał|Microsoft-Windows-Application Server-Applications/Analytics|  
  
## <a name="description"></a>Opis  

 Po przekroczeniu jednego z głównych przepustnic usługi `MessageThrottleExceeded` zdarzenie jest emitowane. Gdy wzrost liczby działań jest wolny i bieżąca wartość ograniczenia wynosi 70% bieżącego limitu, to zdarzenie jest emitowane. Należy zauważyć, że to zdarzenie jest emitowane tylko raz, gdy działanie działa powoli. Jeśli bieżąca wartość zostanie aktywowana z oznaczeniem 70 procent, (na przykład 70, 69, 70, 71, 70, 69), tylko pierwsze wystąpienie 70 procent powoduje wystąpienie zdarzenia. Po wydaniu tego zdarzenia przyszłe wystąpienia przekraczające limit ograniczenia ograniczają `MessageThrottleExceeded` zdarzenie.  
  
## <a name="message"></a>Wiadomość  

 Limit przepustnicy "%1" wynoszący "%2" wynosi od 70%%.  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|Nazwa ograniczenia|`xs:string`|Nazwa ograniczenia, które zostało przekroczone. `MaxConcurrentCalls`, `MaxConcurrentInstances` , Lub `MaxConcurrentSessions` ,|  
|Limit|`xs:long`|Aktualnie skonfigurowany limit ograniczania przepustowości.|  
|HostReference|`xs:string`|W przypadku usług hostowanych w sieci Web to pole jednoznacznie identyfikuje usługę w hierarchii sieci Web. Jego format jest zdefiniowany jako ścieżka wirtualna aplikacji nazwa witryny sieci Web&#124;wirtualnej ścieżki usługi&#124;ServiceName '. Przykład: "Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".|  
|Wywołując|`xs:string`|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
