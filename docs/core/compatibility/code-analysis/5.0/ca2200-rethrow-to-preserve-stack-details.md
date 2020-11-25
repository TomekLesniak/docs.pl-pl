---
title: 'Zmiana podziału: CA2200: ponownie zgłoś, aby zachować szczegóły stosu'
description: Zapoznaj się z nieprzerwaną zmianą w programie .NET 5,0 spowodowaną przez włączenie reguły analizy kodu CA2200.
ms.date: 09/03/2020
ms.openlocfilehash: 74e169906a8b826328de8d4c5f69c32234c2ce95
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761532"
---
# <a name="warning-ca2200-rethrow-to-preserve-stack-details"></a><span data-ttu-id="ec5c0-103">Ostrzeżenie CA2200: ponownie zgłoś, aby zachować szczegóły stosu</span><span class="sxs-lookup"><span data-stu-id="ec5c0-103">Warning CA2200: Rethrow to preserve stack details</span></span>

<span data-ttu-id="ec5c0-104">Reguła analizatora kodu platformy .NET [CA2200](/visualstudio/code-quality/ca2200) jest domyślnie włączona, począwszy od platformy .NET 5,0.</span><span class="sxs-lookup"><span data-stu-id="ec5c0-104">.NET code analyzer rule [CA2200](/visualstudio/code-quality/ca2200) is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="ec5c0-105">Generuje ostrzeżenie kompilacji dla wszystkich `catch` bloków, które ponownie generują wyjątek, a wyjątek jest jawnie określony w `throw` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="ec5c0-105">It produces a build warning for any `catch` blocks that rethrow an exception and the exception is explicitly specified in the `throw` statement.</span></span>

## <a name="change-description"></a><span data-ttu-id="ec5c0-106">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="ec5c0-106">Change description</span></span>

<span data-ttu-id="ec5c0-107">Począwszy od platformy .NET 5,0, zestaw SDK .NET zawiera [analizatory kodu źródłowego platformy .NET](../../../../fundamentals/code-analysis/overview.md).</span><span class="sxs-lookup"><span data-stu-id="ec5c0-107">Starting in .NET 5.0, the .NET SDK includes [.NET source code analyzers](../../../../fundamentals/code-analysis/overview.md).</span></span> <span data-ttu-id="ec5c0-108">Niektóre z tych reguł są domyślnie włączone, w tym [CA2200](/visualstudio/code-quality/ca2200).</span><span class="sxs-lookup"><span data-stu-id="ec5c0-108">Several of these rules are enabled, by default, including [CA2200](/visualstudio/code-quality/ca2200).</span></span> <span data-ttu-id="ec5c0-109">Jeśli projekt zawiera kod naruszający tę regułę i jest skonfigurowany do traktowania ostrzeżeń jako błędów, ta zmiana może spowodować uszkodzenie kompilacji.</span><span class="sxs-lookup"><span data-stu-id="ec5c0-109">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span>

<span data-ttu-id="ec5c0-110">Reguła CA2200 flagi kodu, w którym wyjątki są ponownie zgłaszane i zmienna wyjątku została określona w `throw` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="ec5c0-110">Rule CA2200 flags code where exceptions are rethrown and the exception variable is specified in the `throw` statement.</span></span> <span data-ttu-id="ec5c0-111">Gdy wyjątek jest zgłaszany, część informacji, którą wykonuje, jest śladem stosu.</span><span class="sxs-lookup"><span data-stu-id="ec5c0-111">When an exception is thrown, part of the information it carries is the stack trace.</span></span> <span data-ttu-id="ec5c0-112">Ślad stosu jest listą hierarchii wywołań metody, która rozpoczyna się od metody, która zgłasza wyjątek i kończą się metodą, która przechwytuje wyjątek.</span><span class="sxs-lookup"><span data-stu-id="ec5c0-112">The stack trace is a list of the method call hierarchy that starts with the method that throws the exception and ends with the method that catches the exception.</span></span> <span data-ttu-id="ec5c0-113">Jeśli wyjątek jest zgłaszany ponownie przez określenie wyjątku w `throw` instrukcji, ślad stosu zostanie uruchomiony w bieżącej metodzie, a lista wywołań metod między oryginalną metodą, która wywołała wyjątek, a bieżąca metoda zostanie utracona.</span><span class="sxs-lookup"><span data-stu-id="ec5c0-113">If an exception is rethrown by specifying the exception in the `throw` statement, the stack trace restarts at the current method and the list of method calls between the original method that threw the exception and the current method is lost.</span></span> <span data-ttu-id="ec5c0-114">Aby zachować oryginalne informacje śledzenia stosu z wyjątkiem, należy użyć `throw` instrukcji bez określenia wyjątku.</span><span class="sxs-lookup"><span data-stu-id="ec5c0-114">To keep the original stack trace information with the exception, use the `throw` statement without specifying the exception.</span></span>

<span data-ttu-id="ec5c0-115">Poniższy fragment kodu nie tworzy ostrzeżenia dla reguły CA2200.</span><span class="sxs-lookup"><span data-stu-id="ec5c0-115">The following code snippet does not produce a warning for rule CA2200.</span></span> <span data-ttu-id="ec5c0-116">Jednak *wiersz z* komentarzem wywoła naruszenie.</span><span class="sxs-lookup"><span data-stu-id="ec5c0-116">The commented line *would* trigger a violation, however.</span></span>

```csharp
catch (ArithmeticException e)
{
    // throw e;
    throw;
}
```

## <a name="version-introduced"></a><span data-ttu-id="ec5c0-117">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="ec5c0-117">Version introduced</span></span>

<span data-ttu-id="ec5c0-118">5,0</span><span class="sxs-lookup"><span data-stu-id="ec5c0-118">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="ec5c0-119">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="ec5c0-119">Recommended action</span></span>

- <span data-ttu-id="ec5c0-120">Ponownie zgłoś wyjątki bez określania wyjątku jawnie.</span><span class="sxs-lookup"><span data-stu-id="ec5c0-120">Rethrow exceptions without specifying the exception explicitly.</span></span> <span data-ttu-id="ec5c0-121">Aby uzyskać więcej informacji, zobacz [CA2200](/visualstudio/code-quality/ca2200).</span><span class="sxs-lookup"><span data-stu-id="ec5c0-121">For more information, see [CA2200](/visualstudio/code-quality/ca2200).</span></span>

- <span data-ttu-id="ec5c0-122">Aby całkowicie wyłączyć analizę kodu, ustaw `EnableNETAnalyzers` wartość `false` w pliku projektu.</span><span class="sxs-lookup"><span data-stu-id="ec5c0-122">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="ec5c0-123">Aby uzyskać więcej informacji, zobacz [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).</span><span class="sxs-lookup"><span data-stu-id="ec5c0-123">For more information, see [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

## <a name="affected-apis"></a><span data-ttu-id="ec5c0-124">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="ec5c0-124">Affected APIs</span></span>

<span data-ttu-id="ec5c0-125">Nie wykrywalne za pośrednictwem analizy interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="ec5c0-125">Not detectable via API analysis.</span></span>

<!--

### Affected APIs

Not detectable via API analysis.

### Category

Code analysis

-->
