---
title: 'Instrukcje: Anulowanie pętli Parallel.For lub ForEach'
description: Anuluj pętlę Parallel. for lub Parallel. ForEach w środowisku .NET, dostarczając obiekt tokenu anulowania do metody w parametrze ParallelOptions.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parallel foreach loop, how to cancel
- parallel for loops, how to cancel
ms.assetid: 9d19b591-ea95-4418-8ea7-b6266af9905b
ms.openlocfilehash: 842873afcba1bba3a00ccaa8c95310bd1efd3a92
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713317"
---
# <a name="how-to-cancel-a-parallelfor-or-foreach-loop"></a>Instrukcje: Anulowanie pętli Parallel.For lub ForEach

<xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>Metody i <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> obsługują anulowanie przy użyciu tokenów anulowania. Aby uzyskać więcej informacji na temat anulowania, zobacz [anulowania](../threading/cancellation-in-managed-threads.md). W pętli równoległej należy dostarczyć <xref:System.Threading.CancellationToken> do metody w <xref:System.Threading.Tasks.ParallelOptions> parametrze, a następnie zawrzeć wywołanie równoległe w bloku try-catch.  
  
## <a name="example"></a>Przykład  

 Poniższy przykład pokazuje, jak anulować wywołanie do <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> . Można zastosować takie samo podejście do <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> wywołania.  
  
 [!code-csharp[TPL_Parallel#29](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/parallel_cancel.cs#29)]
 [!code-vb[TPL_Parallel#29](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/cancelloop.vb#29)]  
  
 Jeśli token sygnalizujący anulowanie jest tym samym tokenem, który jest określony w <xref:System.Threading.Tasks.ParallelOptions> wystąpieniu, pętla równoległa zgłosi pojedynczy <xref:System.OperationCanceledException> przy anulowaniu. Jeśli jakiś inny token powoduje anulowanie, pętla zgłosi obiekt <xref:System.AggregateException> with <xref:System.OperationCanceledException> jako InnerException.  
  
## <a name="see-also"></a>Zobacz także

- [Równoległość danych](data-parallelism-task-parallel-library.md)
- [Wyrażenia lambda w PLINQ i TPL](lambda-expressions-in-plinq-and-tpl.md)
