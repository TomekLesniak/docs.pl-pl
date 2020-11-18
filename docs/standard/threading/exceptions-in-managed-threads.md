---
title: Wyjątki w zarządzanych wątkach
description: Zobacz, jak Nieobsłużone wyjątki są obsługiwane w programie .NET. Większość nieobsłużonych wyjątków wątku działa naturalnie i prowadzić do zakończenia działania aplikacji.
ms.date: 03/30/2017
helpviewer_keywords:
- unhandled exceptions,in managed threads
- threading [.NET],unhandled exceptions
- threading [.NET],exceptions in managed threads
- managed threading
ms.assetid: 11294769-2e89-43cb-890e-ad4ad79cfbee
ms.openlocfilehash: e5acda4137d020d35d3144e9cc61e174024e165a
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94826472"
---
# <a name="exceptions-in-managed-threads"></a>Wyjątki w zarządzanych wątkach

Środowisko uruchomieniowe języka wspólnego pozwala na wykonywanie większości nieobsługiwanych wyjątków w wątkach. W większości przypadków, nieobsłużony wyjątek powoduje przerwanie działania aplikacji.
  
Środowisko uruchomieniowe języka wspólnego zapewnia Nieobsłużone wyjątki, które są używane do sterowania przepływem programu:  
  
- Element <xref:System.Threading.ThreadAbortException> jest generowany w wątku, ponieważ <xref:System.Threading.Thread.Abort%2A> został wywołany.  
  
- <xref:System.AppDomainUnloadedException>Jest zgłaszany w wątku, ponieważ trwa zwalnianie domeny aplikacji, w której wykonywany jest wątek.  
  
- Środowisko uruchomieniowe języka wspólnego lub proces hosta przerywa wątek przez wygenerowanie wewnętrznego wyjątku.  
  
 Jeśli którykolwiek z tych wyjątków nie jest obsługiwany w wątkach utworzonych przez środowisko uruchomieniowe języka wspólnego, wyjątek kończy działanie wątku, ale środowisko uruchomieniowe języka wspólnego nie zezwala na dalsze dalsze dalsze działanie.  
  
 Jeśli te wyjątki są nieobsługiwane w wątku głównym lub w wątkach, które zostały wprowadzone w środowisku uruchomieniowym z kodu niezarządzanego, zwykle działają normalnie, co spowoduje zakończenie działania aplikacji.  
  
> [!NOTE]
> Jest możliwe, aby środowisko uruchomieniowe zgłosiło nieobsłużony wyjątek, zanim kod zarządzany miał szansę na zainstalowanie programu obsługi wyjątków. Chociaż kod zarządzany nie był w stanie obsłużyć takiego wyjątku, wyjątek można przeprowadzić w naturalny sposób.  
  
## <a name="exposing-threading-problems-during-development"></a>Uwidacznianie problemów wielowątkowości podczas opracowywania  
 Gdy wątki mogą kończyć się niepowodzeniem w trybie dyskretnym, bez przerywania działania aplikacji, nie wykryto poważnych problemów programistycznych. Jest to konkretny problem dotyczący usług i innych aplikacji uruchamianych przez Rozszerzone okresy. Gdy wątki zakończą się niepowodzeniem, stan programu stopniowo ulega uszkodzeniu. Wydajność aplikacji może być gorsza lub aplikacja może przestać odpowiadać.  
  
 Zezwalanie na Nieobsłużone wyjątki w wątkach w sposób naturalny, dopóki system operacyjny nie zakończy działania programu, ujawnia takie problemy podczas tworzenia i testowania. Raporty o błędach programu obsługują debugowanie.  
  
## <a name="change-from-previous-versions"></a>Zmień z poprzednich wersji

W .NET Framework wersje 1,0 i 1,1 środowisko uruchomieniowe języka wspólnego zapewnia Nieobsłużone wyjątki w następujących sytuacjach:  
  
- Nie ma takiego znaczenia jako nieobsłużonego wyjątku w wątku puli wątków. Gdy zadanie zgłasza wyjątek, który nie jest obsługiwany, środowisko uruchomieniowe drukuje ślad stosu wyjątku do konsoli programu, a następnie zwraca wątek do puli wątków.  
  
- Nie ma takiego znaczenia jako nieobsłużony wyjątek w wątku utworzonym za pomocą <xref:System.Threading.Thread.Start%2A> metody <xref:System.Threading.Thread> klasy. Gdy kod uruchomiony w takim wątku zgłasza wyjątek, który nie jest obsługiwany, środowisko uruchomieniowe drukuje ślad stosu wyjątku do konsoli programu, a następnie przerywa działanie wątku.  
  
- Nie ma takiego znaczenia jako nieobsłużonego wyjątku w wątku finalizatora. Gdy finalizator zgłasza wyjątek, który nie jest obsługiwany, środowisko uruchomieniowe drukuje ślad stosu wyjątku do konsoli programu, a następnie zezwoli wątekowi finalizatora na wznowienie działania finalizatorów.  
  
 Stan pierwszego planu lub tła wątku zarządzanego nie ma wpływu na to zachowanie.  
  
 W przypadku nieobsłużonych wyjątków w wątkach pochodzących z kodu niezarządzanego różnica jest bardziej subtelna. Okno dialogowe do dołączania JIT środowiska uruchomieniowego zastępują okno dialogowe systemu operacyjnego dla wyjątków zarządzanych lub natywnych wyjątków w wątkach, które przechodzą przez kod natywny. Proces kończy się we wszystkich przypadkach.

### <a name="migration"></a>Migracja

Jeśli przeprowadzasz migrację z .NET Framework 1,0 lub 1,1 i wystąpiła próba przerwania działania środowiska uruchomieniowego, należy wziąć pod uwagę jedną z następujących strategii migracji:  
  
- Restrukturyzacja kodu, dzięki czemu wątek zostanie bezproblemowo zakończony po odebraniu sygnału.  
  
- Użyj <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> metody, aby przerwać wątek.  
  
- Jeśli wątek musi zostać zatrzymany, aby zakończyć proces, należy wykonać wątek jako wątek w tle, dzięki czemu zostanie on automatycznie przerwany po zakończeniu procesu.  
  
We wszystkich przypadkach strategia powinna być zgodna z zaleceniami dotyczącymi projektowania wyjątków. Zobacz [wskazówki dotyczące projektowania wyjątków](../design-guidelines/exceptions.md).  
  
Jako tymczasową miarę zgodności Administratorzy mogą umieścić flagę zgodności w `<runtime>` sekcji pliku konfiguracyjnego aplikacji. Powoduje to, że środowisko uruchomieniowe języka wspólnego przywraca zachowanie wersji 1,0 i 1,1.  
  
```xml  
<legacyUnhandledExceptionPolicy enabled="1"/>  
```  
  
## <a name="host-override"></a>Zastąpienie hosta

Niezarządzany host może użyć interfejsu [ICLRPolicyManager](../../framework/unmanaged-api/hosting/iclrpolicymanager-interface.md) w interfejsie API hostingu, aby zastąpić domyślne zasady nieobsłużonego wyjątku środowiska uruchomieniowego języka wspólnego. Funkcja [ICLRPolicyManager:: SetUnhandledExceptionPolicy —](../../framework/unmanaged-api/hosting/iclrpolicymanager-setunhandledexceptionpolicy-method.md) służy do ustawiania zasad dla nieobsłużonych wyjątków.  
  
## <a name="see-also"></a>Zobacz także

- [Zarządzana wątkowość — podstawy](managed-threading-basics.md)
