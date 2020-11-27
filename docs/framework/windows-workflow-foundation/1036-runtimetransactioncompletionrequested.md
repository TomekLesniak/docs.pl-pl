---
title: 1036 — RuntimeTransactionCompletionRequested
ms.date: 03/30/2017
ms.assetid: d36b9f44-7c0f-4083-9d3a-9034dd2b98de
ms.openlocfilehash: 96ea253fd61652a3719eaf8b1a4d31aa88337eeb
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294264"
---
# <a name="1036---runtimetransactioncompletionrequested"></a>1036 — RuntimeTransactionCompletionRequested

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID (Identyfikator)|1036|  
|Słowa kluczowe|WFRuntime|  
|Poziom|Pełny|  
|Kanał|Microsoft-Windows-Application Server — aplikacje/debugowanie|  
  
## <a name="description"></a>Opis  

 Wskazuje, że działanie zaplanował ukończenie transakcji środowiska uruchomieniowego.  
  
## <a name="message"></a>Wiadomość  

 Działanie %1, nazwa wyświetlana: %2, identyfikator wystąpienia: %3, ma zaplanowane zakończenie transakcji środowiska uruchomieniowego.  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|Działanie|XS: ciąg|Nazwa typu działania.|  
|Nazwa wyświetlana|XS: ciąg|Nazwa wyświetlana działania.|  
|InstanceId|XS: ciąg|Identyfikator wystąpienia działania.|  
|Wywołując|XS: ciąg|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
