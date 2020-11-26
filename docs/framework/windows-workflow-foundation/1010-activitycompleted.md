---
title: 1010 — ActivityCompleted
ms.date: 03/30/2017
ms.assetid: d256284e-3fd2-4c33-82f4-abb617575706
ms.openlocfilehash: d0ebf32ec1d5fe5b34ffe650d5547891be0eb665
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239916"
---
# <a name="1010---activitycompleted"></a>1010 — ActivityCompleted

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID (Identyfikator)|1010|  
|Słowa kluczowe|WFRuntime|  
|Poziom|Informacje|  
|Kanał|Microsoft-Windows-Application Server — aplikacje/debugowanie|  
  
## <a name="description"></a>Opis  

 Wskazuje, że działanie zostało ukończone.  
  
## <a name="message"></a>Wiadomość  

 Działanie %1, nazwa wyświetlana: %2, identyfikator wystąpienia: %3, zostało zakończone w stanie %4.  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|Działanie|XS: ciąg|Nazwa typu działania.|  
|Nazwa wyświetlana|XS: ciąg|Nazwa wyświetlana działania.|  
|InstanceId|XS: ciąg|Identyfikator wystąpienia działania.|  
|Stan|XS: ciąg|Stan działania.|  
|Wywołując|XS: ciąg|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
