---
ms.openlocfilehash: faf9459ab9002e6149560e2a3452265fa246bf6b
ms.sourcegitcommit: ef86c24c418439b8bb5e3e7d64bbdbe5e11c3e9c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/21/2020
ms.locfileid: "88720208"
---
### <a name="uri-paths-with-non-ascii-characters-parse-correctly-on-unix"></a>Ścieżki URI zawierające znaki inne niż ASCII są analizowane prawidłowo w systemie UNIX

W klasie rozwiązano błąd <xref:System.Uri?displayProperty=fullName> , który umożliwia poprawne analizowanie bezwzględnych ścieżek URI zawierających znaki inne niż ASCII na platformach UNIX.

#### <a name="change-description"></a>Zmień opis

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

#### <a name="version-introduced"></a>Wprowadzona wersja

5.0

#### <a name="recommended-action"></a>Zalecana akcja

Jeśli masz kod, który oczekuje i konta dla zduplikowanych segmentów ścieżki, możesz usunąć ten kod.

#### <a name="category"></a>Kategoria

Podstawowe biblioteki platformy .NET

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Uri?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Uri`

-->
