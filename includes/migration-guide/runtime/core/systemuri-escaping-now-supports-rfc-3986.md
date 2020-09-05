---
ms.openlocfilehash: e7001fcfdf88fd9e710fbb702f2ed39d63b1e080
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496251"
---
### <a name="systemuri-escaping-now-supports-rfc-3986"></a>Ucieczka system. URI obsługuje teraz RFC 3986

#### <a name="details"></a>Szczegóły

Ucieczka identyfikatorów URI została zmieniona w .NET Framework 4,5 w celu obsługi [specyfikacji RFC 3986](https://tools.ietf.org/html/rfc3986). Określone zmiany obejmują:<ul><li><xref:System.Uri.EscapeDataString(System.String)?displayProperty=fullName> wyprowadza znaki zastrzeżone na podstawie RFC 3986.</li><li><xref:System.Uri.EscapeUriString(System.String)?displayProperty=fullName> nie ma znaków zarezerwowanych.</li><li><xref:System.Uri.UnescapeDataString(System.String)?displayProperty=fullName> nie zgłasza wyjątku, jeśli napotka nieprawidłową sekwencję ucieczki.</li><li>Niezastrzeżone znaki ucieczki przestają być znakami ucieczki.</li></ul>

#### <a name="suggestion"></a>Sugestia

<ul><li>Zaktualizuj aplikacje, aby nie polegać na zgłaszaniu <xref:System.Uri.UnescapeDataString(System.String)?displayProperty=fullName> w przypadku nieprawidłowej sekwencji ucieczki. Takie sekwencje muszą być wykrywane bezpośrednio.</li><li>Podobnie, należy oczekiwać, że identyfikatory URI i niezmienionych ciągów i danych mogą się różnić od .NET Framework 4,0 i .NET Framework 4,5 i nie powinny być porównywane bezpośrednio między wersjami programu .NET. Zamiast tego należy je analizować i znormalizować w jednej wersji platformy .NET przed dokonaniem jakichkolwiek porównań.</li></ul>

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Mały|
|Wersja|4.5|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Uri.EscapeDataString(System.String)?displayProperty=nameWithType>
- <xref:System.Uri.EscapeUriString(System.String)?displayProperty=nameWithType>
- <xref:System.Uri.UnescapeDataString(System.String)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Uri.EscapeDataString(System.String)`
- `M:System.Uri.EscapeUriString(System.String)`
- `M:System.Uri.UnescapeDataString(System.String)`

-->
