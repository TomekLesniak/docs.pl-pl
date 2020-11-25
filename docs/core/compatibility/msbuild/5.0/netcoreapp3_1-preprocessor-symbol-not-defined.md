---
title: 'Istotna zmiana: symbol preprocesora NETCOREAPP3_1 nie jest zdefiniowany podczas określania platformy .NET 5'
description: Dowiedz się więcej na temat istotnej zmiany w programie .NET 5,0, w której projekty nie definiują już symboli preprocesora dla wcześniejszych wersji.
ms.date: 09/17/2020
ms.openlocfilehash: 61a5e4fce258d2be3d584318e154bb752b88ebe1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761452"
---
# <a name="netcoreapp3_1-preprocessor-symbol-is-not-defined-when-targeting-net-5"></a>Symbol preprocesora NETCOREAPP3_1 nie jest zdefiniowany podczas określania platformy .NET 5

W programie .NET 5,0 RC2 i nowszych wersjach projekty nie definiują już symboli preprocesora dla wcześniejszych wersji, ale tylko dla wersji docelowej. Jest to takie samo zachowanie jak .NET Core 1,0-3,1.

## <a name="version-introduced"></a>Wprowadzona wersja

5,0 RC2

## <a name="change-description"></a>Zmień opis

W programie .NET 5,0 w wersji zapoznawczej 7 do RC1, projekty, dla których `net5.0` zdefiniowano zarówno `NETCOREAPP3_1` `NET5_0` symbole preprocesora, jak i. Zamiarem tej zmiany zachowania było rozpoczęcie od platformy .NET 5,0, a warunkowe [symbole kompilacji byłyby skumulowane](https://github.com/dotnet/designs/blob/main/accepted/2020/net5/net5.md#preprocessor-symbols).

W programie .NET 5,0 RC2 lub nowszym projekty definiują tylko symbole dla monikerów platformy docelowej (TFM), które są przeznaczone dla wszystkich wcześniejszych wersji.

## <a name="reason-for-change"></a>Przyczyna zmiany

Zmiana z wersji zapoznawczej 7 została przywrócona ze względu na Opinie klientów. Definiowanie symboli dla wcześniejszych wersji jest zaskoczenie i pomylić klientów, a niektóre założono, że była usterką w kompilatorze języka C#.

## <a name="recommended-action"></a>Zalecana akcja

Upewnij się, że `#if` logika nie założono, że `NETCOREAPP3_1` jest zdefiniowana, gdy projekt jest `net5.0` lub wyższy. Zamiast tego przyjmuje się, że `NETCOREAPP3_1` jest on definiowany tylko wtedy, gdy projekt jest jawnie obiekt docelowy `netcoreapp3.1` .

Na przykład jeśli projekt jest przeznaczony dla platformy .NET Core 2,1 i .NET Core 3,1 i interfejsy API, które zostały wprowadzone w programie .NET Core 3,1, `#if` logika powinna wyglądać w następujący sposób:

```csharp
#if NETCOREAPP2_1 || NETCOREAPP3_0
    // Fallback behavior for old versions.
#elif NETCOREAPP
    // Behavior for .NET Core 3.1 and later.
#endif
```

## <a name="affected-apis"></a>Dotyczy interfejsów API

Nie dotyczy

<!--

### Affected APIs

Not detectable via API analysis.

### Category

MSBuild

-->
