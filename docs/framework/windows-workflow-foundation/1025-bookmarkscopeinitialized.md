---
title: 1025 — BookmarkScopeInitialized
ms.date: 03/30/2017
ms.assetid: 63584434-e709-471d-9e96-97d3d99e70d6
ms.openlocfilehash: 47b4813c21ef637922117d5adf41b3c907c57f32
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275274"
---
# <a name="1025---bookmarkscopeinitialized"></a>1025 — BookmarkScopeInitialized

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID (Identyfikator)|1025|  
|Słowa kluczowe|WFRuntime|  
|Poziom|Pełny|  
|Kanał|Microsoft-Windows-Application Server — aplikacje/debugowanie|  
  
## <a name="description"></a>Opis  

 Wskazuje, że obiektem BookmarkScope został zainicjowany.  
  
## <a name="message"></a>Wiadomość  

 Obiektem BookmarkScope, który miał TemporaryId: "%1", został zainicjowany z identyfikatorem: "%2".  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|TemporaryId|XS: ciąg|Tymczasowy identyfikator zakładki.|  
|InitializedId|XS: ciąg|Identyfikator zainicjowany zakładki.|  
|Wywołując|XS: ciąg|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
