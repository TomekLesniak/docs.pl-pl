---
title: Sprawdzanie, czy format poczty e-mail ciągów jest prawidłowy
description: Zapoznaj się z przykładem, jak wyrażenie regularne sprawdza, czy ciągi są w prawidłowym formacie poczty e-mail w programie .NET.
ms.date: 06/30/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- regular expressions, examples
- user input, examples
- Regex.IsMatch method
- regular expressions [.NET Framework], examples
- examples [Visual Basic], strings
- IsValidEmail
- validation, email strings
- input, checking
- strings [.NET Framework], examples [Visual Basic]
- email [.NET Framework], validating
- IsMatch method
ms.assetid: 7536af08-4e86-4953-98a1-a8298623df92
ms.openlocfilehash: 90e79af649727330c2afa1ccb8c64ffe34733f92
ms.sourcegitcommit: 6d4ee46871deb9ea1e45bb5f3784474e240bbc26
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/11/2020
ms.locfileid: "90022951"
---
# <a name="how-to-verify-that-strings-are-in-valid-email-format"></a>Sprawdzanie, czy format poczty e-mail ciągów jest prawidłowy

Poniższy przykład używa wyrażenia regularnego, aby sprawdzić, czy ciąg jest w prawidłowym formacie poczty e-mail.

To wyrażenie regularne jest proste względem tego, czego można używać jako wiadomości e-mail. Użycie wyrażenia regularnego do weryfikacji wiadomości e-mail jest przydatne, aby upewnić się, że struktura poczty e-mail jest poprawna, ale nie jest to podstawienie w celu sprawdzenia, czy wiadomość e-mail rzeczywiście istnieje.

✔️ Użyj małego wyrażenia regularnego, aby sprawdzić poprawność struktury wiadomości e-mail.

✔️ wysłać testową wiadomość e-mail na adres podany przez użytkownika aplikacji.

❌ NIE używaj wyrażenia regularnego jako jedynego sposobu weryfikacji wiadomości e-mail.

Jeśli spróbujesz utworzyć _idealne_ wyrażenie regularne, aby sprawdzić, czy struktura poczty e-mail jest poprawna, wyrażenie staje się bardziej skomplikowane, ponieważ niezwykle trudno debugować lub poprawić. Wyrażenia regularne nie mogą sprawdzić poprawności wiadomości e-mail, nawet jeśli struktura jest nieprawidłowa. Najlepszym sposobem na zweryfikowanie wiadomości e-mail jest wysłanie testowej wiadomości e-mail na adres.

[!INCLUDE [regex](../../../includes/regex.md)]

## <a name="example"></a>Przykład

W przykładzie zdefiniowano `IsValidEmail` metodę, która zwraca wartość, `true` Jeśli ciąg zawiera prawidłowy adres e-mail `false` , a jeśli nie, ale nie przyjmuje żadnych innych akcji.

Aby sprawdzić, czy adres e-mail jest prawidłowy, `IsValidEmail` Metoda wywołuje <xref:System.Text.RegularExpressions.Regex.Replace%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.MatchEvaluator%29?displayProperty=nameWithType> metodę ze `(@)(.+)$` wzorcem wyrażenia regularnego w celu oddzielenia nazwy domeny od adresu e-mail. Trzeci parametr jest <xref:System.Text.RegularExpressions.MatchEvaluator> delegatem, który reprezentuje metodę, która przetwarza i zastępuje dopasowany tekst. Wzorzec wyrażenia regularnego jest interpretowany w następujący sposób.

| Wzorce | Opis                                                                         |
|---------|-------------------------------------------------------------------------------------|
| `(@)`   | Dopasowuje znak @. Ta część jest pierwszą grupą przechwytywania.                           |
| `(.+)`  | Dopasowuje jedno lub więcej wystąpień dowolnego znaku. Ta część jest drugą grupą przechwytywania. |
| `$`     | Zakończ dopasowanie na końcu ciągu.                                             |

