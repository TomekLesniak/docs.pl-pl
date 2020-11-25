---
title: 'Istotna zmiana: złożoność elementu LINQ OrderBy. pierwszy {OrDefault} wzrósł'
description: Dowiedz się więcej na temat istotnej zmiany w programie .NET 5,0 w bibliotekach podstawowych platformy .NET, w których implementacja OrderBy. First została zmieniona.
ms.date: 11/01/2020
ms.openlocfilehash: 3c4f8fd0bb2051c3e1ac14eab091be11f10f88b4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761544"
---
# <a name="complexity-of-linq-orderbyfirstordefault-increased"></a>Złożoność elementu LINQ OrderBy. pierwszy {OrDefault} wzrósł

Implementacja <xref:System.Linq.Enumerable.OrderBy%2A> `.` <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> i <xref:System.Linq.Enumerable.OrderBy%2A> `.` <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> została zmieniona, co spowodowało zwiększenie złożoności operacji.

## <a name="change-description"></a>Zmień opis

W programie .NET Core 1. x-3. x, wywoływanie <xref:System.Linq.Enumerable.OrderBy%2A> lub <xref:System.Linq.Enumerable.OrderByDescending%2A> po nim <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> lub <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> działa ze `O(N)` skomplikowaniem. Ponieważ wymagany jest tylko pierwszy element (lub domyślny), tylko jedno Wyliczenie jest wymagane, aby je znaleźć. Jednakże predykat, który jest dostarczany <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> lub <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> jest wywoływany dokładnie `N` , gdzie `N` jest długością sekwencji.

W programie .NET 5,0 i jego nowszych wersjach [wprowadzono zmiany](https://github.com/dotnet/runtime/pull/36643) , takie jak wywołanie <xref:System.Linq.Enumerable.OrderBy%2A> lub działanie <xref:System.Linq.Enumerable.OrderByDescending%2A> <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> lub <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> działające z `O(N log N)` złożonością zamiast `O(N)` złożoności. Jednakże predykat, który <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> jest dostarczany lub <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> może być wywoływany *krócej* niż `N` razy, co jest ważniejsze dla ogólnej wydajności.

> [!NOTE]
> Ta zmiana jest zgodna z implementacją i złożonością operacji w .NET Framework.

## <a name="reason-for-change"></a>Przyczyna zmiany

Korzyści wynikające z wywołania predykatu zmniejszają się do mniejszej ogólnej złożoności, więc implementacja wprowadzona w środowisku .NET Core 1,0 została cofnięta. Aby uzyskać więcej informacji, zobacz [ten problem dotnet/Runtime](https://github.com/dotnet/runtime/issues/31554).

## <a name="version-introduced"></a>Wprowadzona wersja

5,0

## <a name="recommended-action"></a>Zalecana akcja

W części dewelopera nie jest wymagana żadna akcja.

## <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=fullName>
- <xref:System.Linq.Enumerable.OrderByDescending%2A?displayProperty=fullName>
- <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})?displayProperty=fullName>
- <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `Overload:System.Linq.Enumerable.OrderBy`
- `Overload:System.Linq.Enumerable.OrderByDescending`
- `M:System.Linq.Enumerable.First``1(System.Collections.Generic.IEnumerable{``0},System.Func{``0,System.Boolean})`
- `M:System.Linq.Enumerable.FirstOrDefault``1(System.Collections.Generic.IEnumerable{``0},System.Func{``0,System.Boolean})`

-->
