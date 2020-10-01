---
ms.openlocfilehash: 8b70df0fb2072fd5243d9e46a4a20c22cc7fd677
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/01/2020
ms.locfileid: "91607798"
---
### <a name="profiling-aspnet-mvc4-apps-can-lead-to-fatal-execution-engine-error"></a>Profilowanie aplikacji ASP.NET MVC4 może prowadzić do błędu aparatu wykonywania krytycznych

#### <a name="details"></a>Szczegóły

Moduły plików używające narzędzia NGEN/profile mogą ulec awarii w profilowanych aplikacjach ASP.NET MVC4 podczas uruchamiania przy użyciu "wyjątku aparatu wykonywania krytycznego"

#### <a name="suggestion"></a>Sugestia

Ten problem został rozwiązany w .NET Framework 4.5.2. Alternatywnie profiler może uniknąć tego problemu przez określenie <code>COR_PRF_DISABLE_ALL_NGEN_IMAGES</code> w jego masce zdarzeń.

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
