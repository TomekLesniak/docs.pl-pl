---
title: 'Istotna zmiana: zmieniono kategorię Unicode dla niektórych znaków łacińskich 1'
description: Dowiedz się więcej o zmianie podziału globalizacji w programie .NET 5,0, gdzie metody char zwracają poprawną kategorię Unicode dla znaków w zakresie łaciński-1.
ms.date: 04/07/2020
ms.openlocfilehash: 8bd093a89857c83921fc0bf987348b529f74ce68
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761704"
---
# <a name="unicode-category-changed-for-some-latin-1-characters"></a>Zmieniono kategorię Unicode dla niektórych znaków łacińskich 1

<xref:System.Char> Metody teraz zwracają poprawną kategorię Unicode dla znaków w zakresie łaciński-1. Kategoria jest zgodna z normą standardu Unicode.

## <a name="change-description"></a>Zmień opis

W poprzednich wersjach .NET, <xref:System.Char> metody używały ustalonej listy kategorii Unicode dla znaków w zakresie łaciński-1. Jednak standard Unicode zmienił kategorie niektórych z tych znaków, ponieważ te interfejsy API zostały zaimplementowane, tworząc niezgodność. Ponadto istnieje również rozbieżność między <xref:System.Char> i <xref:System.Globalization.CharUnicodeInfo> interfejsami API, które są zgodne ze standardem Unicode. W programie .NET 5,0 i jego nowszych wersjach <xref:System.Char> metody używają i zwracają kategorię Unicode zgodną ze standardem Unicode dla wszystkich znaków.

W poniższej tabeli przedstawiono znaki, których kategorie Unicode zostały zmienione w programie .NET 5,0:

| Znak    | Kategoria Unicode<br>w poprzednich wersjach programu .NET | Kategoria Unicode<br>w programie .NET 5,0 i jego nowszych wersjach |
|:------------:|:---------------------------------------------:|:--------------------------------------------------:|
| § (\u00a7)   | `OtherSymbol`                                 | `OtherPunctuation`                                 |
| ª (\u00aa)   | `LowercaseLetter`                             | `OtherLetter`                                      |
| LUBISZ (\u00ad) | `DashPunctuation`                             | `Format`                                           |
| ¶ (\u00b6)   | `OtherSymbol`                                 | `OtherPunctuation`                                 |
| € (\u00ba)   | `LowercaseLetter`                             | `OtherLetter`                                      |

## <a name="version-introduced"></a>Wprowadzona wersja

.NET 5,0

## <a name="recommended-action"></a>Zalecana akcja

Jeśli masz kod, który pobiera kategorię znaku Unicode przy użyciu <xref:System.Char> klasy i zakłada, że Kategoria nigdy nie ulegnie zmianie, może być konieczne jej zaktualizowanie.

## <a name="reason-for-change"></a>Przyczyna zmiany

Ta zmiana została wprowadzona w taki sposób, aby kategorie zwracane przez <xref:System.Char> Typ były zgodne ze standardem Unicode i <xref:System.Globalization.CharUnicodeInfo> typem.

## <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Char.GetUnicodeCategory%2A?displayProperty=fullName>
- <xref:System.Char.IsLetter%2A?displayProperty=fullName>
- <xref:System.Char.IsPunctuation%2A?displayProperty=fullName>
- <xref:System.Char.IsSymbol%2A?displayProperty=fullName>
- <xref:System.Char.IsLower%2A?displayProperty=fullName>

Ponadto ta zmiana ma wpływ na każdą klasę, która jest zależna od elementu w <xref:System.Char> celu uzyskania kategorii znaków Unicode, na przykład <xref:System.Text.RegularExpressions.Regex> .

<!--

### Affected APIs

- `Overload:System.Char.GetUnicodeCategory`
- `Overload:System.Char.IsLetter`
- `Overload:System.Char.IsPunctuation`
- `Overload:System.Char.IsSymbol`
- `Overload:System.Char.IsLower`

### Category

- Core .NET libraries
- Globalization
-
-->
