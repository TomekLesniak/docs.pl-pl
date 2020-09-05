---
ms.openlocfilehash: 49740d3b1890d72935e6e329a4f4be836ed70b25
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496370"
---
### <a name="missing-target-framework-moniker-results-in-40-behavior"></a>Brak monikera platformy docelowej w wyniku 4,0

#### <a name="details"></a>Szczegóły

Aplikacje bez <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName> zastosowania na poziomie zestawu zostaną automatycznie uruchomione przy użyciu semantyki (osobliwości) .NET Framework 4,0. W celu zapewnienia wysokiej jakości zaleca się, aby wszystkie pliki binarne były jawnie przypisane do <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName> wskazania wersji .NET Framework, z których zostały skompilowane. Należy zauważyć, że użycie monikera platformy docelowej w pliku projektu spowoduje automatyczne zastosowanie przez program MSBuild <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName> .

#### <a name="suggestion"></a>Sugestia

<xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName>Powinien być dostarczony przez dodanie atrybutu bezpośrednio do zestawu lub przez określenie platformy docelowej w [pliku projektu lub graficznego interfejsu użytkownika programu Visual Studio](https://devblogs.microsoft.com/visualstudio/visual-studio-managed-multi-targeting-part-1-concepts-target-framework-moniker-target-framework/).

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Duży|
|Wersja|4.5|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

Nie wykrywalne za pośrednictwem analizy interfejsu API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
