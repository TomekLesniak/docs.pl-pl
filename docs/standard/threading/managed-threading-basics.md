---
title: Zarządzana wątkowość — podstawy
description: Zobacz linki do innych zarządzanych artykułów wątków, obejmujących tematy, takie jak wyjątki, synchronizowanie danych, pierwszy plan & wątki w tle, Magazyn lokalny i wiele innych.
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- multiple threads
- threading [.NET], multiple threads
- threading [.NET], about threading
- managed threading
ms.assetid: b2944911-0e8f-427d-a8bb-077550618935
ms.openlocfilehash: ca3073cca9887265b4bacb4f8dfeb01203f82621
ms.sourcegitcommit: 7588b1f16b7608bc6833c05f91ae670c22ef56f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/02/2020
ms.locfileid: "93189137"
---
# <a name="managed-threading-basics"></a>Zarządzane wątki — podstawy

Pierwsze pięć artykułów tej sekcji zaprojektowano w celu ułatwienia ustalenia, kiedy należy używać zarządzanych wątków i wyjaśnić niektóre podstawowe funkcje. Aby uzyskać informacje na temat klas, które udostępniają dodatkowe funkcje, zobacz temat [wątkowość obiektów i funkcji](threading-objects-and-features.md) oraz [Przegląd elementów pierwotnych synchronizacji](overview-of-synchronization-primitives.md).  
  
 Pozostałe artykuły w tej sekcji dotyczą zaawansowanych tematów, w tym interakcji z zarządzanym wątkiem z systemem operacyjnym Windows.  
  
> [!NOTE]
> Począwszy od .NET Framework 4, Biblioteka zadań równoległych i PLINQ zapewniają interfejsy API do równoległego wykonywania zadań i danych w programach wielowątkowych. Aby uzyskać więcej informacji, zobacz [programowanie równoległe](../parallel-programming/index.md).  
  
## <a name="in-this-section"></a>W tej sekcji

 [Wątki i wątkowość](threads-and-threading.md)  
 W tym artykule omówiono zalety i wady wielu wątków oraz opisano scenariusze, w których można tworzyć wątki lub używać wątków puli wątków.  
  
 [Wyjątki w zarządzanych wątkach](exceptions-in-managed-threads.md)  
 Opisuje zachowanie nieobsłużonych wyjątków w wątkach dla różnych wersji platformy .NET, w szczególności sytuacje, w których powodują zakończenie działania aplikacji.  
  
 [Synchronizowanie danych na potrzeby wielowątkowości](synchronizing-data-for-multithreading.md)  
 Opisuje strategie synchronizowania danych w klasach, które będą używane z wieloma wątkami.  
  
 [Wątki pierwszego planu i tła](foreground-and-background-threads.md)  
 Wyjaśnia różnice między wątkami na pierwszym planie i w tle.  
  
 [Zarządzana i niezarządzana wątkowość w systemie Windows](managed-and-unmanaged-threading-in-windows.md)  
 W tym artykule omówiono relacje między zarządzaną i niezarządzaną wielowątkowością, listę zarządzanych odpowiedników interfejsów API wątków systemu Windows i omówiono interakcję apartamentach COM i zarządzanych wątków.  
  
 [Pamięć lokalna wątku: Powiązane z wątkiem pola statyczne i gniazda danych](thread-local-storage-thread-relative-static-fields-and-data-slots.md)  
 Opisuje mechanizmy przechowywania względem wątków.  
  
## <a name="reference"></a>Dokumentacja

 <xref:System.Threading.Thread>  
 Zawiera dokumentację referencyjną dla klasy **wątku** , która reprezentuje wątek zarządzany, niezależnie od tego, czy pochodzi ona z kodu niezarządzanego, czy też została utworzona w zarządzanej aplikacji.  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 Zapewnia bezpieczny sposób implementacji wielowątkowości w połączeniu z obiektami interfejsu użytkownika.  
  
## <a name="related-sections"></a>Sekcje pokrewne

 [Przegląd elementów podstawowych synchronizacji](overview-of-synchronization-primitives.md)  
 Opisuje zarządzane klasy używane do synchronizowania działań wielu wątków.  
  
 [Zarządzana wątkowość — najlepsze rozwiązania](managed-threading-best-practices.md)  
 Opisuje typowe problemy związane z wielowątkowością i strategiami w celu uniknięcia problemów.  
  
 [Programowanie równoległe](../parallel-programming/index.md)  
 Opisuje bibliotekę zadań równoległych i PLINQ, co znacznie upraszcza pracę tworzenia asynchronicznych i wielowątkowych aplikacji .NET.
