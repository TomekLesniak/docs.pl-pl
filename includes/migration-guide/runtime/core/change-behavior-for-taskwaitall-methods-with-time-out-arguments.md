---
ms.openlocfilehash: 9d0791f00db7d830fc5d327af30218a0bbfcb25f
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496292"
---
### <a name="change-in-behavior-for-taskwaitall-methods-with-time-out-arguments"></a><span data-ttu-id="857d6-101">Zmiana zachowania metod Task. WaitAll z argumentami limitu czasu</span><span class="sxs-lookup"><span data-stu-id="857d6-101">Change in behavior for Task.WaitAll methods with time-out arguments</span></span>

#### <a name="details"></a><span data-ttu-id="857d6-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="857d6-102">Details</span></span>

<span data-ttu-id="857d6-103"><xref:System.Threading.Tasks.Task.WaitAll%2A?displayProperty=nameWithType> zachowanie zostało bardziej spójne w .NET Framework 4.5.In .NET Framework 4. te metody zadziałały niespójnie.</span><span class="sxs-lookup"><span data-stu-id="857d6-103"><xref:System.Threading.Tasks.Task.WaitAll%2A?displayProperty=nameWithType> behavior was made more consistent in .NET Framework 4.5.In the .NET Framework 4, these methods behaved inconsistently.</span></span> <span data-ttu-id="857d6-104">Po upływie limitu czasu, jeśli co najmniej jedno zadanie zostało ukończone lub anulowane przed wywołaniem metody, Metoda zgłosiła <xref:System.AggregateException?displayProperty=fullName> wyjątek.</span><span class="sxs-lookup"><span data-stu-id="857d6-104">When the time-out expired, if one or more tasks were completed or canceled before the method call, the method threw an <xref:System.AggregateException?displayProperty=fullName> exception.</span></span> <span data-ttu-id="857d6-105">Po upływie limitu czasu, jeśli żadne zadania nie zostały ukończone lub anulowane przed wywołaniem metody, ale co najmniej jedno zadanie zostało wprowadzone po wywołaniu metody, Metoda zwróciła wartość false.</span><span class="sxs-lookup"><span data-stu-id="857d6-105">When the time-out expired, if no tasks were completed or canceled before the method call, but one or more tasks entered these states after the method call, the method returned false.</span></span><br/><br/><span data-ttu-id="857d6-106">W .NET Framework 4,5 te przeciążenia metody teraz zwracają wartość false, jeśli jakieś zadania są nadal uruchomione, gdy upłynął limit czasu, i zgłasza wyjątek tylko wtedy, <xref:System.AggregateException?displayProperty=fullName> gdy zadanie wejściowe zostało anulowane (bez względu na to, czy przed lub po wywołaniu metody) i nie będzie nadal działać.</span><span class="sxs-lookup"><span data-stu-id="857d6-106">In the .NET Framework 4.5, these method overloads now return false if any tasks are still running when the time-out interval expired, and they throw an <xref:System.AggregateException?displayProperty=fullName> exception only if an input task was cancelled (regardless of whether it was before or after the method call) and no other tasks are still running.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="857d6-107">Sugestia</span><span class="sxs-lookup"><span data-stu-id="857d6-107">Suggestion</span></span>

<span data-ttu-id="857d6-108">Jeśli <xref:System.AggregateException?displayProperty=fullName> został przechwycony jako środek wykrywania zadania, które zostało anulowane przed <xref:System.Threading.Tasks.Task.WaitAll%2A> wywoływaniem wywołania, ten kod powinien zamiast tego przeprowadzić wykrywanie za pośrednictwem  <xref:System.Threading.Tasks.Task.IsCanceled%2A> właściwości (na przykład:. Dowolny (t = &gt; t. Iscanceld)) ponieważ .NET Framework 4,6 będzie zgłaszany w tym przypadku tylko wtedy, gdy wszystkie oczekujące zadania zostaną zakończone przed upływem limitu czasu.</span><span class="sxs-lookup"><span data-stu-id="857d6-108">If an <xref:System.AggregateException?displayProperty=fullName> was being caught as a means of detecting a task that was cancelled prior to the <xref:System.Threading.Tasks.Task.WaitAll%2A> call being invoked, that code should instead do the same detection via the  <xref:System.Threading.Tasks.Task.IsCanceled%2A> property (for example: .Any(t =&gt; t.IsCanceled)) since .NET Framework 4.6 will only throw in that case if all awaited tasks are completed prior to the timeout.</span></span>

| <span data-ttu-id="857d6-109">Nazwa</span><span class="sxs-lookup"><span data-stu-id="857d6-109">Name</span></span>    | <span data-ttu-id="857d6-110">Wartość</span><span class="sxs-lookup"><span data-stu-id="857d6-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="857d6-111">Zakres</span><span class="sxs-lookup"><span data-stu-id="857d6-111">Scope</span></span>   |<span data-ttu-id="857d6-112">Mały</span><span class="sxs-lookup"><span data-stu-id="857d6-112">Minor</span></span>|
|<span data-ttu-id="857d6-113">Wersja</span><span class="sxs-lookup"><span data-stu-id="857d6-113">Version</span></span>|<span data-ttu-id="857d6-114">4.5</span><span class="sxs-lookup"><span data-stu-id="857d6-114">4.5</span></span>|
|<span data-ttu-id="857d6-115">Typ</span><span class="sxs-lookup"><span data-stu-id="857d6-115">Type</span></span>|<span data-ttu-id="857d6-116">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="857d6-116">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="857d6-117">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="857d6-117">Affected APIs</span></span>

- <xref:System.Threading.Tasks.Task.WaitAll(System.Threading.Tasks.Task[],System.Int32)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task.WaitAll(System.Threading.Tasks.Task[],System.Int32,System.Threading.CancellationToken)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task.WaitAll(System.Threading.Tasks.Task[],System.TimeSpan)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Threading.Tasks.Task.WaitAll(System.Threading.Tasks.Task[],System.Int32)`
- `M:System.Threading.Tasks.Task.WaitAll(System.Threading.Tasks.Task[],System.Int32,System.Threading.CancellationToken)`
- `M:System.Threading.Tasks.Task.WaitAll(System.Threading.Tasks.Task[],System.TimeSpan)`

-->
