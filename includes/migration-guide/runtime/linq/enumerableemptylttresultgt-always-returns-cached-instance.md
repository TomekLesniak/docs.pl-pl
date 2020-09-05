---
ms.openlocfilehash: 05f60978f5380c406c43aa98ded0c812b1d50694
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496931"
---
### <a name="enumerableemptylttresultgt-always-returns-cached-instance"></a><span data-ttu-id="3169d-101">Wyliczalne. Empty &lt; TResult &gt; zawsze zwraca buforowane wystąpienie</span><span class="sxs-lookup"><span data-stu-id="3169d-101">Enumerable.Empty&lt;TResult&gt; always returns cached instance</span></span>

#### <a name="details"></a><span data-ttu-id="3169d-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="3169d-102">Details</span></span>

<span data-ttu-id="3169d-103">Począwszy od .NET Framework 4,5, <xref:System.Linq.Enumerable.Empty%60%601> zawsze zwraca buforowane wystąpienie wewnętrzne <xref:System.Collections.Generic.IEnumerable%601> . Wcześniej <xref:System.Linq.Enumerable.Empty%60%601> pamięć podręczna powinna <xref:System.Collections.Generic.IEnumerable%601> być pusta w momencie wywołania interfejsu API, co oznacza, że w niektórych przypadkach, w których <xref:System.Linq.Enumerable.Empty%60%601> została wywołana szybko i współbieżnie, różne wystąpienia typu mogą zostać zwrócone dla różnych wywołań interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="3169d-103">Beginning in .NET Framework 4.5, <xref:System.Linq.Enumerable.Empty%60%601> always returns a cached internal instance <xref:System.Collections.Generic.IEnumerable%601>.Previously, <xref:System.Linq.Enumerable.Empty%60%601> would cache an empty <xref:System.Collections.Generic.IEnumerable%601> at the time the API was called, meaning that in some conditions in which <xref:System.Linq.Enumerable.Empty%60%601> was called rapidly and concurrently, different instances of the type could be returned for different calls to the API.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="3169d-104">Sugestia</span><span class="sxs-lookup"><span data-stu-id="3169d-104">Suggestion</span></span>

<span data-ttu-id="3169d-105">Ze względu na to, że poprzednie zachowanie dotyczyło niedeterministyczności, kod prawdopodobnie nie zależy od niego.</span><span class="sxs-lookup"><span data-stu-id="3169d-105">Because the previous behavior was non-deterministic, code is unlikely to depend on it.</span></span> <span data-ttu-id="3169d-106">Jednak w nieprawdopodobnym przypadku, gdy puste wartości wyliczalne są porównywane i oczekiwano, że czasami nie są równe, należy utworzyć jawne puste tablice ( <code>new T[0]</code> ) zamiast używać <xref:System.Linq.Enumerable.Empty%60%601> .</span><span class="sxs-lookup"><span data-stu-id="3169d-106">However, in the unlikely case that empty enumerables are being compared and expected to sometimes be unequal, explicit empty arrays should be created (<code>new T[0]</code>) instead of using <xref:System.Linq.Enumerable.Empty%60%601>.</span></span>

| <span data-ttu-id="3169d-107">Nazwa</span><span class="sxs-lookup"><span data-stu-id="3169d-107">Name</span></span>    | <span data-ttu-id="3169d-108">Wartość</span><span class="sxs-lookup"><span data-stu-id="3169d-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="3169d-109">Zakres</span><span class="sxs-lookup"><span data-stu-id="3169d-109">Scope</span></span>   |<span data-ttu-id="3169d-110">Edge</span><span class="sxs-lookup"><span data-stu-id="3169d-110">Edge</span></span>|
|<span data-ttu-id="3169d-111">Wersja</span><span class="sxs-lookup"><span data-stu-id="3169d-111">Version</span></span>|<span data-ttu-id="3169d-112">4.5</span><span class="sxs-lookup"><span data-stu-id="3169d-112">4.5</span></span>|
|<span data-ttu-id="3169d-113">Typ</span><span class="sxs-lookup"><span data-stu-id="3169d-113">Type</span></span>|<span data-ttu-id="3169d-114">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="3169d-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="3169d-115">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="3169d-115">Affected APIs</span></span>

- <xref:System.Linq.Enumerable.Empty%60%601?displayProperty=nameWithType>

<!--

#### Affected APIs

- ``M:System.Linq.Enumerable.Empty``1``

-->
