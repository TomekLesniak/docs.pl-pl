---
title: 'Zmiana istotna: ścieżki URI z niestandardowymi znakami ASCII są analizowane prawidłowo w systemie UNIX'
description: Więcej informacji na temat istotnej zmiany w programie .NET 5,0 w bibliotekach podstawowych platformy .NET, w których bezwzględne ścieżki identyfikatorów URI, które zawierają znaki inne niż ASCII, są teraz analizowane poprawnie na platformach UNIX
ms.date: 11/01/2020
ms.openlocfilehash: 94de4e0eb94a11153d873871d4003422a4286a0c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761376"
---
# <a name="uri-paths-with-non-ascii-characters-parse-correctly-on-unix"></a>Ścieżki URI zawierające znaki inne niż ASCII są analizowane prawidłowo w systemie UNIX

W klasie rozwiązano błąd <xref:System.Uri?displayProperty=fullName> , który umożliwia poprawne analizowanie bezwzględnych ścieżek URI zawierających znaki inne niż ASCII na platformach UNIX.

## <a name="change-description"></a>Zmień opis

W poprzednich wersjach programu .NET bezwzględne ścieżki identyfikatorów URI, które zawierają znaki inne niż ASCII, są nieprawidłowo analizowane na platformach UNIX, a segmenty ścieżki są zduplikowane. (Ścieżki bezwzględne to te, które zaczynają się od "/"). Problem z analizą został rozwiązany dla programu .NET 5,0. Przejście z poprzedniej wersji programu .NET do programu .NET 5,0 lub nowszego spowoduje uzyskanie różnych wartości utworzonych przez <xref:System.Uri.AbsoluteUri?displayProperty=nameWithType> , <xref:System.Uri.ToString?displayProperty=nameWithType> i innych <xref:System.Uri> członków.

Podczas uruchamiania w systemie UNIX Rozważ użycie danych wyjściowych następującego kodu.

```csharp
var myUri = new Uri("/üri");

Console.WriteLine($"AbsoluteUri: {myUri.AbsoluteUri}");
Console.WriteLine($"ToString: {myUri.ToString()}");
```

Dane wyjściowe w poprzedniej wersji platformy .NET:

```text
AbsoluteUri: /%C3%BCri/%C3%BCri
ToString: /üri/üri
```

Dane wyjściowe w programie .NET 5,0 lub jego nowszej wersji:

```text
AbsoluteUri: /%C3%BCri
ToString: /üri
```

## <a name="version-introduced"></a>Wprowadzona wersja

5,0

## <a name="recommended-action"></a>Zalecana akcja

Jeśli masz kod, który oczekuje i konta dla zduplikowanych segmentów ścieżki, możesz usunąć ten kod.

## <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Uri?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `T:System.Uri`

-->
