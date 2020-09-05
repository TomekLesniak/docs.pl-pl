---
ms.openlocfilehash: bbeca87b3f498213b91d942cc4f197c9d80457a8
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497414"
---
### <a name="attempting-a-tcpip-connection-to-a-sql-server-database-that-resolves-to-localhost-fails"></a><span data-ttu-id="f40af-101">Próba połączenia TCP/IP z SQL Server bazą danych, która jest rozpoznawana jako `localhost` Niepowodzenie</span><span class="sxs-lookup"><span data-stu-id="f40af-101">Attempting a TCP/IP connection to a SQL Server database that resolves to `localhost` fails</span></span>

#### <a name="details"></a><span data-ttu-id="f40af-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="f40af-102">Details</span></span>

<span data-ttu-id="f40af-103">W .NET Framework 4,6 i 4.6.1 próbuje nawiązać połączenie TCP/IP z bazą danych SQL Server, która jest rozpoznawana jako <code>localhost</code> błąd, &quot; Wystąpił błąd związany z siecią lub wystąpieniem podczas nawiązywania połączenia z SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f40af-103">In the .NET Framework 4.6 and 4.6.1, attempting a TCP/IP connection to a SQL Server database that resolves to <code>localhost</code> fails with the error, &quot;A network-related or instance-specific error occurred while establishing a connection to SQL Server.</span></span> <span data-ttu-id="f40af-104">Serwer nie został znaleziony lub był niedostępny.</span><span class="sxs-lookup"><span data-stu-id="f40af-104">The server was not found or was not accessible.</span></span> <span data-ttu-id="f40af-105">Sprawdź, czy nazwa wystąpienia jest poprawna i czy SQL Server jest skonfigurowany do zezwalania na połączenia zdalne.</span><span class="sxs-lookup"><span data-stu-id="f40af-105">Verify that the instance name is correct and that SQL Server is configured to allow remote connections.</span></span> <span data-ttu-id="f40af-106">(Dostawca: interfejsy sieciowe SQL, błąd: 26 — błąd lokalizowania określonego serwera/wystąpienia)&quot;</span><span class="sxs-lookup"><span data-stu-id="f40af-106">(provider: SQL Network Interfaces, error: 26 - Error Locating Server/Instance Specified)&quot;</span></span>

#### <a name="suggestion"></a><span data-ttu-id="f40af-107">Sugestia</span><span class="sxs-lookup"><span data-stu-id="f40af-107">Suggestion</span></span>

<span data-ttu-id="f40af-108">Ten problem został rozwiązany i poprzednie zachowanie zostało przywrócone w .NET Framework 4.6.2.</span><span class="sxs-lookup"><span data-stu-id="f40af-108">This issue has been addressed and the previous behavior restored in the .NET Framework 4.6.2.</span></span> <span data-ttu-id="f40af-109">Aby nawiązać połączenie z bazą danych SQL Server, która jest rozpoznawana jako <code>localhost</code> , należy przeprowadzić uaktualnienie do .NET Framework 4.6.2.</span><span class="sxs-lookup"><span data-stu-id="f40af-109">To connect to a SQL Server database that resolves to <code>localhost</code>, upgrade to the .NET Framework 4.6.2.</span></span>

| <span data-ttu-id="f40af-110">Nazwa</span><span class="sxs-lookup"><span data-stu-id="f40af-110">Name</span></span>    | <span data-ttu-id="f40af-111">Wartość</span><span class="sxs-lookup"><span data-stu-id="f40af-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="f40af-112">Zakres</span><span class="sxs-lookup"><span data-stu-id="f40af-112">Scope</span></span>   |<span data-ttu-id="f40af-113">Mały</span><span class="sxs-lookup"><span data-stu-id="f40af-113">Minor</span></span>|
|<span data-ttu-id="f40af-114">Wersja</span><span class="sxs-lookup"><span data-stu-id="f40af-114">Version</span></span>|<span data-ttu-id="f40af-115">4,6</span><span class="sxs-lookup"><span data-stu-id="f40af-115">4.6</span></span>|
|<span data-ttu-id="f40af-116">Typ</span><span class="sxs-lookup"><span data-stu-id="f40af-116">Type</span></span>|<span data-ttu-id="f40af-117">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="f40af-117">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="f40af-118">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="f40af-118">Affected APIs</span></span>

<span data-ttu-id="f40af-119">Nie wykrywalne za pośrednictwem analizy interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="f40af-119">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
