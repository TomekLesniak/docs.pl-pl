---
title: 1030 — StartFaultWorkItem
ms.date: 03/30/2017
ms.assetid: e1601fb9-0bc6-4dbe-816f-f24914063d34
ms.openlocfilehash: 52034f7cc7c6f6749fbbbf06db9267ecb6279ee1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96281862"
---
# <a name="1030---startfaultworkitem"></a>1030 — StartFaultWorkItem

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID (Identyfikator)|1030|  
|Słowa kluczowe|WFRuntime|  
|Poziom|Pełny|  
|Kanał|Microsoft-Windows-Application Server — aplikacje/debugowanie|  
  
## <a name="description"></a>Opis  

 Wskazuje, że FaultWorkItem rozpoczyna wykonywanie.  
  
## <a name="message"></a>Wiadomość  

 Rozpoczynanie wykonywania elementu FaultWorkItem dla działania "%1", nazwa wyświetlana: %2, identyfikator wystąpienia: %3.  Wyjątek został rozpropagowany z działania "%4", nazwa wyświetlana: "%5", identyfikator wystąpienia: "%6".  
  
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
