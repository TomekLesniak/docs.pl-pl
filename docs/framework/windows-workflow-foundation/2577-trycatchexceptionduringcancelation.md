---
title: 2577 — TryCatchExceptionDuringCancelation
ms.date: 03/30/2017
ms.assetid: 35ee9f55-227f-4566-bcb4-4c7c75dea85b
ms.openlocfilehash: 33c68984e88eaa5e3028899a7c3066c94a65e8eb
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96271242"
---
# <a name="2577---trycatchexceptionduringcancelation"></a>2577 — TryCatchExceptionDuringCancelation

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID (Identyfikator)|2577|  
|Słowa kluczowe|WFActivities|  
|Poziom|Ostrzeżenie|  
|Kanał|Microsoft-Windows-Application Server — aplikacje/debugowanie|  
  
## <a name="description"></a>Opis  

 Wskazuje, że działanie podrzędne działania TryCatch zgłosiło wyjątek podczas anulowania.  
  
## <a name="message"></a>Wiadomość  

 Działanie podrzędne działania TryCatch "%1" zgłosiło wyjątek podczas anulowania.  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|Nazwa wyświetlana|XS: ciąg|Nazwa wyświetlana działania.|  
|Wywołując|XS: ciąg|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
