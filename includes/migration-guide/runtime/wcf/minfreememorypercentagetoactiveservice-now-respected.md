---
ms.openlocfilehash: b23182ad1da8208a69b78fc7bc872780d386a59a
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496939"
---
### <a name="minfreememorypercentagetoactiveservice-is-now-respected"></a><span data-ttu-id="7bd82-101">MinFreeMemoryPercentageToActiveService jest teraz przestrzegane</span><span class="sxs-lookup"><span data-stu-id="7bd82-101">MinFreeMemoryPercentageToActiveService is now respected</span></span>

#### <a name="details"></a><span data-ttu-id="7bd82-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="7bd82-102">Details</span></span>

<span data-ttu-id="7bd82-103">To ustawienie określa minimalną ilość pamięci, która musi być dostępna na serwerze, zanim będzie można aktywować usługę WCF.</span><span class="sxs-lookup"><span data-stu-id="7bd82-103">This setting establishes the minimum memory that must be available on the server before a WCF service can be activated.</span></span> <span data-ttu-id="7bd82-104">Jest ona przeznaczona do zapobiegania <xref:System.OutOfMemoryException?displayProperty=fullName> wyjątkom.</span><span class="sxs-lookup"><span data-stu-id="7bd82-104">It is designed to prevent <xref:System.OutOfMemoryException?displayProperty=fullName> exceptions.</span></span> <span data-ttu-id="7bd82-105">W .NET Framework 4,5 to ustawienie nie ma żadnego wpływu.</span><span class="sxs-lookup"><span data-stu-id="7bd82-105">In the .NET Framework 4.5, this setting had no effect.</span></span> <span data-ttu-id="7bd82-106">W .NET Framework 4.5.1 zostanie zaobserwowane ustawienie.</span><span class="sxs-lookup"><span data-stu-id="7bd82-106">In the .NET Framework 4.5.1, the setting is observed.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="7bd82-107">Sugestia</span><span class="sxs-lookup"><span data-stu-id="7bd82-107">Suggestion</span></span>

<span data-ttu-id="7bd82-108">Wyjątek występuje, jeśli wolna ilość dostępnej pamięci na serwerze sieci Web jest mniejsza niż wartość procentowa zdefiniowana przez ustawienie konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="7bd82-108">An exception occurs if the free memory available on the web server is less than the percentage defined by the configuration setting.</span></span> <span data-ttu-id="7bd82-109">Niektóre usługi WCF, które zostały pomyślnie uruchomione i działały w ograniczonym środowisku pamięci, mogą teraz kończyć się niepowodzeniem.</span><span class="sxs-lookup"><span data-stu-id="7bd82-109">Some WCF services that successfully started and ran in a constrained memory environment may now fail.</span></span>

| <span data-ttu-id="7bd82-110">Nazwa</span><span class="sxs-lookup"><span data-stu-id="7bd82-110">Name</span></span>    | <span data-ttu-id="7bd82-111">Wartość</span><span class="sxs-lookup"><span data-stu-id="7bd82-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="7bd82-112">Zakres</span><span class="sxs-lookup"><span data-stu-id="7bd82-112">Scope</span></span>   |<span data-ttu-id="7bd82-113">Mały</span><span class="sxs-lookup"><span data-stu-id="7bd82-113">Minor</span></span>|
|<span data-ttu-id="7bd82-114">Wersja</span><span class="sxs-lookup"><span data-stu-id="7bd82-114">Version</span></span>|<span data-ttu-id="7bd82-115">4.5.1</span><span class="sxs-lookup"><span data-stu-id="7bd82-115">4.5.1</span></span>|
|<span data-ttu-id="7bd82-116">Typ</span><span class="sxs-lookup"><span data-stu-id="7bd82-116">Type</span></span>|<span data-ttu-id="7bd82-117">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="7bd82-117">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="7bd82-118">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="7bd82-118">Affected APIs</span></span>

<span data-ttu-id="7bd82-119">Nie wykrywalne za pośrednictwem analizy interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="7bd82-119">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
