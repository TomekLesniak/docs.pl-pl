---
ms.openlocfilehash: 950c69199219cca615e403c6515239de8864d35d
ms.sourcegitcommit: d3c09791297f0edc468a4849a5f11ef62e0e90fd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2020
ms.locfileid: "88137475"
---
### <a name="complexity-of-linq-orderbyfirstordefault-increased"></a>Złożoność elementu LINQ OrderBy. pierwszy {OrDefault} wzrósł

Implementacja <xref:System.Linq.Enumerable.OrderBy%2A> `.` <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> i <xref:System.Linq.Enumerable.OrderBy%2A> `.` <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> została zmieniona, co spowodowało zwiększenie złożoności operacji.

#### <a name="change-description"></a>Zmień opis

W programie .NET Core 1. x-3. x, wywoływanie <xref:System.Linq.Enumerable.OrderBy%2A> lub <xref:System.Linq.Enumerable.OrderByDescending%2A> po nim <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> lub <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> działa ze `O(N)` skomplikowaniem. Ponieważ wymagany jest tylko pierwszy element (lub domyślny), tylko jedno Wyliczenie jest wymagane, aby je znaleźć. Jednakże predykat, który jest dostarczany <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> lub <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> jest wywoływany dokładnie `N` , gdzie `N` jest długością sekwencji.

W programie .NET 5,0 i jego nowszych wersjach [wprowadzono zmiany](https://github.com/dotnet/runtime/pull/36643) , takie jak wywołanie <xref:System.Linq.Enumerable.OrderBy%2A> lub działanie <xref:System.Linq.Enumerable.OrderByDescending%2A> <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> lub <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> działające z `O(N log N)` złożonością zamiast `O(N)` złożoności. Jednakże predykat, który <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> jest dostarczany lub <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> może być wywoływany *krócej* niż `N` razy, co jest ważniejsze dla ogólnej wydajności.

> [!NOTE]
> Ta zmiana jest zgodna z implementacją i złożonością operacji w .NET Framework.

#### <a name="reason-for-change"></a>Przyczyna zmiany

Korzyści wynikające z wywołania predykatu zmniejszają się do mniejszej ogólnej złożoności, więc implementacja wprowadzona w środowisku .NET Core 1,0 została cofnięta. Aby uzyskać więcej informacji, zobacz [ten problem dotnet/Runtime](https://github.com/dotnet/runtime/issues/31554).

#### <a name="version-introduced"></a>Wprowadzona wersja

5.0

#### <a name="recommended-action"></a>Zalecana akcja

W części dewelopera nie jest wymagana żadna akcja.

#### <a name="category"></a>Kategoria

Podstawowe biblioteki platformy .NET

#### <a name="affected-apis"></a>Dotyczy interfejsów API

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
