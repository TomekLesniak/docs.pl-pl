---
title: Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure
ms.date: 03/30/2017
ms.assetid: 3a4ead79-8550-4037-84e3-fd70ff56e001
ms.openlocfilehash: 2f0198d3c288b4c3833cdac8e5f943ba822c22e9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96252026"
---
# <a name="microsofttransactionstransactionbridgeregisterparticipantfailure"></a>Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure

Usługa protokołu WS-AT nie może zarejestrować uczestnika dla protokołu kontroli.  
  
## <a name="description"></a>Opis  

 Śledzone, jeśli usługa MSDTC wykryje Nieprawidłowe żądanie rejestracji. Przyczyną może być wiele żądań rejestracji ukończenia i błędy wewnętrzne.  
  
## <a name="troubleshooting"></a>Rozwiązywanie problemów  

 Nie próbuj rejestrować się w celu ukończenia więcej niż raz.  Sprawdź również ciąg stanu w komunikacie śledzenia, aby określić, czy istnieje jakikolwiek element możliwy do wykonania.  
  
## <a name="see-also"></a>Zobacz też

- [Śledzenie](index.md)
- [Rozwiązywanie problemów z aplikacją za pomocą śledzenia](using-tracing-to-troubleshoot-your-application.md)
- [Administracja i Diagnostyka](../index.md)
