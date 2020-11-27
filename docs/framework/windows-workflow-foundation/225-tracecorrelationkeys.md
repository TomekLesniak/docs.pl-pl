---
title: 225 — TraceCorrelationKeys
ms.date: 03/30/2017
ms.assetid: d9083aaf-3816-4c1c-bae0-2d7f49628345
ms.openlocfilehash: 04c5e0f4fbf3b95485e5bf4aae53aa2e4912d893
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294498"
---
# <a name="225---tracecorrelationkeys"></a>225 — TraceCorrelationKeys

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID (Identyfikator)|225|  
|Słowa kluczowe|Rozwiązywanie problemów, ServiceModel|  
|Poziom|Informacje|  
|Kanał|Microsoft-Windows-Application Server-Applications/Analytics|  
  
## <a name="description"></a>Opis  

 To zdarzenie jest emitowane, gdy korelacja oparta na zawartości jest używana dla usługi przepływu pracy. Zawiera on klucze korelacji, które są stosowane do skorelowania komunikatu z wystąpieniem.  
  
## <a name="message"></a>Wiadomość  

 Obliczony klucz korelacji "%1" używa wartości "%2" w zakresie nadrzędnym "%3".  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|Klucz wystąpienia|`xs:GUID`|Klucz, który został wygenerowany na podstawie wartości korelacji.|  
|Wartości|`xs:string`|Wartości, które były używane do obliczania klucza wystąpienia korelacji.|  
|Zakres nadrzędny|`xs:string`||  
|HostReference|`xs:string`|W przypadku usług hostowanych w sieci Web to pole jednoznacznie identyfikuje usługę w hierarchii sieci Web. Jego format jest zdefiniowany jako ścieżka wirtualna aplikacji nazwa witryny sieci Web&#124;wirtualnej ścieżki usługi&#124;ServiceName '. Przykład: "Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".|  
|Wywołując|`xs:string`|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
