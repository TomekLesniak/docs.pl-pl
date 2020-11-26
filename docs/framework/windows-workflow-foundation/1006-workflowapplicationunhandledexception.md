---
title: 1006 — WorkflowApplicationUnhandledException
ms.date: 03/30/2017
ms.assetid: dfe0f316-e03b-47fb-b6a3-622c56bfd753
ms.openlocfilehash: 4bb76a93ec7a07a735def1f1d5dc79decb7792ad
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239838"
---
# <a name="1006---workflowapplicationunhandledexception"></a>1006 — WorkflowApplicationUnhandledException

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID (Identyfikator)|1006|  
|Słowa kluczowe|WFRuntime|  
|Poziom|Błąd|  
|Kanał|Microsoft-Windows-Application Server — aplikacje/debugowanie|  
  
## <a name="description"></a>Opis  

 Wskazuje, że aplikacja przepływu pracy napotkała nieobsłużony wyjątek.  
  
## <a name="message"></a>Wiadomość  

 Działanie obiektu WorkflowInstance o identyfikatorze: %1 napotkało nieobsługiwany wyjątek.  Wyjątek pochodzący z działania ' %2 ', DisplayName: ' %3 '.  Zostanie podjęta następująca akcja: %4.  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|WorkflowInstanceId|`xs:string`|Identyfikator wystąpienia przepływu pracy|  
|Wyjątek|`xs:string`|Szczegóły wyjątku dla wyjątku|  
|Wywołując|`xs:string`|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
