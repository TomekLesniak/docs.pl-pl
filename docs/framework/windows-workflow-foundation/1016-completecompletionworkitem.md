---
title: 1016 — CompleteCompletionWorkItem
ms.date: 03/30/2017
ms.assetid: 246929fb-6f14-440a-814b-cd8349350644
ms.openlocfilehash: a192ffe19777ca3e2e9784f6506a0c2929ced000
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275534"
---
# <a name="1016---completecompletionworkitem"></a>1016 — CompleteCompletionWorkItem

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID (Identyfikator)|1016|  
|Słowa kluczowe|WFRuntime|  
|Poziom|Pełny|  
|Kanał|Microsoft-Windows-Application Server — aplikacje/debugowanie|  
  
## <a name="description"></a>Opis  

 Wskazuje, że CompletionWorkItem został ukończony.  
  
## <a name="message"></a>Wiadomość  

 Ukończono CompletionWorkItem dla działania nadrzędnego "%1", nazwa wyświetlana: "%2", identyfikator wystąpienia: "%3". Działanie zakończone ' %4 ', nazwa wyświetlana: ' %5 ', identyfikator wystąpienia: ' %6 '.  
  
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
