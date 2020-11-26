---
title: 1009 — ActivityScheduled
ms.date: 03/30/2017
ms.assetid: 307e38b6-d47e-47a4-9708-e74d8314b1a1
ms.openlocfilehash: 812531d4206dfee20f183b9461330e71263b0bf8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239773"
---
# <a name="1009---activityscheduled"></a>1009 — ActivityScheduled

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID (Identyfikator)|1009|  
|Słowa kluczowe|WFRuntime|  
|Poziom|Informacje|  
|Kanał|Microsoft-Windows-Application Server — aplikacje/debugowanie|  
  
## <a name="description"></a>Opis  

 Wskazuje, że działanie jest zaplanowane do wykonania.  
  
## <a name="message"></a>Wiadomość  

 Działanie nadrzędne ' %1 ', nazwa wyświetlana: ' %2 ', identyfikator wystąpienia: ' %3 ' zaplanowane działanie podrzędne ' %4 ', DisplayName: ' %5 ', identyfikator wystąpienia: ' %6 '.  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|Element nadrzędny|XS: ciąg|Nazwa typu działania nadrzędnego.|  
|ParentDisplayName|XS: ciąg|Nazwa wyświetlana działania nadrzędnego.|  
|ParentInstanceId|XS: ciąg|Identyfikator wystąpienia działania nadrzędnego.|  
|Tabela podrzędna|XS: ciąg|Nazwa typu zaplanowanego działania podrzędnego.|  
|ChildDisplayName|XS: ciąg|Nazwa wyświetlana zaplanowanego działania podrzędnego.|  
|ChildInstanceId|XS: ciąg|Identyfikator wystąpienia zaplanowanego działania podrzędnego.|  
|Wywołując|XS: ciąg|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
