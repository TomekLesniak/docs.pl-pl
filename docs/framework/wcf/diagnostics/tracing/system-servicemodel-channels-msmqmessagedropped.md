---
title: System.ServiceModel.Channels.MsmqMessageDropped
ms.date: 03/30/2017
ms.assetid: 8b6e644d-fa68-4be7-abe9-3659671a37c1
ms.openlocfilehash: 6e8b134f61d2dc9bd5daf541db4ec81604166baa
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96260386"
---
# <a name="systemservicemodelchannelsmsmqmessagedropped"></a>System.ServiceModel.Channels.MsmqMessageDropped

Wiadomość została porzucona przez usługę MSMQ.  
  
## <a name="description"></a>Opis  

 Śledzenie wskazuje, że komunikat usługi MSMQ został porzucony. Komunikaty usługi MSMQ można porzucić, gdy Windows Communication Foundation (WCF) (używane z usługą Msmqbinding lub MsmqIntegrationBinding) nie może ich przetworzyć. Takie komunikaty nazywa się skażonymi komunikatami.  
  
 Trująca wiadomość jest usuwana, gdy `ReceiveErrorHandling` Właściwość w sieci msmqbinding lub MsmqIntegrationBinding jest ustawiona na `Drop` . Usunięty komunikat jest usuwany z kolejki i nie jest już możliwy do odzyskania.  
  
 Aby uzyskać więcej informacji na temat sytuacji, w których komunikaty stają się trujące i jak skonfigurować usługę do odpowiednich potrzeb, zobacz [Obsługa komunikatów trujących](../../feature-details/poison-message-handling.md).  
  
## <a name="see-also"></a>Zobacz też

- [Śledzenie](index.md)
- [Rozwiązywanie problemów z aplikacją za pomocą śledzenia](using-tracing-to-troubleshoot-your-application.md)
- [Administracja i Diagnostyka](../index.md)
- [Obsługa komunikatów trujących](../../feature-details/poison-message-handling.md)
