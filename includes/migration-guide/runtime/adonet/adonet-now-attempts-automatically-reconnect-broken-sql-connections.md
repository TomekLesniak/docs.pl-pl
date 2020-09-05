---
ms.openlocfilehash: 7f7e718d543a4abdf2b8a87e52d8c0e2ba28203f
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496415"
---
### <a name="adonet-now-attempts-to-automatically-reconnect-broken-sql-connections"></a><span data-ttu-id="8963b-101">ADO.NET teraz próbuje automatycznie ponownie nawiązać połączenie z przerwanymi połączeniami SQL</span><span class="sxs-lookup"><span data-stu-id="8963b-101">ADO.NET now attempts to automatically reconnect broken SQL connections</span></span>

#### <a name="details"></a><span data-ttu-id="8963b-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="8963b-102">Details</span></span>

<span data-ttu-id="8963b-103">Począwszy od .NET Framework 4.5.1 .NET Framework spróbuje automatycznie ponownie nawiązać połączenie z przerwanymi połączeniami SQL.</span><span class="sxs-lookup"><span data-stu-id="8963b-103">Beginning in the .NET Framework 4.5.1, the .NET Framework will attempt to automatically reconnect broken SQL connections.</span></span> <span data-ttu-id="8963b-104">Chociaż zwykle aplikacje są bardziej niezawodne, istnieją przypadki brzegowe, w których aplikacja musi wiedzieć, że połączenie zostało utracone, dzięki czemu może podejmować pewne działania po ponownej nawiązaniu połączenia.</span><span class="sxs-lookup"><span data-stu-id="8963b-104">Although this will typically make apps more reliable, there are edge cases in which an app needs to know that the connection was lost so that it can take some action upon reconnection.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="8963b-105">Sugestia</span><span class="sxs-lookup"><span data-stu-id="8963b-105">Suggestion</span></span>

<span data-ttu-id="8963b-106">Jeśli ta funkcja jest niepożądana z powodu problemów ze zgodnością, można ją wyłączyć, ustawiając <xref:System.Data.SqlClient.SqlConnectionStringBuilder.ConnectRetryCount?displayProperty=fullName> Właściwość parametrów połączenia (lub <xref:System.Data.SqlClient.SqlConnectionStringBuilder?displayProperty=fullName> ) na 0.</span><span class="sxs-lookup"><span data-stu-id="8963b-106">If this feature is undesirable due to compatibility concerns, it can be disabled by setting the <xref:System.Data.SqlClient.SqlConnectionStringBuilder.ConnectRetryCount?displayProperty=fullName> property of a connection string (or <xref:System.Data.SqlClient.SqlConnectionStringBuilder?displayProperty=fullName>) to 0.</span></span>

| <span data-ttu-id="8963b-107">Nazwa</span><span class="sxs-lookup"><span data-stu-id="8963b-107">Name</span></span>    | <span data-ttu-id="8963b-108">Wartość</span><span class="sxs-lookup"><span data-stu-id="8963b-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="8963b-109">Zakres</span><span class="sxs-lookup"><span data-stu-id="8963b-109">Scope</span></span>   |<span data-ttu-id="8963b-110">Edge</span><span class="sxs-lookup"><span data-stu-id="8963b-110">Edge</span></span>|
|<span data-ttu-id="8963b-111">Wersja</span><span class="sxs-lookup"><span data-stu-id="8963b-111">Version</span></span>|<span data-ttu-id="8963b-112">4.5.1</span><span class="sxs-lookup"><span data-stu-id="8963b-112">4.5.1</span></span>|
|<span data-ttu-id="8963b-113">Typ</span><span class="sxs-lookup"><span data-stu-id="8963b-113">Type</span></span>|<span data-ttu-id="8963b-114">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="8963b-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="8963b-115">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="8963b-115">Affected APIs</span></span>

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
