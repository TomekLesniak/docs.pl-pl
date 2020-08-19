---
title: Rejestrowanie wywołań zwrotnych żądań anulowania
ms.date: 08/14/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cancellation, how to register callbacks
ms.assetid: 8838dd75-18ed-4b8b-b322-cd4531faac64
ms.openlocfilehash: faa8dada5779f6eaee7a60e6210ec604f5fb4680
ms.sourcegitcommit: cbb19e56d48cf88375d35d0c27554d4722761e0d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/19/2020
ms.locfileid: "88608451"
---
# <a name="register-callbacks-for-cancellation-requests"></a><span data-ttu-id="d34aa-102">Rejestrowanie wywołań zwrotnych żądań anulowania</span><span class="sxs-lookup"><span data-stu-id="d34aa-102">Register callbacks for cancellation requests</span></span>

<span data-ttu-id="d34aa-103">Dowiedz się, jak zarejestrować delegata, który zostanie wywołany, gdy <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> Właściwość zostanie prawdziwa.</span><span class="sxs-lookup"><span data-stu-id="d34aa-103">Learn how to register a delegate that will be invoked when a <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> property becomes true.</span></span> <span data-ttu-id="d34aa-104">Wartość jest zmieniana z false na true, gdy następuje wywołanie do <xref:System.Threading.CancellationTokenSource.Cancel%2A> obiektu, który utworzył token.</span><span class="sxs-lookup"><span data-stu-id="d34aa-104">The value changes from false to true when a call to <xref:System.Threading.CancellationTokenSource.Cancel%2A> on the object that created the token is made.</span></span> <span data-ttu-id="d34aa-105">Ta technika służy do anulowania operacji asynchronicznych, które nie obsługują natywnie ujednoliconych struktur anulowania oraz dla metod odblokowywania, które mogą oczekiwać na zakończenie operacji asynchronicznej.</span><span class="sxs-lookup"><span data-stu-id="d34aa-105">Use this technique for canceling asynchronous operations that do not natively support the unified cancellation framework, and for unblocking methods that might be waiting for an asynchronous operation to finish.</span></span>

> [!NOTE]
> <span data-ttu-id="d34aa-106">Po włączeniu "Tylko mój kod" program Visual Studio będzie przerywał pracę w wierszu, który zgłosi wyjątek i wyświetli komunikat o błędzie "wyjątek nie jest obsługiwany przez kod użytkownika".</span><span class="sxs-lookup"><span data-stu-id="d34aa-106">When "Just My Code" is enabled, Visual Studio in some cases will break on the line that throws the exception and display an error message that says "exception not handled by user code."</span></span> <span data-ttu-id="d34aa-107">Ten błąd jest niegroźny.</span><span class="sxs-lookup"><span data-stu-id="d34aa-107">This error is benign.</span></span> <span data-ttu-id="d34aa-108">Możesz nacisnąć klawisz <kbd>F5</kbd> , aby kontynuować z niego i zobaczyć zachowanie obsługi wyjątków, które przedstawiono w poniższych przykładach.</span><span class="sxs-lookup"><span data-stu-id="d34aa-108">You can press <kbd>F5</kbd> to continue from it, and see the exception-handling behavior that is demonstrated in the examples below.</span></span> <span data-ttu-id="d34aa-109">Aby zapobiec utracie przez program Visual Studio pierwszego błędu, po prostu usuń zaznaczenie pola wyboru "Tylko mój kod" w obszarze **Narzędzia, opcje, debugowanie, ogólne**.</span><span class="sxs-lookup"><span data-stu-id="d34aa-109">To prevent Visual Studio from breaking on the first error, just uncheck the "Just My Code" checkbox under **Tools, Options, Debugging, General**.</span></span>

## <a name="example"></a><span data-ttu-id="d34aa-110">Przykład</span><span class="sxs-lookup"><span data-stu-id="d34aa-110">Example</span></span>

<span data-ttu-id="d34aa-111">W poniższym przykładzie <xref:System.Net.WebClient.CancelAsync%2A> Metoda jest zarejestrowana jako metoda do wywołania w przypadku żądania anulowania za pomocą tokenu anulowania.</span><span class="sxs-lookup"><span data-stu-id="d34aa-111">In the following example, the <xref:System.Net.WebClient.CancelAsync%2A> method is registered as the method to be invoked when cancellation is requested through the cancellation token.</span></span>

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.cancellation.callback/cs/howtoexample1.cs":::
:::code language="vb" source="../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.cancellation.callback/vb/howtoexample1.vb":::

<span data-ttu-id="d34aa-112">Jeśli po zarejestrowaniu wywołania zwrotnego zostało już zgłoszone żądanie anulowania, wywołanie zwrotne jest nadal gwarantowane.</span><span class="sxs-lookup"><span data-stu-id="d34aa-112">If cancellation has already been requested when the callback is registered, the callback is still guaranteed to be called.</span></span> <span data-ttu-id="d34aa-113">W tym konkretnym przypadku <xref:System.Net.WebClient.CancelAsync%2A> Metoda nie będzie niczego robić, jeśli żadna operacja asynchroniczna nie jest w toku, więc zawsze jest bezpieczna do wywołania metody.</span><span class="sxs-lookup"><span data-stu-id="d34aa-113">In this particular case, the <xref:System.Net.WebClient.CancelAsync%2A> method will do nothing if no asynchronous operation is in progress, so it is always safe to call the method.</span></span>

## <a name="see-also"></a><span data-ttu-id="d34aa-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="d34aa-114">See also</span></span>

- [<span data-ttu-id="d34aa-115">Anulowanie w zarządzanych wątkach</span><span class="sxs-lookup"><span data-stu-id="d34aa-115">Cancellation in managed threads</span></span>](cancellation-in-managed-threads.md)
- <xref:System.Net.WebClient.DownloadStringTaskAsync(System.String)?displayProperty=nameWithType>
