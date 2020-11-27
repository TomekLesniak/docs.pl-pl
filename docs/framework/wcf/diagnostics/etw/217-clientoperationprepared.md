---
title: 217 — ClientOperationPrepared
ms.date: 03/30/2017
ms.assetid: ad207f04-b038-4f33-95e9-27a361df8ecd
ms.openlocfilehash: e8aaf65bdff0718e932d07937e052541b7134f11
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96278885"
---
# <a name="217---clientoperationprepared"></a>217 — ClientOperationPrepared

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID (Identyfikator)|217|  
|Słowa kluczowe|Rozwiązywanie problemów, ServiceModel|  
|Poziom|Informacje|  
|Kanał|Microsoft-Windows-Application Server-Applications/Analytics|  
  
## <a name="description"></a>Opis  

 To zdarzenie jest emitowane przez klientów tuż przed wysłaniem operacji do usługi.  
  
## <a name="message"></a>Wiadomość  

 Klient wykonuje akcję "%1" skojarzoną z kontraktem "%2". Komunikat zostanie wysłany do "%3".  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|Akcja|`xs:string`|Nagłówek akcji protokołu SOAP wiadomości wychodzącej.|  
|Nazwa kontraktu|`xs:string`|Nazwa kontraktu. Przykład: ICalculator.|  
|Element docelowy|`xs:string`|Adres punktu końcowego usługi, do którego zostanie wysłana wiadomość.|  
|HostReference|`xs:string`|W przypadku usług hostowanych w sieci Web to pole jednoznacznie identyfikuje usługę w hierarchii sieci Web. Jego format jest zdefiniowany jako ścieżka wirtualna aplikacji nazwa witryny sieci Web&#124;wirtualnej ścieżki usługi&#124;ServiceName '. Przykład: "Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".|  
|Wywołując|`xs:string`|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
