---
ms.openlocfilehash: 7bf5f7e8a49acc2918dd0d68a1c54a5c277091b0
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496145"
---
### <a name="chained-popups-with-staysopenfalse"></a>Połączone okienka podręczne z StaysOpen = false

#### <a name="details"></a>Szczegóły

Okno podręczne z StaysOpen = false ma być zamknięte po kliknięciu poza oknem podręcznym. Gdy dwa lub więcej takich okien podręcznych jest łańcucha (tj. jeden zawiera inny), wystąpił wiele problemów, w tym:<ul><li>Otwórz dwa poziomy, kliknij poza P2, ale wewnątrz P1.  Nic się nie dzieje.</li><li>Otwórz dwa poziomy, kliknij poza P1.  Zamknij oba okna podręczne.</li><li>Otwórz i Zamknij dwa poziomy.  Następnie spróbuj ponownie otworzyć P2.  Nic się nie dzieje.</li><li>Spróbuj otworzyć trzy poziomy.  Nie można.  (Nic się nie dzieje lub pierwsze dwa poziomy są zamykane, w zależności od tego, gdzie klikniesz). Te przypadki (i inne warianty) działają teraz zgodnie z oczekiwaniami.</li></ul>

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Edge|
|Wersja|4.7.1|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Windows.Controls.Primitives.Popup.StaysOpen?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.Windows.Controls.Primitives.Popup.StaysOpen`

-->
