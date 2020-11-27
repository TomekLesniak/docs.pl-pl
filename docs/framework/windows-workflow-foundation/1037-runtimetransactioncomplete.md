---
title: 1037 — RuntimeTransactionComplete
ms.date: 03/30/2017
ms.assetid: 2c8c31e0-42a9-4f46-865b-2da9ab16a0ba
ms.openlocfilehash: ad05151a1497ea4b31e0fe33fe2983c1f145f224
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294251"
---
# <a name="1037---runtimetransactioncomplete"></a>1037 — RuntimeTransactionComplete

## <a name="properties"></a>Właściwości  
  
|||  
|-|-|  
|ID (Identyfikator)|1037|  
|Słowa kluczowe|WFRuntime|  
|Poziom|Pełny|  
|Kanał|Microsoft-Windows-Application Server — aplikacje/debugowanie|  
  
## <a name="description"></a>Opis  

 Wskazuje, że transakcja czasu wykonywania została ukończona.  
  
## <a name="message"></a>Wiadomość  

 Transakcja środowiska uruchomieniowego została zakończona ze stanem "%1".  
  
## <a name="details"></a>Szczegóły  
  
|Nazwa elementu danych|Typ elementu danych|Opis|  
|--------------------|--------------------|-----------------|  
|Stan|XS: ciąg|Stan transakcji.|  
|Wywołując|XS: ciąg|Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.|
