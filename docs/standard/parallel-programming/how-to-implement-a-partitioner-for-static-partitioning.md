---
title: 'Instrukcje: Implementowanie partycjonera dla partycjonowania statycznego'
ms.date: 03/30/2017
helpviewer_keywords:
- tasks, how to create a static partitioner
ms.assetid: f4410508-cac6-4ba7-bef1-c5e68b2794f3
ms.openlocfilehash: 59a5519a8f129576c08604633cd3c411d3ca020e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95734494"
---
# <a name="how-to-implement-a-partitioner-for-static-partitioning"></a>Instrukcje: Implementowanie partycjonera dla partycjonowania statycznego

W poniższym przykładzie pokazano jeden ze sposobów implementacji prostego niestandardowego Partitioner dla PLINQ, który wykonuje statyczne partycjonowanie. Ponieważ partycja nie obsługuje partycji dynamicznych, nie można jej używać <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> . Ta konkretna partycja może dostarczyć przyspieszenie przez domyślną partycję zakresu dla źródeł danych, dla których każdy element wymaga wzrostu czasu przetwarzania.  
  
## <a name="example"></a>Przykład  

 [!code-csharp[TPL_Partitioners#05](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioners.cs#05)]  
  
 Partycje w tym przykładzie opierają się na założeniu liniowego wzrostu czasu przetwarzania dla każdego elementu. W świecie rzeczywistym może być trudne przewidywanie czasu przetwarzania w ten sposób. Jeśli używasz statycznej partycji z określonym źródłem danych, możesz zoptymalizować formułę partycjonowania dla źródła, dodać logikę równoważenia obciążenia lub użyć podejścia partycjonowania fragmentu, jak pokazano w [instrukcje: implementowanie partycji dynamicznych](how-to-implement-dynamic-partitions.md).  
  
## <a name="see-also"></a>Zobacz także

- [Niestandardowe partycje dla PLINQ i TPL](custom-partitioners-for-plinq-and-tpl.md)
