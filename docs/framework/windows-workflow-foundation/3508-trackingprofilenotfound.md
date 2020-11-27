---
title: 3508 — TrackingProfileNotFound
ms.date: 03/30/2017
ms.assetid: 4cee3c4a-0490-4c94-aa19-ef7ce7287c02
ms.openlocfilehash: 23262427c3da730eaf930a8b483c7c4d4ec3a3a4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96289844"
---
# <a name="3508---trackingprofilenotfound"></a>3508 — TrackingProfileNotFound

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID (Identyfikator)|3508|  
|Słowa kluczowe|WFServices|  
|Poziom|Pełny|  
|Kanał|Microsoft-Windows-Application Server-Applications/Analytics|  
  
## <a name="description"></a>Opis  

 Wskazuje, że element TrackingProfile nie został znaleziony w pliku konfiguracyjnym lub ActivityDefinitionId nie jest zgodny z profilem.  
  
## <a name="message"></a>Wiadomość  

 Nie znaleziono TrackingProfile "%1" dla ActivityDefinitionId "%2". Nie znaleziono TrackingProfile w pliku konfiguracyjnym lub ActivityDefinitionId nie jest zgodny.  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|TrackingProfile|XS: ciąg|Nazwa profilu śledzenia.|  
|ActivityDefinitionId|XS: ciąg|Identyfikator definicji działania.|  
|Wywołując|XS: ciąg|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
