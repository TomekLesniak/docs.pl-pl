---
title: 'Instrukcje: Mierzenie wydajności zapytań PLINQ'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to measure performance
ms.assetid: 491ba43b-2c10-473d-9aab-e2cb96446711
ms.openlocfilehash: 43f83a34531b853d108785052f637d9568c45280
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94826882"
---
# <a name="how-to-measure-plinq-query-performance"></a>Instrukcje: Mierzenie wydajności zapytań PLINQ

Ten przykład pokazuje, jak używać <xref:System.Diagnostics.Stopwatch> klasy do mierzenia czasu potrzebnego na wykonanie zapytania PLINQ.  
  
## <a name="example"></a>Przykład  
 W tym przykładzie jest używana pusta `foreach` Pętla ( `For Each` w Visual Basic) do mierzenia czasu wykonywania zapytania. W kodzie rzeczywistym pętla zwykle zawiera dodatkowe kroki przetwarzania, które dodają do łącznego czasu wykonywania zapytania. Należy zauważyć, że stopera nie jest uruchomiona przed pętlą, ponieważ jest to wykonywane po rozpoczęciu wykonywania zapytania. Jeśli potrzebujesz bardziej szczegółowych pomiarów, możesz użyć `ElapsedTicks` Właściwości zamiast `ElapsedMilliseconds` .  
  
 [!code-csharp[PLINQ#19](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/measure2.cs#19)]
 [!code-vb[PLINQ#19](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/measure2.vb#19)]  
  
 Łączny czas wykonywania jest przydatną metryką podczas eksperymentowania z implementacjami zapytań, ale nie zawsze informuje cały wątek. Aby uzyskać dokładniejszy i bogatszy widok interakcji między wątkami zapytań i innymi uruchomionymi procesami, użyj [wizualizatora współbieżności](/visualstudio/profiling/concurrency-visualizer).  
  
## <a name="see-also"></a>Zobacz także

- [Równoległe LINQ (PLINQ)](introduction-to-plinq.md)
