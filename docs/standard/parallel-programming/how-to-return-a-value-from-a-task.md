---
title: 'Instrukcje: Zwracanie wartości z zadania'
description: Zobacz, jak używać typu System. Threading. Tasks. Task <TResult> do zwracania wartości z właściwości wynik w programie .NET.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to return a value
ms.assetid: c4bc0f44-eba2-4e96-9e03-1cc787461e61
ms.openlocfilehash: c7a4a683545c9ef0448d9cdce769aae79215aecf
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94825614"
---
# <a name="how-to-return-a-value-from-a-task"></a><span data-ttu-id="e11bf-103">Instrukcje: Zwracanie wartości z zadania</span><span class="sxs-lookup"><span data-stu-id="e11bf-103">How to: Return a Value from a Task</span></span>
<span data-ttu-id="e11bf-104">W tym przykładzie pokazano, jak za pomocą <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> typu zwrócić wartość z <xref:System.Threading.Tasks.Task%601.Result%2A> właściwości.</span><span class="sxs-lookup"><span data-stu-id="e11bf-104">This example shows how to use the <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> type to return a value from the <xref:System.Threading.Tasks.Task%601.Result%2A> property.</span></span> <span data-ttu-id="e11bf-105">Wymaga, aby folder C:\Users\Public\Pictures\Sample obrazy \ katalog istnieje i zawierał pliki.</span><span class="sxs-lookup"><span data-stu-id="e11bf-105">It requires that the C:\Users\Public\Pictures\Sample Pictures\ directory exists, and that it contains files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e11bf-106">Przykład</span><span class="sxs-lookup"><span data-stu-id="e11bf-106">Example</span></span>  
 [!code-csharp[TPL#10](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl/cs/returnavalue10.cs#10)]
 [!code-vb[TPL#10](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl/vb/10_returnavalue.vb#10)]  
  
 <span data-ttu-id="e11bf-107"><xref:System.Threading.Tasks.Task%601.Result%2A>Właściwość blokuje wątek wywołujący do momentu zakończenia zadania.</span><span class="sxs-lookup"><span data-stu-id="e11bf-107">The <xref:System.Threading.Tasks.Task%601.Result%2A> property blocks the calling thread until the task finishes.</span></span>  
  
 <span data-ttu-id="e11bf-108">Aby dowiedzieć się, jak przekazać wynik jednego <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> do zadania kontynuacji, zobacz Tworzenie [łańcucha zadań przy użyciu zadań kontynuacji](chaining-tasks-by-using-continuation-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="e11bf-108">To see how to pass the result of one <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> to a continuation task, see [Chaining Tasks by Using Continuation Tasks](chaining-tasks-by-using-continuation-tasks.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e11bf-109">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="e11bf-109">See also</span></span>

- [<span data-ttu-id="e11bf-110">Programowanie asynchroniczne oparte na zadaniach</span><span class="sxs-lookup"><span data-stu-id="e11bf-110">Task-based Asynchronous Programming</span></span>](task-based-asynchronous-programming.md)
- [<span data-ttu-id="e11bf-111">Wyrażenia lambda w PLINQ i TPL</span><span class="sxs-lookup"><span data-stu-id="e11bf-111">Lambda Expressions in PLINQ and TPL</span></span>](lambda-expressions-in-plinq-and-tpl.md)
