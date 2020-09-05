---
ms.openlocfilehash: fb339fb35cdcbba4f1c860fae9c17162c4cff596
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497594"
---
### <a name="sql_variant-data-uses-sql_variant-collation-rather-than-database-collation"></a><span data-ttu-id="a777f-101">Sql_variant dane używają sortowania sql_variant zamiast sortowania bazy danych</span><span class="sxs-lookup"><span data-stu-id="a777f-101">Sql_variant data uses sql_variant collation rather than database collation</span></span>

#### <a name="details"></a><span data-ttu-id="a777f-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="a777f-102">Details</span></span>

<span data-ttu-id="a777f-103"><code>sql_variant</code> dane korzystają z <code>sql_variant</code> sortowania zamiast sortowania bazy danych.</span><span class="sxs-lookup"><span data-stu-id="a777f-103"><code>sql_variant</code> data uses <code>sql_variant</code> collation rather than database collation.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="a777f-104">Sugestia</span><span class="sxs-lookup"><span data-stu-id="a777f-104">Suggestion</span></span>

<span data-ttu-id="a777f-105">Ta zmiana dotyczy możliwego uszkodzenia danych, jeśli sortowanie bazy danych różni się od <code>sql_variant</code> sortowania.</span><span class="sxs-lookup"><span data-stu-id="a777f-105">This change addresses possible data corruption if the database collation differs from the <code>sql_variant</code> collation.</span></span> <span data-ttu-id="a777f-106">W aplikacjach korzystających z uszkodzonych danych może wystąpić błąd.</span><span class="sxs-lookup"><span data-stu-id="a777f-106">Applications that rely on the corrupted data may experience failure.</span></span>

| <span data-ttu-id="a777f-107">Nazwa</span><span class="sxs-lookup"><span data-stu-id="a777f-107">Name</span></span>    | <span data-ttu-id="a777f-108">Wartość</span><span class="sxs-lookup"><span data-stu-id="a777f-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="a777f-109">Zakres</span><span class="sxs-lookup"><span data-stu-id="a777f-109">Scope</span></span>   |<span data-ttu-id="a777f-110">Przezroczyste</span><span class="sxs-lookup"><span data-stu-id="a777f-110">Transparent</span></span>|
|<span data-ttu-id="a777f-111">Wersja</span><span class="sxs-lookup"><span data-stu-id="a777f-111">Version</span></span>|<span data-ttu-id="a777f-112">4.5</span><span class="sxs-lookup"><span data-stu-id="a777f-112">4.5</span></span>|
|<span data-ttu-id="a777f-113">Typ</span><span class="sxs-lookup"><span data-stu-id="a777f-113">Type</span></span>|<span data-ttu-id="a777f-114">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="a777f-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="a777f-115">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="a777f-115">Affected APIs</span></span>

<span data-ttu-id="a777f-116">Nie wykrywalne za pośrednictwem analizy interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="a777f-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
