---
title: 440 — StartSignpostEvent1
ms.date: 03/30/2017
ms.assetid: 27b551b5-ae76-49f8-bab8-6300009eb4c1
ms.openlocfilehash: 1e0278d665a961afab21445ab8490e3e5a94987c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293458"
---
# <a name="440---startsignpostevent1"></a>440 — StartSignpostEvent1

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID (Identyfikator)|440|  
|Słowa kluczowe|Rozwiązywanie problemów|  
|Poziom|Informacje|  
|Kanał|Microsoft-Windows-Application Server-Applications/Analytics|  
  
## <a name="description"></a>Opis  

 W obszarze śledzenie działań wskazuje, że komunikat spowodował Przekroczenie granicy działania w operacji wysyłania lub odbierania.  
  
## <a name="message"></a>Wiadomość  

 Granica działania.  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|ExtendedData|`xs:string`|Nazwa działania.|  
|Wywołując|`xs:string`|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
