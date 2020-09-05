---
ms.openlocfilehash: 3244913e06a744dafc4440f824ebe6bed25b8dd1
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497393"
---
### <a name="objectdisposedexception-thrown-by-wpf-spellchecker"></a>ObjectDisposedException zgłoszone przez program sprawdzania pisowni WPF

#### <a name="details"></a>Szczegóły

Aplikacje WPF sporadycznie uległy awarii podczas zamykania aplikacji za pomocą modułu <xref:System.ObjectDisposedException?displayProperty=fullName> sprawdzania pisowni. Jest to rozwiązane w 4,7 .NET Frameworkj platformie WPF przez obsługę wyjątku i w ten sposób, dzięki czemu nie ma już negatywnego wpływ na aplikacje. Należy zauważyć, że sporadyczne wyjątki pierwszej szansy byłyby nadal przestrzegane w aplikacjach uruchamianych w ramach debugera.

#### <a name="suggestion"></a>Sugestia

Uaktualnij do .NET Framework 4,7

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Edge|
|Wersja|4.6.1|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

Nie wykrywalne za pośrednictwem analizy interfejsu API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
