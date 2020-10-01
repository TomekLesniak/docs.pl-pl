---
ms.openlocfilehash: 8b70df0fb2072fd5243d9e46a4a20c22cc7fd677
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/01/2020
ms.locfileid: "91607798"
---
### <a name="profiling-aspnet-mvc4-apps-can-lead-to-fatal-execution-engine-error"></a><span data-ttu-id="3339e-101">Profilowanie aplikacji ASP.NET MVC4 może prowadzić do błędu aparatu wykonywania krytycznych</span><span class="sxs-lookup"><span data-stu-id="3339e-101">Profiling ASP.NET MVC4 apps can lead to Fatal Execution Engine Error</span></span>

#### <a name="details"></a><span data-ttu-id="3339e-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="3339e-102">Details</span></span>

<span data-ttu-id="3339e-103">Moduły plików używające narzędzia NGEN/profile mogą ulec awarii w profilowanych aplikacjach ASP.NET MVC4 podczas uruchamiania przy użyciu "wyjątku aparatu wykonywania krytycznego"</span><span class="sxs-lookup"><span data-stu-id="3339e-103">Profilers using NGEN /Profile assemblies may crash profiled ASP.NET MVC4 applications on startup with a 'Fatal Execution Engine Exception'</span></span>

#### <a name="suggestion"></a><span data-ttu-id="3339e-104">Sugestia</span><span class="sxs-lookup"><span data-stu-id="3339e-104">Suggestion</span></span>

<span data-ttu-id="3339e-105">Ten problem został rozwiązany w .NET Framework 4.5.2.</span><span class="sxs-lookup"><span data-stu-id="3339e-105">This issue is fixed in the .NET Framework 4.5.2.</span></span> <span data-ttu-id="3339e-106">Alternatywnie profiler może uniknąć tego problemu przez określenie <code>COR_PRF_DISABLE_ALL_NGEN_IMAGES</code> w jego masce zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="3339e-106">Alternatively, the profiler may avoid this issue by specifying <code>COR_PRF_DISABLE_ALL_NGEN_IMAGES</code> in its event mask.</span></span>

| <span data-ttu-id="3339e-107">Nazwa</span><span class="sxs-lookup"><span data-stu-id="3339e-107">Name</span></span>    | <span data-ttu-id="3339e-108">Wartość</span><span class="sxs-lookup"><span data-stu-id="3339e-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="3339e-109">Zakres</span><span class="sxs-lookup"><span data-stu-id="3339e-109">Scope</span></span>   |<span data-ttu-id="3339e-110">Edge</span><span class="sxs-lookup"><span data-stu-id="3339e-110">Edge</span></span>|
|<span data-ttu-id="3339e-111">Wersja</span><span class="sxs-lookup"><span data-stu-id="3339e-111">Version</span></span>|<span data-ttu-id="3339e-112">4.5</span><span class="sxs-lookup"><span data-stu-id="3339e-112">4.5</span></span>|
|<span data-ttu-id="3339e-113">Typ</span><span class="sxs-lookup"><span data-stu-id="3339e-113">Type</span></span>|<span data-ttu-id="3339e-114">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="3339e-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="3339e-115">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="3339e-115">Affected APIs</span></span>

<span data-ttu-id="3339e-116">Nie wykrywalne za pośrednictwem analizy interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="3339e-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
