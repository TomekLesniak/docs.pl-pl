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
# <a name="blazor-jsobjectreference-and-jsinprocessobjectreference-types-changed-to-internal"></a>Blazor: typy JSObjectReference i JSInProcessObjectReference zmieniły się na Internal

Nowe `Microsoft.JSInterop.JSObjectReference` i `Microsoft.JSInterop.JSInProcessObjectReference` typy wprowadzone w ASP.NET Core 5,0 RC1 zostały oznaczone jako `internal` .

## <a name="version-introduced"></a>Wprowadzona wersja

5,0 RC2

## <a name="old-behavior"></a>Stare zachowanie

`JSObjectReference`Można uzyskać z wywołania międzyoperacyjnego JavaScript za pośrednictwem `IJSRuntime` . Na przykład:

```csharp
var jsObjectReference = await JSRuntime.InvokeAsync<JSObjectReference>(...);
```

## <a name="new-behavior"></a>Nowe zachowanie

`JSObjectReference` używa modyfikatora dostępu [wewnętrznego](../../../../csharp/language-reference/keywords/internal.md) . `public` `IJSObjectReference` Zamiast tego należy użyć interfejsu. Na przykład:

```csharp
var jsObjectReference = await JSRuntime.InvokeAsync<IJSObjectReference>(...);
```

`JSInProcessObjectReference` został również oznaczony jako `internal` i został zastąpiony przez `IJSInProcessObjectReference` .

## <a name="reason-for-change"></a>Przyczyna zmiany

Zmiana powoduje, że funkcja JavaScript Interop jest bardziej spójna z innymi wzorcami w Blazor. `IJSObjectReference` jest analogiczny do w odróżnieniu od `IJSRuntime` tego, że działa podobnie i ma podobne metody i rozszerzenia.

## <a name="recommended-action"></a>Zalecana akcja

Zamień wystąpienia elementów `JSObjectReference` i `JSInProcessObjectReference` z `IJSObjectReference` i `IJSInProcessObjectReference` , odpowiednio.

## <a name="affected-apis"></a>Dotyczy interfejsów API

- `Microsoft.JSInterop.JSObjectReference`
- `Microsoft.JSInterop.JSInProcessObjectReference`

<!--

### Category

ASP.NET Core

### Affected APIs

- `T:Microsoft.JSInterop.JSObjectReference`
- `T:Microsoft.JSInterop.JSInProcessObjectReference`

-->
