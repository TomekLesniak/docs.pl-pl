---
ms.openlocfilehash: c3114277445daaae988b41782721c443c1e780d1
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496859"
---
### <a name="wpf-spawns-a-wisptisexe-process-which-can-freeze-the-mouse"></a><span data-ttu-id="d8a9b-101">WPF duplikuje proces wisptis.exe, który może zablokować mysz</span><span class="sxs-lookup"><span data-stu-id="d8a9b-101">WPF spawns a wisptis.exe process which can freeze the mouse</span></span>

#### <a name="details"></a><span data-ttu-id="d8a9b-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="d8a9b-102">Details</span></span>

<span data-ttu-id="d8a9b-103">W ppkt 4.5.2 wprowadzono problem, który powoduje, <code>wisptis.exe</code> że można zablokować dane wejściowe myszy.</span><span class="sxs-lookup"><span data-stu-id="d8a9b-103">An issue was introduced in 4.5.2 that causes <code>wisptis.exe</code> to be spawned that can freeze mouse input.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="d8a9b-104">Sugestia</span><span class="sxs-lookup"><span data-stu-id="d8a9b-104">Suggestion</span></span>

<span data-ttu-id="d8a9b-105">Rozwiązanie tego problemu jest dostępne w wydaniu obsługi .NET Framework 4.5.2 (pakiet zbiorczy poprawek 3026376) lub przez uaktualnienie do .NET Framework 4,6</span><span class="sxs-lookup"><span data-stu-id="d8a9b-105">A fix for this issue is available in a servicing release of the .NET Framework 4.5.2 (hotfix rollup 3026376), or by upgrading to the .NET Framework 4.6</span></span>

| <span data-ttu-id="d8a9b-106">Nazwa</span><span class="sxs-lookup"><span data-stu-id="d8a9b-106">Name</span></span>    | <span data-ttu-id="d8a9b-107">Wartość</span><span class="sxs-lookup"><span data-stu-id="d8a9b-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="d8a9b-108">Zakres</span><span class="sxs-lookup"><span data-stu-id="d8a9b-108">Scope</span></span>   |<span data-ttu-id="d8a9b-109">Duży</span><span class="sxs-lookup"><span data-stu-id="d8a9b-109">Major</span></span>|
|<span data-ttu-id="d8a9b-110">Wersja</span><span class="sxs-lookup"><span data-stu-id="d8a9b-110">Version</span></span>|<span data-ttu-id="d8a9b-111">4.5.2</span><span class="sxs-lookup"><span data-stu-id="d8a9b-111">4.5.2</span></span>|
|<span data-ttu-id="d8a9b-112">Typ</span><span class="sxs-lookup"><span data-stu-id="d8a9b-112">Type</span></span>|<span data-ttu-id="d8a9b-113">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="d8a9b-113">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="d8a9b-114">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="d8a9b-114">Affected APIs</span></span>

<span data-ttu-id="d8a9b-115">Nie wykrywalne za pośrednictwem analizy interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="d8a9b-115">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
