---
title: 'Nieprzerwana zmiana: LastIndexOf ma ulepszoną obsługę pustych ciągów wyszukiwania'
description: Więcej informacji na temat istotnej zmiany w programie .NET 5,0 w bibliotekach podstawowych platformy .NET, w których LastIndexOf i powiązane interfejsy API teraz zwracają poprawne wartości podczas wyszukiwania podciągu o zerowej długości.
ms.date: 11/01/2020
ms.openlocfilehash: 6d1a676eb2b9ed3de6a745db27d53bd43560a32f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761379"
---
# <a name="lastindexof-has-improved-handling-of-empty-search-strings"></a><span data-ttu-id="ba334-103">LastIndexOf Ulepszono obsługę pustych ciągów wyszukiwania</span><span class="sxs-lookup"><span data-stu-id="ba334-103">LastIndexOf has improved handling of empty search strings</span></span>

<span data-ttu-id="ba334-104"><xref:System.String.LastIndexOf%2A?displayProperty=nameWithType> i powiązane interfejsy API teraz zwracają poprawne wartości podczas wyszukiwania podciągu o zerowej długości (lub o zerowej długości) w większym ciągu.</span><span class="sxs-lookup"><span data-stu-id="ba334-104"><xref:System.String.LastIndexOf%2A?displayProperty=nameWithType> and related APIs now return correct values when searching for a zero-length (or zero-length equivalent) substring within a larger string.</span></span>

## <a name="change-description"></a><span data-ttu-id="ba334-105">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="ba334-105">Change description</span></span>

<span data-ttu-id="ba334-106">W .NET Framework i .NET Core 1,0-3,1 <xref:System.String.LastIndexOf%2A?displayProperty=nameWithType> i powiązane interfejsy API mogą zwracać niepoprawną wartość, gdy obiekt wywołujący wyszukuje podciąg o zerowej długości.</span><span class="sxs-lookup"><span data-stu-id="ba334-106">In .NET Framework and .NET Core 1.0 - 3.1, <xref:System.String.LastIndexOf%2A?displayProperty=nameWithType> and related APIs might return an incorrect value when the caller searches for a zero-length substring.</span></span>

```csharp
Console.WriteLine("Hello".LastIndexOf("")); // prints '4' (incorrect)

ReadOnlySpan<char> span = "Hello";
Console.WriteLine(span.LastIndexOf("")); // prints '0' (incorrect)
```

<span data-ttu-id="ba334-107">Począwszy od platformy .NET 5,0, te interfejsy API zwracają poprawną wartość dla `LastIndexOf` .</span><span class="sxs-lookup"><span data-stu-id="ba334-107">Starting with .NET 5.0, these APIs return the correct value for `LastIndexOf`.</span></span>

```csharp
Console.WriteLine("Hello".LastIndexOf("")); // prints '5' (correct)

ReadOnlySpan<char> span = "Hello";
Console.WriteLine(span.LastIndexOf("")); // prints '5' (correct)
```

<span data-ttu-id="ba334-108">W tych przykładach `5` jest poprawna odpowiedź, ponieważ `"Hello".Substring(5)` i `"Hello".AsSpan().Slice(5)` oba tworzą pusty ciąg, który jest w prosty sposób równy pustemu ciągowi, który jest poszukiwany.</span><span class="sxs-lookup"><span data-stu-id="ba334-108">In these examples, `5` is the correct answer because `"Hello".Substring(5)` and `"Hello".AsSpan().Slice(5)` both produce an empty string, which is trivially equal to the empty substring that is sought.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="ba334-109">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="ba334-109">Reason for change</span></span>

<span data-ttu-id="ba334-110">Ta zmiana była częścią ogólnego nakładu na rozwiązywanie problemów związanych z obsługą ciągów dla platformy .NET 5.</span><span class="sxs-lookup"><span data-stu-id="ba334-110">This change was part of an overall bug fixing effort around string handling for .NET 5.</span></span> <span data-ttu-id="ba334-111">Pomaga również w ujednoliceniu zachowań między platformami systemu Windows i systemami innymi niż Windows.</span><span class="sxs-lookup"><span data-stu-id="ba334-111">It also helps unify our behavior between Windows and non-Windows platforms.</span></span> <span data-ttu-id="ba334-112">Aby uzyskać więcej informacji, zobacz [dotnet/Runtime # 13383](https://github.com/dotnet/runtime/issues/13383) i [dotnet/Runtime # #13382](https://github.com/dotnet/runtime/issues/13382).</span><span class="sxs-lookup"><span data-stu-id="ba334-112">For more information, see [dotnet/runtime#13383](https://github.com/dotnet/runtime/issues/13383) and [dotnet/runtime##13382](https://github.com/dotnet/runtime/issues/13382).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="ba334-113">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="ba334-113">Version introduced</span></span>

<span data-ttu-id="ba334-114">5,0</span><span class="sxs-lookup"><span data-stu-id="ba334-114">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="ba334-115">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="ba334-115">Recommended action</span></span>

<span data-ttu-id="ba334-116">Nie trzeba podejmować żadnych działań.</span><span class="sxs-lookup"><span data-stu-id="ba334-116">You don't need to take any action.</span></span> <span data-ttu-id="ba334-117">Środowisko uruchomieniowe programu .NET 5,0 udostępnia nowe zachowania automatycznie.</span><span class="sxs-lookup"><span data-stu-id="ba334-117">The .NET 5.0 runtime provides the new behaviors automatically.</span></span>

<span data-ttu-id="ba334-118">Nie ma przełącznika zgodności w celu przywrócenia starego zachowania.</span><span class="sxs-lookup"><span data-stu-id="ba334-118">There is no compatibility switch to restore the old behavior.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="ba334-119">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="ba334-119">Affected APIs</span></span>

- <xref:System.String.LastIndexOf%2A?displayProperty=fullName>
- <xref:System.Globalization.CompareInfo.LastIndexOf%2A?displayProperty=fullName>
- <xref:System.MemoryExtensions.LastIndexOf%2A?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `Overload:System.String.LastIndexOf`
- `Overload:System.Globalization.CompareInfo.LastIndexOf`
- `Overload:System.MemoryExtensions.LastIndexOf`

-->
