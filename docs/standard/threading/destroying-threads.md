---
title: Niszczenie wątków
description: Należy znać opcje, gdy trzeba zniszczyć wątek w programie .NET, na przykład w przypadku odwołania do spółdzielni lub metody Thread. Abort. Dowiedz się, jak obsłużyć ThreadAbortException.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- destroying threads
- threading [.NET], destroying threads
ms.assetid: df54e648-c5d1-47c9-bd29-8e4438c1db6d
ms.openlocfilehash: bdba09f5709cf99bc0d076e3875a914cc7c5a11e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723769"
---
# <a name="destroying-threads"></a><span data-ttu-id="9b4b0-104">Niszczenie wątków</span><span class="sxs-lookup"><span data-stu-id="9b4b0-104">Destroying threads</span></span>

<span data-ttu-id="9b4b0-105">Aby zakończyć wykonywanie wątku, zazwyczaj używany jest [wspólny model anulowania](cancellation-in-managed-threads.md).</span><span class="sxs-lookup"><span data-stu-id="9b4b0-105">To terminate the execution of the thread, you usually use the [cooperative cancellation model](cancellation-in-managed-threads.md).</span></span> <span data-ttu-id="9b4b0-106">Czasami nie jest możliwe zatrzymywanie wątku wspólnie, ponieważ uruchamia kod innej firmy, który nie został zaprojektowany w celu uzyskania spółdzielni.</span><span class="sxs-lookup"><span data-stu-id="9b4b0-106">Sometimes it is not possible to stop a thread cooperatively, because it runs third-party code not designed for cooperative cancellation.</span></span> <span data-ttu-id="9b4b0-107"><xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>Metoda w .NET Framework może służyć do kończenia wymuszonego wymuszenia wątku zarządzanego.</span><span class="sxs-lookup"><span data-stu-id="9b4b0-107">The <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> method in .NET Framework can be used to terminate a managed thread forcibly.</span></span> <span data-ttu-id="9b4b0-108">Podczas wywoływania <xref:System.Threading.Thread.Abort%2A> , środowisko uruchomieniowe języka wspólnego generuje <xref:System.Threading.ThreadAbortException> w wątku docelowym, który wątek docelowy może przechwycić.</span><span class="sxs-lookup"><span data-stu-id="9b4b0-108">When you call <xref:System.Threading.Thread.Abort%2A>, the Common Language Runtime throws a <xref:System.Threading.ThreadAbortException> in the target thread, which the target thread can catch.</span></span> <span data-ttu-id="9b4b0-109">Aby uzyskać więcej informacji, zobacz <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9b4b0-109">For more information, see <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="9b4b0-110"><xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>Metoda nie jest obsługiwana w programie .NET 5 (w tym .NET Core) i nowszych wersjach.</span><span class="sxs-lookup"><span data-stu-id="9b4b0-110">The <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> method is not supported in .NET 5 (including .NET Core) and later versions.</span></span> <span data-ttu-id="9b4b0-111">Jeśli konieczne jest zakończenie wykonywania kodu innej firmy w programie .NET 5 +, należy uruchomić go w osobnym procesie i użyć <xref:System.Diagnostics.Process.Kill%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="9b4b0-111">If you need to terminate the execution of third-party code forcibly in .NET 5+, run it in the separate process and use <xref:System.Diagnostics.Process.Kill%2A?displayProperty=nameWithType>.</span></span>

> [!NOTE]
> <span data-ttu-id="9b4b0-112">Jeśli wątek wykonuje kod niezarządzany, gdy <xref:System.Threading.Thread.Abort%2A> Metoda jest wywoływana, środowisko uruchomieniowe go oznaczy <xref:System.Threading.ThreadState.AbortRequested?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="9b4b0-112">If a thread is executing unmanaged code when its <xref:System.Threading.Thread.Abort%2A> method is called, the runtime marks it <xref:System.Threading.ThreadState.AbortRequested?displayProperty=nameWithType>.</span></span> <span data-ttu-id="9b4b0-113">Wyjątek jest zgłaszany, gdy wątek zwraca kod zarządzany.</span><span class="sxs-lookup"><span data-stu-id="9b4b0-113">The exception is thrown when the thread returns to managed code.</span></span>  
  
 <span data-ttu-id="9b4b0-114">Po przerwaniu wątku nie można go ponownie uruchomić.</span><span class="sxs-lookup"><span data-stu-id="9b4b0-114">Once a thread is aborted, it cannot be restarted.</span></span>  
  
 <span data-ttu-id="9b4b0-115"><xref:System.Threading.Thread.Abort%2A>Metoda nie powoduje natychmiastowego przerwania wątku, ponieważ wątek docelowy może przechwycić <xref:System.Threading.ThreadAbortException> i wykonać dowolne ilości kodu w `finally` bloku.</span><span class="sxs-lookup"><span data-stu-id="9b4b0-115">The <xref:System.Threading.Thread.Abort%2A> method does not cause the thread to abort immediately, because the target thread can catch the <xref:System.Threading.ThreadAbortException> and execute arbitrary amounts of code in a `finally` block.</span></span> <span data-ttu-id="9b4b0-116">Możesz wywołać, <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> Jeśli musisz poczekać na zakończenie wątku.</span><span class="sxs-lookup"><span data-stu-id="9b4b0-116">You can call <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> if you need to wait until the thread has ended.</span></span> <span data-ttu-id="9b4b0-117"><xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> jest wywołaniem blokującym, które nie zwraca, dopóki wątek nie zostanie faktycznie zatrzymany lub upłynie opcjonalny interwał limitu czasu.</span><span class="sxs-lookup"><span data-stu-id="9b4b0-117"><xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> is a blocking call that does not return until the thread has actually stopped executing or an optional timeout interval has elapsed.</span></span> <span data-ttu-id="9b4b0-118">Przerwany wątek może wywołać <xref:System.Threading.Thread.ResetAbort%2A> metodę lub wykonać nieograniczone przetwarzanie w `finally` bloku, dlatego jeśli nie określisz limitu czasu, oczekiwania nie zostanie zakończone.</span><span class="sxs-lookup"><span data-stu-id="9b4b0-118">The aborted thread could call the <xref:System.Threading.Thread.ResetAbort%2A> method or perform unbounded processing in a `finally` block, so if you do not specify a timeout, the wait is not guaranteed to end.</span></span>  
  
 <span data-ttu-id="9b4b0-119">Wątki, które oczekują na wywołanie <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> metody mogą zostać przerwane przez inne wątki, które wywołują <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="9b4b0-119">Threads that are waiting on a call to the <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> method can be interrupted by other threads that call <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType>.</span></span>  
  
