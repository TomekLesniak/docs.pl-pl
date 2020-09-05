---
ms.openlocfilehash: c679cb2603d39f580203d9373d76481e904e6c1d
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497204"
---
### <a name="profiling-aspnet-mvc4-apps-can-lead-to-fatal-execution-engine-error"></a><span data-ttu-id="8edf4-101">Profilowanie aplikacji ASP.Net MVC4 może prowadzić do błędu aparatu wykonywania krytycznych</span><span class="sxs-lookup"><span data-stu-id="8edf4-101">Profiling ASP.Net MVC4 apps can lead to Fatal Execution Engine Error</span></span>

#### <a name="details"></a><span data-ttu-id="8edf4-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="8edf4-102">Details</span></span>

<span data-ttu-id="8edf4-103">Moduły plików używające narzędzia NGEN/profile mogą ulec awarii w profilowanych aplikacjach ASP.NET MVC4 podczas uruchamiania przy użyciu "wyjątku aparatu wykonywania krytycznego"</span><span class="sxs-lookup"><span data-stu-id="8edf4-103">Profilers using NGEN /Profile assemblies may crash profiled ASP.NET MVC4 applications on startup with a 'Fatal Execution Engine Exception'</span></span>

#### <a name="suggestion"></a><span data-ttu-id="8edf4-104">Sugestia</span><span class="sxs-lookup"><span data-stu-id="8edf4-104">Suggestion</span></span>

<span data-ttu-id="8edf4-105">Ten problem został rozwiązany w .NET Framework 4.5.2.</span><span class="sxs-lookup"><span data-stu-id="8edf4-105">This issue is fixed in the .NET Framework 4.5.2.</span></span> <span data-ttu-id="8edf4-106">Alternatywnie profiler może uniknąć tego problemu przez określenie <code>COR_PRF_DISABLE_ALL_NGEN_IMAGES</code> w jego masce zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="8edf4-106">Alternatively, the profiler may avoid this issue by specifying <code>COR_PRF_DISABLE_ALL_NGEN_IMAGES</code> in its event mask.</span></span>

| <span data-ttu-id="8edf4-107">Nazwa</span><span class="sxs-lookup"><span data-stu-id="8edf4-107">Name</span></span>    | <span data-ttu-id="8edf4-108">Wartość</span><span class="sxs-lookup"><span data-stu-id="8edf4-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="8edf4-109">Zakres</span><span class="sxs-lookup"><span data-stu-id="8edf4-109">Scope</span></span>   |<span data-ttu-id="8edf4-110">Edge</span><span class="sxs-lookup"><span data-stu-id="8edf4-110">Edge</span></span>|
|<span data-ttu-id="8edf4-111">Wersja</span><span class="sxs-lookup"><span data-stu-id="8edf4-111">Version</span></span>|<span data-ttu-id="8edf4-112">4.5</span><span class="sxs-lookup"><span data-stu-id="8edf4-112">4.5</span></span>|
|<span data-ttu-id="8edf4-113">Typ</span><span class="sxs-lookup"><span data-stu-id="8edf4-113">Type</span></span>|<span data-ttu-id="8edf4-114">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="8edf4-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="8edf4-115">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="8edf4-115">Affected APIs</span></span>

<span data-ttu-id="8edf4-116">Nie wykrywalne za pośrednictwem analizy interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="8edf4-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
