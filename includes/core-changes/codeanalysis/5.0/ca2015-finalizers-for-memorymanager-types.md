---
ms.openlocfilehash: 4fc31f75e8f8cdd50abebd399d9749688e6faa5a
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065177"
---
### <a name="ca2015-do-not-define-finalizers-for-types-derived-from-memorymanagert"></a><span data-ttu-id="83041-101">CA2015: Nie definiuj finalizatorów dla typów pochodzących od typu MemoryManager\<T></span><span class="sxs-lookup"><span data-stu-id="83041-101">CA2015: Do not define finalizers for types derived from MemoryManager\<T></span></span>

<span data-ttu-id="83041-102">Reguła analizatora kodu platformy .NET [CA2015](/visualstudio/code-quality/ca2015) jest domyślnie włączona, począwszy od platformy .NET 5,0.</span><span class="sxs-lookup"><span data-stu-id="83041-102">.NET code analyzer rule [CA2015](/visualstudio/code-quality/ca2015) is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="83041-103">Generuje ostrzeżenie kompilacji dla dowolnego typu, który pochodzi od <xref:System.Buffers.MemoryManager%601> , który definiuje finalizator.</span><span class="sxs-lookup"><span data-stu-id="83041-103">It produces a build warning for any types that derive from <xref:System.Buffers.MemoryManager%601> that define a finalizer.</span></span>

#### <a name="change-description"></a><span data-ttu-id="83041-104">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="83041-104">Change description</span></span>

<span data-ttu-id="83041-105">Począwszy od platformy .NET 5,0, zestaw SDK .NET zawiera [analizatory kodu źródłowego platformy .NET](../../../../docs/fundamentals/productivity/code-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="83041-105">Starting in .NET 5.0, the .NET SDK includes [.NET source code analyzers](../../../../docs/fundamentals/productivity/code-analysis.md).</span></span> <span data-ttu-id="83041-106">Niektóre z tych reguł są domyślnie włączone, w tym [CA2015](/visualstudio/code-quality/ca2015).</span><span class="sxs-lookup"><span data-stu-id="83041-106">Several of these rules are enabled, by default, including [CA2015](/visualstudio/code-quality/ca2015).</span></span> <span data-ttu-id="83041-107">Jeśli projekt zawiera kod naruszający tę regułę i jest skonfigurowany do traktowania ostrzeżeń jako błędów, ta zmiana może spowodować uszkodzenie kompilacji.</span><span class="sxs-lookup"><span data-stu-id="83041-107">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span>

<span data-ttu-id="83041-108">Reguły CA2015 typy flag, które pochodzą od <xref:System.Buffers.MemoryManager%601> elementu, który definiuje finalizator.</span><span class="sxs-lookup"><span data-stu-id="83041-108">Rule CA2015 flags types that derive from <xref:System.Buffers.MemoryManager%601> that define a finalizer.</span></span> <span data-ttu-id="83041-109">Dodanie finalizatora do typu, który pochodzi od, <xref:System.Buffers.MemoryManager%601> prawdopodobnie wskazuje na błąd.</span><span class="sxs-lookup"><span data-stu-id="83041-109">Adding a finalizer to a type that derives from <xref:System.Buffers.MemoryManager%601> is likely an indication of a bug.</span></span> <span data-ttu-id="83041-110">Sugeruje to, że zasób natywny, który mógł zostać uzyskany w <xref:System.Span%601> trakcie, jest wyczyszczony, prawdopodobnie w czasie, gdy jest nadal używany przez <xref:System.Span%601> .</span><span class="sxs-lookup"><span data-stu-id="83041-110">It suggests that a native resource that could have been obtained in a <xref:System.Span%601> is getting cleaned up, potentially while it's still in use by the <xref:System.Span%601>.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="83041-111">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="83041-111">Version introduced</span></span>

<span data-ttu-id="83041-112">5,0 wersja zapoznawcza 8</span><span class="sxs-lookup"><span data-stu-id="83041-112">5.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="83041-113">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="83041-113">Recommended action</span></span>

- <span data-ttu-id="83041-114">Usuń definicję finalizatora.</span><span class="sxs-lookup"><span data-stu-id="83041-114">Remove the finalizer definition.</span></span> <span data-ttu-id="83041-115">Aby uzyskać więcej informacji, zobacz [CA2015](/visualstudio/code-quality/ca2015).</span><span class="sxs-lookup"><span data-stu-id="83041-115">For more information, see [CA2015](/visualstudio/code-quality/ca2015).</span></span>

- <span data-ttu-id="83041-116">Aby całkowicie wyłączyć analizę kodu, ustaw `EnableNETAnalyzers` wartość `false` w pliku projektu.</span><span class="sxs-lookup"><span data-stu-id="83041-116">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="83041-117">Aby uzyskać więcej informacji, zobacz [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).</span><span class="sxs-lookup"><span data-stu-id="83041-117">For more information, see [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

#### <a name="category"></a><span data-ttu-id="83041-118">Kategoria</span><span class="sxs-lookup"><span data-stu-id="83041-118">Category</span></span>

<span data-ttu-id="83041-119">Analiza kodu</span><span class="sxs-lookup"><span data-stu-id="83041-119">Code analysis</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="83041-120">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="83041-120">Affected APIs</span></span>

<span data-ttu-id="83041-121">Nie wykrywalne za pośrednictwem analizy interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="83041-121">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
