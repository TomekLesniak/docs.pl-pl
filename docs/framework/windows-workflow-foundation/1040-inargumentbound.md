---
title: 1040 — InArgumentBound
ms.date: 03/30/2017
ms.assetid: 7dfaad1b-36c0-4575-84c1-31d63b0eaf5d
ms.openlocfilehash: 04a61892ea817d5168ccbfccf68c0b74ee43e983
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96238954"
---
# <a name="1040---inargumentbound"></a>1040 — InArgumentBound

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID (Identyfikator)|1040|  
|Słowa kluczowe|WFActivities|  
|Poziom|Pełny|  
|Kanał|Microsoft-Windows-Application Server — aplikacje/debugowanie|  
  
## <a name="description"></a>Opis  

 Wskazuje, że argument in został powiązany.  
  
## <a name="message"></a>Wiadomość  

 Argument in "%1" w działaniu "%2", nazwa wyświetlana: "%3", identyfikator wystąpienia: "%4", został powiązany z wartością: %5.  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|Brak argumentu|XS: ciąg|Nazwa argumentu.|  
|Działanie|XS: ciąg|Nazwa typu działania.|  
|Nazwa wyświetlana|XS: ciąg|Nazwa wyświetlana działania.|  
|InstanceId|XS: ciąg|Identyfikator wystąpienia działania.|  
|Wartość|XS: ciąg|Wartość powiązana z nieargumentem.|  
|Wywołując|XS: ciąg|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
