---
title: Wyjątki dotyczące transakcji
ms.date: 03/30/2017
ms.assetid: 1d27ed51-7eda-477f-9eca-94fa129f3e07
ms.openlocfilehash: dcdf825699368617335f2d59a05f8826884a8e9e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96285684"
---
# <a name="transaction-exceptions"></a>Wyjątki dotyczące transakcji

W tym temacie wymieniono wszystkie wyjątki wygenerowane przez transakcję Windows Communication Foundation (WCF).  
  
## <a name="exception-list"></a>Lista wyjątków  
  
|Kod zasobu|Ciąg zasobu|  
|-------------------|---------------------|  
|SFxCannotHaveDifferentTransactionProtocolsInOneBinding|Informacje o zasadach importowane z metadanych określają różne wartości element TransactionProtocol między operacjami. Obsługiwane jest tylko pojedyncze element TransactionProtocol dla każdego punktu końcowego.|  
|SFxTransactionAutoCompleteFalseAndInstanceContextMode|Wartość TransactionAutoComplete nie może być fałszywa, chyba że wartość InstanceContextmode usługi jest PerSession. Znaleziono błąd w implementacji określonego kontraktu i operacji.|  
|SFxTransactionInvalidSetTransactionComplete|Element OperationContext. SetTransactionComplete można wywołać w operacji tylko wtedy, gdy wartość TransactionAutoComplete jest ustawiona na false, a wartość TransactionScopeRequired jest ustawiona na true. Jest to nieprawidłowy scenariusz, a bieżąca transakcja została przerwana.|  
|TransactionFlowRequiredIssuedTokens|Przepływy wystawionych tokenów muszą być również obsługiwane w przepływie transakcji.|  
|TrustDriverVersionDoesNotSupportIssuedTokens|Skonfigurowana wersja zaufania nie obsługuje wystawionych tokenów. Użyj WSTrustFeb2005 lub nowszego.|
