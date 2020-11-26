---
title: 206 — ErrorHandlerInvoked
ms.date: 03/30/2017
ms.assetid: 97340f4d-4e09-4e42-a17a-982b3868dbcf
ms.openlocfilehash: 99415733624752217d32f6f026a419b2b32bfa7b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96244616"
---
# <a name="206---errorhandlerinvoked"></a>206 — ErrorHandlerInvoked

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID (Identyfikator)|206|  
|Słowa kluczowe|Rozwiązywanie problemów, ServiceModel|  
|Poziom|Informacje|  
|Kanał|Microsoft-Windows-Application Server-Applications/Analytics|  
  
## <a name="description"></a>Opis  

 To zdarzenie jest emitowane, gdy `ErrorHandler` miało możliwość obsługi wyjątku, który wystąpił w operacji usługi.  
  
## <a name="message"></a>Wiadomość  

 Dyspozytor wywołał ErrorHandler typu ' %1 ' z wyjątkiem typu ' %3 '. ErrorHandled = = ' %2 '.  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|TypeName|`xs:string`|FullName CLR typu wywoływanego `ErrorHandler` .|  
|Obsłużone|`xs:unsignedByte`|`true` Jeśli program obsługi błędów obsłużył błąd, w przeciwnym razie `false` .|  
|ExceptionTypeName|`xs:string`|FullName CLR wyjątku, który był obsługiwany.|  
|HostReference|`xs:string`|W przypadku usług hostowanych w sieci Web to pole jednoznacznie identyfikuje usługę w hierarchii sieci Web. Jego format jest zdefiniowany jako ścieżka wirtualna aplikacji nazwa witryny sieci Web&#124;wirtualnej ścieżki usługi&#124;ServiceName '. Przykład: "Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".|  
|Wywołując|`xs:string`|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
