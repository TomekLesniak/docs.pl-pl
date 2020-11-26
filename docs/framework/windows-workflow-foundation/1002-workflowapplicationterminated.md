---
title: 1002 — WorkflowApplicationTerminated
ms.date: 03/30/2017
ms.assetid: 4e8b111f-79dc-4898-bb4a-e9b36f69420f
ms.openlocfilehash: e7c92dcc9ce472c50af6f0aa26c59f55d62fbb9f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239942"
---
# <a name="1002---workflowapplicationterminated"></a>1002 — WorkflowApplicationTerminated

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID (Identyfikator)|1002|  
|Słowa kluczowe|WFRuntime|  
|Poziom|Informacje|  
|Kanał|Microsoft-Windows-Application Server — aplikacje/debugowanie|  
  
## <a name="description"></a>Opis  

 Wskazuje, że aplikacja przepływu pracy została przerwana w stanie awarii z wyjątkiem.  
  
## <a name="message"></a>Wiadomość  

 Obiekt WorkflowApplication o identyfikatorze: %1 został zakończony. Zakończono w stanie awarii z wyjątkiem.  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|WorkflowApplicationId|`xs:string`|Identyfikator aplikacji przepływu pracy|  
|Wyjątek|`xs:string`|Szczegóły wyjątku dla wyjątku|  
|Wywołując|`xs:string`|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
