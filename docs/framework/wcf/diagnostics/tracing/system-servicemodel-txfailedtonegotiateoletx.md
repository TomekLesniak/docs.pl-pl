---
title: System.ServiceModel.TxFailedToNegotiateOleTx
ms.date: 03/30/2017
ms.assetid: 3f0f0b4b-a1ad-4704-8329-455daf54892d
ms.openlocfilehash: 7b468a57409e9a473a5bbf8e3324435e65e8c60b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96295317"
---
# <a name="systemservicemodeltxfailedtonegotiateoletx"></a>System.ServiceModel.TxFailedToNegotiateOleTx

Nie można ukończyć negocjacji protokołu OleTransactions dla określonego kontekstu koordynacji.  
  
## <a name="description"></a>Opis  

 Śledzone w przypadku, gdy transakcja przychodząca z informacjami OleTx nie może używać dołączonych informacji OleTx i zostanie przywrócona w zamian przy użyciu protokołu WS-AT.  
  
## <a name="troubleshooting"></a>Rozwiązywanie problemów  

 Wskazuje potencjalny problem z komunikacją RPC usługi MSDTC między maszynami. Jeśli wiele z tych śladów jest wyświetlanych w dzienniku, może wynikać drastyczne zmniejszenie wydajności.  Jeśli OleTx nie jest wymagana, ustaw wartość `OleTxUpgradeEnabled` 0 w konfiguracji rejestru WS-AT.  
  
## <a name="see-also"></a>Zobacz też

- [Śledzenie](index.md)
- [Rozwiązywanie problemów z aplikacją za pomocą śledzenia](using-tracing-to-troubleshoot-your-application.md)
- [Administracja i Diagnostyka](../index.md)
