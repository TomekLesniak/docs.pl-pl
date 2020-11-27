---
title: 4201 — EndSqlCommandExecute
ms.date: 03/30/2017
ms.assetid: ae0dbc15-f98c-4096-a8d9-fbe4dc36f1cd
ms.openlocfilehash: 0d6326889077e36ad49aa6267ae7285849c6818d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275869"
---
# <a name="4201---endsqlcommandexecute"></a>4201 — EndSqlCommandExecute

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID (Identyfikator)|4201|  
|Słowa kluczowe|WFInstanceStore|  
|Poziom|Pełny|  
|Kanał|Microsoft-Windows-Application Server — aplikacje/debugowanie|  
  
## <a name="description"></a>Opis  

 Wskazuje, że polecenie SQL zakończyło wykonywanie.  
  
## <a name="message"></a>Wiadomość  

 Zakończenie wykonywania polecenia SQL: %1  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|SqlCommand|XS: ciąg|Polecenie SQL, które zostało wykonane.|  
|Wywołując|XS: ciąg|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
