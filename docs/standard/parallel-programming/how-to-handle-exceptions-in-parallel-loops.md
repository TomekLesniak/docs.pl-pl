---
title: 'Instrukcje: Obsługa wyjątków w pętlach równoległych'
description: Dowiedz się, jak obsługiwać wyjątki w pętlach równoległych w programie .NET. Zapoznaj się z przykładem, jak otoczyć wszystkie wyjątki z pętli w elemencie System. AggregateException.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parallel loops, how to handle exceptions
ms.assetid: 512f0d5a-4636-4875-b766-88f20044f143
ms.openlocfilehash: e8478f27b21b9b9dbf85d68f766c24aa5b9cf600
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94825757"
---
# <a name="how-to-handle-exceptions-in-parallel-loops"></a><span data-ttu-id="c7fcf-104">Instrukcje: Obsługa wyjątków w pętlach równoległych</span><span class="sxs-lookup"><span data-stu-id="c7fcf-104">How to: Handle Exceptions in Parallel Loops</span></span>
<span data-ttu-id="c7fcf-105"><xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>Przeciążenia i <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> nie mają żadnego specjalnego mechanizmu do obsługi wyjątków, które mogą być zgłaszane.</span><span class="sxs-lookup"><span data-stu-id="c7fcf-105">The <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> and <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> overloads do not have any special mechanism to handle exceptions that might be thrown.</span></span> <span data-ttu-id="c7fcf-106">W tym aspekcie przypominają one regularne `for` i `foreach` pętle ( `For` i `For Each` w Visual Basic); nieobsłużony wyjątek powoduje przerwanie działania pętli zaraz po zakończeniu wszystkich aktualnie uruchomionych iteracji.</span><span class="sxs-lookup"><span data-stu-id="c7fcf-106">In this respect, they resemble regular `for` and `foreach` loops (`For` and `For Each` in Visual Basic); an unhandled exception causes the loop to terminate as soon as all currently running iterations finish.</span></span>
  
 <span data-ttu-id="c7fcf-107">W przypadku dodawania własnej logiki obsługi wyjątków do pętli równoległych, należy obsłużyć przypadek, w którym mogą być zgłaszane podobne wyjątki w wielu wątkach jednocześnie, a w przypadku, gdy wyjątek zgłoszony w jednym wątku powoduje zgłoszenie innego wyjątku w innym wątku.</span><span class="sxs-lookup"><span data-stu-id="c7fcf-107">When you add your own exception-handling logic to parallel loops, handle the case in which similar exceptions might be thrown on multiple threads concurrently, and the case in which an exception thrown on one thread causes another exception to be thrown on another thread.</span></span> <span data-ttu-id="c7fcf-108">Oba przypadki można obsługiwać, zawijając wszystkie wyjątki z pętli w <xref:System.AggregateException?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="c7fcf-108">You can handle both cases by wrapping all exceptions from the loop in a <xref:System.AggregateException?displayProperty=nameWithType>.</span></span> <span data-ttu-id="c7fcf-109">W poniższym przykładzie pokazano jedno z możliwych podejścia.</span><span class="sxs-lookup"><span data-stu-id="c7fcf-109">The following example shows one possible approach.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c7fcf-110">Po włączeniu "Tylko mój kod" program Visual Studio będzie przerywał pracę w wierszu, który zgłosi wyjątek i wyświetli komunikat o błędzie "wyjątek nie jest obsługiwany przez kod użytkownika".</span><span class="sxs-lookup"><span data-stu-id="c7fcf-110">When "Just My Code" is enabled, Visual Studio in some cases will break on the line that throws the exception and display an error message that says "exception not handled by user code."</span></span> <span data-ttu-id="c7fcf-111">Ten błąd jest niegroźny.</span><span class="sxs-lookup"><span data-stu-id="c7fcf-111">This error is benign.</span></span> <span data-ttu-id="c7fcf-112">Możesz nacisnąć klawisz F5, aby kontynuować z niego i zobaczyć zachowanie obsługi wyjątków, które zostało przedstawione w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="c7fcf-112">You can press F5 to continue from it, and see the exception-handling behavior that is demonstrated in the example below.</span></span> <span data-ttu-id="c7fcf-113">Aby zapobiec utracie przez program Visual Studio pierwszego błędu, po prostu usuń zaznaczenie pola wyboru "Tylko mój kod" w obszarze **Narzędzia, opcje, debugowanie, ogólne**.</span><span class="sxs-lookup"><span data-stu-id="c7fcf-113">To prevent Visual Studio from breaking on the first error, just uncheck the "Just My Code" checkbox under **Tools, Options, Debugging, General**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7fcf-114">Przykład</span><span class="sxs-lookup"><span data-stu-id="c7fcf-114">Example</span></span>  
 <span data-ttu-id="c7fcf-115">W tym przykładzie wszystkie wyjątki są przechwytywane, a następnie zawijane w <xref:System.AggregateException?displayProperty=nameWithType> , które są generowane.</span><span class="sxs-lookup"><span data-stu-id="c7fcf-115">In this example, all exceptions are caught and then wrapped in an <xref:System.AggregateException?displayProperty=nameWithType> which is thrown.</span></span> <span data-ttu-id="c7fcf-116">Obiekt wywołujący może zdecydować, które wyjątki mają być obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="c7fcf-116">The caller can decide which exceptions to handle.</span></span>  
  
 [!code-csharp[TPL_Exceptions#08](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/exceptions.cs#08)]
 [!code-vb[TPL_Exceptions#08](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/exceptionsinloops.vb#08)]  
  
## <a name="see-also"></a><span data-ttu-id="c7fcf-117">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="c7fcf-117">See also</span></span>

- [<span data-ttu-id="c7fcf-118">Równoległość danych</span><span class="sxs-lookup"><span data-stu-id="c7fcf-118">Data Parallelism</span></span>](data-parallelism-task-parallel-library.md)
- [<span data-ttu-id="c7fcf-119">Wyrażenia lambda w PLINQ i TPL</span><span class="sxs-lookup"><span data-stu-id="c7fcf-119">Lambda Expressions in PLINQ and TPL</span></span>](lambda-expressions-in-plinq-and-tpl.md)
