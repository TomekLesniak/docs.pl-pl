---
title: 57398 — MaxInstancesExceeded
ms.date: 03/30/2017
ms.assetid: f943d209-dfeb-43e5-b572-c9a06217936e
ms.openlocfilehash: bd490aad24fba4550bc778799cd6f836dcfd466c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96289181"
---
# <a name="57398---maxinstancesexceeded"></a>57398 — MaxInstancesExceeded

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID (Identyfikator)|57398|  
|Słowa kluczowe|WFServices|  
|Poziom|Ostrzeżenie|  
|Kanał|Microsoft-Windows-Application Server-Applications/Analytics|  
  
## <a name="description"></a>Opis  

 Wskazuje, że system osiągnął limit ustawiony dla dławienia "MaxConcurrentInstances".  
  
## <a name="message"></a>Wiadomość  

 System osiągnął limit ustawiony dla dławienia "MaxConcurrentInstances". Limit dla tego dławienia został ustawiony na %1. Wartość ograniczenia można zmienić, modyfikując atrybut "maxConcurrentInstances" w elemencie servicedławienia lub modyfikując właściwość "MaxConcurrentInstances" w przypadku zachowania elementu ServiceThrottlingBehavior.  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|Nazwa|XS: ciąg|Nazwa elementu .|  
|Wywołując|XS: ciąg|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
