---
ms.openlocfilehash: d6405573e476ce18513938b500041adefbeeef1b
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496176"
---
### <a name="ribbongroup-background-is-set-to-transparent-in-localized-builds"></a>Tło zestawu wstążki jest ustawione jako przezroczyste w zlokalizowanych kompilacjach

#### <a name="details"></a>Szczegóły

<xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=fullName> w tle dla zlokalizowanych kompilacji zawsze jest malowany przezroczysty Pędzel, co spowodowało słabą obsługę interfejsu użytkownika. Ten problem został rozwiązany w .NET Framework 4,7 WPF, aktualizując zlokalizowane zasoby dla <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=fullName> , które z kolei zapewniają, że wybrany jest prawidłowy pędzel.

#### <a name="suggestion"></a>Sugestia

Uaktualnij do .NET Framework 4,7

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Edge|
|Wersja|4.6.2|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

Nie wykrywalne za pośrednictwem analizy interfejsu API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
