---
title: System.ServiceModel.MessageClosedAgain
ms.date: 03/30/2017
ms.assetid: 24c274d4-65cd-4c91-9869-bc6eb34ef979
ms.openlocfilehash: a8aa5e600789df1b64a8a3f1a6355aaae6a6cf4b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294433"
---
# <a name="systemservicemodelmessageclosedagain"></a>System.ServiceModel.MessageClosedAgain

System.ServiceModel.MessageClosedAgain  
  
## <a name="description"></a>Opis  

 Komunikat został zamknięty ponownie.  
  
 Komunikat powinien być zamknięty tylko raz. Jeśli ślad jest emitowany w kodzie rozszerzenia użytkownika, oznacza to, że kod rozszerzenia użytkownika zamyka komunikat, który został już zamknięty. Jeśli ślad jest emitowany za pomocą kodu produktu, oznacza to, że kod rozszerzenia użytkownika może potencjalnie zamknąć komunikat zbyt wcześnie.  
  
## <a name="see-also"></a>Zobacz też

- [Śledzenie](index.md)
- [Rozwiązywanie problemów z aplikacją za pomocą śledzenia](using-tracing-to-troubleshoot-your-application.md)
- [Administracja i Diagnostyka](../index.md)
