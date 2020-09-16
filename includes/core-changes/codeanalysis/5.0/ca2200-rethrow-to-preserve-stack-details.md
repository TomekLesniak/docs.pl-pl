---
ms.openlocfilehash: b697bbf6844759de8babd4245667e7b333884ff8
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90538930"
---
### <a name="ca2200-rethrow-to-preserve-stack-details"></a><span data-ttu-id="a05bd-101">CA2200: Ponowie zgłoś wyjątek, aby zachować szczegóły stosu</span><span class="sxs-lookup"><span data-stu-id="a05bd-101">CA2200: Rethrow to preserve stack details</span></span>

<span data-ttu-id="a05bd-102">Reguła analizatora kodu platformy .NET [CA2200](/visualstudio/code-quality/ca2200) jest domyślnie włączona, począwszy od platformy .NET 5,0.</span><span class="sxs-lookup"><span data-stu-id="a05bd-102">.NET code analyzer rule [CA2200](/visualstudio/code-quality/ca2200) is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="a05bd-103">Generuje ostrzeżenie kompilacji dla wszystkich `catch` bloków, które ponownie generują wyjątek, a wyjątek jest jawnie określony w `throw` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="a05bd-103">It produces a build warning for any `catch` blocks that rethrow an exception and the exception is explicitly specified in the `throw` statement.</span></span>

#### <a name="change-description"></a><span data-ttu-id="a05bd-104">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="a05bd-104">Change description</span></span>

<span data-ttu-id="a05bd-105">Począwszy od platformy .NET 5,0, zestaw SDK .NET zawiera [analizatory kodu źródłowego platformy .NET](../../../../docs/fundamentals/productivity/code-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="a05bd-105">Starting in .NET 5.0, the .NET SDK includes [.NET source code analyzers](../../../../docs/fundamentals/productivity/code-analysis.md).</span></span> <span data-ttu-id="a05bd-106">Niektóre z tych reguł są domyślnie włączone, w tym [CA2200](/visualstudio/code-quality/ca2200).</span><span class="sxs-lookup"><span data-stu-id="a05bd-106">Several of these rules are enabled, by default, including [CA2200](/visualstudio/code-quality/ca2200).</span></span> <span data-ttu-id="a05bd-107">Jeśli projekt zawiera kod naruszający tę regułę i jest skonfigurowany do traktowania ostrzeżeń jako błędów, ta zmiana może spowodować uszkodzenie kompilacji.</span><span class="sxs-lookup"><span data-stu-id="a05bd-107">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span>

<span data-ttu-id="a05bd-108">Reguła CA2200 flagi kodu, w którym wyjątki są ponownie zgłaszane i zmienna wyjątku została określona w `throw` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="a05bd-108">Rule CA2200 flags code where exceptions are rethrown and the exception variable is specified in the `throw` statement.</span></span> <span data-ttu-id="a05bd-109">Gdy wyjątek jest zgłaszany, część informacji, którą wykonuje, jest śladem stosu.</span><span class="sxs-lookup"><span data-stu-id="a05bd-109">When an exception is thrown, part of the information it carries is the stack trace.</span></span> <span data-ttu-id="a05bd-110">Ślad stosu jest listą hierarchii wywołań metody, która rozpoczyna się od metody, która zgłasza wyjątek i kończą się metodą, która przechwytuje wyjątek.</span><span class="sxs-lookup"><span data-stu-id="a05bd-110">The stack trace is a list of the method call hierarchy that starts with the method that throws the exception and ends with the method that catches the exception.</span></span> <span data-ttu-id="a05bd-111">Jeśli wyjątek jest zgłaszany ponownie przez określenie wyjątku w `throw` instrukcji, ślad stosu zostanie uruchomiony w bieżącej metodzie, a lista wywołań metod między oryginalną metodą, która wywołała wyjątek, a bieżąca metoda zostanie utracona.</span><span class="sxs-lookup"><span data-stu-id="a05bd-111">If an exception is rethrown by specifying the exception in the `throw` statement, the stack trace restarts at the current method and the list of method calls between the original method that threw the exception and the current method is lost.</span></span> <span data-ttu-id="a05bd-112">Aby zachować oryginalne informacje śledzenia stosu z wyjątkiem, należy użyć `throw` instrukcji bez określenia wyjątku.</span><span class="sxs-lookup"><span data-stu-id="a05bd-112">To keep the original stack trace information with the exception, use the `throw` statement without specifying the exception.</span></span>

<span data-ttu-id="a05bd-113">Poniższy fragment kodu nie tworzy ostrzeżenia dla reguły CA2200.</span><span class="sxs-lookup"><span data-stu-id="a05bd-113">The following code snippet does not produce a warning for rule CA2200.</span></span> <span data-ttu-id="a05bd-114">Jednak *wiersz z* komentarzem wywoła naruszenie.</span><span class="sxs-lookup"><span data-stu-id="a05bd-114">The commented line *would* trigger a violation, however.</span></span>

```csharp
catch (ArithmeticException e)
{
    // throw e;
    throw;
}
```

#### <a name="version-introduced"></a><span data-ttu-id="a05bd-115">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="a05bd-115">Version introduced</span></span>

<span data-ttu-id="a05bd-116">5,0 RC1</span><span class="sxs-lookup"><span data-stu-id="a05bd-116">5.0 RC1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="a05bd-117">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="a05bd-117">Recommended action</span></span>

- <span data-ttu-id="a05bd-118">Ponownie zgłoś wyjątki bez określania wyjątku jawnie.</span><span class="sxs-lookup"><span data-stu-id="a05bd-118">Rethrow exceptions without specifying the exception explicitly.</span></span> <span data-ttu-id="a05bd-119">Aby uzyskać więcej informacji, zobacz [CA2200](/visualstudio/code-quality/ca2200).</span><span class="sxs-lookup"><span data-stu-id="a05bd-119">For more information, see [CA2200](/visualstudio/code-quality/ca2200).</span></span>

- <span data-ttu-id="a05bd-120">Aby całkowicie wyłączyć analizę kodu, ustaw `EnableNETAnalyzers` wartość `false` w pliku projektu.</span><span class="sxs-lookup"><span data-stu-id="a05bd-120">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="a05bd-121">Aby uzyskać więcej informacji, zobacz [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).</span><span class="sxs-lookup"><span data-stu-id="a05bd-121">For more information, see [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

#### <a name="category"></a><span data-ttu-id="a05bd-122">Kategoria</span><span class="sxs-lookup"><span data-stu-id="a05bd-122">Category</span></span>

<span data-ttu-id="a05bd-123">Analiza kodu</span><span class="sxs-lookup"><span data-stu-id="a05bd-123">Code analysis</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="a05bd-124">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="a05bd-124">Affected APIs</span></span>

<span data-ttu-id="a05bd-125">Nie wykrywalne za pośrednictwem analizy interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="a05bd-125">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
