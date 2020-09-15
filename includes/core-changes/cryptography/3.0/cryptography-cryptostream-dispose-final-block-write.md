---
ms.openlocfilehash: 7766a59131fffe2b436c15a5ff58e67001be7941
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065109"
---
### <a name="cryptostreamdispose-transforms-final-block-only-when-writing"></a>CryptoStream. Dispose przekształca końcowy blok tylko podczas pisania

<xref:System.Security.Cryptography.CryptoStream.Dispose%2A?displayProperty=nameWithType>Metoda, która jest używana do kończenia `CryptoStream` operacji, nie próbuje przekształcić końcowego bloku podczas odczytu.

#### <a name="change-description"></a>Zmień opis

W poprzednich wersjach platformy .NET, jeśli użytkownik wykonał niekompletny odczyt podczas korzystania <xref:System.Security.Cryptography.CryptoStream> z <xref:System.Security.Cryptography.CryptoStreamMode.Read> trybu, <xref:System.Security.Cryptography.CryptoStream.Dispose%2A> Metoda może zgłosić wyjątek (na przykład w przypadku użycia algorytmu AES z uzupełnieniem). Wyjątek został zgłoszony, ponieważ ostatni podjęto próbę przekształcenia końcowego bloku, ale dane były niekompletne.

W programie .NET Core 3,0 i jego nowszych wersjach program <xref:System.Security.Cryptography.CryptoStream.Dispose%2A> nie próbuje przekształcić końcowego bloku podczas odczytywania, co pozwala na niekompletne odczyty.

#### <a name="reason-for-change"></a>Przyczyna zmiany

Ta zmiana włącza niekompletne odczyty ze strumienia kryptograficznego po anulowaniu operacji sieciowej bez konieczności przechwytywania wyjątku.

#### <a name="version-introduced"></a>Wprowadzona wersja

3,0

#### <a name="recommended-action"></a>Zalecana akcja

Ta zmiana nie powinna mieć wpływ na większość aplikacji.

Jeśli aplikacja wcześniej przechwyciła wyjątek w przypadku niekompletnego odczytu, można usunąć ten `catch` blok.
Jeśli Twoja aplikacja użyła przekształcenia końcowego w scenariusze tworzenia skrótów, może być konieczne upewnienie się, że cały strumień jest odczytywany przed jego usunięciem.

#### <a name="category"></a>Kategoria

Kryptografia

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Security.Cryptography.CryptoStream.Dispose%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Security.Cryptography.CryptoStream.Dispose`

-->
