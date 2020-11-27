---
title: System.ServiceModel.Channels.ConnectionPoolCloseException
ms.date: 03/30/2017
ms.assetid: 8358898e-129e-4fac-a6bf-bf3aa4293ae2
ms.openlocfilehash: d8edb8e916578247e62e3a3eb3b11b80f93416cd
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96286958"
---
# <a name="systemservicemodelchannelsconnectionpoolcloseexception"></a>System.ServiceModel.Channels.ConnectionPoolCloseException

Wystąpił wyjątek podczas zamykania połączeń z tej puli połączeń.  
  
## <a name="description"></a>Opis  

 Ten ślad poziomu błędu wskazuje, że wystąpił błąd podczas zamykania pul połączeń używanych przez funkcję puli połączeń Windows Communication Foundation (WCF). Jedną z możliwych przyczyn jest to nieudane zamknięcie połączenia w puli lub zestaw połączeń w puli w ramach CloseTimeout. Gdy ten wyjątek jest zgłaszany, wszystkie pozostałe niezamknięte połączenia w tej puli są przerywane; niezamknięte połączenia w innych pulach są porzucane.  
  
## <a name="see-also"></a>Zobacz też

- [Śledzenie](index.md)
- [Rozwiązywanie problemów z aplikacją za pomocą śledzenia](using-tracing-to-troubleshoot-your-application.md)
- [Administracja i Diagnostyka](../index.md)
