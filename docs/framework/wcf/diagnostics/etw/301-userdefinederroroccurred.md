---
title: 301 — UserDefinedErrorOccurred
ms.date: 03/30/2017
ms.assetid: a0285d1c-550f-4c14-9c36-a96e97f1c4e4
ms.openlocfilehash: 2c3ff1905a1d17413211246f5b3cc156bcbb7320
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96243459"
---
# <a name="301---userdefinederroroccurred"></a>301 — UserDefinedErrorOccurred

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID (Identyfikator)|301|  
|Słowa kluczowe|Rozwiązywanie problemów, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring|  
|Poziom|Błąd|  
|Kanał|Microsoft-Windows-Application Server-Applications/Analytics|  
  
## <a name="description"></a>Opis  

 To zdarzenie jest emitowane z kodu użytkownika. Deweloperzy mogą emitować to zdarzenie, gdy w swojej usłudze wystąpi błąd zdefiniowany przez użytkownika. Można to zrobić za pomocą <xref:System.Diagnostics.Eventing> interfejsów API. Ponadto istnieje przykład WCF, który otacza ten interfejs API i pokazuje, jak prawidłowo emitować to zdarzenie.  
  
## <a name="message"></a>Wiadomość  

 Nazwa: ' %1 ', odwołanie: ' %2 ', ładunek: %3  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|Nazwa|`xs:string`|Zdefiniowana przez użytkownika nazwa zdarzenia.|  
|HostReference|`xs:string`|W przypadku usług hostowanych w sieci Web to pole jednoznacznie identyfikuje usługę w hierarchii sieci Web. Jego format jest zdefiniowany jako ścieżka wirtualna aplikacji nazwa witryny sieci Web&#124;wirtualnej ścieżki usługi&#124;ServiceName '. Przykład: "Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".|  
|Ładunku|`xs:string`|Zdefiniowany przez użytkownika ładunek zdarzenia.|
