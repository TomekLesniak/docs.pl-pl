---
title: 'Nieprzerwana zmiana: LastIndexOf ma ulepszoną obsługę pustych ciągów wyszukiwania'
description: Więcej informacji na temat istotnej zmiany w programie .NET 5,0 w bibliotekach podstawowych platformy .NET, w których LastIndexOf i powiązane interfejsy API teraz zwracają poprawne wartości podczas wyszukiwania podciągu o zerowej długości.
ms.date: 11/01/2020
ms.openlocfilehash: 6d1a676eb2b9ed3de6a745db27d53bd43560a32f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761379"
---
# <a name="lastindexof-has-improved-handling-of-empty-search-strings"></a>LastIndexOf Ulepszono obsługę pustych ciągów wyszukiwania

<xref:System.String.LastIndexOf%2A?displayProperty=nameWithType> i powiązane interfejsy API teraz zwracają poprawne wartości podczas wyszukiwania podciągu o zerowej długości (lub o zerowej długości) w większym ciągu.

## <a name="change-description"></a>Zmień opis

W .NET Framework i .NET Core 1,0-3,1 <xref:System.String.LastIndexOf%2A?displayProperty=nameWithType> i powiązane interfejsy API mogą zwracać niepoprawną wartość, gdy obiekt wywołujący wyszukuje podciąg o zerowej długości.

```csharp
Console.WriteLine("Hello".LastIndexOf("")); // prints '4' (incorrect)

ReadOnlySpan<char> span = "Hello";
Console.WriteLine(span.LastIndexOf("")); // prints '0' (incorrect)
```

Począwszy od platformy .NET 5,0, te interfejsy API zwracają poprawną wartość dla `LastIndexOf` .

```csharp
Console.WriteLine("Hello".LastIndexOf("")); // prints '5' (correct)

ReadOnlySpan<char> span = "Hello";
Console.WriteLine(span.LastIndexOf("")); // prints '5' (correct)
```

W tych przykładach `5` jest poprawna odpowiedź, ponieważ `"Hello".Substring(5)` i `"Hello".AsSpan().Slice(5)` oba tworzą pusty ciąg, który jest w prosty sposób równy pustemu ciągowi, który jest poszukiwany.

## <a name="reason-for-change"></a>Przyczyna zmiany

Ta zmiana była częścią ogólnego nakładu na rozwiązywanie problemów związanych z obsługą ciągów dla platformy .NET 5. Pomaga również w ujednoliceniu zachowań między platformami systemu Windows i systemami innymi niż Windows. Aby uzyskać więcej informacji, zobacz [dotnet/Runtime # 13383](https://github.com/dotnet/runtime/issues/13383) i [dotnet/Runtime # #13382](https://github.com/dotnet/runtime/issues/13382).

## <a name="version-introduced"></a>Wprowadzona wersja

5,0

## <a name="recommended-action"></a>Zalecana akcja

Nie trzeba podejmować żadnych działań. Środowisko uruchomieniowe programu .NET 5,0 udostępnia nowe zachowania automatycznie.

Nie ma przełącznika zgodności w celu przywrócenia starego zachowania.

## <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.String.LastIndexOf%2A?displayProperty=fullName>
- <xref:System.Globalization.CompareInfo.LastIndexOf%2A?displayProperty=fullName>
- <xref:System.MemoryExtensions.LastIndexOf%2A?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `Overload:System.String.LastIndexOf`
- `Overload:System.Globalization.CompareInfo.LastIndexOf`
- `Overload:System.MemoryExtensions.LastIndexOf`

-->
