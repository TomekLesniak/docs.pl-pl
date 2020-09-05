---
ms.openlocfilehash: 1487b5f47966cfcae0e47848dae99b39b42db18d
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496184"
---
### <a name="keytips-behavior-improved-in-wpf"></a>Ulepszone zachowanie podpowiedzi w WPF

#### <a name="details"></a>Szczegóły

W celu zachowania zgodności z zachowaniem programu Microsoft Word i Eksploratora Windows należy zmodyfikować zachowanie podpowiedzi. Sprawdzając, czy stan poradę dotyczącą klawiszy jest włączony lub nie jest w przypadku <xref:System.Windows.Input.KeyEventArgs.SystemKey> naciśnięcia (w szczególności <xref:System.Windows.Input.Key> lub <xref:System.Windows.Input.Key.F11> ), WPF odpowiednio obsługuje klucze poradę dotyczącą klawiszy. Porady dotyczące klawisza umożliwiają teraz odrzucanie menu nawet wtedy, gdy jest ono otwierane za pomocą myszy.

#### <a name="suggestion"></a>Sugestia

Nie dotyczy

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Edge|
|Wersja|4.7.2|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

Nie wykrywalne za pośrednictwem analizy interfejsu API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
