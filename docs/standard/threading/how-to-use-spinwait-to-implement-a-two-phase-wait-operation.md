---
title: 'Porady: korzystanie z metody SpinWait do implementacji dwufazowej operacji oczekiwania'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SpinWait, how to synchronize two-phase wait
ms.assetid: b2ac4e4a-051a-4f65-b4b9-f8e103aff195
ms.openlocfilehash: 0a8ece86d71823eb78a9ebbec661722f0e249790
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94819724"
---
# <a name="how-to-use-spinwait-to-implement-a-two-phase-wait-operation"></a>Porady: korzystanie z metody SpinWait do implementacji dwufazowej operacji oczekiwania
Poniższy przykład pokazuje, jak używać <xref:System.Threading.SpinWait?displayProperty=nameWithType> obiektu do implementowania dwufazowej operacji oczekiwania. W pierwszej fazie obiekt synchronizacji, a `Latch` , obraca się dla kilku cykli podczas sprawdzania, czy blokada stanie się dostępna. W drugiej fazie, jeśli blokada zostanie udostępniona, `Wait` Metoda zwróci metodę bez użycia polecenia, <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> Aby wykonać oczekiwanie; w przeciwnym razie `Wait` wykonuje oczekiwanie.  
  
## <a name="example"></a>Przykład  
 W tym przykładzie przedstawiono bardzo podstawową implementację elementu pierwotnego synchronizacji zamka. Tej struktury danych można użyć, gdy czasy oczekiwania są bardzo krótkie. Ten przykład służy tylko do celów demonstracyjnych. Jeśli w programie jest wymagana funkcja typu zatrzaśnięcia, rozważ użycie <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType> .  
  
 [!code-csharp[CDS_SpinWait#03](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinwait/cs/spinwait03.cs#03)]
 [!code-vb[CDS_SpinWait#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinwait/vb/spinwait2.vb#03)]  
  
 Zamk używa obiektu, <xref:System.Threading.SpinWait> Aby obracać się tylko do następnego wywołania, aby `SpinOnce` spowodować wygenerowanie <xref:System.Threading.SpinWait> wycinka czasu wątku. W tym momencie zamk wywołuje swój własny przełącznik kontekstu przez wywołanie <xref:System.Threading.WaitHandle.WaitOne%2A> <xref:System.Threading.ManualResetEvent> i przekazanie w pozostałej części wartości limitu czasu.  
  
 Dane wyjściowe rejestrowania pokazują, jak często zatrzaśnięcie było w stanie zwiększyć wydajność dzięki uzyskaniu blokady bez użycia <xref:System.Threading.ManualResetEvent> .  
  
## <a name="see-also"></a>Zobacz także

- [SpinWait](spinwait.md)
- [Wątkowość obiektów i funkcji](threading-objects-and-features.md)
