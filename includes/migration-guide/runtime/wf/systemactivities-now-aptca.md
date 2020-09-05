---
ms.openlocfilehash: 51ac10e6b4cc9c757cb7f68d7d665982bcb57d4e
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496226"
---
### <a name="systemactivities-is-now-aptca"></a>System. Activities jest teraz APTCA

#### <a name="details"></a>Szczegóły

Zestaw jest oznaczony <xref:System.Security.AllowPartiallyTrustedCallersAttribute?displayProperty=fullName> atrybutem.

#### <a name="suggestion"></a>Sugestia

Klasy pochodne nie mogą być oznaczone atrybutem <xref:System.Security.SecurityCriticalAttribute?displayProperty=fullName> . Wcześniej typy pochodne musiały zostać oznaczone jako <xref:System.Security.SecurityCriticalAttribute?displayProperty=fullName> . Jednak ta zmiana nie powinna mieć rzeczywistego wpływu.

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
