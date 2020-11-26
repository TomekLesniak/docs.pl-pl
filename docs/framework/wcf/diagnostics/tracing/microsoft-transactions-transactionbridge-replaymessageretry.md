---
title: Microsoft.Transactions.TransactionBridge.ReplayMessageRetry
ms.date: 03/30/2017
ms.assetid: e5b820ae-504d-405a-926a-9effa41d2369
ms.openlocfilehash: 23a0113488b1b1ef0bc161d4134b9325ef81406c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236718"
---
# <a name="microsofttransactionstransactionbridgereplaymessageretry"></a>Microsoft.Transactions.TransactionBridge.ReplayMessageRetry

Do koordynatora, który nie odpowiada, wysłano ponowną próbę komunikatu powtórzenia.  
  
## <a name="description"></a>Opis  

 Śledzony, jeśli lokalny Menedżer transakcji jest wymagany do ponownego wysłania komunikatu powtarzania do koordynatora wyższego, ponieważ nie otrzymał odpowiedzi w danym czasie.  
  
## <a name="troubleshooting"></a>Rozwiązywanie problemów  

 Zbadaj potencjalne problemy z siecią lub produktem, które uniemożliwiają dostarczenie odpowiedzi na czas.  Jeśli jest widocznych wiele z tych komunikatów, może to oznaczać problemy z infrastrukturą lub czasy nietypowej odpowiedzi. Oba problemy znacząco zmniejszają przepływność transakcji w ramach systemu.  
  
## <a name="see-also"></a>Zobacz też

- [Śledzenie](index.md)
- [Rozwiązywanie problemów z aplikacją za pomocą śledzenia](using-tracing-to-troubleshoot-your-application.md)
- [Administracja i Diagnostyka](../index.md)
