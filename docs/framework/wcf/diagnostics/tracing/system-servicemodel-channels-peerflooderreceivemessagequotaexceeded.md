---
title: System.ServiceModel.Channels.PeerFlooderReceiveMessageQuotaExceeded
ms.date: 03/30/2017
ms.assetid: b8371d0a-843e-440b-b86a-6996db131cb0
ms.openlocfilehash: d4fbbeaaa1daeea62b5495d0b30c37d0297ccd75
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96249920"
---
# <a name="systemservicemodelchannelspeerflooderreceivemessagequotaexceeded"></a>System.ServiceModel.Channels.PeerFlooderReceiveMessageQuotaExceeded

Szybkość odbierania komunikatów przychodzących jest zbyt wysoka.  
  
## <a name="description"></a>Opis  

 Ten ślad występuje podczas próby przetworzenia komunikatów przychodzących. Nie można przesłać komunikatu do określonego sąsiada, ponieważ został przekroczony limit przydziału ustawiony dla tego sąsiada. Dzieje się tak, gdy nieodpowiadający sąsiad nie może wyczyścić zaległości komunikatów oczekujących dla tego sąsiada.  
  
## <a name="troubleshooting"></a>Rozwiązywanie problemów  

 Zmniejsz szybkość, z jaką komunikaty są wysyłane w obrębie siatki.  
  
## <a name="see-also"></a>Zobacz też

- [Śledzenie](index.md)
- [Rozwiązywanie problemów z aplikacją za pomocą śledzenia](using-tracing-to-troubleshoot-your-application.md)
- [Administracja i Diagnostyka](../index.md)
