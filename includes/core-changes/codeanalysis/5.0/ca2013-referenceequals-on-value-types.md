---
ms.openlocfilehash: b01424c63d6e7956127bf889c53422b60ba2f219
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065209"
---
### <a name="ca2013-do-not-use-referenceequals-with-value-types"></a><span data-ttu-id="bf715-101">CA2013: Nie używaj metody ReferenceEquals z typami wartości</span><span class="sxs-lookup"><span data-stu-id="bf715-101">CA2013: Do not use ReferenceEquals with value types</span></span>

<span data-ttu-id="bf715-102">Reguła analizatora kodu platformy .NET [CA2013](/visualstudio/code-quality/ca2013) jest domyślnie włączona, począwszy od platformy .NET 5,0.</span><span class="sxs-lookup"><span data-stu-id="bf715-102">.NET code analyzer rule [CA2013](/visualstudio/code-quality/ca2013) is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="bf715-103">Generuje ostrzeżenie kompilacji dla dowolnego kodu, gdzie <xref:System.Object.ReferenceEquals(System.Object,System.Object)> jest używany do porównywania co najmniej jednego typu wartości dla równości.</span><span class="sxs-lookup"><span data-stu-id="bf715-103">It produces a build warning for any code where <xref:System.Object.ReferenceEquals(System.Object,System.Object)> is used to compare one or more value types for equality.</span></span>

#### <a name="change-description"></a><span data-ttu-id="bf715-104">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="bf715-104">Change description</span></span>

<span data-ttu-id="bf715-105">Począwszy od platformy .NET 5,0, zestaw SDK .NET zawiera [analizatory kodu źródłowego platformy .NET](../../../../docs/fundamentals/productivity/code-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="bf715-105">Starting in .NET 5.0, the .NET SDK includes [.NET source code analyzers](../../../../docs/fundamentals/productivity/code-analysis.md).</span></span> <span data-ttu-id="bf715-106">Niektóre z tych reguł są domyślnie włączone, w tym [CA2013](/visualstudio/code-quality/ca2013).</span><span class="sxs-lookup"><span data-stu-id="bf715-106">Several of these rules are enabled, by default, including [CA2013](/visualstudio/code-quality/ca2013).</span></span> <span data-ttu-id="bf715-107">Jeśli projekt zawiera kod naruszający tę regułę i jest skonfigurowany do traktowania ostrzeżeń jako błędów, ta zmiana może spowodować uszkodzenie kompilacji.</span><span class="sxs-lookup"><span data-stu-id="bf715-107">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span>

<span data-ttu-id="bf715-108">CA2013 reguły znajduje wystąpienia <xref:System.Object.ReferenceEquals(System.Object,System.Object)> , gdzie jest używany do porównywania co najmniej jednego typu wartości dla równości.</span><span class="sxs-lookup"><span data-stu-id="bf715-108">Rule CA2013 finds instances where <xref:System.Object.ReferenceEquals(System.Object,System.Object)> is used to compare one or more value types for equality.</span></span> <span data-ttu-id="bf715-109">Porównywanie typów wartości dla równości w ten sposób może prowadzić do niepoprawnych wyników, ponieważ wartości są opakowane przed ich porównaniem.</span><span class="sxs-lookup"><span data-stu-id="bf715-109">Comparing value types for equality in this way can lead to incorrect results, because the values are boxed before they're compared.</span></span> <span data-ttu-id="bf715-110"><xref:System.Object.ReferenceEquals(System.Object,System.Object)> zwróci `false` nawet wtedy, gdy porównane wartości reprezentują to samo wystąpienie typu wartości.</span><span class="sxs-lookup"><span data-stu-id="bf715-110"><xref:System.Object.ReferenceEquals(System.Object,System.Object)> will return `false` even if the compared values represent the same instance of a value type.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="bf715-111">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="bf715-111">Version introduced</span></span>

<span data-ttu-id="bf715-112">5,0 wersja zapoznawcza 8</span><span class="sxs-lookup"><span data-stu-id="bf715-112">5.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="bf715-113">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="bf715-113">Recommended action</span></span>

- <span data-ttu-id="bf715-114">Zmień kod, aby użyć odpowiedniego operatora równości, takiego jak `==` .</span><span class="sxs-lookup"><span data-stu-id="bf715-114">Change the code to use an appropriate equality operator, such as `==`.</span></span> <span data-ttu-id="bf715-115">Nie należy pomijać tego ostrzeżenia.</span><span class="sxs-lookup"><span data-stu-id="bf715-115">You should not suppress this warning.</span></span>

- <span data-ttu-id="bf715-116">Aby całkowicie wyłączyć analizę kodu, ustaw `EnableNETAnalyzers` wartość `false` w pliku projektu.</span><span class="sxs-lookup"><span data-stu-id="bf715-116">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="bf715-117">Aby uzyskać więcej informacji, zobacz [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).</span><span class="sxs-lookup"><span data-stu-id="bf715-117">For more information, see [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

#### <a name="category"></a><span data-ttu-id="bf715-118">Kategoria</span><span class="sxs-lookup"><span data-stu-id="bf715-118">Category</span></span>

<span data-ttu-id="bf715-119">Analiza kodu</span><span class="sxs-lookup"><span data-stu-id="bf715-119">Code analysis</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="bf715-120">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="bf715-120">Affected APIs</span></span>

- <xref:System.Object.ReferenceEquals(System.Object,System.Object)?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Object.ReferenceEquals(System.Object,System.Object)`

-->
