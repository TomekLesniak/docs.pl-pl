---
title: 4202 — StartSqlCommandExecute
ms.date: 03/30/2017
ms.assetid: 4559f64f-c824-4075-9e7e-4710bf30f805
ms.openlocfilehash: d3f27c6ed28efe9d099dcedfc676b839ae9b1dee
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275843"
---
# <a name="4202---startsqlcommandexecute"></a>4202 — StartSqlCommandExecute

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID (Identyfikator)|4202|  
|Słowa kluczowe|WFInstanceStore|  
|Poziom|Pełny|  
|Kanał|Microsoft-Windows-Application Server — aplikacje/debugowanie|  
  
## <a name="description"></a>Opis  

 Wskazuje, że wykonywane jest polecenie SQL.  
  
## <a name="message"></a>Wiadomość  

 Uruchamianie wykonywania polecenia SQL: %1  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|SqlCommand|XS: ciąg|Polecenie SQL, które zostało wykonane.|  
|Wywołując|XS: ciąg|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
