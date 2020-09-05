---
ms.openlocfilehash: fb339fb35cdcbba4f1c860fae9c17162c4cff596
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497594"
---
### <a name="sql_variant-data-uses-sql_variant-collation-rather-than-database-collation"></a>Sql_variant dane używają sortowania sql_variant zamiast sortowania bazy danych

#### <a name="details"></a>Szczegóły

<code>sql_variant</code> dane korzystają z <code>sql_variant</code> sortowania zamiast sortowania bazy danych.

#### <a name="suggestion"></a>Sugestia

Ta zmiana dotyczy możliwego uszkodzenia danych, jeśli sortowanie bazy danych różni się od <code>sql_variant</code> sortowania. W aplikacjach korzystających z uszkodzonych danych może wystąpić błąd.

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Przezroczyste|
|Wersja|4.5|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

Nie wykrywalne za pośrednictwem analizy interfejsu API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
