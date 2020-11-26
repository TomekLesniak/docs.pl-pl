---
title: Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing
ms.date: 03/30/2017
ms.assetid: 10ef3876-6f8e-4d4e-8444-f47847b64795
ms.openlocfilehash: bfa279887339f025e4cb7c9c455fd25098684073
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236614"
---
# <a name="microsofttransactionstransactionbridgedurableparticipantreplaywhilepreparing"></a>Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing

Usługa protokołu WS-AT otrzymała komunikat powtarzania od trwałego uczestnika, który nie odpowiedział na przygotowanie. W związku z tym transakcja została przerwana.  
  
## <a name="description"></a>Opis  

 Śledzone w przypadku odebrania komunikatu powtarzania, gdy trwały uczestnik nadal trwa przygotowywanie. Jest to niedozwolony komunikat dla tego stanu i transakcja zostanie przerwana.  
  
## <a name="troubleshooting"></a>Rozwiązywanie problemów

Otrzymanie tego błędu może wskazywać, że trwały uczestnik (w tym podrzędny TransactionManagers) odzyskał sprawność po awarii; nie należy jednak pamiętać o wyniku transakcji i żądania jego stanu.  
  
## <a name="see-also"></a>Zobacz też

- [Śledzenie](index.md)
- [Rozwiązywanie problemów z aplikacją za pomocą śledzenia](using-tracing-to-troubleshoot-your-application.md)
- [Administracja i Diagnostyka](../index.md)
