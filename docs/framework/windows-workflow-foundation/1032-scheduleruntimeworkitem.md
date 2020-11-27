---
title: 1032 — ScheduleRuntimeWorkItem
ms.date: 03/30/2017
ms.assetid: 54688101-becf-42f3-80ca-f53a7b527620
ms.openlocfilehash: da35201f2b3e3bc07e0b9139b0584ce37011e168
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294316"
---
# <a name="1032---scheduleruntimeworkitem"></a>1032 — ScheduleRuntimeWorkItem

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID (Identyfikator)|1032|  
|Słowa kluczowe|WFRuntime|  
|Poziom|Pełny|  
|Kanał|Microsoft-Windows-Application Server — aplikacje/debugowanie|  
  
## <a name="description"></a>Opis  

 Wskazuje, że zaplanowano RuntimeWorkItem.  
  
## <a name="message"></a>Wiadomość  

 Zaplanowano element roboczy środowiska uruchomieniowego dla działania %1, nazwa wyświetlana: %2, identyfikator wystąpienia: %3.  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|Działanie|XS: ciąg|Nazwa typu działania.|  
|Nazwa wyświetlana|XS: ciąg|Nazwa wyświetlana działania.|  
|InstanceId|XS: ciąg|Identyfikator wystąpienia działania.|  
|Wywołując|XS: ciąg|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
