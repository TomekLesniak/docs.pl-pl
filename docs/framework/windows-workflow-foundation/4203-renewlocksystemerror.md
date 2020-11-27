---
title: 4203 — RenewLockSystemError
ms.date: 03/30/2017
ms.assetid: 6ec9ec6f-4ae2-45cf-b99b-02cdb9dc9ec9
ms.openlocfilehash: 17617e25c5cf8cecae608438529e9ce1a7d506f7
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96251272"
---
# <a name="4203---renewlocksystemerror"></a>4203 — RenewLockSystemError

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID (Identyfikator)|4203|  
|Słowa kluczowe|WFInstanceStore|  
|Poziom|Błąd|  
|Kanał|Microsoft-Windows-Application Server — aplikacje/debugowanie|  
  
## <a name="description"></a>Opis  

 Wskazuje, że dostawca SQL nie może zwiększyć wygaśnięcia blokady z powodu wygaśnięcia blokady lub usunięcia właściciela blokady. Obiekt SqlWorkflowInstanceStore zostanie przerwana.  
  
## <a name="message"></a>Wiadomość  

 Nie można zwiększyć ważności blokady, upłynął już okres ważności blokady lub właściciel blokady został usunięty. Przerywanie obiekt SqlWorkflowInstanceStore.  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|Wywołując|XS: ciąg|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
