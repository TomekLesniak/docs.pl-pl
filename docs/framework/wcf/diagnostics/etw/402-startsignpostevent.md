---
title: 402 — StartSignpostEvent
ms.date: 03/30/2017
ms.assetid: 5e5be126-765d-4ac9-88e7-008e9ef4f0e5
ms.openlocfilehash: ff32c900f4e357b7f1eca669a0ea60f80ea24b19
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96258325"
---
# <a name="402---startsignpostevent"></a>402 — StartSignpostEvent

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID (Identyfikator)|402|  
|Słowa kluczowe|Rozwiązywanie problemów|  
|Poziom|Informacje|  
|Kanał|Microsoft-Windows-Application Server-Applications/Analytics|  
  
## <a name="description"></a>Opis  

 To zdarzenie oznacza początek działania end-to-end. Zawiera nazwę działania.  
  
## <a name="message"></a>Wiadomość  

 Granica działania.  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|Dane rozszerzone|`xs:string`|Nazwa działania.|  
|Wywołując|`xs:string`|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
