---
title: 1031 — CompleteFaultWorkItem
ms.date: 03/30/2017
ms.assetid: 95f4ccb0-6be4-41f3-9330-fae43165828f
ms.openlocfilehash: 557155fab35a37bdbaa45efb26d6bc025ad825c4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96281836"
---
# <a name="1031---completefaultworkitem"></a>1031 — CompleteFaultWorkItem

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID (Identyfikator)|1031|  
|Słowa kluczowe|WFRuntime|  
|Poziom|Pełny|  
|Kanał|Microsoft-Windows-Application Server — aplikacje/debugowanie|  
  
## <a name="description"></a>Opis  

 Wskazuje, że FaultWorkItem został ukończony.  
  
## <a name="message"></a>Wiadomość  

 FaultWorkItem dla działania %1, nazwa wyświetlana: %2, identyfikator wystąpienia: %3. Wyjątek został rozpropagowany z działania "%4", nazwa wyświetlana: "%5", identyfikator wystąpienia: "%6".  
  
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
