---
title: 1041 — WorkflowApplicationPersistableIdle
ms.date: 03/30/2017
ms.assetid: 966adf2f-e21d-44df-a3ec-a8e285e0a316
ms.openlocfilehash: 9995823753fc78ca3f278cd635fcf6c7d2b84325
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96238941"
---
# <a name="1041---workflowapplicationpersistableidle"></a>1041 — WorkflowApplicationPersistableIdle

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID (Identyfikator)|1041|  
|Słowa kluczowe|WFRuntime|  
|Poziom|Informacje|  
|Kanał|Microsoft-Windows-Application Server — aplikacje/debugowanie|  
  
## <a name="description"></a>Opis  

 Wskazuje, że aplikacja przepływu pracy jest bezczynna i trwała. Aplikacja przepływu pracy zostanie przeaktywna lub utrwalona.  
  
## <a name="message"></a>Wiadomość  

 Obiekt WorkflowApplication o identyfikatorze: "%1" jest bezczynny i trwały.  Zostanie podjęta następująca akcja: %2.  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|WorkflowApplicationId|XS: ciąg|Identyfikator aplikacji przepływu pracy|  
|ActionTaken|XS: ciąg|Akcja, która zostanie wykonana w aplikacji przepływu pracy.|  
|Wywołując|XS: ciąg|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
