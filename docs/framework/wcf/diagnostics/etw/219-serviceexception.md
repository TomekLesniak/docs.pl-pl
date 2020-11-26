---
title: 219 — ServiceException
ms.date: 03/30/2017
ms.assetid: 81e2efac-39aa-4ed2-85a9-97eb8793b844
ms.openlocfilehash: 832ced406b6079fad8f4b9bea512a6d390bdcc0f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96241944"
---
# <a name="219---serviceexception"></a>219 — ServiceException

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID (Identyfikator)|219|  
|Słowa kluczowe|EndToEndMonitoring, HealthMonitoring, rozwiązywanie problemów, ServiceModel|  
|Poziom|Błąd|  
|Kanał|Microsoft-Windows-Application Server-Applications/Analytics|  
  
## <a name="description"></a>Opis  

 To zdarzenie jest emitowane, gdy usługa WCF napotka nieobsługiwany wyjątek. Obejmuje to Nieobsłużone wyjątki podczas aktywacji, podczas przetwarzania komunikatów oraz w kodzie użytkownika.  
  
## <a name="message"></a>Wiadomość  

 Podczas przetwarzania komunikatu Wystąpił nieobsługiwany wyjątek typu "%2". Pełny wyjątek ToString: %1.  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|ExceptionToString|`xs:string`|Wynik wywołania `ToString` () w wyjątku CLR.|  
|ExceptionTypeName|`xs:string`|FullName CLR typu wyjątku.|  
|HostReference|`xs:string`|W przypadku usług hostowanych w sieci Web to pole jednoznacznie identyfikuje usługę w hierarchii sieci Web. Jego format jest zdefiniowany jako ścieżka wirtualna aplikacji nazwa witryny sieci Web&#124;wirtualnej ścieżki usługi&#124;ServiceName '. Przykład: "Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".|  
|Wywołując|`xs:string`|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
