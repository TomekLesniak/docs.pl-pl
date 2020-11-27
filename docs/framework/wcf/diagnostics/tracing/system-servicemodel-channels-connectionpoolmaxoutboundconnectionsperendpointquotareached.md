---
title: Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure
ms.date: 03/30/2017
ms.assetid: 1b9f5139-e122-4716-9ef7-2f38e1813993
ms.openlocfilehash: 3e4e1ff7ea8d8768c8d902dc09bd3b78646c2caf
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96256329"
---
# <a name="microsofttransactionstransactionbridgeenlisttransactionfailure"></a>Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure

Usługa protokołu WS-AT nie może zarejestrować się w transakcji przy użyciu podanego kontekstu koordynacji.  
  
## <a name="description"></a>Opis  

 Śledzone, gdy usługa MSDTC nie może zarejestrować się w transakcji dla danego protokołu 2PC.  Może się tak zdarzyć, ponieważ transakcja już nie istnieje, rejestracja nie jest już dozwolona lub zbyt wiele rejestracji już istnieje.  
  
## <a name="troubleshooting"></a>Rozwiązywanie problemów  

 Sprawdź ciąg stanu w komunikacie śledzenia, aby określić, czy istnieje jakikolwiek element możliwy do wykonania.  
  
## <a name="see-also"></a>Zobacz też

- [Śledzenie](index.md)
- [Rozwiązywanie problemów z aplikacją za pomocą śledzenia](using-tracing-to-troubleshoot-your-application.md)
- [Administracja i Diagnostyka](../index.md)
