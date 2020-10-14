---
ms.openlocfilehash: 80d13609f1b02ae0ac875b2028e745670bb8f503
ms.sourcegitcommit: 39b1d5f2978be15409c189a66ab30781d9082cd8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/14/2020
ms.locfileid: "92050572"
---
### <a name="frameworkdescriptions-value-is-net-instead-of-net-core"></a><span data-ttu-id="8de69-101">FrameworkDescription jest wartością .NET zamiast .NET Core</span><span class="sxs-lookup"><span data-stu-id="8de69-101">FrameworkDescription's value is .NET instead of .NET Core</span></span>

<span data-ttu-id="8de69-102"><xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> teraz zwraca wartość ".NET" zamiast ".NET Core".</span><span class="sxs-lookup"><span data-stu-id="8de69-102"><xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> now returns ".NET" instead of ".NET Core".</span></span>

#### <a name="change-description"></a><span data-ttu-id="8de69-103">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="8de69-103">Change description</span></span>

<span data-ttu-id="8de69-104">W poprzednich wersjach programu .NET <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> zwraca wartość ".NET Core" jako część ciągu opisu, na przykład `.NET Core 3.1.1` .</span><span class="sxs-lookup"><span data-stu-id="8de69-104">In previous .NET versions, <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> returns ".NET Core" as part of the description string, for example, `.NET Core 3.1.1`.</span></span>

<span data-ttu-id="8de69-105">Począwszy od platformy .NET 5,0, <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> zwraca ".NET" jako część ciągu opisu, na przykład `.NET 5.0.0` .</span><span class="sxs-lookup"><span data-stu-id="8de69-105">Starting in .NET 5.0, <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> returns ".NET" as part of the description string, for example, `.NET 5.0.0`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="8de69-106">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="8de69-106">Reason for change</span></span>

<span data-ttu-id="8de69-107">Program .NET 5 `netcoreapp` jest zastępowany przez `net` krótką moniker struktury Target.</span><span class="sxs-lookup"><span data-stu-id="8de69-107">With .NET 5, `netcoreapp` is replaced by `net` as the short target-framework moniker.</span></span> <span data-ttu-id="8de69-108">W celu zapewnienia spójności Opis został również zaktualizowany.</span><span class="sxs-lookup"><span data-stu-id="8de69-108">For consistency, the framework's description has also been updated.</span></span> <span data-ttu-id="8de69-109">Zmiana jest Kosmetyka, ponieważ `FrameworkName` nie jest zaszyfrowana w dowolnym miejscu niż we <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> właściwości.</span><span class="sxs-lookup"><span data-stu-id="8de69-109">The change is cosmetic, as the `FrameworkName` isn't encoded anywhere else than in the <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> property.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="8de69-110">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="8de69-110">Version introduced</span></span>

<span data-ttu-id="8de69-111">5,0</span><span class="sxs-lookup"><span data-stu-id="8de69-111">5.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="8de69-112">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="8de69-112">Recommended action</span></span>

<span data-ttu-id="8de69-113">Zaktualizuj dowolny kod, który wyszukuje ".NET Core" w ciągu zwracanym przez <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription> .</span><span class="sxs-lookup"><span data-stu-id="8de69-113">Update any code that searches for ".NET Core" in the string returned by <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription>.</span></span>

#### <a name="category"></a><span data-ttu-id="8de69-114">Kategoria</span><span class="sxs-lookup"><span data-stu-id="8de69-114">Category</span></span>

<span data-ttu-id="8de69-115">Podstawowe biblioteki platformy .NET</span><span class="sxs-lookup"><span data-stu-id="8de69-115">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="8de69-116">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="8de69-116">Affected APIs</span></span>

- <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription`

-->
