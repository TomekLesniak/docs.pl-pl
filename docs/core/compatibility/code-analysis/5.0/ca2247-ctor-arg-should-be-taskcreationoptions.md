---
title: 'Nieprzerwana zmiana: CA2247: argument konstruktora TaskCompletionSource powinien być wartością opcji TaskCreationOptions'
description: Zapoznaj się z nieprzerwaną zmianą w programie .NET 5,0 spowodowaną przez włączenie reguły analizy kodu CA2247.
ms.date: 09/03/2020
ms.openlocfilehash: 323fd5a05da4dfeb68ef75d88d5d293ba01c8ade
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761535"
---
# <a name="warning-ca2247-argument-to-taskcompletionsource-constructor-should-be-taskcreationoptions-value"></a><span data-ttu-id="322f1-103">Ostrzeżenie CA2247: argument konstruktora TaskCompletionSource powinien być wartością opcji TaskCreationOptions</span><span class="sxs-lookup"><span data-stu-id="322f1-103">Warning CA2247: Argument to TaskCompletionSource constructor should be TaskCreationOptions value</span></span>

<span data-ttu-id="322f1-104">Reguła analizatora kodu platformy .NET [CA2247](/visualstudio/code-quality/ca2247) jest domyślnie włączona, począwszy od platformy .NET 5,0.</span><span class="sxs-lookup"><span data-stu-id="322f1-104">.NET code analyzer rule [CA2247](/visualstudio/code-quality/ca2247) is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="322f1-105">Generuje ostrzeżenie kompilacji dla wywołań <xref:System.Threading.Tasks.TaskCompletionSource%601> konstruktora, który przekazuje argument typu <xref:System.Threading.Tasks.TaskContinuationOptions> .</span><span class="sxs-lookup"><span data-stu-id="322f1-105">It produces a build warning for calls to the <xref:System.Threading.Tasks.TaskCompletionSource%601> constructor that pass an argument of type <xref:System.Threading.Tasks.TaskContinuationOptions>.</span></span>

## <a name="change-description"></a><span data-ttu-id="322f1-106">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="322f1-106">Change description</span></span>

<span data-ttu-id="322f1-107">Począwszy od platformy .NET 5,0, zestaw SDK .NET zawiera [analizatory kodu źródłowego platformy .NET](../../../../fundamentals/code-analysis/overview.md).</span><span class="sxs-lookup"><span data-stu-id="322f1-107">Starting in .NET 5.0, the .NET SDK includes [.NET source code analyzers](../../../../fundamentals/code-analysis/overview.md).</span></span> <span data-ttu-id="322f1-108">Niektóre z tych reguł są domyślnie włączone, w tym [CA2247](/visualstudio/code-quality/ca2247).</span><span class="sxs-lookup"><span data-stu-id="322f1-108">Several of these rules are enabled, by default, including [CA2247](/visualstudio/code-quality/ca2247).</span></span> <span data-ttu-id="322f1-109">Jeśli projekt zawiera kod naruszający tę regułę i jest skonfigurowany do traktowania ostrzeżeń jako błędów, ta zmiana może spowodować uszkodzenie kompilacji.</span><span class="sxs-lookup"><span data-stu-id="322f1-109">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span>

<span data-ttu-id="322f1-110">CA2247 reguły odnajduje wywołania <xref:System.Threading.Tasks.TaskCompletionSource%601> konstruktora, które przekazują argument typu <xref:System.Threading.Tasks.TaskContinuationOptions> .</span><span class="sxs-lookup"><span data-stu-id="322f1-110">Rule CA2247 finds calls to the <xref:System.Threading.Tasks.TaskCompletionSource%601> constructor that pass an argument of type <xref:System.Threading.Tasks.TaskContinuationOptions>.</span></span> <span data-ttu-id="322f1-111"><xref:System.Threading.Tasks.TaskCompletionSource%601>Typ ma konstruktora, który akceptuje <xref:System.Threading.Tasks.TaskCreationOptions> wartość i inny Konstruktor akceptujący <xref:System.Object> .</span><span class="sxs-lookup"><span data-stu-id="322f1-111">The <xref:System.Threading.Tasks.TaskCompletionSource%601> type has a constructor that accepts a <xref:System.Threading.Tasks.TaskCreationOptions> value, and another constructor that accepts an <xref:System.Object>.</span></span> <span data-ttu-id="322f1-112">Jeśli przypadkowo przeszedł <xref:System.Threading.Tasks.TaskContinuationOptions> wartość zamiast <xref:System.Threading.Tasks.TaskCreationOptions> wartości, Konstruktor z <xref:System.Object> parametrem jest wywoływany w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="322f1-112">If you accidentally pass a <xref:System.Threading.Tasks.TaskContinuationOptions> value instead of a <xref:System.Threading.Tasks.TaskCreationOptions> value, the constructor with the <xref:System.Object> parameter is called at run time.</span></span> <span data-ttu-id="322f1-113">Kod zostanie skompilowany i uruchomiony, ale nie będzie miał zamierzonego zachowania.</span><span class="sxs-lookup"><span data-stu-id="322f1-113">Your code will compile and run but won't have the intended behavior.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="322f1-114">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="322f1-114">Version introduced</span></span>

<span data-ttu-id="322f1-115">5,0</span><span class="sxs-lookup"><span data-stu-id="322f1-115">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="322f1-116">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="322f1-116">Recommended action</span></span>

- <span data-ttu-id="322f1-117">Zamień <xref:System.Threading.Tasks.TaskContinuationOptions> argument na odpowiadającą <xref:System.Threading.Tasks.TaskCreationOptions> wartość.</span><span class="sxs-lookup"><span data-stu-id="322f1-117">Replace the <xref:System.Threading.Tasks.TaskContinuationOptions> argument with the corresponding <xref:System.Threading.Tasks.TaskCreationOptions> value.</span></span> <span data-ttu-id="322f1-118">Nie pomijaj tego ostrzeżenia, ponieważ prawie zawsze wyróżnia usterkę w kodzie.</span><span class="sxs-lookup"><span data-stu-id="322f1-118">Do not suppress this warning, since it almost always highlights a bug in your code.</span></span> <span data-ttu-id="322f1-119">Aby uzyskać więcej informacji, zobacz [CA2247](/visualstudio/code-quality/ca2247).</span><span class="sxs-lookup"><span data-stu-id="322f1-119">For more information, see [CA2247](/visualstudio/code-quality/ca2247).</span></span>

- <span data-ttu-id="322f1-120">Aby całkowicie wyłączyć analizę kodu, ustaw `EnableNETAnalyzers` wartość `false` w pliku projektu.</span><span class="sxs-lookup"><span data-stu-id="322f1-120">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="322f1-121">Aby uzyskać więcej informacji, zobacz [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).</span><span class="sxs-lookup"><span data-stu-id="322f1-121">For more information, see [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

## <a name="affected-apis"></a><span data-ttu-id="322f1-122">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="322f1-122">Affected APIs</span></span>

- <xref:System.Threading.Tasks.TaskCompletionSource%601.%23ctor(System.Object)>

<!--

### Affected APIs

- ``M:System.Threading.Tasks.TaskCompletionSource`1.#ctor(System.Object)``

### Category

Code analysis

-->
