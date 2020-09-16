---
ms.openlocfilehash: e65ba0edb132f5cded244a69d58e43ffea76a039
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606956"
---
### <a name="sqlconnection-can-no-longer-connect-to-sql-server-1997-or-databases-using-the-via-adapter"></a><span data-ttu-id="8e5ec-101">Element SqlConnection nie może już łączyć się z SQL Server 1997 lub bazami danych przy użyciu adaptera VIA</span><span class="sxs-lookup"><span data-stu-id="8e5ec-101">SqlConnection can no longer connect to SQL Server 1997 or databases using the VIA adapter</span></span>

#### <a name="details"></a><span data-ttu-id="8e5ec-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="8e5ec-102">Details</span></span>

<span data-ttu-id="8e5ec-103">Połączenia z bazami danych SQL Server przy użyciu [protokołu wirtualnej karty interfejsu (Via)](/previous-versions/sql/sql-server-2008-r2/ms191229(v=sql.105)) nie są już obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="8e5ec-103">Connections to SQL Server databases using the [Virtual Interface Adapter (VIA) protocol](/previous-versions/sql/sql-server-2008-r2/ms191229(v=sql.105)) are no longer supported.</span></span> <span data-ttu-id="8e5ec-104">Protokół używany do nawiązywania połączenia z SQL Server bazą danych jest widoczny w parametrach połączenia.</span><span class="sxs-lookup"><span data-stu-id="8e5ec-104">The protocol used to connect to a SQL Server database is visible in the connection string.</span></span> <span data-ttu-id="8e5ec-105">Połączenie TELEFONICZne będzie zawierać: &lt; servername &gt; .</span><span class="sxs-lookup"><span data-stu-id="8e5ec-105">A VIA connection will contain via:&lt;servername&gt;.</span></span> <span data-ttu-id="8e5ec-106">Jeśli ta aplikacja nawiązuje połączenie z usługą SQL za pośrednictwem protokołu innego niż VIA (TCP: lub np.), nie zostanie napotkana żadna przerwana zmiana.</span><span class="sxs-lookup"><span data-stu-id="8e5ec-106">If this app is connecting to SQL via a protocol other than VIA (tcp: or np: for example), then no breaking change will be encountered.</span></span> <span data-ttu-id="8e5ec-107">Ponadto połączenia z SQL Server 7 (1997) nie są już obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="8e5ec-107">Also, connections to SQL Server 7 (1997) are no longer supported.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="8e5ec-108">Sugestia</span><span class="sxs-lookup"><span data-stu-id="8e5ec-108">Suggestion</span></span>

<span data-ttu-id="8e5ec-109">Protokół VIA jest przestarzały, więc do łączenia się z bazami danych SQL należy używać alternatywnego protokołu.</span><span class="sxs-lookup"><span data-stu-id="8e5ec-109">The VIA protocol is deprecated, so an alternative protocol should be used to connect to SQL databases.</span></span> <span data-ttu-id="8e5ec-110">Najczęściej używanym protokołem jest TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="8e5ec-110">The most common protocol used is TCP/IP.</span></span> <span data-ttu-id="8e5ec-111">Aby uzyskać więcej informacji na temat nawiązywania połączenia za pośrednictwem protokołu TCP/IP, zobacz [Włączanie protokołu TCP/IP dla wystąpienia bazy danych](/previous-versions/visualstudio/visual-studio-2008/bb909712(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="8e5ec-111">For more information about connecting through TCP/IP, see [Enable the TCP/IP protocol for a database instance](/previous-versions/visualstudio/visual-studio-2008/bb909712(v=vs.90)).</span></span> <span data-ttu-id="8e5ec-112">Jeśli dostęp do bazy danych odbywa się tylko z intranetu, protokół współużytkowanych potoków może zapewnić lepszą wydajność w przypadku powolnej sieci.</span><span class="sxs-lookup"><span data-stu-id="8e5ec-112">If the database is only accessed from within an intranet, the shared pipes protocol may provide better performance if the network is slow.</span></span>

| <span data-ttu-id="8e5ec-113">Nazwa</span><span class="sxs-lookup"><span data-stu-id="8e5ec-113">Name</span></span>    | <span data-ttu-id="8e5ec-114">Wartość</span><span class="sxs-lookup"><span data-stu-id="8e5ec-114">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="8e5ec-115">Zakres</span><span class="sxs-lookup"><span data-stu-id="8e5ec-115">Scope</span></span>   |<span data-ttu-id="8e5ec-116">Edge</span><span class="sxs-lookup"><span data-stu-id="8e5ec-116">Edge</span></span>|
|<span data-ttu-id="8e5ec-117">Wersja</span><span class="sxs-lookup"><span data-stu-id="8e5ec-117">Version</span></span>|<span data-ttu-id="8e5ec-118">4.5</span><span class="sxs-lookup"><span data-stu-id="8e5ec-118">4.5</span></span>|
|<span data-ttu-id="8e5ec-119">Typ</span><span class="sxs-lookup"><span data-stu-id="8e5ec-119">Type</span></span>|<span data-ttu-id="8e5ec-120">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="8e5ec-120">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="8e5ec-121">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="8e5ec-121">Affected APIs</span></span>

- <xref:System.Data.SqlClient.SqlConnection.%23ctor(System.String)>
- <xref:System.Data.SqlClient.SqlConnection.%23ctor(System.String,System.Data.SqlClient.SqlCredential)>

<!--

#### Affected APIs

- `M:System.Data.SqlClient.SqlConnection.#ctor(System.String)`
- `M:System.Data.SqlClient.SqlConnection.#ctor(System.String,System.Data.SqlClient.SqlCredential)`

-->
