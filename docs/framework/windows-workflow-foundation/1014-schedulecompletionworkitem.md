---
title: 1014 — ScheduleCompletionWorkItem
ms.date: 03/30/2017
ms.assetid: 84203735-478d-42d8-a320-c175dbddcb38
ms.openlocfilehash: 7fd93683851c5a8c4ab253272c3f2129b3f0bb49
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275560"
---
# <a name="1014---schedulecompletionworkitem"></a>1014 — ScheduleCompletionWorkItem

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID (Identyfikator)|1014|  
|Słowa kluczowe|WFRuntime|  
|Poziom|Pełny|  
|Kanał|Microsoft-Windows-Application Server — aplikacje/debugowanie|  
  
## <a name="description"></a>Opis  

 Wskazuje, że zaplanowano CompletionWorkItem.  
  
## <a name="message"></a>Wiadomość  

 Zaplanowano CompletionWorkItem dla działania nadrzędnego "%1", nazwa wyświetlana: "%2", identyfikator wystąpienia: "%3".  Działanie zakończone ' %4 ', nazwa wyświetlana: ' %5 ', identyfikator wystąpienia: ' %6 '.  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|Element nadrzędny|XS: ciąg|Nazwa typu działania nadrzędnego.|  
|ParentDisplayName|XS: ciąg|Nazwa wyświetlana działania nadrzędnego.|  
|ParentInstanceId|XS: ciąg|Identyfikator wystąpienia działania nadrzędnego.|  
|Zakończenie|XS: ciąg|Nazwa typu działania zakończonego.|  
|CompletedActivityDisplayName|XS: ciąg|Nazwa wyświetlana działania zakończonego.|  
|CompletedActivityInstanceId|XS: ciąg|Identyfikator wystąpienia ukończonego działania.|  
|Wywołując|XS: ciąg|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
