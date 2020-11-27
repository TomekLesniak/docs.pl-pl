---
title: Okres odnowienia blokady hosta
ms.date: 03/30/2017
ms.assetid: f8ba94fc-27e0-4d8e-8f85-50a6d2a3cd43
ms.openlocfilehash: 82073377353be6d4f8a7d0a343c31f2b49a2873f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96268199"
---
# <a name="host-lock-renewal-period"></a>Okres odnowienia blokady hosta

Właściwość **Okres odnawiania blokady hosta** w magazynie wystąpienia przepływu pracy SQL umożliwia określenie czasu, w którym Host odnawia blokadę w wystąpieniu przepływu pracy. Blokada pozostaje ważna przez okres odnawiania blokady hosta + 30 sekund. Jeśli host nie może odnowić blokady (innymi słowy, przedłużyć dzierżawę) w tym okresie, blokada wygaśnie, a dostawca trwałości odblokowuje wystąpienie. Wartość tej właściwości jest typu TimeSpan w postaci "gg: mm: SS". Minimalna dozwolona wartość to "00:00:01" (1 sekunda). Wartość domyślna tej właściwości to "00:00:30" (30 sekund).  
  
 Ta właściwość ma znaczny wpływ na sytuacje, w których Host usługi przepływu pracy kończy się niepowodzeniem, zanim będzie mógł odblokować wystąpienie usługi przepływu pracy, do którego należy. W tym scenariuszu blokada wystąpienia usługi przepływu pracy w bazie danych trwałości jest usuwana przez dostawcę trwałości po wygaśnięciu blokady, aby inny host usługi przepływu pracy uruchomiony na tym samym komputerze lub innym komputerze w farmie serwerów mógł uzyskać blokadę i załadować wystąpienie usługi przepływu pracy do pamięci, aby wznowić jego wykonywanie od ostatniego utrwalonego stanu.  
  
 Ustawienie wyższej wartości dla tej właściwości powoduje, że wystąpienia usługi przepływu pracy mają być blokowane w trwałości bazy danych przez dłuższy czas i w związku z tym opóźniają odzyskiwanie wystąpienia od ostatniego punktu trwałości. Ustawienie krótkiego interwału dla tej właściwości powoduje, że nowe wystąpienie hosta usługi przepływu pracy umożliwia szybkie pobieranie wystąpienia niepowodzenia usługi przepływu pracy, ale powoduje zwiększenie obciążenia dla hosta usługi przepływu pracy i bazy danych SQL Server.  
  
 Magazyn wystąpień przepływu pracy SQL uruchamia zadanie wewnętrzne, które okresowo wznawia i wykrywa wystąpienia z wygasłymi blokadami. Gdy odnajdzie wystąpienia z wygasłymi blokadami, umieści je w tabeli RunnableInstances, tak aby host przepływu pracy mógł pobrać i uruchomić te wystąpienia.
