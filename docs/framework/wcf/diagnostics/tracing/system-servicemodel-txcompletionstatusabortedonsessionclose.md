---
title: System.ServiceModel.TxCompletionStatusAbortedOnSessionClose
ms.date: 03/30/2017
ms.assetid: 7e142e9d-e81b-4309-974a-02e9cc064ea0
ms.openlocfilehash: 0d8c77d01351b0c62e0186e5aee69ca70aebe15e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96274325"
---
# <a name="systemservicemodeltxcompletionstatusabortedonsessionclose"></a>System.ServiceModel.TxCompletionStatusAbortedOnSessionClose

Określona transakcja została przerwana, ponieważ została zakończona, gdy sesja została zamknięta i TransactionAutoCompleteOnSessionClose OperationBehaviorAttribute będący została ustawiona na wartość false.  
  
## <a name="description"></a>Opis  

 Śledzone, jeśli bieżąca aktywna sesja została zamknięta i transakcja nie została ukończona, a TransactionAutoCompleteOnSessionClose jest ustawiona na `false` .  
  
## <a name="troubleshooting"></a>Rozwiązywanie problemów  

 Ten ślad wskazuje potencjalną usterkę aplikacji, która powinna zostać zbadana.  
  
## <a name="see-also"></a>Zobacz też

- [Śledzenie](index.md)
- [Rozwiązywanie problemów z aplikacją za pomocą śledzenia](using-tracing-to-troubleshoot-your-application.md)
- [Administracja i Diagnostyka](../index.md)
