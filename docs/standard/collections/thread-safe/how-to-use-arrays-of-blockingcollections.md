---
title: 'Instrukcje: Używanie tablic kolekcji blokujących w potoku'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- thread-safe collections, blocking collections in pipeline
ms.assetid: a39c7ec3-3ad7-4f4d-8fe4-b3e9dbabe2ed
ms.openlocfilehash: 55dc3e9934efa153c61322f63b7dde8077442fd9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733467"
---
# <a name="how-to-use-arrays-of-blocking-collections-in-a-pipeline"></a>Instrukcje: Używanie tablic kolekcji blokujących w potoku

Poniższy przykład pokazuje, jak używać tablic <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType> obiektów ze statycznymi metodami, takimi jak <xref:System.Collections.Concurrent.BlockingCollection%601.TryAddToAny%2A> i <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny%2A> do implementowania szybkiego i elastycznego transferu danych między składnikami.  
  
## <a name="example"></a>Przykład  

 Poniższy przykład pokazuje podstawową implementację potoku, w której każdy obiekt jednocześnie pobiera dane z kolekcji wejściowej, przekształca je i przekazuje je do kolekcji wyjściowej.  
  
 [!code-csharp[CDS_BlockingCollection#07](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example07.cs#07)]
 [!code-vb[CDS_BlockingCollection#07](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/bcpipeline.vb#07)]  
  
## <a name="see-also"></a>Zobacz także

- <xref:System.Collections.Concurrent?displayProperty=nameWithType>
- [Kolekcje bezpieczne dla wątków](index.md)
