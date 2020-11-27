---
title: 1015 — StartCompletionWorkItem
ms.date: 03/30/2017
ms.assetid: 96fd1d4e-c5d0-46ad-8a71-4b4b49ac7262
ms.openlocfilehash: c0d8572f192a8faa22327fd671cd9ea49c5054ca
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275547"
---
# <a name="1015---startcompletionworkitem"></a>1015 — StartCompletionWorkItem

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID (Identyfikator)|1015|  
|Słowa kluczowe|WFRuntime|  
|Poziom|Pełny|  
|Kanał|Microsoft-Windows-Application Server — aplikacje/debugowanie|  
  
## <a name="description"></a>Opis  

 Wskazuje, że CompletionWorkItem rozpoczyna wykonywanie.  
  
## <a name="message"></a>Wiadomość  

 Rozpoczynanie wykonywania elementu CompletionWorkItem dla działania nadrzędnego "%1", nazwa wyświetlana: %2, identyfikator wystąpienia: %3. Działanie zakończone ' %4 ', nazwa wyświetlana: ' %5 ', identyfikator wystąpienia: ' %6 '.  
  
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
