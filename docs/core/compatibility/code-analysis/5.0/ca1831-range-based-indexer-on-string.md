---
title: 'Nieprzerwana zmiana: CA1831: Użyj AsSpan zamiast indeksatorów opartych na zakresie dla ciągu'
description: Zapoznaj się z nieprzerwaną zmianą w programie .NET 5,0 spowodowaną przez włączenie reguły analizy kodu CA1831.
ms.date: 08/21/2020
ms.openlocfilehash: 74f34af04a56b73478ffb3305d69ed49f3a30072
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761331"
---
# <a name="warning-ca1831-use-asspan-instead-of-range-based-indexers-for-string"></a><span data-ttu-id="436ad-103">Ostrzeżenie CA1831: Użyj AsSpan zamiast indeksatorów opartych na zakresie dla ciągu</span><span class="sxs-lookup"><span data-stu-id="436ad-103">Warning CA1831: Use AsSpan instead of Range-based indexers for string</span></span>

<span data-ttu-id="436ad-104">Reguła analizatora kodu platformy .NET [CA1831](/visualstudio/code-quality/ca1831) jest domyślnie włączona, począwszy od platformy .NET 5,0.</span><span class="sxs-lookup"><span data-stu-id="436ad-104">.NET code analyzer rule [CA1831](/visualstudio/code-quality/ca1831) is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="436ad-105">Generuje ostrzeżenie kompilacji dla dowolnego kodu <xref:System.Range> , w którym jest używany indeksator oparty na ciągu, ale nie ma zamierzonego kopiowania.</span><span class="sxs-lookup"><span data-stu-id="436ad-105">It produces a build warning for any code where a <xref:System.Range>-based indexer is used on a string, but no copy was intended.</span></span>

## <a name="change-description"></a><span data-ttu-id="436ad-106">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="436ad-106">Change description</span></span>

<span data-ttu-id="436ad-107">Począwszy od platformy .NET 5,0, zestaw SDK .NET zawiera [analizatory kodu źródłowego platformy .NET](../../../../fundamentals/code-analysis/overview.md).</span><span class="sxs-lookup"><span data-stu-id="436ad-107">Starting in .NET 5.0, the .NET SDK includes [.NET source code analyzers](../../../../fundamentals/code-analysis/overview.md).</span></span> <span data-ttu-id="436ad-108">Niektóre z tych reguł są domyślnie włączone, w tym [CA1831](/visualstudio/code-quality/ca1831).</span><span class="sxs-lookup"><span data-stu-id="436ad-108">Several of these rules are enabled, by default, including [CA1831](/visualstudio/code-quality/ca1831).</span></span> <span data-ttu-id="436ad-109">Jeśli projekt zawiera kod naruszający tę regułę i jest skonfigurowany do traktowania ostrzeżeń jako błędów, ta zmiana może spowodować uszkodzenie kompilacji.</span><span class="sxs-lookup"><span data-stu-id="436ad-109">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span>

<span data-ttu-id="436ad-110">CA1831 reguły odnajduje wystąpienia <xref:System.Range> , w których jest używany indeksator oparty na ciągu, ale nie ma zamierzonego kopiowania.</span><span class="sxs-lookup"><span data-stu-id="436ad-110">Rule CA1831 finds instances where a <xref:System.Range>-based indexer is used on a string, but no copy was intended.</span></span> <span data-ttu-id="436ad-111">Jeśli <xref:System.Range> indeksator jest używany bezpośrednio w ciągu do tworzenia rzutowania niejawnego, wówczas tworzona jest niezbędna kopia żądanej części ciągu.</span><span class="sxs-lookup"><span data-stu-id="436ad-111">If the <xref:System.Range>-based indexer is used directly on a string to produce an implicit cast, then an unnecessary copy of the requested portion of the string is created.</span></span> <span data-ttu-id="436ad-112">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="436ad-112">For example:</span></span>

```csharp
ReadOnlySpan<char> slice = str[1..3];
```

<span data-ttu-id="436ad-113">CA1831 sugeruje użycie <xref:System.Range> indeksatora opartego na indeksie dla *zakresu* ciągu.</span><span class="sxs-lookup"><span data-stu-id="436ad-113">CA1831 suggests using the <xref:System.Range>-based indexer on a *span* of the string, instead.</span></span> <span data-ttu-id="436ad-114">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="436ad-114">For example:</span></span>

```csharp
ReadOnlySpan<char> slice = str.AsSpan()[1..3];
```

## <a name="version-introduced"></a><span data-ttu-id="436ad-115">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="436ad-115">Version introduced</span></span>

<span data-ttu-id="436ad-116">5,0</span><span class="sxs-lookup"><span data-stu-id="436ad-116">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="436ad-117">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="436ad-117">Recommended action</span></span>

- <span data-ttu-id="436ad-118">Aby poprawić kod i uniknąć niepotrzebnych alokacji, wywołaj <xref:System.MemoryExtensions.AsSpan(System.String)> lub <xref:System.MemoryExtensions.AsMemory(System.String)> przed użyciem <xref:System.Range> indeksatora opartego na usłudze.</span><span class="sxs-lookup"><span data-stu-id="436ad-118">To correct your code and avoid unnecessary allocations, call <xref:System.MemoryExtensions.AsSpan(System.String)> or <xref:System.MemoryExtensions.AsMemory(System.String)> before using the <xref:System.Range>-based indexer.</span></span> <span data-ttu-id="436ad-119">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="436ad-119">For example:</span></span>

  ```csharp
  ReadOnlySpan<char> slice = str.AsSpan()[1..3];
  ```

- <span data-ttu-id="436ad-120">Jeśli nie chcesz zmieniać kodu, możesz wyłączyć regułę, ustawiając jej ważność na `suggestion` lub `none` .</span><span class="sxs-lookup"><span data-stu-id="436ad-120">If you don't want to change your code, you can disable the rule by setting its severity to `suggestion` or `none`.</span></span> <span data-ttu-id="436ad-121">Aby uzyskać więcej informacji, zobacz [Konfigurowanie reguł analizy kodu](../../../../fundamentals/productivity/configure-code-analysis-rules.md).</span><span class="sxs-lookup"><span data-stu-id="436ad-121">For more information, see [Configure code analysis rules](../../../../fundamentals/productivity/configure-code-analysis-rules.md).</span></span>

- <span data-ttu-id="436ad-122">Aby całkowicie wyłączyć analizę kodu, ustaw `EnableNETAnalyzers` wartość `false` w pliku projektu.</span><span class="sxs-lookup"><span data-stu-id="436ad-122">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="436ad-123">Aby uzyskać więcej informacji, zobacz [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).</span><span class="sxs-lookup"><span data-stu-id="436ad-123">For more information, see [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

## <a name="affected-apis"></a><span data-ttu-id="436ad-124">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="436ad-124">Affected APIs</span></span>

- <xref:System.Range?displayProperty=fullName>

<!--

### Affected APIs

- `T:System.Range`

### Category

Code analysis

-->
