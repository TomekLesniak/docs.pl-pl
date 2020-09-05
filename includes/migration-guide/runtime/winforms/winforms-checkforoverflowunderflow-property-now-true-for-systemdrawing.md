---
ms.openlocfilehash: 68b0c4bb032b9744ef585eaef3d68e31afebee24
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496125"
---
### <a name="winforms-checkforoverflowunderflow-property-is-now-true-for-systemdrawing"></a>Właściwość CheckForOverflowUnderflow kontrolki WinForm jest teraz prawdziwa dla elementu System. Drawing

#### <a name="details"></a>Szczegóły

Właściwość CheckForOverflowUnderflow zestawu System.Drawing.dll ma wartość true.

#### <a name="suggestion"></a>Sugestia

Poprzednio po wystąpieniu przepełnienia wynik zostałby dyskretnie obcięty. Zostanie <xref:System.OverflowException?displayProperty=fullName> zgłoszony wyjątek.

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Edge|
|Wersja|4.5|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

Nie wykrywalne za pośrednictwem analizy interfejsu API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
