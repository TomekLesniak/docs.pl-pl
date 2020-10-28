---
title: Współdziałanie z innymi wzorcami asynchronicznymi i typami
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- asynchronous design patterns, .NET
- TAP, .NET support for
- Task-based Asynchronous Pattern, .NET support for
- .NET, asynchronous design patterns
ms.assetid: f120a5d9-933b-4d1d-acb6-f034a57c3749
ms.openlocfilehash: 5ad49c70aaa69d8a4f830851b80b6a4839388b0f
ms.sourcegitcommit: 4a938327bad8b2e20cabd0f46a9dc50882596f13
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/28/2020
ms.locfileid: "92888753"
---
# <a name="interop-with-other-asynchronous-patterns-and-types"></a><span data-ttu-id="57dc5-102">Współdziałanie z innymi wzorcami asynchronicznymi i typami</span><span class="sxs-lookup"><span data-stu-id="57dc5-102">Interop with Other Asynchronous Patterns and Types</span></span>

<span data-ttu-id="57dc5-103">Krótka historia asynchronicznych wzorców w programie .NET:</span><span class="sxs-lookup"><span data-stu-id="57dc5-103">A brief history of asynchronous patterns in .NET:</span></span>

- <span data-ttu-id="57dc5-104">W .NET Framework 1,0 wprowadzono <xref:System.IAsyncResult> wzorzec, w przeciwnym razie znany jako [asynchroniczny model programowania (APM)](asynchronous-programming-model-apm.md)lub `Begin/End` wzorzec.</span><span class="sxs-lookup"><span data-stu-id="57dc5-104">.NET Framework 1.0 introduced the <xref:System.IAsyncResult> pattern, otherwise known as the [Asynchronous Programming Model (APM)](asynchronous-programming-model-apm.md), or the `Begin/End` pattern.</span></span>
- <span data-ttu-id="57dc5-105">.NET Framework 2,0 dodano [wzorzec asynchroniczny oparty na zdarzeniach (EAP)](event-based-asynchronous-pattern-eap.md).</span><span class="sxs-lookup"><span data-stu-id="57dc5-105">.NET Framework 2.0 added the [Event-based Asynchronous Pattern (EAP)](event-based-asynchronous-pattern-eap.md).</span></span>
- <span data-ttu-id="57dc5-106">.NET Framework 4 wprowadził [wzorzec asynchroniczny oparty na zadaniach (TAP)](task-based-asynchronous-pattern-tap.md), który zastępuje zarówno APM, jak i EAP, i umożliwia łatwe tworzenie procedur migracji z wcześniejszych wzorców.</span><span class="sxs-lookup"><span data-stu-id="57dc5-106">.NET Framework 4 introduced the [Task-based Asynchronous Pattern (TAP)](task-based-asynchronous-pattern-tap.md), which supersedes both APM and EAP and provides the ability to easily build migration routines from the earlier patterns.</span></span>
  
## <a name="tasks-and-the-asynchronous-programming-model-apm"></a><span data-ttu-id="57dc5-107">Zadania i model programowania asynchronicznego (APM)</span><span class="sxs-lookup"><span data-stu-id="57dc5-107">Tasks and the Asynchronous Programming Model (APM)</span></span>

