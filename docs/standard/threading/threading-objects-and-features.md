---
title: Wątkowość obiektów i funkcji
ms.date: 10/01/2018
helpviewer_keywords:
- threading [.NET], features
- managed threading
ms.assetid: 239b2e8d-581b-4ca3-992b-0e8525b9321c
ms.openlocfilehash: 8a66904a6db3fa45d8a42dec4e1e42883c1c3e98
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94826173"
---
# <a name="threading-objects-and-features"></a>Wątkowość obiektów i funkcji

Wraz z <xref:System.Threading.Thread?displayProperty=nameWithType> klasą platforma .NET udostępnia wiele klas, które ułatwiają tworzenie aplikacji wielowątkowych. W poniższych artykułach przedstawiono przegląd tych klas:

|Tytuł|Opis|  
|-----------|-----------------|  
|[Zarządzana pula wątków](the-managed-thread-pool.md)|Opisuje <xref:System.Threading.ThreadPool?displayProperty=nameWithType> klasę, która dostarcza pulę wątków roboczych, które są zarządzane przez platformę .NET.|  
|[Czasomierze](timers.md)|Opisuje czasomierze programu .NET, które mogą być używane w środowisku wielowątkowym.|
|[Przegląd elementów podstawowych synchronizacji](overview-of-synchronization-primitives.md)|Opisuje typy, których można użyć do synchronizowania dostępu do współużytkowanego zasobu lub interakcji wątku kontroli.|
|[EventWaitHandle](eventwaithandle.md)|Opisuje <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType> klasę, która reprezentuje zdarzenie synchronizacji wątku.|
|[CountdownEvent](countdownevent.md)|Opisuje <xref:System.Threading.CountdownEvent?displayProperty=nameWithType> klasę, która reprezentuje zdarzenie synchronizacji wątku, które zostaje ustawione, gdy jego licznik ma wartość zero.|
|[Muteksy](mutexes.md)|Opisuje <xref:System.Threading.Mutex?displayProperty=nameWithType> klasę, która przyznaje wyłączny dostęp do zasobu udostępnionego.|
|[Semafor i klasa SemaphoreSlim](semaphore-and-semaphoreslim.md)|Opisuje <xref:System.Threading.Semaphore?displayProperty=nameWithType> klasę, która ogranicza liczbę wątków, które mogą uzyskiwać dostęp do zasobów udostępnionych lub puli zasobów współbieżnie.|
|[Bariera](barrier.md)|Opisuje <xref:System.Threading.Barrier?displayProperty=nameWithType> klasę, która implementuje wzorzec bariery do koordynacji wątków w operacjach stopniowanych.|
|[SpinLock](spinlock.md)|Opisuje <xref:System.Threading.SpinLock?displayProperty=nameWithType> strukturę, która jest lekkim alternatywą <xref:System.Threading.Monitor?displayProperty=nameWithType> dla klasy dla pewnych scenariuszy blokowania niskiego poziomu.|
|[SpinWait](spinwait.md)|Opisuje <xref:System.Threading.SpinWait?displayProperty=nameWithType> strukturę, która zapewnia obsługę czekania na grzbiet.|

## <a name="see-also"></a>Zobacz także

- <xref:System.Threading.Monitor?displayProperty=nameWithType>
- <xref:System.Threading.WaitHandle?displayProperty=nameWithType>
- <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>
- [Używanie wątków i wątkowości](using-threads-and-threading.md)
- [Asynchroniczne operacje we/wy pliku](../io/asynchronous-file-i-o.md)
- [Programowanie równoległe](../parallel-programming/index.md)
- [Biblioteka zadań równoległych (TPL)](../parallel-programming/task-parallel-library-tpl.md)
