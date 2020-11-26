---
title: 302 — UserDefinedWarningOccurred
ms.date: 03/30/2017
ms.assetid: 8d1f0bf1-0151-45e6-be92-573d397b54de
ms.openlocfilehash: b942b2e9716713371b8679fc9df9b9634dfc7283
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96243446"
---
# <a name="302---userdefinedwarningoccurred"></a>302 — UserDefinedWarningOccurred

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID (Identyfikator)|302|  
|Słowa kluczowe|Rozwiązywanie problemów, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring|  
|Poziom|Ostrzeżenie|  
|Kanał|Microsoft-Windows-Application Server-Applications/Analytics|  
  
## <a name="description"></a>Opis  

 To zdarzenie jest emitowane z kodu użytkownika. Deweloperzy mogą emitować to zdarzenie, gdy w usłudze występuje niestandardowe zdarzenie ostrzegawcze. Można to zrobić za pomocą <xref:System.Diagnostics.Eventing> interfejsów API. Ponadto istnieje przykład WCF, który otacza ten interfejs API i pokazuje, jak prawidłowo emitować to zdarzenie.  
  
## <a name="message"></a>Wiadomość  

 Nazwa: ' %1 ', odwołanie: ' %2 ', ładunek: %3  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|Nazwa|`xs:string`|Zdefiniowana przez użytkownika nazwa zdarzenia.|  
|HostReference|`xs:string`|W przypadku usług hostowanych w sieci Web to pole jednoznacznie identyfikuje usługę w hierarchii sieci Web. Jego format jest zdefiniowany jako ścieżka wirtualna aplikacji nazwa witryny sieci Web&#124;wirtualnej ścieżki usługi&#124;ServiceName '. Przykład: "Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".|  
|Ładunku|`xs:string`|Zdefiniowany przez użytkownika ładunek zdarzenia.|
