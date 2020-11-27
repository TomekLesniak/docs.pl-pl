---
title: Aktywacja wystąpienia
ms.date: 03/30/2017
ms.assetid: 134c3f70-5d4e-46d0-9d49-469a6643edd8
ms.openlocfilehash: 1fd30d9d440c06c03e726ed1f1ddbebb0d5f7e8c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96279938"
---
# <a name="instance-activation"></a>Aktywacja wystąpienia

Magazyn wystąpień przepływu pracy SQL uruchamia zadanie wewnętrzne, które okresowo wznawia i wykrywa wystąpienia przepływu pracy możliwy do uruchomienia lub aktywowalnej w bazie danych trwałości. Jeśli odnajdzie wystąpienie przepływu pracy możliwy do uruchomienia, powiadamia hosta przepływu pracy, który może aktywować wystąpienie. Jeśli magazyn wystąpień znajdzie wystąpienie przepływu pracy aktywowalnej, powiadamia hosta ogólnego, który aktywuje hosta przepływu pracy, który z kolei uruchamia wystąpienie przepływu pracy. Poniższe sekcje w tym temacie wyjaśniają proces aktywacji wystąpienia szczegółowo.  
  
## <a name="detecting-and-activating-runnable-workflow-instances"></a><a name="RunnableSection"></a> Wykrywanie i aktywowanie wystąpień przepływu pracy możliwy do uruchomienia  

 Magazyn wystąpień przepływu pracy SQL traktuje wystąpienie przepływu pracy *możliwy do uruchomienia* , jeśli wystąpienie nie jest w stanie wstrzymania lub ukończone, i spełnia następujące warunki:  
  
- Wystąpienie jest odblokowane i ma oczekujący czasomierz, który wygasł.  
  
- Wystąpienie ma wygasłą blokadę.  
  
- Wystąpienie jest odblokowane i jego stan jest **wykonywany**.  
  
 Magazyn wystąpień programu SQL Workflow podnosi wartość <xref:System.Activities.DurableInstancing.HasRunnableWorkflowEvent> podczas znajdowania wystąpienia możliwy do uruchomienia. Po wykonaniu tej obiekt SqlWorkflowInstanceStore monitorowanie zostanie zatrzymane do momentu <xref:System.Activities.DurableInstancing.TryLoadRunnableWorkflowCommand> wywołania programu w sklepie.  
  
 Host przepływu pracy, który subskrybuje dla <xref:System.Activities.DurableInstancing.HasRunnableWorkflowEvent> i może załadować wystąpienie, wykonuje <xref:System.Activities.DurableInstancing.TryLoadRunnableWorkflowCommand> względem magazynu wystąpień, aby załadować wystąpienie do pamięci. Host przepływu pracy jest uznawany za możliwy do załadowania wystąpienia przepływu pracy, Jeśli host i wystąpienie mają właściwość metadanych **WorkflowServiceType** ustawioną na tę samą wartość.  
  
## <a name="detecting-and-activating-activatable-workflow-instances"></a>Wykrywanie i aktywowanie wystąpień przepływu pracy Aktywowalnej  

 Wystąpienie przepływu pracy jest uznawane za *aktywowalnej* , jeśli wystąpienie jest możliwy do uruchomienia i nie ma hosta przepływu pracy, który jest w stanie załadować wystąpienie na komputerze. Zobacz wykrywanie i aktywowanie wystąpień przepływu pracy możliwy do uruchomienia powyżej dla definicji wystąpienia przepływu pracy możliwy do uruchomienia.  
  
 Magazyn wystąpień programu SQL Workflow podnosi <xref:System.Activities.DurableInstancing.HasActivatableWorkflowEvent> czas, gdy odnajdzie wystąpienie przepływu pracy aktywowalnej w bazie danych. Po wykonaniu tej obiekt SqlWorkflowInstanceStore monitorowanie zostanie zatrzymane do momentu <xref:System.Activities.DurableInstancing.QueryActivatableWorkflowsCommand> wywołania programu w sklepie.  
  
 Gdy host ogólny, który ma subskrypcję dla <xref:System.Activities.DurableInstancing.HasActivatableWorkflowEvent> odbiera zdarzenia, wykonuje <xref:System.Activities.DurableInstancing.QueryActivatableWorkflowsCommand> względem magazynu wystąpienia, aby uzyskać parametry aktywacji wymagane do utworzenia hosta przepływu pracy. Host ogólny używa tych parametrów aktywacji do utworzenia hosta przepływu pracy, który z kolei ładuje i uruchamia wystąpienie usługi możliwy do uruchomienia.  
  
## <a name="generic-hosts"></a>Hosty ogólne  

 Host generyczny jest hostem o wartości właściwości metadanych **WorkflowServiceType** dla hostów ogólnych jest ustawiony na **WorkflowServiceType. any** , aby wskazać, że może obsługiwać dowolny typ przepływu pracy. Host ogólny ma parametr XName o nazwie **ActivationType**.  
  
 Obecnie magazyn wystąpień programu SQL Workflow obsługuje hosty ogólne z wartością parametru ActivationType ustawionego na wartość **was**. Jeśli wartość ActivationType nie jest ustawiona na WAS, magazyn wystąpień programu SQL Workflow zgłasza <xref:System.Runtime.DurableInstancing.InstancePersistenceException> . Usługa zarządzania przepływami pracy dostarczana z funkcjami hostingu systemu Windows Server AppFabric jest hostem ogólnym z ustawionym typem aktywacji **was**.  
  
 W przypadku aktywacji programu Host ogólny wymaga zestawu parametrów aktywacji do uzyskania adresu punktu końcowego, na którym można aktywować nowe hosty. Parametry aktywacji dla usługi WAS są nazwami lokacji, ścieżką do aplikacji względem lokacji oraz ścieżką do usługi względem aplikacji. Magazyn wystąpień przepływu pracy SQL przechowuje te parametry aktywacji podczas wykonywania <xref:System.Activities.DurableInstancing.SaveWorkflowCommand> .  
  
## <a name="runnable-instances-detection-period"></a>Okres wykrywania wystąpień możliwych do uruchomienia  

 Właściwość **okres wykrywania wystąpień możliwy do uruchomienia** magazynu wystąpień przepływu pracy SQL określa czas, po upływie którego magazyn wystąpień przepływu pracy SQL uruchamia zadanie wykrywania w celu wykrycia dowolnego wystąpienia przepływu pracy możliwy do uruchomienia lub aktywowalnej w bazie danych trwałości po poprzednim cyklu wykrywania. Zobacz [okres wykrywania wystąpień możliwy do uruchomienia](runnable-instances-detection-period.md) , aby uzyskać więcej informacji na temat tej właściwości.
