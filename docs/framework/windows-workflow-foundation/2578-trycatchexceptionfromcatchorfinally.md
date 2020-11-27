---
title: 2578 — TryCatchExceptionFromCatchOrFinally
ms.date: 03/30/2017
ms.assetid: 4803fee6-b8d8-4937-9907-d5c5fd5299db
ms.openlocfilehash: 92503b13f59556fa21d058578982c3fa7b7a6b96
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96271202"
---
# <a name="2578---trycatchexceptionfromcatchorfinally"></a>2578 — TryCatchExceptionFromCatchOrFinally

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID (Identyfikator)|2578|  
|Słowa kluczowe|WFActivities|  
|Poziom|Ostrzeżenie|  
|Kanał|Microsoft-Windows-Application Server — aplikacje/debugowanie|  
  
## <a name="description"></a>Opis  

 Wskazuje, że działanie catch lub finally zgłosiło wyjątek.  
  
## <a name="message"></a>Wiadomość  

 Działanie catch lub finally skojarzone z działaniem TryCatch "%1" zgłosiło wyjątek.  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|Nazwa wyświetlana|XS: ciąg|Nazwa wyświetlana działania.|  
|Wywołując|XS: ciąg|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
