---
title: 'Instrukcje: Przyspieszanie małych jednostek pętli'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parallel loops, how to speed up
ms.assetid: c7a66677-cb59-4cbf-969a-d2e8fc61a6ce
ms.openlocfilehash: 2597e37ed5901d704c94ff960bcb4b2c97633392
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722404"
---
# <a name="how-to-speed-up-small-loop-bodies"></a><span data-ttu-id="85a20-102">Instrukcje: Przyspieszanie małych jednostek pętli</span><span class="sxs-lookup"><span data-stu-id="85a20-102">How to: Speed Up Small Loop Bodies</span></span>

<span data-ttu-id="85a20-103">Gdy <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> Pętla ma małą treść, może działać wolniej niż równoważna pętla sekwencyjna, taka jak pętla [for](../../csharp/language-reference/keywords/for.md) w C# i pętla [for](/previous-versions/visualstudio/visual-studio-2008/44kykk21(v=vs.90)) w Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="85a20-103">When a <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> loop has a small body, it might perform more slowly than the equivalent sequential loop, such as the [for](../../csharp/language-reference/keywords/for.md) loop in C# and the [For](/previous-versions/visualstudio/visual-studio-2008/44kykk21(v=vs.90)) loop in Visual Basic.</span></span> <span data-ttu-id="85a20-104">Mniejsza wydajność wynika z obciążenia związanego z partycjonowaniem danych i kosztem wywołania delegata dla każdej iteracji pętli.</span><span class="sxs-lookup"><span data-stu-id="85a20-104">Slower performance is caused by the overhead involved in partitioning the data and the cost of invoking a delegate on each loop iteration.</span></span> <span data-ttu-id="85a20-105">Aby rozwiązać takie scenariusze, <xref:System.Collections.Concurrent.Partitioner> Klasa udostępnia <xref:System.Collections.Concurrent.Partitioner.Create%2A?displayProperty=nameWithType> metodę, która umożliwia wykonywanie pętli sekwencyjnej dla treści delegata, tak aby delegat został wywołany tylko raz na partycję, a nie raz na iterację.</span><span class="sxs-lookup"><span data-stu-id="85a20-105">To address such scenarios, the <xref:System.Collections.Concurrent.Partitioner> class provides the <xref:System.Collections.Concurrent.Partitioner.Create%2A?displayProperty=nameWithType> method, which enables you to provide a sequential loop for the delegate body, so that the delegate is invoked only once per partition, instead of once per iteration.</span></span> <span data-ttu-id="85a20-106">Aby uzyskać więcej informacji, zobacz [niestandardowe partycje dla PLINQ i TPL](custom-partitioners-for-plinq-and-tpl.md).</span><span class="sxs-lookup"><span data-stu-id="85a20-106">For more information, see [Custom Partitioners for PLINQ and TPL](custom-partitioners-for-plinq-and-tpl.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="85a20-107">Przykład</span><span class="sxs-lookup"><span data-stu-id="85a20-107">Example</span></span>  

 [!code-csharp[TPL_Partitioners#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioner01.cs#01)]
 [!code-vb[TPL_Partitioners#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/partitionercreate01.vb#01)]  
  
 <span data-ttu-id="85a20-108">Podejście przedstawione w tym przykładzie jest przydatne, gdy pętla wykonuje minimalną ilość pracy.</span><span class="sxs-lookup"><span data-stu-id="85a20-108">The approach demonstrated in this example is useful when the loop performs a minimal amount of work.</span></span> <span data-ttu-id="85a20-109">Gdy prace staną się bardziej kosztowne, prawdopodobnie będziesz mieć taką samą lub lepszą wydajność przy użyciu <xref:System.Threading.Tasks.Parallel.For%2A> <xref:System.Threading.Tasks.Parallel.ForEach%2A> pętli lub z domyślną partycją.</span><span class="sxs-lookup"><span data-stu-id="85a20-109">As the work becomes more computationally expensive, you will probably get the same or better performance by using a <xref:System.Threading.Tasks.Parallel.For%2A> or <xref:System.Threading.Tasks.Parallel.ForEach%2A> loop with the default partitioner.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85a20-110">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="85a20-110">See also</span></span>

- [<span data-ttu-id="85a20-111">Równoległość danych</span><span class="sxs-lookup"><span data-stu-id="85a20-111">Data Parallelism</span></span>](data-parallelism-task-parallel-library.md)
- [<span data-ttu-id="85a20-112">Niestandardowe partycje dla PLINQ i TPL</span><span class="sxs-lookup"><span data-stu-id="85a20-112">Custom Partitioners for PLINQ and TPL</span></span>](custom-partitioners-for-plinq-and-tpl.md)
- [<span data-ttu-id="85a20-113">Iteratory (C#)</span><span class="sxs-lookup"><span data-stu-id="85a20-113">Iterators (C#)</span></span>](../../csharp/programming-guide/concepts/iterators.md)
- [<span data-ttu-id="85a20-114">Iteratory (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="85a20-114">Iterators (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/iterators.md)
- [<span data-ttu-id="85a20-115">Wyrażenia lambda w PLINQ i TPL</span><span class="sxs-lookup"><span data-stu-id="85a20-115">Lambda Expressions in PLINQ and TPL</span></span>](lambda-expressions-in-plinq-and-tpl.md)
