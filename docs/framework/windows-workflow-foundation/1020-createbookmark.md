---
title: 1020 — CreateBookmark
ms.date: 03/30/2017
ms.assetid: 4bee948d-816f-4803-85cc-3883b5e23d10
ms.openlocfilehash: 8c9c20fd4fb74f80779c1d2ef8f29ac3d44050d9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275378"
---
# <a name="1020---createbookmark"></a>1020 — CreateBookmark

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID (Identyfikator)|1020|  
|Słowa kluczowe|WFRuntime|  
|Poziom|Pełny|  
|Kanał|Microsoft-Windows-Application Server — aplikacje/debugowanie|  
  
## <a name="description"></a>Opis  

 Wskazuje, że utworzono zakładkę dla działania.  
  
## <a name="message"></a>Wiadomość  

 Utworzono zakładkę dla działania %1, nazwa wyświetlana: %2, identyfikator wystąpienia: %3.  Zakładkaname: %4, obiektem BookmarkScope: %5.  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|Działanie|XS: ciąg|Nazwa typu działania.|  
|Nazwa wyświetlana|XS: ciąg|Nazwa wyświetlana działania.|  
|InstanceId|XS: ciąg|Identyfikator wystąpienia działania.|  
|Zakładkaname|XS: ciąg|Nazwa zakładki.|  
|Obiektem BookmarkScope|XS: ciąg|Zakres zakładki.|  
|Wywołując|XS: ciąg|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
