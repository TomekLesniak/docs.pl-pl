---
ms.openlocfilehash: af8de731ee93d0bfb01042d894f5730570dcdd78
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497848"
---
### <a name="null-coalescer-values-are-not-visible-in-debugger-until-one-step-later"></a>Wartości parametrów łączenia wartości null nie są widoczne w debugerze, dopóki nie zostanie później jeden krok

#### <a name="details"></a>Szczegóły

Usterka w .NET Framework 4,5 powoduje, że wartości ustawione za pośrednictwem operacji łączenia zerowego nie będą widoczne w debugerze natychmiast po wykonaniu operacji przypisania w przypadku uruchamiania w wersji 64-bitowej struktury.

#### <a name="suggestion"></a>Sugestia

Przechodzenie po jednym dodatkowym czasie w debugerze spowoduje, że wartość lokalna/pole zostanie prawidłowo zaktualizowane. Ten problem został również rozwiązany w .NET Framework 4,6; uaktualnienie do tej wersji środowiska powinno rozwiązać problem.

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
