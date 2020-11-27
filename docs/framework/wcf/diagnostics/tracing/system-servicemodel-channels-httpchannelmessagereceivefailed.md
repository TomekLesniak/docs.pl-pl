---
title: System.ServiceModel.Channels.HttpChannelMessageReceiveFailed
ms.date: 03/30/2017
ms.assetid: 9eb311da-fdcc-4dd3-9d85-05b3280dfdda
ms.openlocfilehash: 97f22a01df84c39915f74fa7677e5dd18154b952
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96256225"
---
# <a name="systemservicemodelchannelshttpchannelmessagereceivefailed"></a>System.ServiceModel.Channels.HttpChannelMessageReceiveFailed

Nie można odebrać wiadomości kanałem HTTP.  
  
## <a name="description"></a>Opis  

 Ten ślad może być emitowany jako ostrzeżenie lub błąd. W obu przypadkach ślad jest emitowany, gdy nie znaleziono zgodnego odbiornika dla przychodzącego żądania HTTP, a żądanie HTTP zostanie odrzucone. Może się tak zdarzyć, ponieważ czasownik HTTP żądania nie został rozpoznany przez żaden odbiornik HTTP lub żaden odbiornik nie nasłuchuje na adresie, którego dotyczy żądanie. Ślad jest emitowany jako ostrzeżenie w przypadku samodzielnego użycia i jako błąd, gdy usługa jest hostowana w usługach IIS.  
  
## <a name="see-also"></a>Zobacz też

- [Śledzenie](index.md)
- [Rozwiązywanie problemów z aplikacją za pomocą śledzenia](using-tracing-to-troubleshoot-your-application.md)
- [Administracja i Diagnostyka](../index.md)
