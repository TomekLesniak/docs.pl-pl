---
title: Zmiany w analizie kodu
description: Wyświetla listę istotnych zmian w analizatorach kodu źródłowego platformy .NET.
ms.date: 09/02/2020
ms.openlocfilehash: 3cbe2ecf5d08084db542db0c2da016f1f391452e
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90538929"
---
# <a name="code-analysis-breaking-changes"></a><span data-ttu-id="b908c-103">Zmiany w analizie kodu</span><span class="sxs-lookup"><span data-stu-id="b908c-103">Code analysis breaking changes</span></span>

<span data-ttu-id="b908c-104">Następujące istotne zmiany zostały udokumentowane na tej stronie:</span><span class="sxs-lookup"><span data-stu-id="b908c-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="b908c-105">Zmiana podziału</span><span class="sxs-lookup"><span data-stu-id="b908c-105">Breaking change</span></span> | <span data-ttu-id="b908c-106">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="b908c-106">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="b908c-107">CA1416: zgodność platformy</span><span class="sxs-lookup"><span data-stu-id="b908c-107">CA1416: Platform compatibility</span></span>](#ca1416-platform-compatibility) | <span data-ttu-id="b908c-108">5,0</span><span class="sxs-lookup"><span data-stu-id="b908c-108">5.0</span></span> |
| [<span data-ttu-id="b908c-109">CA1417: atrybut unattribute dla parametru String dla elementu P/Invoke</span><span class="sxs-lookup"><span data-stu-id="b908c-109">CA1417: OutAttribute on string parameter for P/Invoke</span></span>](#ca1417-outattribute-on-string-parameter-for-pinvoke) | <span data-ttu-id="b908c-110">5,0</span><span class="sxs-lookup"><span data-stu-id="b908c-110">5.0</span></span> |
| [<span data-ttu-id="b908c-111">CA1831: Użyj AsSpan zamiast indeksatorów opartych na zakresie dla ciągu</span><span class="sxs-lookup"><span data-stu-id="b908c-111">CA1831: Use AsSpan instead of Range-based indexers for string</span></span>](#ca1831-use-asspan-instead-of-range-based-indexers-for-string) | <span data-ttu-id="b908c-112">5,0</span><span class="sxs-lookup"><span data-stu-id="b908c-112">5.0</span></span> |
| [<span data-ttu-id="b908c-113">CA2013: Nie używaj metody ReferenceEquals z typami wartości</span><span class="sxs-lookup"><span data-stu-id="b908c-113">CA2013: Do not use ReferenceEquals with value types</span></span>](#ca2013-do-not-use-referenceequals-with-value-types) | <span data-ttu-id="b908c-114">5,0</span><span class="sxs-lookup"><span data-stu-id="b908c-114">5.0</span></span> |
| [<span data-ttu-id="b908c-115">CA2014: Nie używaj słowa kluczowego stackalloc w pętlach</span><span class="sxs-lookup"><span data-stu-id="b908c-115">CA2014: Do not use stackalloc in loops</span></span>](#ca2014-do-not-use-stackalloc-in-loops) | <span data-ttu-id="b908c-116">5,0</span><span class="sxs-lookup"><span data-stu-id="b908c-116">5.0</span></span> |
| [<span data-ttu-id="b908c-117">CA2015: nie Definiuj finalizatorów dla typów pochodnych z pamięci\<T></span><span class="sxs-lookup"><span data-stu-id="b908c-117">CA2015: Do not define finalizers for types derived from MemoryManager\<T></span></span>](#ca2015-do-not-define-finalizers-for-types-derived-from-memorymanagert) | <span data-ttu-id="b908c-118">5,0</span><span class="sxs-lookup"><span data-stu-id="b908c-118">5.0</span></span> |
| [<span data-ttu-id="b908c-119">CA2200: Ponowie zgłoś wyjątek, aby zachować szczegóły stosu</span><span class="sxs-lookup"><span data-stu-id="b908c-119">CA2200: Rethrow to preserve stack details</span></span>](#ca2200-rethrow-to-preserve-stack-details) | <span data-ttu-id="b908c-120">5,0</span><span class="sxs-lookup"><span data-stu-id="b908c-120">5.0</span></span> |
| [<span data-ttu-id="b908c-121">CA2247: argumentem konstruktora TaskCompletionSource powinien być wartość opcji TaskCreationOptions</span><span class="sxs-lookup"><span data-stu-id="b908c-121">CA2247: Argument to TaskCompletionSource constructor should be TaskCreationOptions value</span></span>](#ca2247-argument-to-taskcompletionsource-constructor-should-be-taskcreationoptions-value) | <span data-ttu-id="b908c-122">5,0</span><span class="sxs-lookup"><span data-stu-id="b908c-122">5.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="b908c-123">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="b908c-123">.NET 5.0</span></span>

[!INCLUDE [ca1416-platform-compatibility-analyzer](../../../includes/core-changes/codeanalysis/5.0/ca1416-platform-compatibility-analyzer.md)]

***

[!INCLUDE [outattributes-on-pinvoke-string-parameters](../../../includes/core-changes/codeanalysis/5.0/ca1417-outattributes-on-pinvoke-string-parameters.md)]

***

[!INCLUDE [range-based-indexer-on-string](../../../includes/core-changes/codeanalysis/5.0/ca1831-range-based-indexer-on-string.md)]

***

[!INCLUDE [referenceequals-on-value-types](../../../includes/core-changes/codeanalysis/5.0/ca2013-referenceequals-on-value-types.md)]

***

[!INCLUDE [stackalloc-in-loops](../../../includes/core-changes/codeanalysis/5.0/ca2014-stackalloc-in-loops.md)]

***

[!INCLUDE [finalizers-for-memorymanager-types](../../../includes/core-changes/codeanalysis/5.0/ca2015-finalizers-for-memorymanager-types.md)]

***

[!INCLUDE [ca2200-rethrow-to-preserve-stack-details](../../../includes/core-changes/codeanalysis/5.0/ca2200-rethrow-to-preserve-stack-details.md)]

***

[!INCLUDE [ctor-arg-should-be-taskcreationoptions](../../../includes/core-changes/codeanalysis/5.0/ca2247-ctor-arg-should-be-taskcreationoptions.md)]

***
