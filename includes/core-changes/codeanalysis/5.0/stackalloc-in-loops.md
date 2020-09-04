---
ms.openlocfilehash: a51160a8ab5a4b437e51db31def577f8d8f50182
ms.sourcegitcommit: e7acba36517134238065e4d50bb4a1cfe47ebd06
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/04/2020
ms.locfileid: "89465590"
---
### <a name="ca2014-do-not-use-stackalloc-in-loops"></a><span data-ttu-id="a517a-101">CA2014: Nie używaj słowa kluczowego stackalloc w pętlach</span><span class="sxs-lookup"><span data-stu-id="a517a-101">CA2014: Do not use stackalloc in loops</span></span>

<span data-ttu-id="a517a-102">Reguła analizatora kodu platformy .NET [CA2014](/visualstudio/code-quality/ca2014) jest domyślnie włączona, począwszy od platformy .NET 5,0.</span><span class="sxs-lookup"><span data-stu-id="a517a-102">.NET code analyzer rule [CA2014](/visualstudio/code-quality/ca2014) is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="a517a-103">Generuje ostrzeżenie kompilacji dla dowolnego kodu C#, gdzie wyrażenie [stackalloc](../../../../docs/csharp/language-reference/operators/stackalloc.md) jest używane wewnątrz pętli.</span><span class="sxs-lookup"><span data-stu-id="a517a-103">It produces a build warning for any C# code where a [stackalloc](../../../../docs/csharp/language-reference/operators/stackalloc.md) expression is used inside a loop.</span></span>

#### <a name="change-description"></a><span data-ttu-id="a517a-104">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="a517a-104">Change description</span></span>

<span data-ttu-id="a517a-105">Począwszy od platformy .NET 5,0, zestaw SDK .NET zawiera [analizatory kodu źródłowego platformy .NET](../../../../docs/fundamentals/productivity/code-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="a517a-105">Starting in .NET 5.0, the .NET SDK includes [.NET source code analyzers](../../../../docs/fundamentals/productivity/code-analysis.md).</span></span> <span data-ttu-id="a517a-106">Niektóre z tych reguł są domyślnie włączone, w tym [CA2014](/visualstudio/code-quality/ca2014).</span><span class="sxs-lookup"><span data-stu-id="a517a-106">Several of these rules are enabled, by default, including [CA2014](/visualstudio/code-quality/ca2014).</span></span> <span data-ttu-id="a517a-107">Jeśli projekt zawiera kod naruszający tę regułę i jest skonfigurowany do traktowania ostrzeżeń jako błędów, ta zmiana może spowodować uszkodzenie kompilacji.</span><span class="sxs-lookup"><span data-stu-id="a517a-107">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span>

<span data-ttu-id="a517a-108">CA2014 reguł wyszukuje kod C#, gdzie [wyrażenie stackalloc](../../../../docs/csharp/language-reference/operators/stackalloc.md) jest używane wewnątrz pętli.</span><span class="sxs-lookup"><span data-stu-id="a517a-108">Rule CA2014 looks for C# code where a [stackalloc expression](../../../../docs/csharp/language-reference/operators/stackalloc.md) is used inside a loop.</span></span> <span data-ttu-id="a517a-109">[stackalloc](../../../../docs/csharp/language-reference/operators/stackalloc.md) przydziela pamięć z bieżącej ramki stosu.</span><span class="sxs-lookup"><span data-stu-id="a517a-109">[stackalloc](../../../../docs/csharp/language-reference/operators/stackalloc.md) allocates memory from the current stack frame.</span></span> <span data-ttu-id="a517a-110">Pamięć nie zostanie wydzielona do momentu, gdy bieżące wywołanie metody nie zwróci, co może prowadzić do przepełnienia stosu.</span><span class="sxs-lookup"><span data-stu-id="a517a-110">The memory isn't released until the current method call returns, which can lead to stack overflows.</span></span> <span data-ttu-id="a517a-111">Ponieważ nie można przechwytywać wyjątków przepełnienia stosu, aplikacja zostanie zakończona w przypadku przepełnienia stosu.</span><span class="sxs-lookup"><span data-stu-id="a517a-111">Because you can't catch stack overflow exceptions, the app will terminate in case of stack overflow.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="a517a-112">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="a517a-112">Version introduced</span></span>

<span data-ttu-id="a517a-113">5,0 wersja zapoznawcza 8</span><span class="sxs-lookup"><span data-stu-id="a517a-113">5.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="a517a-114">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="a517a-114">Recommended action</span></span>

- <span data-ttu-id="a517a-115">Unikaj używania [stackalloc](../../../../docs/csharp/language-reference/operators/stackalloc.md) wewnątrz pętli.</span><span class="sxs-lookup"><span data-stu-id="a517a-115">Avoid using [stackalloc](../../../../docs/csharp/language-reference/operators/stackalloc.md) inside loops.</span></span> <span data-ttu-id="a517a-116">Przydziel blok pamięci poza pętlą i ponownie Użyj go wewnątrz pętli.</span><span class="sxs-lookup"><span data-stu-id="a517a-116">Allocate the memory block outside the loop and reuse it inside the loop.</span></span> <span data-ttu-id="a517a-117">Aby uzyskać więcej informacji, zobacz [CA2014](/visualstudio/code-quality/ca2014).</span><span class="sxs-lookup"><span data-stu-id="a517a-117">For more information, see [CA2014](/visualstudio/code-quality/ca2014).</span></span>

- <span data-ttu-id="a517a-118">Aby całkowicie wyłączyć analizę kodu, ustaw `EnableNETAnalyzers` wartość `false` w pliku projektu.</span><span class="sxs-lookup"><span data-stu-id="a517a-118">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="a517a-119">Aby uzyskać więcej informacji, zobacz [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).</span><span class="sxs-lookup"><span data-stu-id="a517a-119">For more information, see [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

#### <a name="category"></a><span data-ttu-id="a517a-120">Kategoria</span><span class="sxs-lookup"><span data-stu-id="a517a-120">Category</span></span>

<span data-ttu-id="a517a-121">Analiza kodu</span><span class="sxs-lookup"><span data-stu-id="a517a-121">Code analysis</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="a517a-122">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="a517a-122">Affected APIs</span></span>

<span data-ttu-id="a517a-123">Nie wykrywalne za pośrednictwem analizy interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="a517a-123">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
