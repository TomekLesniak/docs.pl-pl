---
title: 210 — MessageThrottleExceeded
ms.date: 03/30/2017
ms.assetid: 24ca08ea-c11c-4753-946e-98aa820f8711
ms.openlocfilehash: a0da1c198700407d8cdf699d1b734247024717a9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96267744"
---
# <a name="210---messagethrottleexceeded"></a>210 — MessageThrottleExceeded

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID (Identyfikator)|210|  
|Słowa kluczowe|EndToEndMonitoring, HealthMonitoring, rozwiązywanie problemów, ServiceModel|  
|Poziom|Ostrzeżenie|  
|Kanał|Microsoft-Windows-Application Server-Applications/Analytics|  
  
## <a name="description"></a>Opis  

 To zdarzenie jest emitowane po przekroczeniu jednego z trzech głównych dławienia usług. Należy zauważyć, że to zdarzenie jest emitowane tylko po początkowym przekroczeniu limitu ograniczania. Na przykład, jeśli limit ograniczania wywołań współbieżnych wynosi 10, jedenaste wywołanie współbieżne powoduje `MessageThrottleExceeded` zdarzenie. Dwunaste wywołanie nie powoduje innego zdarzenia. Ponadto, aby uniknąć zakłócenia strumienia zdarzeń, aktywność, której nie ma na granicy, nie powoduje innego zdarzenia. W tym przykładzie, jeśli kilka wywołań zostanie ukończonych, dostępne są 9 współbieżnych wywołań. Jeśli kolejne dwa wywołania są dostępne, bieżąca wartość zostanie ponownie 11. Nie powoduje to innego zdarzenia. Gdy bieżąca wartość jest równa 70% ograniczenia przepustowości, zostanie wyemitowane inne zdarzenie, które wskazuje, że działanie zostało spowolnione. Przyszłe działanie, które przekracza limit, powoduje `MessageThrottleExceeded` wyemitowanie innego zdarzenia. W tym przykładzie, jeśli liczba współbieżnych wywołań spadnie do 7, a następnie ponownie osiągnie wartość 11 i `MessageThrottleExceeded` zostanie wyemitowane inne zdarzenie.  
  
## <a name="message"></a>Wiadomość  

 Osiągnięto limit przepustnicy "%1" wynoszący "%2".  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|Nazwa ograniczenia|`xs:string`|Nazwa ograniczenia, które zostało przekroczone. `MaxConcurrentCalls`, `MaxConcurrentInstances` , Lub `MaxConcurrentSessions` ,|  
|Limit|`xs:long`|Aktualnie skonfigurowany limit ograniczania przepustowości.|  
|HostReference|`xs:string`|W przypadku usług hostowanych w sieci Web to pole jednoznacznie identyfikuje usługę w hierarchii sieci Web. Jego format jest zdefiniowany jako ścieżka wirtualna aplikacji nazwa witryny sieci Web&#124;wirtualnej ścieżki usługi&#124;ServiceName '. Przykład: "Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".|  
|Wywołując|`xs:string`|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
