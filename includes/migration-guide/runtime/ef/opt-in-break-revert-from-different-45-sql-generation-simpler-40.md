---
ms.openlocfilehash: 346fb6ecd43f7f93529e45f169c79b7acacc9c1f
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496269"
---
### <a name="opt-in-break-to-revert-from-different-45-sql-generation-to-simpler-40-sql-generation"></a><span data-ttu-id="96dee-101">Cofnięcie zgody na przywrócenie z różnych 4,5 generacji SQL do 4,0 prostszej generacji SQL</span><span class="sxs-lookup"><span data-stu-id="96dee-101">Opt-in break to revert from different 4.5 SQL generation to simpler 4.0 SQL generation</span></span>

#### <a name="details"></a><span data-ttu-id="96dee-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="96dee-102">Details</span></span>

<span data-ttu-id="96dee-103">Zapytania, które tworzą instrukcje JOIN i zawierają wywołanie operacji ograniczającej bez wcześniejszego użycia polecenia OrderBy teraz generują prostsze SQL.</span><span class="sxs-lookup"><span data-stu-id="96dee-103">Queries that produce JOIN statements and contain a call to a limiting operation without first using OrderBy now produce simpler SQL.</span></span> <span data-ttu-id="96dee-104">Po uaktualnieniu do .NET Framework 4,5 te zapytania wygenerowały bardziej skomplikowane SQL niż poprzednie wersje.</span><span class="sxs-lookup"><span data-stu-id="96dee-104">After upgrading to .NET Framework 4.5, these queries produced more complicated SQL than previous versions.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="96dee-105">Sugestia</span><span class="sxs-lookup"><span data-stu-id="96dee-105">Suggestion</span></span>

<span data-ttu-id="96dee-106">Ta funkcja jest domyślnie wyłączona.</span><span class="sxs-lookup"><span data-stu-id="96dee-106">This feature is disabled by default.</span></span> <span data-ttu-id="96dee-107">Jeśli Entity Framework generuje dodatkowe instrukcje JOIN, które powodują spadek wydajności, możesz włączyć tę funkcję, dodając następujący wpis do <code>&lt;appSettings&gt;</code> sekcji pliku konfiguracji aplikacji (app.config):</span><span class="sxs-lookup"><span data-stu-id="96dee-107">If Entity Framework generates extra JOIN statements that cause performance degradation, you can enable this feature by adding the following entry to the <code>&lt;appSettings&gt;</code> section of the application configuration (app.config) file:</span></span><pre><code class="lang-xml">&lt;add key=&quot;EntityFramework_SimplifyLimitOperations&quot; value=&quot;true&quot; /&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="96dee-108">Nazwa</span><span class="sxs-lookup"><span data-stu-id="96dee-108">Name</span></span>    | <span data-ttu-id="96dee-109">Wartość</span><span class="sxs-lookup"><span data-stu-id="96dee-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="96dee-110">Zakres</span><span class="sxs-lookup"><span data-stu-id="96dee-110">Scope</span></span>   |<span data-ttu-id="96dee-111">Przezroczyste</span><span class="sxs-lookup"><span data-stu-id="96dee-111">Transparent</span></span>|
|<span data-ttu-id="96dee-112">Wersja</span><span class="sxs-lookup"><span data-stu-id="96dee-112">Version</span></span>|<span data-ttu-id="96dee-113">4.5.2</span><span class="sxs-lookup"><span data-stu-id="96dee-113">4.5.2</span></span>|
|<span data-ttu-id="96dee-114">Typ</span><span class="sxs-lookup"><span data-stu-id="96dee-114">Type</span></span>|<span data-ttu-id="96dee-115">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="96dee-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="96dee-116">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="96dee-116">Affected APIs</span></span>

<span data-ttu-id="96dee-117">Nie wykrywalne za pośrednictwem analizy interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="96dee-117">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
