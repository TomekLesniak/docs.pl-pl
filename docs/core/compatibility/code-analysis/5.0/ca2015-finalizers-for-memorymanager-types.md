---
title: 'Nieprzerwana zmiana: CA2015: nie Definiuj finalizatorów dla typów pochodzących z pamięci<T>'
description: Zapoznaj się z nieprzerwaną zmianą w programie .NET 5,0 spowodowaną przez włączenie reguły analizy kodu CA2015.
ms.date: 09/03/2020
ms.openlocfilehash: 5d0ba0546b5a72363559f23713c8af4bb4e26e48
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761324"
---
# <a name="warning-ca2015-do-not-define-finalizers-for-types-derived-from-memorymanagert"></a><span data-ttu-id="6372e-103">Ostrzeżenie CA2015: nie Definiuj finalizatorów dla typów pochodzących z pamięci\<T></span><span class="sxs-lookup"><span data-stu-id="6372e-103">Warning CA2015: Do not define finalizers for types derived from MemoryManager\<T></span></span>

<span data-ttu-id="6372e-104">Reguła analizatora kodu platformy .NET [CA2015](/visualstudio/code-quality/ca2015) jest domyślnie włączona, począwszy od platformy .NET 5,0.</span><span class="sxs-lookup"><span data-stu-id="6372e-104">.NET code analyzer rule [CA2015](/visualstudio/code-quality/ca2015) is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="6372e-105">Generuje ostrzeżenie kompilacji dla dowolnego typu, który pochodzi od <xref:System.Buffers.MemoryManager%601> , który definiuje finalizator.</span><span class="sxs-lookup"><span data-stu-id="6372e-105">It produces a build warning for any types that derive from <xref:System.Buffers.MemoryManager%601> that define a finalizer.</span></span>

## <a name="change-description"></a><span data-ttu-id="6372e-106">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="6372e-106">Change description</span></span>

<span data-ttu-id="6372e-107">Począwszy od platformy .NET 5,0, zestaw SDK .NET zawiera [analizatory kodu źródłowego platformy .NET](../../../../fundamentals/code-analysis/overview.md).</span><span class="sxs-lookup"><span data-stu-id="6372e-107">Starting in .NET 5.0, the .NET SDK includes [.NET source code analyzers](../../../../fundamentals/code-analysis/overview.md).</span></span> <span data-ttu-id="6372e-108">Niektóre z tych reguł są domyślnie włączone, w tym [CA2015](/visualstudio/code-quality/ca2015).</span><span class="sxs-lookup"><span data-stu-id="6372e-108">Several of these rules are enabled, by default, including [CA2015](/visualstudio/code-quality/ca2015).</span></span> <span data-ttu-id="6372e-109">Jeśli projekt zawiera kod naruszający tę regułę i jest skonfigurowany do traktowania ostrzeżeń jako błędów, ta zmiana może spowodować uszkodzenie kompilacji.</span><span class="sxs-lookup"><span data-stu-id="6372e-109">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span>

<span data-ttu-id="6372e-110">Reguły CA2015 typy flag, które pochodzą od <xref:System.Buffers.MemoryManager%601> elementu, który definiuje finalizator.</span><span class="sxs-lookup"><span data-stu-id="6372e-110">Rule CA2015 flags types that derive from <xref:System.Buffers.MemoryManager%601> that define a finalizer.</span></span> <span data-ttu-id="6372e-111">Dodanie finalizatora do typu, który pochodzi od, <xref:System.Buffers.MemoryManager%601> prawdopodobnie wskazuje na błąd.</span><span class="sxs-lookup"><span data-stu-id="6372e-111">Adding a finalizer to a type that derives from <xref:System.Buffers.MemoryManager%601> is likely an indication of a bug.</span></span> <span data-ttu-id="6372e-112">Sugeruje to, że zasób natywny, który mógł zostać uzyskany w <xref:System.Span%601> trakcie, jest wyczyszczony, prawdopodobnie w czasie, gdy jest nadal używany przez <xref:System.Span%601> .</span><span class="sxs-lookup"><span data-stu-id="6372e-112">It suggests that a native resource that could have been obtained in a <xref:System.Span%601> is getting cleaned up, potentially while it's still in use by the <xref:System.Span%601>.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="6372e-113">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="6372e-113">Version introduced</span></span>

<span data-ttu-id="6372e-114">5,0</span><span class="sxs-lookup"><span data-stu-id="6372e-114">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="6372e-115">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="6372e-115">Recommended action</span></span>

- <span data-ttu-id="6372e-116">Usuń definicję finalizatora.</span><span class="sxs-lookup"><span data-stu-id="6372e-116">Remove the finalizer definition.</span></span> <span data-ttu-id="6372e-117">Aby uzyskać więcej informacji, zobacz [CA2015](/visualstudio/code-quality/ca2015).</span><span class="sxs-lookup"><span data-stu-id="6372e-117">For more information, see [CA2015](/visualstudio/code-quality/ca2015).</span></span>

- <span data-ttu-id="6372e-118">Aby całkowicie wyłączyć analizę kodu, ustaw `EnableNETAnalyzers` wartość `false` w pliku projektu.</span><span class="sxs-lookup"><span data-stu-id="6372e-118">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="6372e-119">Aby uzyskać więcej informacji, zobacz [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).</span><span class="sxs-lookup"><span data-stu-id="6372e-119">For more information, see [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

## <a name="affected-apis"></a><span data-ttu-id="6372e-120">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="6372e-120">Affected APIs</span></span>

<span data-ttu-id="6372e-121">Nie wykrywalne za pośrednictwem analizy interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="6372e-121">Not detectable via API analysis.</span></span>

<!--

### Affected APIs

Not detectable via API analysis.

### Category

Code analysis

-->
