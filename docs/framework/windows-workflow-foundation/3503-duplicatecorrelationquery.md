---
title: 3503 — DuplicateCorrelationQuery
ms.date: 03/30/2017
ms.assetid: b857f8e6-ce4d-4da4-bc9d-6cd63fa558a4
ms.openlocfilehash: e1e64824ee9a95757ed7c00aa17fa80898219401
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96270331"
---
# <a name="3503---duplicatecorrelationquery"></a>3503 — DuplicateCorrelationQuery

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID (Identyfikator)|3503|  
|Słowa kluczowe|WFServices|  
|Poziom|Ostrzeżenie|  
|Kanał|Microsoft-Windows-Application Server-Applications/Analytics|  
  
## <a name="description"></a>Opis  

 Wskazuje, że znaleziono zduplikowany CorrelationQuery. Zduplikowane zapytanie nie zostanie użyte podczas obliczania korelacji.  
  
## <a name="message"></a>Wiadomość  

 Znaleziono zduplikowany CorrelationQuery z WHERE = ' %1 '. To zduplikowane zapytanie nie zostanie użyte podczas obliczania korelacji.  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|Lokalizacja|XS: ciąg|Część WHERE zapytania korelacji.|  
|Wywołując|XS: ciąg|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
