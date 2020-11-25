---
title: 'Nieprzerwana zmiana: wartość FrameworkDescription jest platformą .NET zamiast .NET Core'
description: Dowiedz się więcej na temat istotnej zmiany w programie .NET 5,0 w bibliotekach podstawowych platformy .NET, gdzie RuntimeInformation. FrameworkDescription teraz zwraca wartość ".NET" zamiast ".NET Core".
ms.date: 11/01/2020
ms.openlocfilehash: 3925fb092135c26291e1e60b99f359974d21553c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761559"
---
# <a name="frameworkdescriptions-value-is-net-instead-of-net-core"></a><span data-ttu-id="4f5b0-103">FrameworkDescription jest wartością .NET zamiast .NET Core</span><span class="sxs-lookup"><span data-stu-id="4f5b0-103">FrameworkDescription's value is .NET instead of .NET Core</span></span>

<span data-ttu-id="4f5b0-104"><xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> teraz zwraca wartość ".NET" zamiast ".NET Core".</span><span class="sxs-lookup"><span data-stu-id="4f5b0-104"><xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> now returns ".NET" instead of ".NET Core".</span></span>

## <a name="change-description"></a><span data-ttu-id="4f5b0-105">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="4f5b0-105">Change description</span></span>

<span data-ttu-id="4f5b0-106">W poprzednich wersjach programu .NET <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> zwraca wartość ".NET Core" jako część ciągu opisu, na przykład `.NET Core 3.1.1` .</span><span class="sxs-lookup"><span data-stu-id="4f5b0-106">In previous .NET versions, <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> returns ".NET Core" as part of the description string, for example, `.NET Core 3.1.1`.</span></span>

<span data-ttu-id="4f5b0-107">Począwszy od platformy .NET 5,0, <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> zwraca ".NET" jako część ciągu opisu, na przykład `.NET 5.0.0` .</span><span class="sxs-lookup"><span data-stu-id="4f5b0-107">Starting in .NET 5.0, <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> returns ".NET" as part of the description string, for example, `.NET 5.0.0`.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="4f5b0-108">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="4f5b0-108">Reason for change</span></span>

<span data-ttu-id="4f5b0-109">Program .NET 5 `netcoreapp` jest zastępowany przez `net` krótką moniker struktury Target.</span><span class="sxs-lookup"><span data-stu-id="4f5b0-109">With .NET 5, `netcoreapp` is replaced by `net` as the short target-framework moniker.</span></span> <span data-ttu-id="4f5b0-110">W celu zapewnienia spójności Opis został również zaktualizowany.</span><span class="sxs-lookup"><span data-stu-id="4f5b0-110">For consistency, the framework's description has also been updated.</span></span> <span data-ttu-id="4f5b0-111">Zmiana jest Kosmetyka, ponieważ `FrameworkName` nie jest zaszyfrowana w dowolnym miejscu niż we <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> właściwości.</span><span class="sxs-lookup"><span data-stu-id="4f5b0-111">The change is cosmetic, as the `FrameworkName` isn't encoded anywhere else than in the <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> property.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="4f5b0-112">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="4f5b0-112">Version introduced</span></span>

<span data-ttu-id="4f5b0-113">5,0</span><span class="sxs-lookup"><span data-stu-id="4f5b0-113">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="4f5b0-114">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="4f5b0-114">Recommended action</span></span>

<span data-ttu-id="4f5b0-115">Zaktualizuj dowolny kod, który wyszukuje ".NET Core" w ciągu zwracanym przez <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription> .</span><span class="sxs-lookup"><span data-stu-id="4f5b0-115">Update any code that searches for ".NET Core" in the string returned by <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription>.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="4f5b0-116">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="4f5b0-116">Affected APIs</span></span>

- <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `P:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription`

-->
