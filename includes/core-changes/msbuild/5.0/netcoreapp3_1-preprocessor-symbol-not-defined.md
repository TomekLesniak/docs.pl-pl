---
ms.openlocfilehash: de35df21d1887bc95a3106edba312c53daad8b68
ms.sourcegitcommit: 4d45bda8cd9558ea8af4be591e3d5a29360c1ece
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/02/2020
ms.locfileid: "91654744"
---
### <a name="netcoreapp3_1-preprocessor-symbol-is-not-defined-when-targeting-net-5"></a>Symbol preprocesora NETCOREAPP3_1 nie jest zdefiniowany podczas określania platformy .NET 5

W programie .NET 5,0 RC2 i nowszych wersjach projekty nie definiują już symboli preprocesora dla wcześniejszych wersji, ale tylko dla wersji docelowej. Jest to takie samo zachowanie jak .NET Core 1,0-3,1.

#### <a name="version-introduced"></a>Wprowadzona wersja

5,0 RC2

#### <a name="change-description"></a>Zmień opis

W programie .NET 5,0 w wersji zapoznawczej 7 do RC1, projekty, dla których `net5.0` zdefiniowano zarówno `NETCOREAPP3_1` `NET5_0` symbole preprocesora, jak i. Zamiarem tej zmiany zachowania było rozpoczęcie od platformy .NET 5,0, a warunkowe [symbole kompilacji byłyby skumulowane](https://github.com/dotnet/designs/blob/main/accepted/2020/net5/net5.md#preprocessor-symbols).

W programie .NET 5,0 RC2 lub nowszym projekty definiują tylko symbole dla monikerów platformy docelowej (TFM), które są przeznaczone dla wszystkich wcześniejszych wersji.

#### <a name="reason-for-change"></a>Przyczyna zmiany

Zmiana z wersji zapoznawczej 7 została przywrócona ze względu na Opinie klientów. Definiowanie symboli dla wcześniejszych wersji jest zaskoczenie i pomylić klientów, a niektóre założono, że była usterką w kompilatorze języka C#.

#### <a name="recommended-action"></a>Zalecana akcja

Upewnij się, że `#if` logika nie założono, że `NETCOREAPP3_1` jest zdefiniowana, gdy projekt jest `net5.0` lub wyższy. Zamiast tego przyjmuje się, że `NETCOREAPP3_1` jest on definiowany tylko wtedy, gdy projekt jest jawnie obiekt docelowy `netcoreapp3.1` .

Na przykład jeśli projekt jest przeznaczony dla platformy .NET Core 2,1 i .NET Core 3,1 i interfejsy API, które zostały wprowadzone w programie .NET Core 3,1, `#if` logika powinna wyglądać w następujący sposób:

```csharp
#if NETCOREAPP2_1 || NETCOREAPP3_0
    // Fallback behavior for old versions.
#elif NETCOREAPP
    // Behavior for .NET Core 3.1 and later.
#endif
```

#### <a name="category"></a>Kategoria

MSBuild

#### <a name="affected-apis"></a>Dotyczy interfejsów API

Brak

<!--

#### Affected APIs

Not detectable via API analysis.

-->
