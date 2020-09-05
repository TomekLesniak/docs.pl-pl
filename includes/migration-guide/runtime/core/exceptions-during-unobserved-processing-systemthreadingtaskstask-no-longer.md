---
ms.openlocfilehash: bae211e5684dc1fbbb1d7e69c928e37c1c532096
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497400"
---
### <a name="exceptions-during-unobserved-processing-in-systemthreadingtaskstask-no-longer-propagate-on-finalizer-thread"></a><span data-ttu-id="c12fc-101">Wyjątki podczas niezauważalnego przetwarzania w wątku system. Threading. Tasks. Task nie są już propagowane na etapie finalizatora</span><span class="sxs-lookup"><span data-stu-id="c12fc-101">Exceptions during unobserved processing in System.Threading.Tasks.Task no longer propagate on finalizer thread</span></span>

#### <a name="details"></a><span data-ttu-id="c12fc-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="c12fc-102">Details</span></span>

<span data-ttu-id="c12fc-103">Ponieważ <xref:System.Threading.Tasks.Task?displayProperty=fullName> Klasa reprezentuje operację asynchroniczną, przechwytuje wszystkie niepoważne wyjątki, które występują podczas przetwarzania asynchronicznego.</span><span class="sxs-lookup"><span data-stu-id="c12fc-103">Because the <xref:System.Threading.Tasks.Task?displayProperty=fullName> class represents an asynchronous operation, it catches all non-severe exceptions that occur during asynchronous processing.</span></span> <span data-ttu-id="c12fc-104">W .NET Framework 4,5, jeśli wyjątek nie zostanie zaobserwowany i kod nigdy nie czeka na zadanie, wyjątek nie będzie już propagowany w wątku finalizatora i wystąpił awarię procesu podczas wyrzucania elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="c12fc-104">In the .NET Framework 4.5, if an exception is not observed and your code never waits on the task, the exception will no longer propagate on the finalizer thread and crash the process during garbage collection.</span></span> <span data-ttu-id="c12fc-105">Ta zmiana zwiększa niezawodność aplikacji, które używają klasy zadań do wykonywania niezauważalnego przetwarzania asynchronicznego.</span><span class="sxs-lookup"><span data-stu-id="c12fc-105">This change enhances the reliability of applications that use the Task class to perform unobserved asynchronous processing.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="c12fc-106">Sugestia</span><span class="sxs-lookup"><span data-stu-id="c12fc-106">Suggestion</span></span>

<span data-ttu-id="c12fc-107">Jeśli aplikacja jest zależna od nieobserwowanych wyjątków asynchronicznych propagowanych do wątku finalizatora, poprzednie zachowanie można przywrócić, dostarczając odpowiedni program obsługi <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> zdarzenia lub ustawiając [element konfiguracji środowiska uruchomieniowego](~/docs/framework/configure-apps/file-schema/runtime/throwunobservedtaskexceptions-element.md).</span><span class="sxs-lookup"><span data-stu-id="c12fc-107">If an app depends on unobserved asynchronous exceptions propagating to the finalizer thread, the previous behavior can be restored by providing an appropriate handler for the <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> event, or by setting a [runtime configuration element](~/docs/framework/configure-apps/file-schema/runtime/throwunobservedtaskexceptions-element.md).</span></span>

| <span data-ttu-id="c12fc-108">Nazwa</span><span class="sxs-lookup"><span data-stu-id="c12fc-108">Name</span></span>    | <span data-ttu-id="c12fc-109">Wartość</span><span class="sxs-lookup"><span data-stu-id="c12fc-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="c12fc-110">Zakres</span><span class="sxs-lookup"><span data-stu-id="c12fc-110">Scope</span></span>   |<span data-ttu-id="c12fc-111">Edge</span><span class="sxs-lookup"><span data-stu-id="c12fc-111">Edge</span></span>|
|<span data-ttu-id="c12fc-112">Wersja</span><span class="sxs-lookup"><span data-stu-id="c12fc-112">Version</span></span>|<span data-ttu-id="c12fc-113">4.5</span><span class="sxs-lookup"><span data-stu-id="c12fc-113">4.5</span></span>|
|<span data-ttu-id="c12fc-114">Typ</span><span class="sxs-lookup"><span data-stu-id="c12fc-114">Type</span></span>|<span data-ttu-id="c12fc-115">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="c12fc-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="c12fc-116">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="c12fc-116">Affected APIs</span></span>

- <xref:System.Threading.Tasks.Task.Run(System.Action)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task.Run(System.Action,System.Threading.CancellationToken)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task.Run(System.Func{System.Threading.Tasks.Task})?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task.Run(System.Func{System.Threading.Tasks.Task},System.Threading.CancellationToken)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task.Run%60%601(System.Func{%60%600})?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task.Run%60%601(System.Func{%60%600},System.Threading.CancellationToken)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task.Run%60%601(System.Func{System.Threading.Tasks.Task{%60%600}})?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task.Run%60%601(System.Func{System.Threading.Tasks.Task{%60%600}},System.Threading.CancellationToken)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task.Start?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task.Start(System.Threading.Tasks.TaskScheduler)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Threading.Tasks.Task.Run(System.Action)`
- `M:System.Threading.Tasks.Task.Run(System.Action,System.Threading.CancellationToken)`
- `M:System.Threading.Tasks.Task.Run(System.Func{System.Threading.Tasks.Task})`
- `M:System.Threading.Tasks.Task.Run(System.Func{System.Threading.Tasks.Task},System.Threading.CancellationToken)`
- ``M:System.Threading.Tasks.Task.Run``1(System.Func{``0})``
- ``M:System.Threading.Tasks.Task.Run``1(System.Func{``0},System.Threading.CancellationToken)``
- ``M:System.Threading.Tasks.Task.Run``1(System.Func{System.Threading.Tasks.Task{``0}})``
- ``M:System.Threading.Tasks.Task.Run``1(System.Func{System.Threading.Tasks.Task{``0}},System.Threading.CancellationToken)``
- `M:System.Threading.Tasks.Task.Start`
- `M:System.Threading.Tasks.Task.Start(System.Threading.Tasks.TaskScheduler)`

-->