### <a name="from-apm-to-tap"></a><span data-ttu-id="57dc5-108">Z usługi APM do NACIŚNIĘCIa</span><span class="sxs-lookup"><span data-stu-id="57dc5-108">From APM to TAP</span></span>  
 <span data-ttu-id="57dc5-109">Ze względu na to, że wzorzec [modelu programowania asynchronicznego (APM)](asynchronous-programming-model-apm.md) jest strukturalny, można łatwo utworzyć otokę, aby uwidocznić implementację APM jako implementację TAP.</span><span class="sxs-lookup"><span data-stu-id="57dc5-109">Because the [Asynchronous Programming Model (APM)](asynchronous-programming-model-apm.md) pattern is structured, it is quite easy to build a wrapper to expose an APM implementation as a TAP implementation.</span></span> <span data-ttu-id="57dc5-110">.NET Framework 4 i nowsze wersje zawierają procedury pomocnika w postaci <xref:System.Threading.Tasks.TaskFactory.FromAsync%2A> przeciążeń metod w celu zapewnienia tego tłumaczenia.</span><span class="sxs-lookup"><span data-stu-id="57dc5-110">.NET Framework 4 and later versions include helper routines in the form of <xref:System.Threading.Tasks.TaskFactory.FromAsync%2A> method overloads to provide this translation.</span></span>  
  
 <span data-ttu-id="57dc5-111">Rozważmy <xref:System.IO.Stream> klasę i jej <xref:System.IO.Stream.BeginRead%2A> <xref:System.IO.Stream.EndRead%2A> metody, które reprezentują odpowiedniki APM do metody synchronicznej <xref:System.IO.Stream.Read%2A> :</span><span class="sxs-lookup"><span data-stu-id="57dc5-111">Consider the <xref:System.IO.Stream> class and its <xref:System.IO.Stream.BeginRead%2A> and <xref:System.IO.Stream.EndRead%2A> methods, which represent the APM counterpart to the synchronous <xref:System.IO.Stream.Read%2A> method:</span></span>  
  
 [!code-csharp[Conceptual.AsyncInterop#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Stream1.cs#1)]
 [!code-vb[Conceptual.AsyncInterop#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/stream1.vb#1)]  
[!code-csharp[Conceptual.AsyncInterop#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Stream1.cs#2)]
[!code-vb[Conceptual.AsyncInterop#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/stream1.vb#2)]  
[!code-csharp[Conceptual.AsyncInterop#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Stream1.cs#3)]
[!code-vb[Conceptual.AsyncInterop#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/stream1.vb#3)]  
  
 <span data-ttu-id="57dc5-112">Można użyć <xref:System.Threading.Tasks.TaskFactory%601.FromAsync%2A?displayProperty=nameWithType> metody do zaimplementowania otoki TAP dla tej operacji w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="57dc5-112">You can use the <xref:System.Threading.Tasks.TaskFactory%601.FromAsync%2A?displayProperty=nameWithType> method to implement a TAP wrapper for this operation as follows:</span></span>  
  
 [!code-csharp[Conceptual.AsyncInterop#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Wrap1.cs#4)]
 [!code-vb[Conceptual.AsyncInterop#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/Wrap1.vb#4)]  
  
 <span data-ttu-id="57dc5-113">Ta implementacja jest podobna do następującej:</span><span class="sxs-lookup"><span data-stu-id="57dc5-113">This implementation is similar to the following:</span></span>  
  
 [!code-csharp[Conceptual.AsyncInterop#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Wrap2.cs#5)]
 [!code-vb[Conceptual.AsyncInterop#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/Wrap2.vb#5)]  
  
### <a name="from-tap-to-apm"></a><span data-ttu-id="57dc5-114">Od TAP do APM</span><span class="sxs-lookup"><span data-stu-id="57dc5-114">From TAP to APM</span></span>  
 <span data-ttu-id="57dc5-115">Jeśli istniejąca infrastruktura oczekuje wzorca APM, należy również wykonać implementację TAP i użyć jej, w której oczekiwana jest implementacja APM.</span><span class="sxs-lookup"><span data-stu-id="57dc5-115">If your existing infrastructure expects the APM pattern, you'll also want to take a TAP implementation and use it where an APM implementation is expected.</span></span>  <span data-ttu-id="57dc5-116">Ponieważ zadania mogą być złożone, a <xref:System.Threading.Tasks.Task> Klasa implementuje <xref:System.IAsyncResult> , można użyć prostej funkcji pomocnika, aby to zrobić.</span><span class="sxs-lookup"><span data-stu-id="57dc5-116">Because tasks can be composed and  the <xref:System.Threading.Tasks.Task> class implements <xref:System.IAsyncResult>, you can use a straightforward helper function to do this.</span></span> <span data-ttu-id="57dc5-117">Poniższy kod używa rozszerzenia <xref:System.Threading.Tasks.Task%601> klasy, ale można użyć prawie identycznej funkcji dla zadań innych niż ogólne.</span><span class="sxs-lookup"><span data-stu-id="57dc5-117">The following code uses an extension of the <xref:System.Threading.Tasks.Task%601> class, but you can use an almost identical function for non-generic tasks.</span></span>  
  
 [!code-csharp[Conceptual.AsyncInterop#6](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/APM1.cs#6)]
 [!code-vb[Conceptual.AsyncInterop#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/APM1.vb#6)]  
  
 <span data-ttu-id="57dc5-118">Teraz Rozważmy przypadek, w którym masz następującą implementację TAP:</span><span class="sxs-lookup"><span data-stu-id="57dc5-118">Now, consider a case where you have the following TAP implementation:</span></span>  
  
 [!code-csharp[Conceptual.AsyncInterop#7](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/APM2.cs#7)]
 [!code-vb[Conceptual.AsyncInterop#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/APM2.vb#7)]  
  
 <span data-ttu-id="57dc5-119">i chcesz zapewnić tę implementację APM:</span><span class="sxs-lookup"><span data-stu-id="57dc5-119">and you want to provide this APM implementation:</span></span>  
  
 [!code-csharp[Conceptual.AsyncInterop#8](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/APM2.cs#8)]
 [!code-vb[Conceptual.AsyncInterop#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/APM2.vb#8)]  
[!code-csharp[Conceptual.AsyncInterop#9](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/APM2.cs#9)]
[!code-vb[Conceptual.AsyncInterop#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/APM2.vb#9)]  
  
 <span data-ttu-id="57dc5-120">Poniższy przykład ilustruje jedną migrację do APM:</span><span class="sxs-lookup"><span data-stu-id="57dc5-120">The following example demonstrates one migration to APM:</span></span>  
  
 [!code-csharp[Conceptual.AsyncInterop#10](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/APM2.cs#10)]
 [!code-vb[Conceptual.AsyncInterop#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/APM2.vb#10)]  
  
## <a name="tasks-and-the-event-based-asynchronous-pattern-eap"></a><span data-ttu-id="57dc5-121">Zadania i wzorzec asynchroniczny oparty na zdarzeniach (EAP)</span><span class="sxs-lookup"><span data-stu-id="57dc5-121">Tasks and the Event-based Asynchronous Pattern (EAP)</span></span>  
 <span data-ttu-id="57dc5-122">Otoka implementacji [wzorca asynchronicznego opartego na zdarzeniach (EAP)](event-based-asynchronous-pattern-eap.md) jest większa niż otoka wzorca APM, ponieważ wzorzec protokołu EAP ma większą odmianę i mniejszą strukturę niż wzorzec APM.</span><span class="sxs-lookup"><span data-stu-id="57dc5-122">Wrapping an [Event-based Asynchronous Pattern (EAP)](event-based-asynchronous-pattern-eap.md) implementation is more involved than wrapping an APM pattern, because the EAP pattern has more variation and less structure than the APM pattern.</span></span>  <span data-ttu-id="57dc5-123">Aby przedstawić, poniższy kod otacza `DownloadStringAsync` metodę.</span><span class="sxs-lookup"><span data-stu-id="57dc5-123">To demonstrate, the following code wraps the `DownloadStringAsync` method.</span></span>  <span data-ttu-id="57dc5-124">`DownloadStringAsync` akceptuje identyfikator URI, podnosi `DownloadProgressChanged` zdarzenie podczas pobierania, aby raportować wiele statystyk w toku i wywołuje `DownloadStringCompleted` zdarzenie po jego zakończeniu.</span><span class="sxs-lookup"><span data-stu-id="57dc5-124">`DownloadStringAsync` accepts a URI, raises the `DownloadProgressChanged` event while downloading in order to report multiple statistics on progress, and raises the `DownloadStringCompleted` event when it's done.</span></span>  <span data-ttu-id="57dc5-125">Końcowy wynik jest ciągiem zawierającym zawartość strony o określonym identyfikatorze URI.</span><span class="sxs-lookup"><span data-stu-id="57dc5-125">The final result is a string that contains the contents of the page at the specified URI.</span></span>  
  
 [!code-csharp[Conceptual.AsyncInterop#11](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/EAP1.cs#11)]
 [!code-vb[Conceptual.AsyncInterop#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/EAP1.vb#11)]  
  
## <a name="tasks-and-wait-handles"></a><span data-ttu-id="57dc5-126">Zadania i uchwyty oczekiwania</span><span class="sxs-lookup"><span data-stu-id="57dc5-126">Tasks and Wait Handles</span></span>  
  
### <a name="from-wait-handles-to-tap"></a><span data-ttu-id="57dc5-127">Z uchwytów oczekiwania na NACIŚNIĘCIe</span><span class="sxs-lookup"><span data-stu-id="57dc5-127">From Wait Handles to TAP</span></span>  
 <span data-ttu-id="57dc5-128">Chociaż uchwyty oczekiwania nie implementują wzorca asynchronicznego, zaawansowani deweloperzy mogą używać <xref:System.Threading.WaitHandle> klasy i <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A?displayProperty=nameWithType> metody dla powiadomień asynchronicznych, gdy jest ustawiona obsługa oczekiwania.</span><span class="sxs-lookup"><span data-stu-id="57dc5-128">Although wait handles don't implement an asynchronous pattern, advanced developers may use the <xref:System.Threading.WaitHandle> class and the <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A?displayProperty=nameWithType> method for asynchronous notifications when a wait handle is set.</span></span>  <span data-ttu-id="57dc5-129">Możesz otoczyć metodę, <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A> Aby włączyć alternatywną dla wszystkich zadań w przypadku oczekiwania synchronicznego na dojście oczekiwania:</span><span class="sxs-lookup"><span data-stu-id="57dc5-129">You can wrap the <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A> method to enable a task-based alternative to any synchronous wait on a wait handle:</span></span>  
  
 [!code-csharp[Conceptual.AsyncInterop#12](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Wait1.cs#12)]
 [!code-vb[Conceptual.AsyncInterop#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/Wait1.vb#12)]  
  
 <span data-ttu-id="57dc5-130">Za pomocą tej metody można używać istniejących <xref:System.Threading.WaitHandle> implementacji w metodach asynchronicznych.</span><span class="sxs-lookup"><span data-stu-id="57dc5-130">With this method, you can use existing <xref:System.Threading.WaitHandle> implementations in asynchronous methods.</span></span>  <span data-ttu-id="57dc5-131">Na przykład jeśli chcesz ograniczyć liczbę operacji asynchronicznych wykonywanych w dowolnym określonym czasie, możesz użyć semafora ( <xref:System.Threading.SemaphoreSlim?displayProperty=nameWithType> obiektu).</span><span class="sxs-lookup"><span data-stu-id="57dc5-131">For example, if you want to throttle the number of asynchronous operations that are executing at any particular time, you can utilize a semaphore (a <xref:System.Threading.SemaphoreSlim?displayProperty=nameWithType> object).</span></span>  <span data-ttu-id="57dc5-132">Można ograniczyć do *n* liczbę operacji, które są uruchamiane współbieżnie, inicjując liczbę semaforów na *n* , czekając na semafor w dowolnym momencie, gdy chcesz wykonać operację, i zwolnij semafor po wykonaniu operacji:</span><span class="sxs-lookup"><span data-stu-id="57dc5-132">You can throttle to *N* the number of operations that run concurrently by initializing the semaphore's count to *N* , waiting on the semaphore any time you want to perform an operation, and releasing the semaphore when you're done with an operation:</span></span>  
  
 [!code-csharp[Conceptual.AsyncInterop#13](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Semaphore1.cs#13)]
 [!code-vb[Conceptual.AsyncInterop#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/Semaphore1.vb#13)]  
  
 <span data-ttu-id="57dc5-133">Można również utworzyć semafor asynchroniczny, który nie bazuje na dojściach oczekiwania i zamiast tego działa całkowicie z zadaniami.</span><span class="sxs-lookup"><span data-stu-id="57dc5-133">You can also build an asynchronous semaphore that does not rely on wait handles and instead works completely with tasks.</span></span> <span data-ttu-id="57dc5-134">Aby to zrobić, można użyć technik takich jak omówione w temacie [zużywanie wzorca asynchronicznego opartego na zadaniach](consuming-the-task-based-asynchronous-pattern.md) w celu kompilowania struktur danych w oparciu o <xref:System.Threading.Tasks.Task> .</span><span class="sxs-lookup"><span data-stu-id="57dc5-134">To do this, you can use techniques such as those discussed in [Consuming the Task-based Asynchronous Pattern](consuming-the-task-based-asynchronous-pattern.md) for building data structures on top of <xref:System.Threading.Tasks.Task>.</span></span>  
  
### <a name="from-tap-to-wait-handles"></a><span data-ttu-id="57dc5-135">Od NACIŚNIĘCIa do uchwytów oczekiwania</span><span class="sxs-lookup"><span data-stu-id="57dc5-135">From TAP to Wait Handles</span></span>  
 <span data-ttu-id="57dc5-136">Jak wspomniano wcześniej, <xref:System.Threading.Tasks.Task> Klasa implementuje <xref:System.IAsyncResult> , a ta implementacja ujawnia <xref:System.Threading.Tasks.Task.System%23IAsyncResult%23AsyncWaitHandle%2A> Właściwość, która zwraca dojście oczekiwania, który zostanie ustawiony po <xref:System.Threading.Tasks.Task> zakończeniu.</span><span class="sxs-lookup"><span data-stu-id="57dc5-136">As previously mentioned, the <xref:System.Threading.Tasks.Task> class implements <xref:System.IAsyncResult>, and that implementation exposes an <xref:System.Threading.Tasks.Task.System%23IAsyncResult%23AsyncWaitHandle%2A> property that returns a wait handle that will be set when the <xref:System.Threading.Tasks.Task> completes.</span></span>  <span data-ttu-id="57dc5-137">Możesz uzyskać w <xref:System.Threading.WaitHandle> <xref:System.Threading.Tasks.Task> następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="57dc5-137">You can get a <xref:System.Threading.WaitHandle> for a <xref:System.Threading.Tasks.Task> as follows:</span></span>  
  
 [!code-csharp[Conceptual.AsyncInterop#14](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Wait1.cs#14)]
 [!code-vb[Conceptual.AsyncInterop#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/Wait1.vb#14)]  
  
## <a name="see-also"></a><span data-ttu-id="57dc5-138">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="57dc5-138">See also</span></span>

- [<span data-ttu-id="57dc5-139">Wzorzec asynchroniczny oparty na zadaniach (TAP)</span><span class="sxs-lookup"><span data-stu-id="57dc5-139">Task-based Asynchronous Pattern (TAP)</span></span>](task-based-asynchronous-pattern-tap.md)
- [<span data-ttu-id="57dc5-140">Implementacja wzorca asynchronicznego opartego na zadaniach</span><span class="sxs-lookup"><span data-stu-id="57dc5-140">Implementing the Task-based Asynchronous Pattern</span></span>](implementing-the-task-based-asynchronous-pattern.md)
- [<span data-ttu-id="57dc5-141">Wykorzystywanie wzorca asynchronicznego opartego na zadaniach</span><span class="sxs-lookup"><span data-stu-id="57dc5-141">Consuming the Task-based Asynchronous Pattern</span></span>](consuming-the-task-based-asynchronous-pattern.md)
