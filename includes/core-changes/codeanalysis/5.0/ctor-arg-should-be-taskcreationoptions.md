---
ms.openlocfilehash: 6bb3b11ef4e4cb6f6a039c97911b0acca862fe6f
ms.sourcegitcommit: e7acba36517134238065e4d50bb4a1cfe47ebd06
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/04/2020
ms.locfileid: "89465591"
---
### <a name="ca2247-argument-to-taskcompletionsource-constructor-should-be-taskcreationoptions-value"></a><span data-ttu-id="c82e4-101">CA2247: argumentem konstruktora TaskCompletionSource powinien być wartość opcji TaskCreationOptions</span><span class="sxs-lookup"><span data-stu-id="c82e4-101">CA2247: Argument to TaskCompletionSource constructor should be TaskCreationOptions value</span></span>

<span data-ttu-id="c82e4-102">Reguła analizatora kodu platformy .NET [CA2247](/visualstudio/code-quality/ca2247) jest domyślnie włączona, począwszy od platformy .NET 5,0.</span><span class="sxs-lookup"><span data-stu-id="c82e4-102">.NET code analyzer rule [CA2247](/visualstudio/code-quality/ca2247) is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="c82e4-103">Generuje ostrzeżenie kompilacji dla wywołań <xref:System.Threading.Tasks.TaskCompletionSource%601> konstruktora, który przekazuje argument typu <xref:System.Threading.Tasks.TaskContinuationOptions> .</span><span class="sxs-lookup"><span data-stu-id="c82e4-103">It produces a build warning for calls to the <xref:System.Threading.Tasks.TaskCompletionSource%601> constructor that pass an argument of type <xref:System.Threading.Tasks.TaskContinuationOptions>.</span></span>

#### <a name="change-description"></a><span data-ttu-id="c82e4-104">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="c82e4-104">Change description</span></span>

<span data-ttu-id="c82e4-105">Począwszy od platformy .NET 5,0, zestaw SDK .NET zawiera [analizatory kodu źródłowego platformy .NET](../../../../docs/fundamentals/productivity/code-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="c82e4-105">Starting in .NET 5.0, the .NET SDK includes [.NET source code analyzers](../../../../docs/fundamentals/productivity/code-analysis.md).</span></span> <span data-ttu-id="c82e4-106">Niektóre z tych reguł są domyślnie włączone, w tym [CA2247](/visualstudio/code-quality/ca2247).</span><span class="sxs-lookup"><span data-stu-id="c82e4-106">Several of these rules are enabled, by default, including [CA2247](/visualstudio/code-quality/ca2247).</span></span> <span data-ttu-id="c82e4-107">Jeśli projekt zawiera kod naruszający tę regułę i jest skonfigurowany do traktowania ostrzeżeń jako błędów, ta zmiana może spowodować uszkodzenie kompilacji.</span><span class="sxs-lookup"><span data-stu-id="c82e4-107">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span>

<span data-ttu-id="c82e4-108">CA2247 reguły odnajduje wywołania <xref:System.Threading.Tasks.TaskCompletionSource%601> konstruktora, które przekazują argument typu <xref:System.Threading.Tasks.TaskContinuationOptions> .</span><span class="sxs-lookup"><span data-stu-id="c82e4-108">Rule CA2247 finds calls to the <xref:System.Threading.Tasks.TaskCompletionSource%601> constructor that pass an argument of type <xref:System.Threading.Tasks.TaskContinuationOptions>.</span></span> <span data-ttu-id="c82e4-109"><xref:System.Threading.Tasks.TaskCompletionSource%601>Typ ma konstruktora, który akceptuje <xref:System.Threading.Tasks.TaskCreationOptions> wartość i inny Konstruktor akceptujący <xref:System.Object> .</span><span class="sxs-lookup"><span data-stu-id="c82e4-109">The <xref:System.Threading.Tasks.TaskCompletionSource%601> type has a constructor that accepts a <xref:System.Threading.Tasks.TaskCreationOptions> value, and another constructor that accepts an <xref:System.Object>.</span></span> <span data-ttu-id="c82e4-110">Jeśli przypadkowo przeszedł <xref:System.Threading.Tasks.TaskContinuationOptions> wartość zamiast <xref:System.Threading.Tasks.TaskCreationOptions> wartości, Konstruktor z <xref:System.Object> parametrem jest wywoływany w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="c82e4-110">If you accidentally pass a <xref:System.Threading.Tasks.TaskContinuationOptions> value instead of a <xref:System.Threading.Tasks.TaskCreationOptions> value, the constructor with the <xref:System.Object> parameter is called at run time.</span></span> <span data-ttu-id="c82e4-111">Kod zostanie skompilowany i uruchomiony, ale nie będzie miał zamierzonego zachowania.</span><span class="sxs-lookup"><span data-stu-id="c82e4-111">Your code will compile and run but won't have the intended behavior.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="c82e4-112">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="c82e4-112">Version introduced</span></span>

<span data-ttu-id="c82e4-113">5,0 wersja zapoznawcza 8</span><span class="sxs-lookup"><span data-stu-id="c82e4-113">5.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="c82e4-114">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="c82e4-114">Recommended action</span></span>

- <span data-ttu-id="c82e4-115">Zamień <xref:System.Threading.Tasks.TaskContinuationOptions> argument na odpowiadającą <xref:System.Threading.Tasks.TaskCreationOptions> wartość.</span><span class="sxs-lookup"><span data-stu-id="c82e4-115">Replace the <xref:System.Threading.Tasks.TaskContinuationOptions> argument with the corresponding <xref:System.Threading.Tasks.TaskCreationOptions> value.</span></span> <span data-ttu-id="c82e4-116">Nie pomijaj tego ostrzeżenia, ponieważ prawie zawsze wyróżnia usterkę w kodzie.</span><span class="sxs-lookup"><span data-stu-id="c82e4-116">Do not suppress this warning, since it almost always highlights a bug in your code.</span></span> <span data-ttu-id="c82e4-117">Aby uzyskać więcej informacji, zobacz [CA2247](/visualstudio/code-quality/ca2247).</span><span class="sxs-lookup"><span data-stu-id="c82e4-117">For more information, see [CA2247](/visualstudio/code-quality/ca2247).</span></span>

- <span data-ttu-id="c82e4-118">Aby całkowicie wyłączyć analizę kodu, ustaw `EnableNETAnalyzers` wartość `false` w pliku projektu.</span><span class="sxs-lookup"><span data-stu-id="c82e4-118">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="c82e4-119">Aby uzyskać więcej informacji, zobacz [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).</span><span class="sxs-lookup"><span data-stu-id="c82e4-119">For more information, see [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

#### <a name="category"></a><span data-ttu-id="c82e4-120">Kategoria</span><span class="sxs-lookup"><span data-stu-id="c82e4-120">Category</span></span>

<span data-ttu-id="c82e4-121">Analiza kodu</span><span class="sxs-lookup"><span data-stu-id="c82e4-121">Code analysis</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="c82e4-122">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="c82e4-122">Affected APIs</span></span>

- <xref:System.Threading.Tasks.TaskCompletionSource%601.%23ctor(System.Object)>

<!--

#### Affected APIs

- ``M:System.Threading.Tasks.TaskCompletionSource`1.#ctor(System.Object)``

-->
