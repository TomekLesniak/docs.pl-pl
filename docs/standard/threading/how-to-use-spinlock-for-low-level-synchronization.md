---
title: 'Instrukcje: korzystanie z struktury spinlock w przypadku synchronizacji niskiego poziomu'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SpinLock, how to use
ms.assetid: a9ed3e4e-4f29-4207-b730-ed0a51ecbc19
ms.openlocfilehash: 8f81df527f83183804132ce09ae713fbbcf6f3ce
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634249"
---
# <a name="how-to-use-spinlock-for-low-level-synchronization"></a>Instrukcje: korzystanie z struktury spinlock w przypadku synchronizacji niskiego poziomu

Poniższy przykład ilustruje sposób użycia <xref:System.Threading.SpinLock> . W tym przykładzie Sekcja krytyczna wykonuje minimalną ilość pracy, co sprawia, że jest dobrym kandydatem do <xref:System.Threading.SpinLock> . Zwiększenie nakładu pracy spowoduje zwiększenie wydajności w <xref:System.Threading.SpinLock> porównaniu do standardowej blokady. Istnieje jednak punkt, w którym struktury SpinLock jest droższa od standardowej blokady. Możesz użyć funkcji profilowania współbieżności w narzędziach profilowania, aby sprawdzić, który typ blokady zapewnia lepszą wydajność programu. Aby uzyskać więcej informacji, zobacz [Concurrency Visualizer](/visualstudio/profiling/concurrency-visualizer).  
  
 [!code-csharp[CDS_SpinLock#02](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinlock/cs/spinlockdemo.cs#02)]
 [!code-vb[CDS_SpinLock#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinlock/vb/spinlock_vb.vb#02)]  
  
 <xref:System.Threading.SpinLock> może być przydatne, gdy blokada zasobu udostępnionego nie będzie utrzymywana przez bardzo długi czas. W takich przypadkach na komputerach z procesorem wielordzeniowym może być skuteczny, aby zablokowany wątek mógł obracać się na kilka cykli do momentu zwolnienia blokady. Przez nawirowanie wątek nie stanie się zablokowany, co stanowi proces intensywnie obciążający procesor CPU. <xref:System.Threading.SpinLock> program przestanie obracać się pod pewnymi warunkami, aby zapobiec przetrzymywaniu procesorów logicznych lub niewersji priorytetu w systemach z funkcją wielowątkowości.  
  
 Ten przykład używa <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType> klasy, która wymaga synchronizacji użytkowników w przypadku dostępu wielowątkowego. Innym rozwiązaniem jest użycie <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=nameWithType> , które nie wymaga żadnych blokad użytkownika.  
  
 Zwróć uwagę na użycie `false` w wywołaniu metody <xref:System.Threading.SpinLock.Exit%2A?displayProperty=nameWithType> . Zapewnia to najlepszą wydajność. Określ `true` w architekturach IA64, aby użyć ogrodzenia pamięci, która opróżnia bufory zapisu, aby upewnić się, że blokada jest teraz dostępna dla innych wątków do wprowadzenia.
  
## <a name="see-also"></a>Zobacz też

- [Wątkowość obiektów i funkcji](threading-objects-and-features.md)
- [lock — Instrukcja (C#)](../../csharp/language-reference/keywords/lock-statement.md)
- [SyncLock — instrukcja (Visual Basic)](../../visual-basic/language-reference/statements/synclock-statement.md)
