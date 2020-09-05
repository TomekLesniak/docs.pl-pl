---
ms.openlocfilehash: 8dc947f584d3433f0638a72f4db86ac2680c8dbf
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496832"
---
### <a name="sqlconnection-can-no-longer-connect-to-sql-server-1997-or-databases-using-the-via-adapter"></a><span data-ttu-id="17266-101">Element SqlConnection nie może już łączyć się z SQL Server 1997 lub bazami danych przy użyciu adaptera VIA</span><span class="sxs-lookup"><span data-stu-id="17266-101">SqlConnection can no longer connect to SQL Server 1997 or databases using the VIA adapter</span></span>

#### <a name="details"></a><span data-ttu-id="17266-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="17266-102">Details</span></span>

<span data-ttu-id="17266-103">Połączenia z bazami danych SQL Server przy użyciu [protokołu wirtualnej karty interfejsu (Via)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms191229(v=sql.105)) nie są już obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="17266-103">Connections to SQL Server databases using the [Virtual Interface Adapter (VIA) protocol](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms191229(v=sql.105)) are no longer supported.</span></span> <span data-ttu-id="17266-104">Protokół używany do nawiązywania połączenia z SQL Server bazą danych jest widoczny w parametrach połączenia.</span><span class="sxs-lookup"><span data-stu-id="17266-104">The protocol used to connect to a SQL Server database is visible in the connection string.</span></span> <span data-ttu-id="17266-105">Połączenie TELEFONICZne będzie zawierać: &lt; servername &gt; .</span><span class="sxs-lookup"><span data-stu-id="17266-105">A VIA connection will contain via:&lt;servername&gt;.</span></span> <span data-ttu-id="17266-106">Jeśli ta aplikacja nawiązuje połączenie z usługą SQL za pośrednictwem protokołu innego niż VIA (TCP: lub np.), nie zostanie napotkana żadna przerwana zmiana.</span><span class="sxs-lookup"><span data-stu-id="17266-106">If this app is connecting to SQL via a protocol other than VIA (tcp: or np: for example), then no breaking change will be encountered.</span></span> <span data-ttu-id="17266-107">Ponadto połączenia z SQL Server 7 (1997) nie są już obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="17266-107">Also, connections to SQL Server 7 (1997) are no longer supported.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="17266-108">Sugestia</span><span class="sxs-lookup"><span data-stu-id="17266-108">Suggestion</span></span>

<span data-ttu-id="17266-109">Protokół VIA jest przestarzały, więc do łączenia się z bazami danych SQL należy używać alternatywnego protokołu.</span><span class="sxs-lookup"><span data-stu-id="17266-109">The VIA protocol is deprecated, so an alternative protocol should be used to connect to SQL databases.</span></span> <span data-ttu-id="17266-110">Najczęściej używanym protokołem jest TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="17266-110">The most common protocol used is TCP/IP.</span></span> <span data-ttu-id="17266-111">Aby uzyskać więcej informacji na temat nawiązywania połączenia za pośrednictwem protokołu TCP/IP, zobacz [Włączanie protokołu TCP/IP dla wystąpienia bazy danych](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/bb909712(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="17266-111">For more information about connecting through TCP/IP, see [Enable the TCP/IP protocol for a database instance](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/bb909712(v=vs.90)).</span></span> <span data-ttu-id="17266-112">Jeśli dostęp do bazy danych odbywa się tylko z intranetu, protokół współużytkowanych potoków może zapewnić lepszą wydajność w przypadku powolnej sieci.</span><span class="sxs-lookup"><span data-stu-id="17266-112">If the database is only accessed from within an intranet, the shared pipes protocol may provide better performance if the network is slow.</span></span>

| <span data-ttu-id="17266-113">Nazwa</span><span class="sxs-lookup"><span data-stu-id="17266-113">Name</span></span>    | <span data-ttu-id="17266-114">Wartość</span><span class="sxs-lookup"><span data-stu-id="17266-114">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="17266-115">Zakres</span><span class="sxs-lookup"><span data-stu-id="17266-115">Scope</span></span>   |<span data-ttu-id="17266-116">Edge</span><span class="sxs-lookup"><span data-stu-id="17266-116">Edge</span></span>|
|<span data-ttu-id="17266-117">Wersja</span><span class="sxs-lookup"><span data-stu-id="17266-117">Version</span></span>|<span data-ttu-id="17266-118">4.5</span><span class="sxs-lookup"><span data-stu-id="17266-118">4.5</span></span>|
|<span data-ttu-id="17266-119">Typ</span><span class="sxs-lookup"><span data-stu-id="17266-119">Type</span></span>|<span data-ttu-id="17266-120">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="17266-120">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="17266-121">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="17266-121">Affected APIs</span></span>

- <xref:System.Data.SqlClient.SqlConnection.%23ctor(System.String)>
- <xref:System.Data.SqlClient.SqlConnection.%23ctor(System.String,System.Data.SqlClient.SqlCredential)>

<!--

#### Affected APIs

- `M:System.Data.SqlClient.SqlConnection.#ctor(System.String)`
- `M:System.Data.SqlClient.SqlConnection.#ctor(System.String,System.Data.SqlClient.SqlCredential)`

-->
