---
title: Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout
ms.date: 03/30/2017
ms.assetid: 2dbe34c5-57c7-4b64-9257-63021911d03c
ms.openlocfilehash: bc2cdc2221ec522b44c36ef3320b77124d61850e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236705"
---
# <a name="microsofttransactionstransactionbridgevolatileoutcometimeout"></a>Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout

Przekroczono limit czasu usługi protokołu WS-AT podczas oczekiwania na odpowiedź na komunikat o wyniku z nietrwałego uczestnika. Wynik transakcji może być wątpliwy, jeśli uczestnik zwróci wartość.  
  
## <a name="description"></a>Opis  

 Śledzenie, gdy uczestnik trwały zdecydował się zatwierdzić lub przerwać, ale nie odpowiedział na żądanie zatwierdzenia lub wycofania w określonym czasie.  
  
## <a name="troubleshooting"></a>Rozwiązywanie problemów  

 Upewnij się, że wszyscy uczestnicy nietrwałe mogą reagować w danym czasie. Domyślny okres to 180 sekund.  Jeśli jest to niewystarczające, należy zwiększyć `VolatileOutcomeDelay` zasady czasomierza dla usługi WS-AT.  
  
## <a name="see-also"></a>Zobacz też

- [Śledzenie](index.md)
- [Rozwiązywanie problemów z aplikacją za pomocą śledzenia](using-tracing-to-troubleshoot-your-application.md)
- [Administracja i Diagnostyka](../index.md)
