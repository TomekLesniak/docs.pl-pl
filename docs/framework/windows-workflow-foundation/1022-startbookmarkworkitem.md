---
title: 1022 — StartBookmarkWorkItem
ms.date: 03/30/2017
ms.assetid: 4415fbdb-0329-4019-803f-aea66e75f3da
ms.openlocfilehash: ca1f4244fb1a5144cb2d86eaacb9b31137d317c2
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275339"
---
# <a name="1022---startbookmarkworkitem"></a>1022 — StartBookmarkWorkItem

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID (Identyfikator)|1022|  
|Słowa kluczowe|WFRuntime|  
|Poziom|Pełny|  
|Kanał|Microsoft-Windows-Application Server — aplikacje/debugowanie|  
  
## <a name="description"></a>Opis  

 Wskazuje, że BookmarkWorkItem rozpoczyna wykonywanie.  
  
## <a name="message"></a>Wiadomość  

 Rozpoczynanie wykonywania elementu BookmarkWorkItem dla działania "%1", nazwa wyświetlana: %2, identyfikator wystąpienia: %3.  Zakładkaname: %4, obiektem BookmarkScope: %5.  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|Działanie|XS: ciąg|Nazwa typu działania.|  
|Nazwa wyświetlana|XS: ciąg|Nazwa wyświetlana działania.|  
|InstanceId|XS: ciąg|Identyfikator wystąpienia działania.|  
|Zakładkaname|XS: ciąg|Nazwa zakładki.|  
|Obiektem BookmarkScope|XS: ciąg|Zakres zakładki.|  
|Wywołując|XS: ciąg|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
