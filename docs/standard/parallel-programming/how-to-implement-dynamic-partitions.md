---
title: 'Instrukcje: Implementowanie partycji dynamicznych'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to create a dynamic partitioner
ms.assetid: c875ad12-a161-43e6-ad1c-3d6927c536a7
ms.openlocfilehash: 1120d846743ac3b89d2d110b4d1abdd0083f9eab
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94825744"
---
# <a name="how-to-implement-dynamic-partitions"></a>Instrukcje: Implementowanie partycji dynamicznych

Poniższy przykład pokazuje, jak zaimplementować niestandardowe <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=nameWithType> , które implementują partycjonowanie dynamiczne i mogą być używane z określonych przeciążeń <xref:System.Threading.Tasks.Parallel.ForEach%2A> i z PLINQ.  
  
## <a name="example"></a>Przykład

Za każdym razem, gdy partycja jest wywoływana <xref:System.Collections.IEnumerator.MoveNext%2A> w module wyliczającym, moduł wyliczający tworzy partycję z jednym elementem listy. W przypadku PLINQ i <xref:System.Threading.Tasks.Parallel.ForEach%2A> , partycja jest <xref:System.Threading.Tasks.Task> wystąpieniem. Ponieważ żądania są wykonywane współbieżnie w wielu wątkach, jest synchronizowany dostęp do bieżącego indeksu.  

[!code-csharp[TPL_Partitioners#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioner02.cs#OrderableListPartitioner)]
[!code-vb[TPL_Partitioners#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/dynamicpartitioner.vb#04)]  

Jest to przykład partycjonowania fragmentu, z każdym fragmentem składającym się z jednego elementu. Zapewniając więcej elementów naraz, można zmniejszyć rywalizację o blokadę i teoretycznie osiągnąć wyższą wydajność. Jednak w pewnym momencie większe fragmenty mogą wymagać dodatkowej logiki równoważenia obciążenia, aby zapewnić, że wszystkie wątki są zajęte, dopóki wszystkie zadania nie zostaną wykonane.  
  
## <a name="see-also"></a>Zobacz także

* [Niestandardowe partycje dla PLINQ i TPL](custom-partitioners-for-plinq-and-tpl.md)
* [Instrukcje: Implementowanie partycjonera dla partycjonowania statycznego](how-to-implement-a-partitioner-for-static-partitioning.md)
