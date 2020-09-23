---
ms.openlocfilehash: 46f6f77a543dfcf2073063d8ec200ef7d71e6b1f
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077595"
---
### <a name="blazor-jsobjectreference-and-jsinprocessobjectreference-types-changed-to-internal"></a>Blazor: typy JSObjectReference i JSInProcessObjectReference zmieniły się na Internal

Nowe `Microsoft.JSInterop.JSObjectReference` i `Microsoft.JSInterop.JSInProcessObjectReference` typy wprowadzone w ASP.NET Core 5,0 RC1 zostały oznaczone jako `internal` .

#### <a name="version-introduced"></a>Wprowadzona wersja

5,0 RC2

#### <a name="old-behavior"></a>Stare zachowanie

`JSObjectReference`Można uzyskać z wywołania międzyoperacyjnego JavaScript za pośrednictwem `IJSRuntime` . Na przykład:

```csharp
var jsObjectReference = await JSRuntime.InvokeAsync<JSObjectReference>(...);
```

#### <a name="new-behavior"></a>Nowe zachowanie

`JSObjectReference` używa modyfikatora dostępu [wewnętrznego](../../../../docs/csharp/language-reference/keywords/internal.md) . `public` `IJSObjectReference` Zamiast tego należy użyć interfejsu. Na przykład:

```csharp
var jsObjectReference = await JSRuntime.InvokeAsync<IJSObjectReference>(...);
```

`JSInProcessObjectReference` został również oznaczony jako `internal` i został zastąpiony przez `IJSInProcessObjectReference` .

#### <a name="reason-for-change"></a>Przyczyna zmiany

Zmiana powoduje, że funkcja JavaScript Interop jest bardziej spójna z innymi wzorcami w Blazor. `IJSObjectReference` jest analogiczny do w odróżnieniu od `IJSRuntime` tego, że działa podobnie i ma podobne metody i rozszerzenia.

#### <a name="recommended-action"></a>Zalecana akcja

Zamień wystąpienia elementów `JSObjectReference` i `JSInProcessObjectReference` z `IJSObjectReference` i `IJSInProcessObjectReference` , odpowiednio.

#### <a name="category"></a>Kategoria

ASP.NET Core

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- `Microsoft.JSInterop.JSObjectReference`
- `Microsoft.JSInterop.JSInProcessObjectReference`

<!--

#### Affected APIs

- `T:Microsoft.JSInterop.JSObjectReference`
- `T:Microsoft.JSInterop.JSInProcessObjectReference`

-->