Nazwa domeny wraz ze znakiem @ jest przenoszona do `DomainMapper` metody, która używa <xref:System.Globalization.IdnMapping> klasy do translacji znaków Unicode, które są spoza zakresu znaków US-ASCII do formacie Punycode. Metoda ustawia również `invalid` flagę na, `True` Jeśli <xref:System.Globalization.IdnMapping.GetAscii%2A?displayProperty=nameWithType> Metoda wykryje nieprawidłowe znaki w nazwie domeny. Metoda zwraca nazwę domeny formacie Punycode poprzedzoną symbolem @ do `IsValidEmail` metody.

> [!TIP]
> Zaleca się, `(@)(.+)$` Aby użyć wzorca prostego wyrażenia regularnego do normalizacji domeny, a następnie zwrócić wartość wskazującą, że została przeniesiona lub niepowodzenie. Jednak w przykładzie w tym artykule opisano sposób dalszej weryfikacji wiadomości e-mail przy użyciu wyrażenia regularnego. Bez względu na to, jak sprawdzasz poprawność wiadomości e-mail, należy zawsze wysyłać testową wiadomość e-mail na adres, aby upewnić się, że istnieje.

`IsValidEmail`Metoda następnie wywołuje metodę, <xref:System.Text.RegularExpressions.Regex.IsMatch%28System.String%2CSystem.String%29?displayProperty=nameWithType> Aby sprawdzić, czy adres jest zgodny ze wzorcem wyrażenia regularnego.

`IsValidEmail`Metoda określa jedynie, czy format wiadomości e-mail jest prawidłowy dla adresu e-mail, a nie sprawdza poprawność wiadomości e-mail. Ponadto `IsValidEmail` Metoda nie sprawdza, czy nazwa domeny najwyższego poziomu jest prawidłową nazwą domeny wymienioną w [bazie danych strefy głównej Iana](https://www.iana.org/domains/root/db), co wymagałoby operacji wyszukiwania.

:::code language="csharp" source="snippets/how-to-verify-that-strings-are-in-valid-email-format/csharp/RegexUtilities.cs":::

:::code language="vb" source="snippets/how-to-verify-that-strings-are-in-valid-email-format/vb/RegexUtilities.vb":::

W tym przykładzie wzorzec wyrażenia regularnego `^[^@\s]+@[^@\s]+\.[^@\s]+$` jest interpretowany jak pokazano w poniższej tabeli. Wyrażenie regularne jest kompilowane przy użyciu <xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase?displayProperty=nameWithType> flagi.

| Wzorce   | Opis                                                                              |
|-----------|------------------------------------------------------------------------------------------|
| `^`       | Rozpocznij dopasowanie na początku ciągu.                                              |
| `[^@\s]+` | Dopasowuje jedno lub więcej wystąpień dowolnego znaku innego niż znak @ lub odstęp. |
| `@`       | Dopasowuje znak @.                                                                   |
| `[^@\s]+` | Dopasowuje jedno lub więcej wystąpień dowolnego znaku innego niż znak @ lub odstęp. |
| `\.`      | Dopasowuje pojedynczy odstęp czasu.                                                         |
| `[^@\s]+` | Dopasowuje jedno lub więcej wystąpień dowolnego znaku innego niż znak @ lub odstęp. |
| `$`       | Zakończ dopasowanie na końcu ciągu.                                                  |

> [!IMPORTANT]
> To wyrażenie regularne nie obejmuje każdego aspektu prawidłowego adresu e-mail. Jest on dostępny jako przykład do rozbudowania w razie potrzeby.

## <a name="see-also"></a>Zobacz także

- [.NET Framework — Wyrażenia regularne](regular-expressions.md)
- [Jak daleko powinna zostać przesunięta Weryfikacja adresu e-mail?](https://softwareengineering.stackexchange.com/questions/78353/how-far-should-one-take-e-mail-address-validation#78363)
