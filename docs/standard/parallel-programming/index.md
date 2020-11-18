---
title: Programowanie równoległe w .NET
description: Dowiedz się więcej na temat programowania równoległego w programie .NET. Użyj środowiska uruchomieniowego platformy .NET, typów bibliotek klas i narzędzi diagnostycznych, aby uprościć Programowanie na platformie .NET.
ms.date: 09/12/2018
helpviewer_keywords:
- parallel programming
ms.assetid: 4d83c690-ad2d-489e-a2e0-b85b898a672d
ms.openlocfilehash: 4d141a6a8fd7b7bf1aad943f8b911c8b39267223
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94820361"
---
# <a name="parallel-programming-in-net"></a>Programowanie równoległe w .NET

Wiele komputerów osobistych i stacji roboczych ma wiele rdzeni procesora, które umożliwiają jednoczesne wykonywanie wielu wątków. Aby skorzystać ze sprzętu, możesz zrównoleglanie swój kod w celu dystrybucji pracy na wielu procesorach.

W przeszłości przetwarzanie równoległe wymagało operowania wątkami i blokadami na niskim poziomie. Programy Visual Studio i .NET rozszerzają obsługę programowania równoległego przez dostarczanie środowiska uruchomieniowego, typów bibliotek klas i narzędzi diagnostycznych. Te funkcje, które zostały wprowadzone w .NET Framework 4, upraszczają programowanie równoległe. Można napisać wydajny, szczegółowy i skalowalny kod równoległy w naturalnym idiom bez konieczności bezpośredniej pracy z wątkami lub pulą wątków.

Poniższa ilustracja przedstawia ogólny przegląd architektury programowania równoległego w programie .NET.

![Architektura programowania równoległego .NET](./media/tpl-architecture.png)

## <a name="related-topics"></a>Tematy pokrewne

|Technologia|Opis|
|----------------|-----------------|
|[Biblioteka zadań równoległych (TPL)](task-parallel-library-tpl.md)|Zawiera dokumentację <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType> klasy, która obejmuje równoległe wersje `For` i `ForEach` pętle, a także dla <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> klasy, która reprezentuje preferowany sposób ekspresowych operacji asynchronicznych.|
|[Równoległe LINQ (PLINQ)](introduction-to-plinq.md)|Implementacja przetwarzania równoległego LINQ to Objects, która znacznie zwiększa wydajność w wielu scenariuszach.|
|[Struktury danych dla programowania równoległego](data-structures-for-parallel-programming.md)|Zawiera łącza do dokumentacji dla kolekcji klas o bezpiecznych wątkowo, lekkich typów synchronizacji i typów d inicjowania z opóźnieniem.|
|[narzędzia diagnostyczne równoległe](parallel-diagnostic-tools.md)|Zawiera łącza do dokumentacji programu Visual Studio debugger Windows na potrzeby zadań i stosów równoległych oraz dla [wizualizatora współbieżności](/visualstudio/profiling/concurrency-visualizer).|
|[Niestandardowe partycje dla PLINQ i TPL](custom-partitioners-for-plinq-and-tpl.md)|W tym artykule opisano, jak działają moduły partycjonowania i jak konfigurować domyślne moduły partycjonowania lub tworzyć nowe.|
|[Harmonogramy zadań](xref:System.Threading.Tasks.TaskScheduler)|Opisano, jak działa harmonogram zadań i jak można konfigurować domyślny harmonogram.|
|[Wyrażenia lambda w PLINQ i TPL](lambda-expressions-in-plinq-and-tpl.md)|Zawiera krótki przegląd wyrażeń lambda w języku C# i Visual Basic i przedstawia, jak są używane w PLINQ i w bibliotece zadań równoległych.|
|[Dalsze informacje](for-further-reading-parallel-programming.md)|Zawiera łącza do dodatkowych informacji i przykładowych zasobów na potrzeby programowania równoległego w programie .NET.|

## <a name="see-also"></a>Zobacz także

- [Przegląd Async](../async.md)
- [Zarządzane wątki](../threading/index.md)
