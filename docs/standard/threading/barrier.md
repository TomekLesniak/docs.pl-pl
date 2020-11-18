---
title: Bariera
ms.date: 09/14/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- synchronization primitives, Barrier
ms.assetid: 613a8bc7-6a28-4795-bd6c-1abd9050478f
ms.openlocfilehash: 4eab74ef07ac56a4d3ff65e67bb9fbd45dbfc9bc
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94819945"
---
# <a name="barrier"></a><span data-ttu-id="64a15-102">Bariera</span><span class="sxs-lookup"><span data-stu-id="64a15-102">Barrier</span></span>

<span data-ttu-id="64a15-103">A <xref:System.Threading.Barrier?displayProperty=nameWithType> to element pierwotny synchronizacji, który umożliwia wielu wątkom (nazywanym *uczestnikami*) równoczesne działanie na algorytmie w fazach.</span><span class="sxs-lookup"><span data-stu-id="64a15-103">A <xref:System.Threading.Barrier?displayProperty=nameWithType> is a synchronization primitive that enables multiple threads (known as *participants*) to work concurrently on an algorithm in phases.</span></span> <span data-ttu-id="64a15-104">Każdy uczestnik jest wykonywany do momentu osiągnięcia punktu bariery w kodzie.</span><span class="sxs-lookup"><span data-stu-id="64a15-104">Each participant executes until it reaches the barrier point in the code.</span></span> <span data-ttu-id="64a15-105">Bariera reprezentuje koniec jednej fazy pracy.</span><span class="sxs-lookup"><span data-stu-id="64a15-105">The barrier represents the end of one phase of work.</span></span> <span data-ttu-id="64a15-106">Gdy uczestnik osiągnie barierę, jest blokowany do momentu, aż wszyscy uczestnicy osiągnąli tę samą barierę.</span><span class="sxs-lookup"><span data-stu-id="64a15-106">When a participant reaches the barrier, it blocks until all participants have reached the same barrier.</span></span> <span data-ttu-id="64a15-107">Po osiągnięciu bariery przez wszystkich uczestników można opcjonalnie wywołać akcję po fazie.</span><span class="sxs-lookup"><span data-stu-id="64a15-107">After all participants have reached the barrier, you can optionally invoke a post-phase action.</span></span> <span data-ttu-id="64a15-108">Ta akcja po fazie może służyć do wykonywania akcji przez pojedynczy wątek, gdy wszystkie pozostałe wątki są nadal zablokowane.</span><span class="sxs-lookup"><span data-stu-id="64a15-108">This post-phase action can be used to perform actions by a single thread while all other threads are still blocked.</span></span> <span data-ttu-id="64a15-109">Po wykonaniu akcji wszystkie osoby nie zostały odblokowane.</span><span class="sxs-lookup"><span data-stu-id="64a15-109">After the action has been executed, the participants are all unblocked.</span></span>  
  
 <span data-ttu-id="64a15-110">Poniższy fragment kodu przedstawia podstawowy wzorzec bariery.</span><span class="sxs-lookup"><span data-stu-id="64a15-110">The following code snippet shows a basic barrier pattern.</span></span>  
  
 [!code-csharp[CDS_Barrier#02](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_barrier/cs/barrier.cs#02)]
 [!code-vb[CDS_Barrier#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_barrier/vb/barrier_vb.vb#02)]  
  
 <span data-ttu-id="64a15-111">Pełny przykład można znaleźć w temacie [How to: Synchronizing współbieżnych operacji z barierą](how-to-synchronize-concurrent-operations-with-a-barrier.md).</span><span class="sxs-lookup"><span data-stu-id="64a15-111">For a complete example, see [How to: synchronize concurrent operations with a Barrier](how-to-synchronize-concurrent-operations-with-a-barrier.md).</span></span>  
  
## <a name="adding-and-removing-participants"></a><span data-ttu-id="64a15-112">Dodawanie i usuwanie uczestników</span><span class="sxs-lookup"><span data-stu-id="64a15-112">Adding and removing participants</span></span>

 <span data-ttu-id="64a15-113">Podczas tworzenia <xref:System.Threading.Barrier> wystąpienia należy określić liczbę uczestników.</span><span class="sxs-lookup"><span data-stu-id="64a15-113">When you create a <xref:System.Threading.Barrier> instance, specify the number of participants.</span></span> <span data-ttu-id="64a15-114">Możesz również dynamicznie dodawać i usuwać uczestników w dowolnym momencie.</span><span class="sxs-lookup"><span data-stu-id="64a15-114">You can also add or remove participants dynamically at any time.</span></span> <span data-ttu-id="64a15-115">Na przykład, jeśli jeden z uczestników rozwiąże swoją część problemu, można przechowywać wyniki, zatrzymać wykonywanie tego wątku i wywoływać, <xref:System.Threading.Barrier.RemoveParticipant%2A?displayProperty=nameWithType> Aby zmniejszyć liczbę uczestników w barierie.</span><span class="sxs-lookup"><span data-stu-id="64a15-115">For example, if one participant solves its part of the problem, you can store the result, stop execution on that thread, and call <xref:System.Threading.Barrier.RemoveParticipant%2A?displayProperty=nameWithType> to decrement the number of participants in the barrier.</span></span> <span data-ttu-id="64a15-116">Po dodaniu uczestnika przez wywołanie <xref:System.Threading.Barrier.AddParticipant%2A?displayProperty=nameWithType> , wartość zwracana określa bieżący numer fazy, co może być przydatne w celu zainicjowania pracy nowego uczestnika.</span><span class="sxs-lookup"><span data-stu-id="64a15-116">When you add a participant by calling <xref:System.Threading.Barrier.AddParticipant%2A?displayProperty=nameWithType>, the return value specifies the current phase number, which may be useful in order to initialize the work of the new participant.</span></span>  
  
## <a name="broken-barriers"></a><span data-ttu-id="64a15-117">Naruszone bariery</span><span class="sxs-lookup"><span data-stu-id="64a15-117">Broken barriers</span></span>

 <span data-ttu-id="64a15-118">Zakleszczenie mogą wystąpić, jeśli jeden z uczestników nie osiągnie przeszkody.</span><span class="sxs-lookup"><span data-stu-id="64a15-118">Deadlocks can occur if one participant fails to reach the barrier.</span></span> <span data-ttu-id="64a15-119">Aby uniknąć tych zakleszczeń, użyj przeciążeń <xref:System.Threading.Barrier.SignalAndWait%2A?displayProperty=nameWithType> metody, aby określić limit czasu i token anulowania.</span><span class="sxs-lookup"><span data-stu-id="64a15-119">To avoid these deadlocks, use the overloads of the <xref:System.Threading.Barrier.SignalAndWait%2A?displayProperty=nameWithType> method to specify a time-out period and a cancellation token.</span></span> <span data-ttu-id="64a15-120">Te przeciążenia zwracają wartość logiczną, którą każdy uczestnik może sprawdzić przed przejściem do kolejnej fazy.</span><span class="sxs-lookup"><span data-stu-id="64a15-120">These overloads return a Boolean value that every participant can check before it continues to the next phase.</span></span>  
  
## <a name="post-phase-exceptions"></a><span data-ttu-id="64a15-121">Wyjątki po fazie</span><span class="sxs-lookup"><span data-stu-id="64a15-121">Post-phase exceptions</span></span>

 <span data-ttu-id="64a15-122">Jeśli delegat po fazie zgłasza wyjątek, jest opakowany w <xref:System.Threading.BarrierPostPhaseException> obiekt, który następnie jest propagowany do wszystkich uczestników.</span><span class="sxs-lookup"><span data-stu-id="64a15-122">If the post-phase delegate throws an exception, it is wrapped in a <xref:System.Threading.BarrierPostPhaseException> object which is then propagated to all participants.</span></span>  
  
## <a name="barrier-versus-continuewhenall"></a><span data-ttu-id="64a15-123">Bariera a ContinueWhenAll</span><span class="sxs-lookup"><span data-stu-id="64a15-123">Barrier versus ContinueWhenAll</span></span>

 <span data-ttu-id="64a15-124">Bariery są szczególnie przydatne, gdy wątki wykonują wiele faz w pętlach.</span><span class="sxs-lookup"><span data-stu-id="64a15-124">Barriers are especially useful when the threads are performing multiple phases in loops.</span></span> <span data-ttu-id="64a15-125">Jeśli kod wymaga tylko jednej lub dwóch faz pracy, należy rozważyć, czy należy używać <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> obiektów z dowolnym rodzajem niejawnego sprzężenia, w tym:</span><span class="sxs-lookup"><span data-stu-id="64a15-125">If your code requires only one or two phases of work, consider whether to use <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> objects with any kind of implicit join, including:</span></span>  
  
- <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAll%2A?displayProperty=nameWithType>  
  
- <xref:System.Threading.Tasks.Parallel.Invoke%2A?displayProperty=nameWithType>  
  
- <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>  
  
- <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="64a15-126">Aby uzyskać więcej informacji, zobacz Tworzenie [łańcucha zadań przy użyciu zadań kontynuacji](../parallel-programming/chaining-tasks-by-using-continuation-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="64a15-126">For more information, see [Chaining Tasks by Using Continuation Tasks](../parallel-programming/chaining-tasks-by-using-continuation-tasks.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64a15-127">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="64a15-127">See also</span></span>

- [<span data-ttu-id="64a15-128">Wątkowość obiektów i funkcji</span><span class="sxs-lookup"><span data-stu-id="64a15-128">Threading objects and features</span></span>](threading-objects-and-features.md)
- [<span data-ttu-id="64a15-129">Instrukcje: synchronizowanie operacji współbieżnych z barierą</span><span class="sxs-lookup"><span data-stu-id="64a15-129">How to: synchronize concurrent operations with a Barrier</span></span>](how-to-synchronize-concurrent-operations-with-a-barrier.md)
