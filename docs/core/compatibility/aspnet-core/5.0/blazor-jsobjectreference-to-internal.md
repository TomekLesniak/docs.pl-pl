---
title: 'Zmiana podziału: Blazor: typy JSObjectReference i JSInProcessObjectReference zmieniły się na Internal'
description: 'Dowiedz się więcej o istotnej zmianie w ASP.NET Core 5,0 zatytułowanej Blazor: typy JSObjectReference i JSInProcessObjectReference zmieniły się na Internal'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 43a66d204f8309dc5afc57d099b2201c477cc3ad
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761483"
---
# <a name="blazor-jsobjectreference-and-jsinprocessobjectreference-types-changed-to-internal"></a><span data-ttu-id="bd01f-103">Blazor: typy JSObjectReference i JSInProcessObjectReference zmieniły się na Internal</span><span class="sxs-lookup"><span data-stu-id="bd01f-103">Blazor: JSObjectReference and JSInProcessObjectReference types changed to internal</span></span>

<span data-ttu-id="bd01f-104">Nowe `Microsoft.JSInterop.JSObjectReference` i `Microsoft.JSInterop.JSInProcessObjectReference` typy wprowadzone w ASP.NET Core 5,0 RC1 zostały oznaczone jako `internal` .</span><span class="sxs-lookup"><span data-stu-id="bd01f-104">The new `Microsoft.JSInterop.JSObjectReference` and `Microsoft.JSInterop.JSInProcessObjectReference` types introduced in ASP.NET Core 5.0 RC1 have been marked as `internal`.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="bd01f-105">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="bd01f-105">Version introduced</span></span>

<span data-ttu-id="bd01f-106">5,0 RC2</span><span class="sxs-lookup"><span data-stu-id="bd01f-106">5.0 RC2</span></span>

## <a name="old-behavior"></a><span data-ttu-id="bd01f-107">Stare zachowanie</span><span class="sxs-lookup"><span data-stu-id="bd01f-107">Old behavior</span></span>

<span data-ttu-id="bd01f-108">`JSObjectReference`Można uzyskać z wywołania międzyoperacyjnego JavaScript za pośrednictwem `IJSRuntime` .</span><span class="sxs-lookup"><span data-stu-id="bd01f-108">A `JSObjectReference` can be obtained from a JavaScript interop call via `IJSRuntime`.</span></span> <span data-ttu-id="bd01f-109">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="bd01f-109">For example:</span></span>

```csharp
var jsObjectReference = await JSRuntime.InvokeAsync<JSObjectReference>(...);
```

## <a name="new-behavior"></a><span data-ttu-id="bd01f-110">Nowe zachowanie</span><span class="sxs-lookup"><span data-stu-id="bd01f-110">New behavior</span></span>

<span data-ttu-id="bd01f-111">`JSObjectReference` używa modyfikatora dostępu [wewnętrznego](../../../../csharp/language-reference/keywords/internal.md) .</span><span class="sxs-lookup"><span data-stu-id="bd01f-111">`JSObjectReference` uses the [internal](../../../../csharp/language-reference/keywords/internal.md) access modifier.</span></span> <span data-ttu-id="bd01f-112">`public` `IJSObjectReference` Zamiast tego należy użyć interfejsu.</span><span class="sxs-lookup"><span data-stu-id="bd01f-112">The `public` `IJSObjectReference` interface must be used instead.</span></span> <span data-ttu-id="bd01f-113">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="bd01f-113">For example:</span></span>

```csharp
var jsObjectReference = await JSRuntime.InvokeAsync<IJSObjectReference>(...);
```

<span data-ttu-id="bd01f-114">`JSInProcessObjectReference` został również oznaczony jako `internal` i został zastąpiony przez `IJSInProcessObjectReference` .</span><span class="sxs-lookup"><span data-stu-id="bd01f-114">`JSInProcessObjectReference` was also marked as `internal` and was replaced by `IJSInProcessObjectReference`.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="bd01f-115">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="bd01f-115">Reason for change</span></span>

<span data-ttu-id="bd01f-116">Zmiana powoduje, że funkcja JavaScript Interop jest bardziej spójna z innymi wzorcami w Blazor.</span><span class="sxs-lookup"><span data-stu-id="bd01f-116">The change makes the JavaScript interop feature more consistent with other patterns within Blazor.</span></span> <span data-ttu-id="bd01f-117">`IJSObjectReference` jest analogiczny do w odróżnieniu od `IJSRuntime` tego, że działa podobnie i ma podobne metody i rozszerzenia.</span><span class="sxs-lookup"><span data-stu-id="bd01f-117">`IJSObjectReference` is analogous to `IJSRuntime` in that it serves a similar purpose and has similar methods and extensions.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="bd01f-118">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="bd01f-118">Recommended action</span></span>

<span data-ttu-id="bd01f-119">Zamień wystąpienia elementów `JSObjectReference` i `JSInProcessObjectReference` z `IJSObjectReference` i `IJSInProcessObjectReference` , odpowiednio.</span><span class="sxs-lookup"><span data-stu-id="bd01f-119">Replace occurrences of `JSObjectReference` and `JSInProcessObjectReference` with `IJSObjectReference` and `IJSInProcessObjectReference`, respectively.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="bd01f-120">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="bd01f-120">Affected APIs</span></span>

- `Microsoft.JSInterop.JSObjectReference`
- `Microsoft.JSInterop.JSInProcessObjectReference`

<!--

### Category

ASP.NET Core

### Affected APIs

- `T:Microsoft.JSInterop.JSObjectReference`
- `T:Microsoft.JSInterop.JSInProcessObjectReference`

-->