## <a name="handling-threadabortexception"></a><span data-ttu-id="9b4b0-120">Obsługa ThreadAbortException</span><span class="sxs-lookup"><span data-stu-id="9b4b0-120">Handling ThreadAbortException</span></span>  

 <span data-ttu-id="9b4b0-121">Jeśli oczekujesz, że wątek zostanie przerwany, w wyniku wywołania <xref:System.Threading.Thread.Abort%2A> z własnego kodu lub w wyniku rozładowania domeny aplikacji, w której działa wątek ( <xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> używany <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> do kończenia wątków), wątek musi obsłużyć <xref:System.Threading.ThreadAbortException> i wykonać dowolne końcowe przetwarzanie w `finally` klauzuli, jak pokazano w poniższym kodzie.</span><span class="sxs-lookup"><span data-stu-id="9b4b0-121">If you expect your thread to be aborted, either as a result of calling <xref:System.Threading.Thread.Abort%2A> from your own code or as a result of unloading an application domain in which the thread is running (<xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> uses <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> to terminate threads), your thread must handle the <xref:System.Threading.ThreadAbortException> and perform any final processing in a `finally` clause, as shown in the following code.</span></span>  
  
```vb  
Try  
    ' Code that is executing when the thread is aborted.  
Catch ex As ThreadAbortException  
    ' Clean-up code can go here.  
    ' If there is no Finally clause, ThreadAbortException is  
    ' re-thrown by the system at the end of the Catch clause.
Finally  
    ' Clean-up code can go here.  
End Try  
' Do not put clean-up code here, because the exception
' is rethrown at the end of the Finally clause.  
```  
  
```csharp  
try
{  
    // Code that is executing when the thread is aborted.  
}
catch (ThreadAbortException ex)
{  
    // Clean-up code can go here.  
    // If there is no Finally clause, ThreadAbortException is  
    // re-thrown by the system at the end of the Catch clause.
}  
// Do not put clean-up code here, because the exception
// is rethrown at the end of the Finally clause.  
```  
  
 <span data-ttu-id="9b4b0-122">Kod czyszczący musi znajdować się w `catch` klauzuli lub `finally` klauzuli, ponieważ <xref:System.Threading.ThreadAbortException> jest ponownie zgłaszany przez system na końcu `finally` klauzuli lub na końcu `catch` klauzuli, jeśli nie ma `finally` klauzuli.</span><span class="sxs-lookup"><span data-stu-id="9b4b0-122">Your clean-up code must be in the `catch` clause or the `finally` clause, because a <xref:System.Threading.ThreadAbortException> is rethrown by the system at the end of the `finally` clause, or at the end of the `catch` clause if there is no `finally` clause.</span></span>  
  
 <span data-ttu-id="9b4b0-123">Można uniemożliwić ponowne zgłoszenie wyjątku przez system, wywołując <xref:System.Threading.Thread.ResetAbort%2A?displayProperty=nameWithType> metodę.</span><span class="sxs-lookup"><span data-stu-id="9b4b0-123">You can prevent the system from rethrowing the exception by calling the <xref:System.Threading.Thread.ResetAbort%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="9b4b0-124">Jednak należy to zrobić tylko wtedy, gdy własny kod spowodował <xref:System.Threading.ThreadAbortException> .</span><span class="sxs-lookup"><span data-stu-id="9b4b0-124">However, you should do this only if your own code caused the <xref:System.Threading.ThreadAbortException>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b4b0-125">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="9b4b0-125">See also</span></span>

- <xref:System.Threading.ThreadAbortException>
- <xref:System.Threading.Thread>
- [<span data-ttu-id="9b4b0-126">Używanie wątków i wątkowości</span><span class="sxs-lookup"><span data-stu-id="9b4b0-126">Using Threads and Threading</span></span>](using-threads-and-threading.md)
