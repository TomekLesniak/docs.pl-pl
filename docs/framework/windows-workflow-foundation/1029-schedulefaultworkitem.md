---
title: 1029 — ScheduleFaultWorkItem
ms.date: 03/30/2017
ms.assetid: 3a56b29e-f740-459d-8576-d81e58bf5a03
ms.openlocfilehash: 5c109607b2d353d3d4a5a693f29ab66bb76c8398
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275092"
---
# <a name="1029---schedulefaultworkitem"></a>1029 — ScheduleFaultWorkItem

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID (Identyfikator)|1029|  
|Słowa kluczowe|WFRuntime|  
|Poziom|Pełny|  
|Kanał|Microsoft-Windows-Application Server — aplikacje/debugowanie|  
  
## <a name="description"></a>Opis  

 Wskazuje, że zaplanowano FaultWorkItem.  
  
## <a name="message"></a>Wiadomość  

 FaultWorkItem zaplanowano dla działania %1, nazwa wyświetlana: %2, identyfikator wystąpienia: %3.  Wyjątek został rozpropagowany z działania "%4", nazwa wyświetlana: "%5", identyfikator wystąpienia: "%6".  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|Błąd|XS: ciąg|Nazwa typu działania dotyczącego błędu.|  
|FaultActivityDisplayName|XS: ciąg|Nazwa wyświetlana działania dotyczącego błędu.|  
|FaultActivityInstanceId|XS: ciąg|Identyfikator wystąpienia działania błędu.|  
|Wyjątek|XS: ciąg|Nazwa typu działania, które wywołało wyjątek.|  
|ExceptionActivityDisplayName|XS: ciąg|Nazwa wyświetlana działania, które wywołało wyjątek.|  
|ExceptionActivityInstanceId|XS: ciąg|Identyfikator wystąpienia działania, które wywołało wyjątek.|  
|Wyjątek|XS: ciąg|Szczegóły wyjątku dla wyjątku|  
|Wywołując|XS: ciąg|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
