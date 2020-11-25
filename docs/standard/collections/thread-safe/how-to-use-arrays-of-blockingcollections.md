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
# <a name="how-to-use-arrays-of-blocking-collections-in-a-pipeline"></a><span data-ttu-id="de71b-102">Instrukcje: Używanie tablic kolekcji blokujących w potoku</span><span class="sxs-lookup"><span data-stu-id="de71b-102">How to: Use Arrays of Blocking Collections in a Pipeline</span></span>

<span data-ttu-id="de71b-103">Poniższy przykład pokazuje, jak używać tablic <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType> obiektów ze statycznymi metodami, takimi jak <xref:System.Collections.Concurrent.BlockingCollection%601.TryAddToAny%2A> i <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny%2A> do implementowania szybkiego i elastycznego transferu danych między składnikami.</span><span class="sxs-lookup"><span data-stu-id="de71b-103">The following example shows how to use arrays of <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType> objects with static methods such as <xref:System.Collections.Concurrent.BlockingCollection%601.TryAddToAny%2A> and <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny%2A> to implement fast and flexible data transfer between components.</span></span>  
  
## <a name="example"></a><span data-ttu-id="de71b-104">Przykład</span><span class="sxs-lookup"><span data-stu-id="de71b-104">Example</span></span>  

 <span data-ttu-id="de71b-105">Poniższy przykład pokazuje podstawową implementację potoku, w której każdy obiekt jednocześnie pobiera dane z kolekcji wejściowej, przekształca je i przekazuje je do kolekcji wyjściowej.</span><span class="sxs-lookup"><span data-stu-id="de71b-105">The following example demonstrates a basic pipeline implementation in which each object is concurrently taking data from the input collection, transforming it, and passing it to the output collection.</span></span>  
  
 [!code-csharp[CDS_BlockingCollection#07](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example07.cs#07)]
 [!code-vb[CDS_BlockingCollection#07](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/bcpipeline.vb#07)]  
  
## <a name="see-also"></a><span data-ttu-id="de71b-106">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="de71b-106">See also</span></span>

- <xref:System.Collections.Concurrent?displayProperty=nameWithType>
- [<span data-ttu-id="de71b-107">Kolekcje bezpieczne dla wątków</span><span class="sxs-lookup"><span data-stu-id="de71b-107">Thread-Safe Collections</span></span>](index.md)
