---
ms.openlocfilehash: 25437dcc0c814ed2265b2efb34316af48b372ebd
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497540"
---
### <a name="cor_prf_gc_root_handles-are-not-being-enumerated-by-profilers"></a><span data-ttu-id="b3663-101">COR_PRF_GC_ROOT_HANDLEs nie są wyliczane przez program do plików</span><span class="sxs-lookup"><span data-stu-id="b3663-101">COR_PRF_GC_ROOT_HANDLEs are not being enumerated by profilers</span></span>

#### <a name="details"></a><span data-ttu-id="b3663-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="b3663-102">Details</span></span>

<span data-ttu-id="b3663-103">W .NET Framework v 4.5.1 interfejs API profilowania <code>RootReferences2()</code> jest niepoprawnie nigdy nie zwraca <code>COR_PRF_GC_ROOT_HANDLE</code> (są zwracane jako <code>COR_PRF_GC_ROOT_OTHER</code> zamiast).</span><span class="sxs-lookup"><span data-stu-id="b3663-103">In the .NET Framework v4.5.1, the profiling API <code>RootReferences2()</code> is incorrectly never returning <code>COR_PRF_GC_ROOT_HANDLE</code> (they are returned as <code>COR_PRF_GC_ROOT_OTHER</code> instead).</span></span> <span data-ttu-id="b3663-104">Ten problem został rozwiązany, rozpoczynając od .NET Framework 4,6.</span><span class="sxs-lookup"><span data-stu-id="b3663-104">This issue is fixed beginning in the .NET Framework 4.6.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="b3663-105">Sugestia</span><span class="sxs-lookup"><span data-stu-id="b3663-105">Suggestion</span></span>

<span data-ttu-id="b3663-106">Ten problem został rozwiązany w .NET Framework 4,6 i może zostać rozwiązany przez uaktualnienie do tej wersji .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b3663-106">This issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span>

| <span data-ttu-id="b3663-107">Nazwa</span><span class="sxs-lookup"><span data-stu-id="b3663-107">Name</span></span>    | <span data-ttu-id="b3663-108">Wartość</span><span class="sxs-lookup"><span data-stu-id="b3663-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="b3663-109">Zakres</span><span class="sxs-lookup"><span data-stu-id="b3663-109">Scope</span></span>   |<span data-ttu-id="b3663-110">Mały</span><span class="sxs-lookup"><span data-stu-id="b3663-110">Minor</span></span>|
|<span data-ttu-id="b3663-111">Wersja</span><span class="sxs-lookup"><span data-stu-id="b3663-111">Version</span></span>|<span data-ttu-id="b3663-112">4.5.1</span><span class="sxs-lookup"><span data-stu-id="b3663-112">4.5.1</span></span>|
|<span data-ttu-id="b3663-113">Typ</span><span class="sxs-lookup"><span data-stu-id="b3663-113">Type</span></span>|<span data-ttu-id="b3663-114">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="b3663-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="b3663-115">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="b3663-115">Affected APIs</span></span>

<span data-ttu-id="b3663-116">Nie wykrywalne za pośrednictwem analizy interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="b3663-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
