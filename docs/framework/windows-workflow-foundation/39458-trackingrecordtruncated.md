---
title: 39458 — TrackingRecordTruncated
ms.date: 03/30/2017
ms.assetid: 5352f0eb-d571-454a-bab5-e2162888b218
ms.openlocfilehash: f02a34673c51be6e0b127a64e4622131575d836f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275895"
---
# <a name="39458---trackingrecordtruncated"></a>39458 — TrackingRecordTruncated

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID (Identyfikator)|39458|  
|Słowa kluczowe|WFTracking|  
|Poziom|Ostrzeżenie|  
|Kanał|Microsoft-Windows-Application Server — aplikacje/debugowanie|  
  
## <a name="description"></a>Opis  

 Wskazuje, że rekord śledzenia został obcięty. Zmienne/adnotacje/dane użytkownika zostały usunięte.  
  
## <a name="message"></a>Wiadomość  

 Obcięty rekord śledzenia %1 zapisany w sesji ETW z dostawcą %2. Zmienne/adnotacje/dane użytkownika zostały usunięte  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|RecordNumber|XS: ciąg|Numer rekordu śledzenia.|  
|Identyfikatorem|XS: ciąg|Identyfikator dostawcy ETW.|  
|Wywołując|XS: ciąg|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
