---
ms.openlocfilehash: 46f6f77a543dfcf2073063d8ec200ef7d71e6b1f
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077595"
---
### <a name="blazor-jsobjectreference-and-jsinprocessobjectreference-types-changed-to-internal"></a><span data-ttu-id="73873-101">Blazor: typy JSObjectReference i JSInProcessObjectReference zmieniły się na Internal</span><span class="sxs-lookup"><span data-stu-id="73873-101">Blazor: JSObjectReference and JSInProcessObjectReference types changed to internal</span></span>

<span data-ttu-id="73873-102">Nowe `Microsoft.JSInterop.JSObjectReference` i `Microsoft.JSInterop.JSInProcessObjectReference` typy wprowadzone w ASP.NET Core 5,0 RC1 zostały oznaczone jako `internal` .</span><span class="sxs-lookup"><span data-stu-id="73873-102">The new `Microsoft.JSInterop.JSObjectReference` and `Microsoft.JSInterop.JSInProcessObjectReference` types introduced in ASP.NET Core 5.0 RC1 have been marked as `internal`.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="73873-103">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="73873-103">Version introduced</span></span>

<span data-ttu-id="73873-104">5,0 RC2</span><span class="sxs-lookup"><span data-stu-id="73873-104">5.0 RC2</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="73873-105">Stare zachowanie</span><span class="sxs-lookup"><span data-stu-id="73873-105">Old behavior</span></span>

<span data-ttu-id="73873-106">`JSObjectReference`Można uzyskać z wywołania międzyoperacyjnego JavaScript za pośrednictwem `IJSRuntime` .</span><span class="sxs-lookup"><span data-stu-id="73873-106">A `JSObjectReference` can be obtained from a JavaScript interop call via `IJSRuntime`.</span></span> <span data-ttu-id="73873-107">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="73873-107">For example:</span></span>

```csharp
var jsObjectReference = await JSRuntime.InvokeAsync<JSObjectReference>(...);
```

#### <a name="new-behavior"></a><span data-ttu-id="73873-108">Nowe zachowanie</span><span class="sxs-lookup"><span data-stu-id="73873-108">New behavior</span></span>

<span data-ttu-id="73873-109">`JSObjectReference` używa modyfikatora dostępu [wewnętrznego](../../../../docs/csharp/language-reference/keywords/internal.md) .</span><span class="sxs-lookup"><span data-stu-id="73873-109">`JSObjectReference` uses the [internal](../../../../docs/csharp/language-reference/keywords/internal.md) access modifier.</span></span> <span data-ttu-id="73873-110">`public` `IJSObjectReference` Zamiast tego należy użyć interfejsu.</span><span class="sxs-lookup"><span data-stu-id="73873-110">The `public` `IJSObjectReference` interface must be used instead.</span></span> <span data-ttu-id="73873-111">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="73873-111">For example:</span></span>

```csharp
var jsObjectReference = await JSRuntime.InvokeAsync<IJSObjectReference>(...);
```

<span data-ttu-id="73873-112">`JSInProcessObjectReference` został również oznaczony jako `internal` i został zastąpiony przez `IJSInProcessObjectReference` .</span><span class="sxs-lookup"><span data-stu-id="73873-112">`JSInProcessObjectReference` was also marked as `internal` and was replaced by `IJSInProcessObjectReference`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="73873-113">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="73873-113">Reason for change</span></span>

<span data-ttu-id="73873-114">Zmiana powoduje, że funkcja JavaScript Interop jest bardziej spójna z innymi wzorcami w Blazor.</span><span class="sxs-lookup"><span data-stu-id="73873-114">The change makes the JavaScript interop feature more consistent with other patterns within Blazor.</span></span> <span data-ttu-id="73873-115">`IJSObjectReference` jest analogiczny do w odróżnieniu od `IJSRuntime` tego, że działa podobnie i ma podobne metody i rozszerzenia.</span><span class="sxs-lookup"><span data-stu-id="73873-115">`IJSObjectReference` is analogous to `IJSRuntime` in that it serves a similar purpose and has similar methods and extensions.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="73873-116">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="73873-116">Recommended action</span></span>

<span data-ttu-id="73873-117">Zamień wystąpienia elementów `JSObjectReference` i `JSInProcessObjectReference` z `IJSObjectReference` i `IJSInProcessObjectReference` , odpowiednio.</span><span class="sxs-lookup"><span data-stu-id="73873-117">Replace occurrences of `JSObjectReference` and `JSInProcessObjectReference` with `IJSObjectReference` and `IJSInProcessObjectReference`, respectively.</span></span>

#### <a name="category"></a><span data-ttu-id="73873-118">Kategoria</span><span class="sxs-lookup"><span data-stu-id="73873-118">Category</span></span>

<span data-ttu-id="73873-119">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="73873-119">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="73873-120">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="73873-120">Affected APIs</span></span>

- `Microsoft.JSInterop.JSObjectReference`
- `Microsoft.JSInterop.JSInProcessObjectReference`

<!--

#### Affected APIs

- `T:Microsoft.JSInterop.JSObjectReference`
- `T:Microsoft.JSInterop.JSInProcessObjectReference`

-->
