---
ms.openlocfilehash: f389a9e9bcf4ac1777db66731a085d74889c4a98
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496131"
---
### <a name="unicode-standard-version-80-categories-now-supported"></a>Kategorie Unicode w wersji Standard 8,0 są teraz obsługiwane

#### <a name="details"></a>Szczegóły

W .NET Framework 4.6.2 dane Unicode zostały uaktualnione z wersji standard Unicode 6,3 do wersji 8,0.  Podczas żądania kategorii znaków Unicode w .NET Framework 4.6.2 niektóre wyniki mogą być niezgodne z wynikami w poprzednich .NET Framework wersjach.  Ta zmiana głównie ma wpływ na sylaby czirokeski i nowe znaki samogłosek artość oraz znaki tonu.

#### <a name="suggestion"></a>Sugestia

Przejrzyj kod i Usuń lub Zmień logikę, która zależy od zakodowanych kategorii znaków Unicode.

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Mały|
|Wersja|4.6.2|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Char.GetUnicodeCategory(System.Char)?displayProperty=nameWithType>
- <xref:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.Char)?displayProperty=nameWithType>
- <xref:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.String,System.Int32)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Char.GetUnicodeCategory(System.Char)`
- `M:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.Char)`
- `M:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.String,System.Int32)`

-->
