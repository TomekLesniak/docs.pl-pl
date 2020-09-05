---
ms.openlocfilehash: 6af63c0a58a3273aa98fa70f22e3637b481806b4
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497224"
---
### <a name="path-colon-checks-are-stricter"></a>Sprawdzanie dwukropek ścieżki jest bardziej rygorystyczne

#### <a name="details"></a>Szczegóły

W .NET Framework 4.6.2 wprowadzono wiele zmian do obsługi wcześniej nieobsługiwanych ścieżek (zarówno w formacie długości, jak i formatu). Sprawdza, czy składnia separatora dysku (dwukropek) była bardziej poprawna, co spowodowało zablokowanie niektórych ścieżek URI w kilku interfejsów API do wybierania ścieżek, w których zostały wcześniej tolerowane.

#### <a name="suggestion"></a>Sugestia

W przypadku przekazywania identyfikatora URI do odpowiednich interfejsów API należy najpierw zmodyfikować ciąg tak, aby był on ścieżką prawną.

- Ręcznie usuń schemat z adresów URL (na przykład Usuń `file://` z adresów URL).

- Przekaż identyfikator URI do <xref:System.Uri> klasy i Użyj <xref:System.Uri.LocalPath> .

Alternatywnie możesz zrezygnować z nowej normalizacji ścieżki, ustawiając `Switch.System.IO.UseLegacyPathHandling` przełącznik AppContext na `true` .

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   | Edge        |
| Wersja | 4.6.2       |
| Typ    | Przekierowanie |

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.IO.Path.GetDirectoryName(System.String)?displayProperty=nameWithType>
- <xref:System.IO.Path.GetPathRoot(System.String)?displayProperty=nameWithType>
