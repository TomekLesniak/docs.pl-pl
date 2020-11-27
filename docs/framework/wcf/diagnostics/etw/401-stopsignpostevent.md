---
title: 401— StopSignPostEvent
ms.date: 03/30/2017
ms.assetid: e033d03a-510d-4300-aa65-ef02cb4807f2
ms.openlocfilehash: e549a8aabd0a54022000515050cde19dc4f20dd3
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294069"
---
# <a name="401--stopsignpostevent"></a>401— StopSignPostEvent

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID (Identyfikator)|401|  
|Słowa kluczowe|Rozwiązywanie problemów|  
|Poziom|Informacje|  
|Kanał|Microsoft-Windows-Application Server-Applications/Analytics|  
  
## <a name="description"></a>Opis  

 To zdarzenie oznacza zakończenie działania end-to-end. Zawiera nazwę działania.  
  
## <a name="message"></a>Wiadomość  

 Granica działania.  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|Dane rozszerzone|`xs:string`|Nazwa działania.|  
|Wywołując|`xs:string`|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
