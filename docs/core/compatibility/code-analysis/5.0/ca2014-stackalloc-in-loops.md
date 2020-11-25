---
title: 'Nieprzerwana zmiana: CA2014: nie używaj stackalloc w pętlach'
description: Zapoznaj się z nieprzerwaną zmianą w programie .NET 5,0 spowodowaną przez włączenie reguły analizy kodu CA2014.
ms.date: 09/03/2020
ms.openlocfilehash: 7ad6203c0edd930bbbe43cdb8df0413cba833d8e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761327"
---
# <a name="warning-ca2014-do-not-use-stackalloc-in-loops"></a><span data-ttu-id="71aa9-103">Ostrzeżenie CA2014: nie używaj stackalloc w pętlach</span><span class="sxs-lookup"><span data-stu-id="71aa9-103">Warning CA2014: Do not use stackalloc in loops</span></span>

<span data-ttu-id="71aa9-104">Reguła analizatora kodu platformy .NET [CA2014](/visualstudio/code-quality/ca2014) jest domyślnie włączona, począwszy od platformy .NET 5,0.</span><span class="sxs-lookup"><span data-stu-id="71aa9-104">.NET code analyzer rule [CA2014](/visualstudio/code-quality/ca2014) is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="71aa9-105">Generuje ostrzeżenie kompilacji dla dowolnego kodu C#, gdzie wyrażenie [stackalloc](../../../../csharp/language-reference/operators/stackalloc.md) jest używane wewnątrz pętli.</span><span class="sxs-lookup"><span data-stu-id="71aa9-105">It produces a build warning for any C# code where a [stackalloc](../../../../csharp/language-reference/operators/stackalloc.md) expression is used inside a loop.</span></span>

## <a name="change-description"></a><span data-ttu-id="71aa9-106">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="71aa9-106">Change description</span></span>

<span data-ttu-id="71aa9-107">Począwszy od platformy .NET 5,0, zestaw SDK .NET zawiera [analizatory kodu źródłowego platformy .NET](../../../../fundamentals/code-analysis/overview.md).</span><span class="sxs-lookup"><span data-stu-id="71aa9-107">Starting in .NET 5.0, the .NET SDK includes [.NET source code analyzers](../../../../fundamentals/code-analysis/overview.md).</span></span> <span data-ttu-id="71aa9-108">Niektóre z tych reguł są domyślnie włączone, w tym [CA2014](/visualstudio/code-quality/ca2014).</span><span class="sxs-lookup"><span data-stu-id="71aa9-108">Several of these rules are enabled, by default, including [CA2014](/visualstudio/code-quality/ca2014).</span></span> <span data-ttu-id="71aa9-109">Jeśli projekt zawiera kod naruszający tę regułę i jest skonfigurowany do traktowania ostrzeżeń jako błędów, ta zmiana może spowodować uszkodzenie kompilacji.</span><span class="sxs-lookup"><span data-stu-id="71aa9-109">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span>

<span data-ttu-id="71aa9-110">CA2014 reguł wyszukuje kod C#, gdzie [wyrażenie stackalloc](../../../../csharp/language-reference/operators/stackalloc.md) jest używane wewnątrz pętli.</span><span class="sxs-lookup"><span data-stu-id="71aa9-110">Rule CA2014 looks for C# code where a [stackalloc expression](../../../../csharp/language-reference/operators/stackalloc.md) is used inside a loop.</span></span> <span data-ttu-id="71aa9-111">[stackalloc](../../../../csharp/language-reference/operators/stackalloc.md) przydziela pamięć z bieżącej ramki stosu.</span><span class="sxs-lookup"><span data-stu-id="71aa9-111">[stackalloc](../../../../csharp/language-reference/operators/stackalloc.md) allocates memory from the current stack frame.</span></span> <span data-ttu-id="71aa9-112">Pamięć nie zostanie wydzielona do momentu, gdy bieżące wywołanie metody nie zwróci, co może prowadzić do przepełnienia stosu.</span><span class="sxs-lookup"><span data-stu-id="71aa9-112">The memory isn't released until the current method call returns, which can lead to stack overflows.</span></span> <span data-ttu-id="71aa9-113">Ponieważ nie można przechwytywać wyjątków przepełnienia stosu, aplikacja zostanie zakończona w przypadku przepełnienia stosu.</span><span class="sxs-lookup"><span data-stu-id="71aa9-113">Because you can't catch stack overflow exceptions, the app will terminate in case of stack overflow.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="71aa9-114">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="71aa9-114">Version introduced</span></span>

<span data-ttu-id="71aa9-115">5,0</span><span class="sxs-lookup"><span data-stu-id="71aa9-115">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="71aa9-116">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="71aa9-116">Recommended action</span></span>

- <span data-ttu-id="71aa9-117">Unikaj używania [stackalloc](../../../../csharp/language-reference/operators/stackalloc.md) wewnątrz pętli.</span><span class="sxs-lookup"><span data-stu-id="71aa9-117">Avoid using [stackalloc](../../../../csharp/language-reference/operators/stackalloc.md) inside loops.</span></span> <span data-ttu-id="71aa9-118">Przydziel blok pamięci poza pętlą i ponownie Użyj go wewnątrz pętli.</span><span class="sxs-lookup"><span data-stu-id="71aa9-118">Allocate the memory block outside the loop and reuse it inside the loop.</span></span> <span data-ttu-id="71aa9-119">Aby uzyskać więcej informacji, zobacz [CA2014](/visualstudio/code-quality/ca2014).</span><span class="sxs-lookup"><span data-stu-id="71aa9-119">For more information, see [CA2014](/visualstudio/code-quality/ca2014).</span></span>

- <span data-ttu-id="71aa9-120">Aby całkowicie wyłączyć analizę kodu, ustaw `EnableNETAnalyzers` wartość `false` w pliku projektu.</span><span class="sxs-lookup"><span data-stu-id="71aa9-120">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="71aa9-121">Aby uzyskać więcej informacji, zobacz [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).</span><span class="sxs-lookup"><span data-stu-id="71aa9-121">For more information, see [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

## <a name="affected-apis"></a><span data-ttu-id="71aa9-122">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="71aa9-122">Affected APIs</span></span>

<span data-ttu-id="71aa9-123">Nie wykrywalne za pośrednictwem analizy interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="71aa9-123">Not detectable via API analysis.</span></span>

<!--

### Affected APIs

Not detectable via API analysis.

### Category

Code analysis

-->
