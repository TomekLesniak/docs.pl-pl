---
title: 1021 — ScheduleBookmarkWorkItem
ms.date: 03/30/2017
ms.assetid: 2e0da311-b219-4637-9460-90cdafcc4ecd
ms.openlocfilehash: 42ed23654622e29df8ffc210c8d5ba572fa69fd4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275352"
---
# <a name="1021---schedulebookmarkworkitem"></a>1021 — ScheduleBookmarkWorkItem

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID (Identyfikator)|1021|  
|Słowa kluczowe|WFRuntime|  
|Poziom|Pełny|  
|Kanał|Microsoft-Windows-Application Server — aplikacje/debugowanie|  
  
## <a name="description"></a>Opis  

 Wskazuje, że zaplanowano BookmarkWorkItem.  
  
## <a name="message"></a>Wiadomość  

 BookmarkWorkItem zaplanowano dla działania %1, nazwa wyświetlana: %2, identyfikator wystąpienia: %3.  Zakładkaname: %4, obiektem BookmarkScope: %5.  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|Działanie|XS: ciąg|Nazwa typu działania.|  
|Nazwa wyświetlana|XS: ciąg|Nazwa wyświetlana działania.|  
|InstanceId|XS: ciąg|Identyfikator wystąpienia działania.|  
|Zakładkaname|XS: ciąg|Nazwa zakładki.|  
|Obiektem BookmarkScope|XS: ciąg|Zakres zakładki.|  
|Wywołując|XS: ciąg|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
