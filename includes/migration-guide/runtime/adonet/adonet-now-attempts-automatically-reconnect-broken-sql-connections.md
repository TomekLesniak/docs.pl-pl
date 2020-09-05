---
ms.openlocfilehash: 7f7e718d543a4abdf2b8a87e52d8c0e2ba28203f
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496415"
---
### <a name="adonet-now-attempts-to-automatically-reconnect-broken-sql-connections"></a>ADO.NET teraz próbuje automatycznie ponownie nawiązać połączenie z przerwanymi połączeniami SQL

#### <a name="details"></a>Szczegóły

Począwszy od .NET Framework 4.5.1 .NET Framework spróbuje automatycznie ponownie nawiązać połączenie z przerwanymi połączeniami SQL. Chociaż zwykle aplikacje są bardziej niezawodne, istnieją przypadki brzegowe, w których aplikacja musi wiedzieć, że połączenie zostało utracone, dzięki czemu może podejmować pewne działania po ponownej nawiązaniu połączenia.

#### <a name="suggestion"></a>Sugestia

Jeśli ta funkcja jest niepożądana z powodu problemów ze zgodnością, można ją wyłączyć, ustawiając <xref:System.Data.SqlClient.SqlConnectionStringBuilder.ConnectRetryCount?displayProperty=fullName> Właściwość parametrów połączenia (lub <xref:System.Data.SqlClient.SqlConnectionStringBuilder?displayProperty=fullName> ) na 0.

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Edge|
|Wersja|4.5.1|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Data.IDbConnection.ConnectionString?displayProperty=nameWithType>
- <xref:System.Data.SqlClient.SqlConnection.ConnectionString?displayProperty=nameWithType>
- <xref:System.Configuration.ConnectionStringSettings.ConnectionString?displayProperty=nameWithType>
- <xref:System.Data.Common.DbConnection.ConnectionString?displayProperty=nameWithType>
- <xref:System.Data.Common.DbConnectionStringBuilder.ConnectionString?displayProperty=nameWithType>
- <xref:System.Data.SqlClient.SqlConnectionStringBuilder.%23ctor>
- <xref:System.Data.SqlClient.SqlConnectionStringBuilder.%23ctor(System.String)>
- <xref:System.Data.Common.DbConnectionStringBuilder.%23ctor>
- <xref:System.Data.Common.DbConnectionStringBuilder.%23ctor(System.Boolean)>

<!--

#### Affected APIs

- `P:System.Data.IDbConnection.ConnectionString`
- `P:System.Data.SqlClient.SqlConnection.ConnectionString`
- `P:System.Configuration.ConnectionStringSettings.ConnectionString`
- `P:System.Data.Common.DbConnection.ConnectionString`
- `P:System.Data.Common.DbConnectionStringBuilder.ConnectionString`
- `M:System.Data.SqlClient.SqlConnectionStringBuilder.#ctor`
- `M:System.Data.SqlClient.SqlConnectionStringBuilder.#ctor(System.String)`
- `M:System.Data.Common.DbConnectionStringBuilder.#ctor`
- `M:System.Data.Common.DbConnectionStringBuilder.#ctor(System.Boolean)`

-->
