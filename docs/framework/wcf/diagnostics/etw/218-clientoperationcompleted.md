---
title: 218 — ClientOperationCompleted
ms.date: 03/30/2017
ms.assetid: b069bced-7bb2-4e01-8227-e5dbda17af09
ms.openlocfilehash: d74aa77aff7b45b50f6891c999889011d9e03381
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96278859"
---
# <a name="218---clientoperationcompleted"></a>218 — ClientOperationCompleted

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID (Identyfikator)|218|  
|Słowa kluczowe|Rozwiązywanie problemów, ServiceModel|  
|Poziom|Informacje|  
|Kanał|Microsoft-Windows-Application Server-Applications/Analytics|  
  
## <a name="description"></a>Opis  

 To zdarzenie jest emitowane przez klientów tuż po zakończeniu operacji. W przypadku operacji jednokierunkowych jest to zaraz po pomyślnym wysłaniu wiadomości. W przypadku operacji żądanie-odpowiedź jest to po odebraniu odpowiedzi.  
  
## <a name="message"></a>Wiadomość  

 Klient ukończył wykonywanie akcji "%1" skojarzonej z kontraktem "%2". Wiadomość została wysłana do ' %3 '.  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|Akcja|XS: ciąg|Nagłówek akcji protokołu SOAP wiadomości wychodzącej.|  
|Nazwa kontraktu|`xs:string`|Nazwa kontraktu. Przykład: ICalculator.|  
|Element docelowy|`xs:string`|Adres punktu końcowego usługi, do którego wiadomość została wysłana.|  
|HostReference|`xs:string`|W przypadku usług hostowanych w sieci Web to pole jednoznacznie identyfikuje usługę w hierarchii sieci Web. Jego format jest zdefiniowany jako ścieżka wirtualna aplikacji nazwa witryny sieci Web&#124;wirtualnej ścieżki usługi&#124;ServiceName '. Przykład: "Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".|  
|Wywołując|`xs:string`|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
