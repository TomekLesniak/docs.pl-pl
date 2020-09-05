---
ms.openlocfilehash: cb9305f623044233082286863d2f2d2c7e9d665a
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496816"
---
### <a name="workflow-sql-persistence-adds-primary-key-clusters-and-disallows-null-values-in-some-columns"></a>Trwałość SQL przepływu pracy dodaje klastry kluczy podstawowych i nie zezwala na wartości null w niektórych kolumnach

#### <a name="details"></a>Szczegóły

Począwszy od .NET Framework 4,7, tabele utworzone dla magazynu wystąpienia przepływu pracy SQL (SWIS) przez skrypt SqlWorkflowInstanceStoreSchema. SQL używają klastrowanych kluczy podstawowych. Z tego powodu tożsamości nie obsługują <code>null</code> wartości. Ta zmiana nie ma wpływu na operację SWIS. Wprowadzono aktualizacje obsługujące SQL Server replikację transakcyjną.

#### <a name="suggestion"></a>Sugestia

Aby można było obsłużyć tę zmianę, należy zastosować plik SQL SqlWorkflowInstanceStoreSchemaUpgrade. SQL do istniejących instalacji. Nowe instalacje baz danych zostaną automatycznie zmienione.

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Edge|
|Wersja|4,7|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

Nie wykrywalne za pośrednictwem analizy interfejsu API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
