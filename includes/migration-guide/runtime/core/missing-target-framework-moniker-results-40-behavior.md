---
ms.openlocfilehash: 49740d3b1890d72935e6e329a4f4be836ed70b25
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496370"
---
### <a name="missing-target-framework-moniker-results-in-40-behavior"></a><span data-ttu-id="d9047-101">Brak monikera platformy docelowej w wyniku 4,0</span><span class="sxs-lookup"><span data-stu-id="d9047-101">Missing Target Framework Moniker results in 4.0 behavior</span></span>

#### <a name="details"></a><span data-ttu-id="d9047-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="d9047-102">Details</span></span>

<span data-ttu-id="d9047-103">Aplikacje bez <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName> zastosowania na poziomie zestawu zostaną automatycznie uruchomione przy użyciu semantyki (osobliwości) .NET Framework 4,0.</span><span class="sxs-lookup"><span data-stu-id="d9047-103">Applications without a <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName> applied at the assembly level will automatically run using the semantics (quirks) of the .NET Framework 4.0.</span></span> <span data-ttu-id="d9047-104">W celu zapewnienia wysokiej jakości zaleca się, aby wszystkie pliki binarne były jawnie przypisane do <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName> wskazania wersji .NET Framework, z których zostały skompilowane.</span><span class="sxs-lookup"><span data-stu-id="d9047-104">To ensure high quality, it is recommended that all binaries be explicitly attributed with a <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName> indicating the version of the .NET Framework they were built with.</span></span> <span data-ttu-id="d9047-105">Należy zauważyć, że użycie monikera platformy docelowej w pliku projektu spowoduje automatyczne zastosowanie przez program MSBuild <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName> .</span><span class="sxs-lookup"><span data-stu-id="d9047-105">Note that using a target framework moniker in a project file will cause MSBuild to automatically apply a <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName>.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="d9047-106">Sugestia</span><span class="sxs-lookup"><span data-stu-id="d9047-106">Suggestion</span></span>

<span data-ttu-id="d9047-107"><xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName>Powinien być dostarczony przez dodanie atrybutu bezpośrednio do zestawu lub przez określenie platformy docelowej w [pliku projektu lub graficznego interfejsu użytkownika programu Visual Studio](https://devblogs.microsoft.com/visualstudio/visual-studio-managed-multi-targeting-part-1-concepts-target-framework-moniker-target-framework/).</span><span class="sxs-lookup"><span data-stu-id="d9047-107">A <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName> should be supplied, either through adding the attribute directly to the assembly or by specifying a target framework in the [project file or through Visual Studio's project properties GUI](https://devblogs.microsoft.com/visualstudio/visual-studio-managed-multi-targeting-part-1-concepts-target-framework-moniker-target-framework/).</span></span>

| <span data-ttu-id="d9047-108">Nazwa</span><span class="sxs-lookup"><span data-stu-id="d9047-108">Name</span></span>    | <span data-ttu-id="d9047-109">Wartość</span><span class="sxs-lookup"><span data-stu-id="d9047-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="d9047-110">Zakres</span><span class="sxs-lookup"><span data-stu-id="d9047-110">Scope</span></span>   |<span data-ttu-id="d9047-111">Duży</span><span class="sxs-lookup"><span data-stu-id="d9047-111">Major</span></span>|
|<span data-ttu-id="d9047-112">Wersja</span><span class="sxs-lookup"><span data-stu-id="d9047-112">Version</span></span>|<span data-ttu-id="d9047-113">4.5</span><span class="sxs-lookup"><span data-stu-id="d9047-113">4.5</span></span>|
|<span data-ttu-id="d9047-114">Typ</span><span class="sxs-lookup"><span data-stu-id="d9047-114">Type</span></span>|<span data-ttu-id="d9047-115">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="d9047-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="d9047-116">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="d9047-116">Affected APIs</span></span>

<span data-ttu-id="d9047-117">Nie wykrywalne za pośrednictwem analizy interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="d9047-117">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
