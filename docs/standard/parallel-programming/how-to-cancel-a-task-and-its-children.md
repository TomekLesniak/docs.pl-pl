---
title: 'Instrukcje: Anulowanie zadania i jego elementów podrzędnych'
description: Zobacz przykłady sposobów anulowania zadania i jego elementów podrzędnych w programie .NET. Przykłady obejmują kroki z możliwością anulowania zadań, aby zauważyć, że zadanie zostało anulowane.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to cancel
ms.assetid: 08574301-8331-4719-ad50-9cf7f6ff3048
ms.openlocfilehash: 82a71faf3a2390f5bb36dd896cf865f773f54bd9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713226"
---
# <a name="how-to-cancel-a-task-and-its-children"></a><span data-ttu-id="8f9f2-104">Instrukcje: Anulowanie zadania i jego elementów podrzędnych</span><span class="sxs-lookup"><span data-stu-id="8f9f2-104">How to: Cancel a Task and Its Children</span></span>

<span data-ttu-id="8f9f2-105">W poniższych przykładach pokazano, jak wykonywać następujące zadania:</span><span class="sxs-lookup"><span data-stu-id="8f9f2-105">These examples show how to perform the following tasks:</span></span>  
  
1. <span data-ttu-id="8f9f2-106">Utwórz i uruchom zadanie z możliwością anulowania.</span><span class="sxs-lookup"><span data-stu-id="8f9f2-106">Create and start a cancelable task.</span></span>  
  
2. <span data-ttu-id="8f9f2-107">Przekaż token anulowania do delegata użytkownika i opcjonalnie do wystąpienia zadania.</span><span class="sxs-lookup"><span data-stu-id="8f9f2-107">Pass a cancellation token to your user delegate and optionally to the task instance.</span></span>  
  
3. <span data-ttu-id="8f9f2-108">Zwróć uwagę i Odpowiedz na żądanie anulowania w oddelegowaniu użytkownika.</span><span class="sxs-lookup"><span data-stu-id="8f9f2-108">Notice and respond to the cancellation request in your user delegate.</span></span>  
  
4. <span data-ttu-id="8f9f2-109">Opcjonalnie Zwróć uwagę na wątek wywołujący, że zadanie zostało anulowane.</span><span class="sxs-lookup"><span data-stu-id="8f9f2-109">Optionally notice on the calling thread that the task was canceled.</span></span>  
  
 <span data-ttu-id="8f9f2-110">Wątek wywołujący nie wymusi zakończyć zadania; tylko sygnalizuje to żądanie anulowania.</span><span class="sxs-lookup"><span data-stu-id="8f9f2-110">The calling thread does not forcibly end the task; it only signals that cancellation is requested.</span></span> <span data-ttu-id="8f9f2-111">Jeśli zadanie jest już uruchomione, należy do delegata użytkownika, aby zwrócić uwagę na żądanie i odpowiednio odpowiedzieć.</span><span class="sxs-lookup"><span data-stu-id="8f9f2-111">If the task is already running, it is up to the user delegate to notice the request and respond appropriately.</span></span> <span data-ttu-id="8f9f2-112">Jeśli przed uruchomieniem zadania zostanie wysłane żądanie anulowania, delegat użytkownika nigdy nie zostanie wykonany, a obiekt zadania przechodzi do stanu anulowane.</span><span class="sxs-lookup"><span data-stu-id="8f9f2-112">If cancellation is requested before the task runs, then the user delegate is never executed and the task object transitions into the Canceled state.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8f9f2-113">Przykład</span><span class="sxs-lookup"><span data-stu-id="8f9f2-113">Example</span></span>  

 <span data-ttu-id="8f9f2-114">Ten przykład pokazuje, jak przerwać a <xref:System.Threading.Tasks.Task> i jego elementy podrzędne w odpowiedzi na żądanie anulowania.</span><span class="sxs-lookup"><span data-stu-id="8f9f2-114">This example shows how to terminate a <xref:System.Threading.Tasks.Task> and its children in response to a cancellation request.</span></span> <span data-ttu-id="8f9f2-115">Pokazuje również, że gdy delegat użytkownika kończy działanie przez wyrzucanie <xref:System.Threading.Tasks.TaskCanceledException> , wątek wywołujący może opcjonalnie użyć <xref:System.Threading.Tasks.Task.Wait%2A> metody lub <xref:System.Threading.Tasks.Task.WaitAll%2A> metody, aby poczekać na zakończenie zadań.</span><span class="sxs-lookup"><span data-stu-id="8f9f2-115">It also shows that when a user delegate terminates by throwing a <xref:System.Threading.Tasks.TaskCanceledException>, the calling thread can optionally use the <xref:System.Threading.Tasks.Task.Wait%2A> method or <xref:System.Threading.Tasks.Task.WaitAll%2A> method to wait for the tasks to finish.</span></span> <span data-ttu-id="8f9f2-116">W takim przypadku należy użyć `try/catch` bloku, aby obsłużyć wyjątki w wątku wywołującym.</span><span class="sxs-lookup"><span data-stu-id="8f9f2-116">In this case, you must use a `try/catch` block to handle the exceptions on the calling thread.</span></span>  
  
 [!code-csharp[TPL_Cancellation#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_cancellation/cs/cancel1.cs#04)]
 [!code-vb[TPL_Cancellation#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_cancellation/vb/cancel1.vb#04)]  
  
 <span data-ttu-id="8f9f2-117"><xref:System.Threading.Tasks.Task?displayProperty=nameWithType>Klasa jest w pełni zintegrowana z modelem anulowania opartym na <xref:System.Threading.CancellationTokenSource?displayProperty=nameWithType> typach i <xref:System.Threading.CancellationToken?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="8f9f2-117">The <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> class is fully integrated with the cancellation model that is based on the <xref:System.Threading.CancellationTokenSource?displayProperty=nameWithType> and <xref:System.Threading.CancellationToken?displayProperty=nameWithType> types.</span></span> <span data-ttu-id="8f9f2-118">Aby uzyskać więcej informacji, zobacz [Anulowanie w zarządzanych wątkach](../threading/cancellation-in-managed-threads.md) i [Anulowanie zadania](task-cancellation.md).</span><span class="sxs-lookup"><span data-stu-id="8f9f2-118">For more information, see [Cancellation in Managed Threads](../threading/cancellation-in-managed-threads.md) and [Task Cancellation](task-cancellation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f9f2-119">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="8f9f2-119">See also</span></span>

- <xref:System.Threading.CancellationTokenSource?displayProperty=nameWithType>
- <xref:System.Threading.CancellationToken?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType>
- [<span data-ttu-id="8f9f2-120">Programowanie asynchroniczne oparte na zadaniach</span><span class="sxs-lookup"><span data-stu-id="8f9f2-120">Task-based Asynchronous Programming</span></span>](task-based-asynchronous-programming.md)
- [<span data-ttu-id="8f9f2-121">Dołączone i odłączone zadania podrzędne</span><span class="sxs-lookup"><span data-stu-id="8f9f2-121">Attached and Detached Child Tasks</span></span>](attached-and-detached-child-tasks.md)
- [<span data-ttu-id="8f9f2-122">Wyrażenia lambda w PLINQ i TPL</span><span class="sxs-lookup"><span data-stu-id="8f9f2-122">Lambda Expressions in PLINQ and TPL</span></span>](lambda-expressions-in-plinq-and-tpl.md)
