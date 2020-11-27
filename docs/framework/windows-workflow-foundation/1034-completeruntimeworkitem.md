---
title: 1034 — CompleteRuntimeWorkItem
ms.date: 03/30/2017
ms.assetid: 45620011-8b04-4f87-ab5a-65b24145e17d
ms.openlocfilehash: 837adc9e143060284f2373a049bc9ad9c8cee336
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294290"
---
# <a name="1034---completeruntimeworkitem"></a>1034 — CompleteRuntimeWorkItem

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID (Identyfikator)|1034|  
|Słowa kluczowe|WFRuntime|  
|Poziom|Pełny|  
|Kanał|Microsoft-Windows-Application Server — aplikacje/debugowanie|  
  
## <a name="description"></a>Opis  

 Wskazuje, że RuntimeWorkItem został ukończony.  
  
## <a name="message"></a>Wiadomość  

 Ukończono element roboczy środowiska uruchomieniowego dla działania %1, nazwa wyświetlana: %2, identyfikator wystąpienia: %3.  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|Działanie|XS: ciąg|Nazwa typu działania.|  
|Nazwa wyświetlana|XS: ciąg|Nazwa wyświetlana działania.|  
|InstanceId|XS: ciąg|Identyfikator wystąpienia działania.|  
|Wywołując|XS: ciąg|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
