---
title: 3557 — TransactedReceiveScopeEndCommitFailed
ms.date: 03/30/2017
ms.assetid: 079f0188-8146-49ee-b6ae-a08f4e4d2b9b
ms.openlocfilehash: 4a4979047481687ef0d5c9d5891dec8f2826beed
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96263662"
---
# <a name="3557---transactedreceivescopeendcommitfailed"></a>3557 — TransactedReceiveScopeEndCommitFailed

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID (Identyfikator)|3557|  
|Słowa kluczowe|WFServices|  
|Poziom|Informacje|  
|Kanał|Microsoft-Windows-Application Server-Applications/Analytics|  
  
## <a name="description"></a>Opis  

 Wskazuje, że wywołanie metody EndCommit na CommittableTransaction zgłosiło wyjątek TransactionException.  
  
## <a name="message"></a>Wiadomość  

 Wywołanie metody metody EndCommit na CommittableTransaction o identyfikatorze "%1" spowodowało wyjęcie operacji TransactionException z następującym komunikatem: "%2".  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|TransactionId|XS: ciąg|Identyfikator CommittableTransaction.|  
|Wyjątek|XS: ciąg|Szczegóły wyjątku dla wyjątku|  
|Wywołując|XS: ciąg|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
