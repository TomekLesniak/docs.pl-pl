---
title: 4208 — RetryingSqlCommandDueToSqlError
ms.date: 03/30/2017
ms.assetid: a8e6483a-a6e4-4bbf-82ec-cd8b6e711aad
ms.openlocfilehash: 088754cb15c2e55faa1d43a1da1c79ddcddd69f1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96280419"
---
# <a name="4208---retryingsqlcommandduetosqlerror"></a>4208 — RetryingSqlCommandDueToSqlError

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID (Identyfikator)|4208|  
|Słowa kluczowe|WFInstanceStore|  
|Poziom|Informacje|  
|Kanał|Microsoft-Windows-Application Server — aplikacje/debugowanie|  
  
## <a name="description"></a>Opis  

 Wskazuje, że dostawca SQL próbuje wykonać polecenie SQL z powodu błędu SQL.  
  
## <a name="message"></a>Wiadomość  

 Ponawianie próby wykonania polecenia SQL z powodu błędu SQL o numerze %1.  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|ErrorNumber|XS: ciąg|Numer błędu SQL.|  
|Wywołując|XS: ciąg|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
