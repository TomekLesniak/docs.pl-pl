---
ms.openlocfilehash: 950c69199219cca615e403c6515239de8864d35d
ms.sourcegitcommit: d3c09791297f0edc468a4849a5f11ef62e0e90fd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2020
ms.locfileid: "88137475"
---
### <a name="complexity-of-linq-orderbyfirstordefault-increased"></a><span data-ttu-id="c1c3e-101">Złożoność elementu LINQ OrderBy. pierwszy {OrDefault} wzrósł</span><span class="sxs-lookup"><span data-stu-id="c1c3e-101">Complexity of LINQ OrderBy.First{OrDefault} increased</span></span>

<span data-ttu-id="c1c3e-102">Implementacja <xref:System.Linq.Enumerable.OrderBy%2A> `.` <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> i <xref:System.Linq.Enumerable.OrderBy%2A> `.` <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> została zmieniona, co spowodowało zwiększenie złożoności operacji.</span><span class="sxs-lookup"><span data-stu-id="c1c3e-102">The implementation of <xref:System.Linq.Enumerable.OrderBy%2A>`.`<xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> and <xref:System.Linq.Enumerable.OrderBy%2A>`.`<xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> has changed, resulting in increased complexity for the operation.</span></span>

#### <a name="change-description"></a><span data-ttu-id="c1c3e-103">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="c1c3e-103">Change description</span></span>

<span data-ttu-id="c1c3e-104">W programie .NET Core 1. x-3. x, wywoływanie <xref:System.Linq.Enumerable.OrderBy%2A> lub <xref:System.Linq.Enumerable.OrderByDescending%2A> po nim <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> lub <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> działa ze `O(N)` skomplikowaniem.</span><span class="sxs-lookup"><span data-stu-id="c1c3e-104">In .NET Core 1.x - 3.x, calling <xref:System.Linq.Enumerable.OrderBy%2A> or <xref:System.Linq.Enumerable.OrderByDescending%2A> followed by <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> or <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> operates with `O(N)` complexity.</span></span> <span data-ttu-id="c1c3e-105">Ponieważ wymagany jest tylko pierwszy element (lub domyślny), tylko jedno Wyliczenie jest wymagane, aby je znaleźć.</span><span class="sxs-lookup"><span data-stu-id="c1c3e-105">Since only the first (or default) element is required, only one enumeration is required to find it.</span></span> <span data-ttu-id="c1c3e-106">Jednakże predykat, który jest dostarczany <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> lub <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> jest wywoływany dokładnie `N` , gdzie `N` jest długością sekwencji.</span><span class="sxs-lookup"><span data-stu-id="c1c3e-106">However, the predicate that's supplied to <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> or <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> is invoked exactly `N` times, where `N` is the length of the sequence.</span></span>

<span data-ttu-id="c1c3e-107">W programie .NET 5,0 i jego nowszych wersjach [wprowadzono zmiany](https://github.com/dotnet/runtime/pull/36643) , takie jak wywołanie <xref:System.Linq.Enumerable.OrderBy%2A> lub działanie <xref:System.Linq.Enumerable.OrderByDescending%2A> <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> lub <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> działające z `O(N log N)` złożonością zamiast `O(N)` złożoności.</span><span class="sxs-lookup"><span data-stu-id="c1c3e-107">In .NET 5.0 and later versions, a [change was made](https://github.com/dotnet/runtime/pull/36643) such that calling <xref:System.Linq.Enumerable.OrderBy%2A> or <xref:System.Linq.Enumerable.OrderByDescending%2A> followed by <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> or <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> operates with `O(N log N)` complexity instead of `O(N)` complexity.</span></span> <span data-ttu-id="c1c3e-108">Jednakże predykat, który <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> jest dostarczany lub <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> może być wywoływany *krócej* niż `N` razy, co jest ważniejsze dla ogólnej wydajności.</span><span class="sxs-lookup"><span data-stu-id="c1c3e-108">However, the predicate that's supplied to <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> or <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> may be invoked *less* than `N` times, which is more important for overall performance.</span></span>

> [!NOTE]
> <span data-ttu-id="c1c3e-109">Ta zmiana jest zgodna z implementacją i złożonością operacji w .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c1c3e-109">This change matches the implementation and complexity of the operation in .NET Framework.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="c1c3e-110">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="c1c3e-110">Reason for change</span></span>

<span data-ttu-id="c1c3e-111">Korzyści wynikające z wywołania predykatu zmniejszają się do mniejszej ogólnej złożoności, więc implementacja wprowadzona w środowisku .NET Core 1,0 została cofnięta.</span><span class="sxs-lookup"><span data-stu-id="c1c3e-111">The benefit of invoking the predicate fewer times outweighs a lower overall complexity, so the implementation that was introduced in .NET Core 1.0 was reverted.</span></span> <span data-ttu-id="c1c3e-112">Aby uzyskać więcej informacji, zobacz [ten problem dotnet/Runtime](https://github.com/dotnet/runtime/issues/31554).</span><span class="sxs-lookup"><span data-stu-id="c1c3e-112">For more information, see [this dotnet/runtime issue](https://github.com/dotnet/runtime/issues/31554).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="c1c3e-113">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="c1c3e-113">Version introduced</span></span>

<span data-ttu-id="c1c3e-114">5.0</span><span class="sxs-lookup"><span data-stu-id="c1c3e-114">5.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="c1c3e-115">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="c1c3e-115">Recommended action</span></span>

<span data-ttu-id="c1c3e-116">W części dewelopera nie jest wymagana żadna akcja.</span><span class="sxs-lookup"><span data-stu-id="c1c3e-116">No action is required on the developer's part.</span></span>

#### <a name="category"></a><span data-ttu-id="c1c3e-117">Kategoria</span><span class="sxs-lookup"><span data-stu-id="c1c3e-117">Category</span></span>

<span data-ttu-id="c1c3e-118">Podstawowe biblioteki platformy .NET</span><span class="sxs-lookup"><span data-stu-id="c1c3e-118">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="c1c3e-119">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="c1c3e-119">Affected APIs</span></span>

- <xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=fullName>
- <xref:System.Linq.Enumerable.OrderByDescending%2A?displayProperty=fullName>
- <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})?displayProperty=fullName>
- <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})?displayProperty=fullName>

<!--

#### Affected APIs

- `Overload:System.Linq.Enumerable.OrderBy`
- `Overload:System.Linq.Enumerable.OrderByDescending`
- `M:System.Linq.Enumerable.First``1(System.Collections.Generic.IEnumerable{``0},System.Func{``0,System.Boolean})`
- `M:System.Linq.Enumerable.FirstOrDefault``1(System.Collections.Generic.IEnumerable{``0},System.Func{``0,System.Boolean})`

-->
