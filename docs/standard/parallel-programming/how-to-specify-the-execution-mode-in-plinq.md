---
title: 'Instrukcje: Określanie trybu wykonywania w PLINQ'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to use execution mode
ms.assetid: e52ff26c-c5d3-4fab-9fec-c937fb387963
ms.openlocfilehash: d45aaa04e08c0ada77a01d4f67379c9b1b8773e2
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94825549"
---
# <a name="how-to-specify-the-execution-mode-in-plinq"></a><span data-ttu-id="2b87a-102">Instrukcje: Określanie trybu wykonywania w PLINQ</span><span class="sxs-lookup"><span data-stu-id="2b87a-102">How to: Specify the Execution Mode in PLINQ</span></span>

<span data-ttu-id="2b87a-103">Ten przykład pokazuje, jak wymusić PLINQ, aby pominąć domyślne heurystyke i zrównoleglanie zapytanie niezależnie od kształtu zapytania.</span><span class="sxs-lookup"><span data-stu-id="2b87a-103">This example shows how to force PLINQ to bypass its default heuristics and parallelize a query regardless of the query's shape.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2b87a-104">Ten przykład jest przeznaczony do zademonstrowania użycia i może nie działać szybciej niż równoważne LINQ to Objects sekwencyjne zapytanie.</span><span class="sxs-lookup"><span data-stu-id="2b87a-104">This example is intended to demonstrate usage and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="2b87a-105">Aby uzyskać więcej informacji na temat przyspieszenie, zobacz [Opis przyspieszenie w PLINQ](understanding-speedup-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="2b87a-105">For more information about speedup, see [Understanding Speedup in PLINQ](understanding-speedup-in-plinq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b87a-106">Przykład</span><span class="sxs-lookup"><span data-stu-id="2b87a-106">Example</span></span>  
 [!code-csharp[PLINQ#22](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#22)]
 [!code-vb[PLINQ#22](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#22)]  
  
 <span data-ttu-id="2b87a-107">PLINQ zaprojektowano w celu wykorzystania możliwości programu przetwarzanie równoległe.</span><span class="sxs-lookup"><span data-stu-id="2b87a-107">PLINQ is designed to exploit opportunities for parallelization.</span></span> <span data-ttu-id="2b87a-108">Jednak nie wszystkie zapytania korzystają z wykonywania równoległego.</span><span class="sxs-lookup"><span data-stu-id="2b87a-108">However, not all queries benefit from parallel execution.</span></span> <span data-ttu-id="2b87a-109">Na przykład, gdy zapytanie zawiera pojedynczego delegata użytkownika, który wykonuje małą ilość pracy, zapytanie będzie zazwyczaj wykonywane szybciej sekwencyjnie.</span><span class="sxs-lookup"><span data-stu-id="2b87a-109">For example, when a query contains a single user delegate that does little work, the query will usually run faster sequentially.</span></span> <span data-ttu-id="2b87a-110">Wykonywanie sekwencyjne jest szybsze, ponieważ obciążenie związane z włączaniem wykonywania przekształcają jest droższe niż uzyskany przyspieszenie.</span><span class="sxs-lookup"><span data-stu-id="2b87a-110">Sequential execution is faster because the overhead involved in enabling parallelizing execution is more expensive than the speedup that's obtained.</span></span> <span data-ttu-id="2b87a-111">W związku z tym PLINQ nie jest automatycznie zrównoleglanie wszystkich zapytań.</span><span class="sxs-lookup"><span data-stu-id="2b87a-111">Therefore, PLINQ does not automatically parallelize every query.</span></span> <span data-ttu-id="2b87a-112">Najpierw analizuje kształt zapytania i różne operatory, które go tworzą.</span><span class="sxs-lookup"><span data-stu-id="2b87a-112">It first examines the shape of the query and the various operators that comprise it.</span></span> <span data-ttu-id="2b87a-113">Na podstawie tej analizy PLINQ w domyślnym trybie wykonywania może zdecydować się na wykonanie niektórych lub wszystkich zapytań sekwencyjnie.</span><span class="sxs-lookup"><span data-stu-id="2b87a-113">Based on this analysis, PLINQ in the default execution mode may decide to execute some or all of the query sequentially.</span></span> <span data-ttu-id="2b87a-114">Jednak w niektórych przypadkach można dowiedzieć się więcej o zapytaniu niż PLINQ jest w stanie określić na podstawie jego analizy.</span><span class="sxs-lookup"><span data-stu-id="2b87a-114">However, in some cases you may know more about your query than PLINQ is able to determine from its analysis.</span></span> <span data-ttu-id="2b87a-115">Na przykład może być wiadomo, że delegat jest kosztowny i że zapytanie będzie ostatecznie korzystać z przetwarzanie równoległe.</span><span class="sxs-lookup"><span data-stu-id="2b87a-115">For example, you may know that a delegate is expensive and that the query will definitely benefit from parallelization.</span></span> <span data-ttu-id="2b87a-116">W takich przypadkach można użyć <xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A> metody i określić <xref:System.Linq.ParallelExecutionMode.ForceParallelism> wartość, aby polecić PLINQ, aby zawsze uruchamiała zapytanie jako Parallel.</span><span class="sxs-lookup"><span data-stu-id="2b87a-116">In such cases, you can use the <xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A> method and specify the <xref:System.Linq.ParallelExecutionMode.ForceParallelism> value to instruct PLINQ to always run the query as parallel.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2b87a-117">Kompilowanie kodu</span><span class="sxs-lookup"><span data-stu-id="2b87a-117">Compiling the Code</span></span>  
 <span data-ttu-id="2b87a-118">Wytnij i wklej ten kod do [przykładu danych PLINQ](plinq-data-sample.md) i Wywołaj metodę z `Main` .</span><span class="sxs-lookup"><span data-stu-id="2b87a-118">Cut and paste this code into the [PLINQ Data Sample](plinq-data-sample.md) and call the method from `Main`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b87a-119">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="2b87a-119">See also</span></span>

- <xref:System.Linq.ParallelEnumerable.AsSequential%2A>
- [<span data-ttu-id="2b87a-120">Równoległe LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="2b87a-120">Parallel LINQ (PLINQ)</span></span>](introduction-to-plinq.md)
