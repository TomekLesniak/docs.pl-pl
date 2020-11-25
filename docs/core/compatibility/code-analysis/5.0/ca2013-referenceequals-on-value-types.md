---
title: 'Nieprzerwana zmiana: CA2013: nie należy używać ReferenceEquals z typami wartości'
description: Zapoznaj się z nieprzerwaną zmianą w programie .NET 5,0 spowodowaną przez włączenie reguły analizy kodu CA2013.
ms.date: 09/03/2020
ms.openlocfilehash: ca2b845427eff547b996b577394c6859e30f50bf
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761328"
---
# <a name="warning-ca2013-do-not-use-referenceequals-with-value-types"></a><span data-ttu-id="68b53-103">Ostrzeżenie CA2013: nie należy używać ReferenceEquals z typami wartości</span><span class="sxs-lookup"><span data-stu-id="68b53-103">Warning CA2013: Do not use ReferenceEquals with value types</span></span>

<span data-ttu-id="68b53-104">Reguła analizatora kodu platformy .NET [CA2013](/visualstudio/code-quality/ca2013) jest domyślnie włączona, począwszy od platformy .NET 5,0.</span><span class="sxs-lookup"><span data-stu-id="68b53-104">.NET code analyzer rule [CA2013](/visualstudio/code-quality/ca2013) is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="68b53-105">Generuje ostrzeżenie kompilacji dla dowolnego kodu, gdzie <xref:System.Object.ReferenceEquals(System.Object,System.Object)> jest używany do porównywania co najmniej jednego typu wartości dla równości.</span><span class="sxs-lookup"><span data-stu-id="68b53-105">It produces a build warning for any code where <xref:System.Object.ReferenceEquals(System.Object,System.Object)> is used to compare one or more value types for equality.</span></span>

## <a name="change-description"></a><span data-ttu-id="68b53-106">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="68b53-106">Change description</span></span>

<span data-ttu-id="68b53-107">Począwszy od platformy .NET 5,0, zestaw SDK .NET zawiera [analizatory kodu źródłowego platformy .NET](../../../../fundamentals/code-analysis/overview.md).</span><span class="sxs-lookup"><span data-stu-id="68b53-107">Starting in .NET 5.0, the .NET SDK includes [.NET source code analyzers](../../../../fundamentals/code-analysis/overview.md).</span></span> <span data-ttu-id="68b53-108">Niektóre z tych reguł są domyślnie włączone, w tym [CA2013](/visualstudio/code-quality/ca2013).</span><span class="sxs-lookup"><span data-stu-id="68b53-108">Several of these rules are enabled, by default, including [CA2013](/visualstudio/code-quality/ca2013).</span></span> <span data-ttu-id="68b53-109">Jeśli projekt zawiera kod naruszający tę regułę i jest skonfigurowany do traktowania ostrzeżeń jako błędów, ta zmiana może spowodować uszkodzenie kompilacji.</span><span class="sxs-lookup"><span data-stu-id="68b53-109">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span>

<span data-ttu-id="68b53-110">CA2013 reguły znajduje wystąpienia <xref:System.Object.ReferenceEquals(System.Object,System.Object)> , gdzie jest używany do porównywania co najmniej jednego typu wartości dla równości.</span><span class="sxs-lookup"><span data-stu-id="68b53-110">Rule CA2013 finds instances where <xref:System.Object.ReferenceEquals(System.Object,System.Object)> is used to compare one or more value types for equality.</span></span> <span data-ttu-id="68b53-111">Porównywanie typów wartości dla równości w ten sposób może prowadzić do niepoprawnych wyników, ponieważ wartości są opakowane przed ich porównaniem.</span><span class="sxs-lookup"><span data-stu-id="68b53-111">Comparing value types for equality in this way can lead to incorrect results, because the values are boxed before they're compared.</span></span> <span data-ttu-id="68b53-112"><xref:System.Object.ReferenceEquals(System.Object,System.Object)> zwróci `false` nawet wtedy, gdy porównane wartości reprezentują to samo wystąpienie typu wartości.</span><span class="sxs-lookup"><span data-stu-id="68b53-112"><xref:System.Object.ReferenceEquals(System.Object,System.Object)> will return `false` even if the compared values represent the same instance of a value type.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="68b53-113">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="68b53-113">Version introduced</span></span>

<span data-ttu-id="68b53-114">5,0</span><span class="sxs-lookup"><span data-stu-id="68b53-114">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="68b53-115">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="68b53-115">Recommended action</span></span>

- <span data-ttu-id="68b53-116">Zmień kod, aby użyć odpowiedniego operatora równości, takiego jak `==` .</span><span class="sxs-lookup"><span data-stu-id="68b53-116">Change the code to use an appropriate equality operator, such as `==`.</span></span> <span data-ttu-id="68b53-117">Nie należy pomijać tego ostrzeżenia.</span><span class="sxs-lookup"><span data-stu-id="68b53-117">You should not suppress this warning.</span></span>

- <span data-ttu-id="68b53-118">Aby całkowicie wyłączyć analizę kodu, ustaw `EnableNETAnalyzers` wartość `false` w pliku projektu.</span><span class="sxs-lookup"><span data-stu-id="68b53-118">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="68b53-119">Aby uzyskać więcej informacji, zobacz [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).</span><span class="sxs-lookup"><span data-stu-id="68b53-119">For more information, see [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

## <a name="affected-apis"></a><span data-ttu-id="68b53-120">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="68b53-120">Affected APIs</span></span>

- <xref:System.Object.ReferenceEquals(System.Object,System.Object)?displayProperty=fullName>

<!--

### Affected APIs

- `M:System.Object.ReferenceEquals(System.Object,System.Object)`

### Category

Code analysis

-->
