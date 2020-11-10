---
ms.openlocfilehash: 0ba77a6a6ac0e2d29036635ea3cdb9ba9a9da10e
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/10/2020
ms.locfileid: "94440187"
---
### <a name="lastindexof-has-improved-handling-of-empty-search-strings"></a><span data-ttu-id="d47cc-101">LastIndexOf Ulepszono obsługę pustych ciągów wyszukiwania</span><span class="sxs-lookup"><span data-stu-id="d47cc-101">LastIndexOf has improved handling of empty search strings</span></span>

<span data-ttu-id="d47cc-102"><xref:System.String.LastIndexOf%2A?displayProperty=nameWithType> i powiązane interfejsy API teraz zwracają poprawne wartości podczas wyszukiwania podciągu o zerowej długości (lub o zerowej długości) w większym ciągu.</span><span class="sxs-lookup"><span data-stu-id="d47cc-102"><xref:System.String.LastIndexOf%2A?displayProperty=nameWithType> and related APIs now return correct values when searching for a zero-length (or zero-length equivalent) substring within a larger string.</span></span>

#### <a name="change-description"></a><span data-ttu-id="d47cc-103">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="d47cc-103">Change description</span></span>

<span data-ttu-id="d47cc-104">W .NET Framework i .NET Core 1,0-3,1 <xref:System.String.LastIndexOf%2A?displayProperty=nameWithType> i powiązane interfejsy API mogą zwracać niepoprawną wartość, gdy obiekt wywołujący wyszukuje podciąg o zerowej długości.</span><span class="sxs-lookup"><span data-stu-id="d47cc-104">In .NET Framework and .NET Core 1.0 - 3.1, <xref:System.String.LastIndexOf%2A?displayProperty=nameWithType> and related APIs might return an incorrect value when the caller searches for a zero-length substring.</span></span>

```csharp
Console.WriteLine("Hello".LastIndexOf("")); // prints '4' (incorrect)

ReadOnlySpan<char> span = "Hello";
Console.WriteLine(span.LastIndexOf("")); // prints '0' (incorrect)
```

<span data-ttu-id="d47cc-105">Począwszy od platformy .NET 5,0, te interfejsy API zwracają poprawną wartość dla `LastIndexOf` .</span><span class="sxs-lookup"><span data-stu-id="d47cc-105">Starting with .NET 5.0, these APIs return the correct value for `LastIndexOf`.</span></span>

```csharp
Console.WriteLine("Hello".LastIndexOf("")); // prints '5' (correct)

ReadOnlySpan<char> span = "Hello";
Console.WriteLine(span.LastIndexOf("")); // prints '5' (correct)
```

<span data-ttu-id="d47cc-106">W tych przykładach `5` jest poprawna odpowiedź, ponieważ `"Hello".Substring(5)` i `"Hello".AsSpan().Slice(5)` oba tworzą pusty ciąg, który jest w prosty sposób równy pustemu ciągowi, który jest poszukiwany.</span><span class="sxs-lookup"><span data-stu-id="d47cc-106">In these examples, `5` is the correct answer because `"Hello".Substring(5)` and `"Hello".AsSpan().Slice(5)` both produce an empty string, which is trivially equal to the empty substring that is sought.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="d47cc-107">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="d47cc-107">Reason for change</span></span>

<span data-ttu-id="d47cc-108">Ta zmiana była częścią ogólnego nakładu na rozwiązywanie problemów związanych z obsługą ciągów dla platformy .NET 5.</span><span class="sxs-lookup"><span data-stu-id="d47cc-108">This change was part of an overall bug fixing effort around string handling for .NET 5.</span></span> <span data-ttu-id="d47cc-109">Pomaga również w ujednoliceniu zachowań między platformami systemu Windows i systemami innymi niż Windows.</span><span class="sxs-lookup"><span data-stu-id="d47cc-109">It also helps unify our behavior between Windows and non-Windows platforms.</span></span> <span data-ttu-id="d47cc-110">Aby uzyskać więcej informacji, zobacz [dotnet/Runtime # 13383](https://github.com/dotnet/runtime/issues/13383) i [dotnet/Runtime # #13382](https://github.com/dotnet/runtime/issues/13382).</span><span class="sxs-lookup"><span data-stu-id="d47cc-110">For more information, see [dotnet/runtime#13383](https://github.com/dotnet/runtime/issues/13383) and [dotnet/runtime##13382](https://github.com/dotnet/runtime/issues/13382).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="d47cc-111">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="d47cc-111">Version introduced</span></span>

<span data-ttu-id="d47cc-112">5,0</span><span class="sxs-lookup"><span data-stu-id="d47cc-112">5.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="d47cc-113">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="d47cc-113">Recommended action</span></span>

<span data-ttu-id="d47cc-114">Nie trzeba podejmować żadnych działań.</span><span class="sxs-lookup"><span data-stu-id="d47cc-114">You don't need to take any action.</span></span> <span data-ttu-id="d47cc-115">Środowisko uruchomieniowe programu .NET 5,0 udostępnia nowe zachowania automatycznie.</span><span class="sxs-lookup"><span data-stu-id="d47cc-115">The .NET 5.0 runtime provides the new behaviors automatically.</span></span>

<span data-ttu-id="d47cc-116">Nie ma przełącznika zgodności w celu przywrócenia starego zachowania.</span><span class="sxs-lookup"><span data-stu-id="d47cc-116">There is no compatibility switch to restore the old behavior.</span></span>

#### <a name="category"></a><span data-ttu-id="d47cc-117">Kategoria</span><span class="sxs-lookup"><span data-stu-id="d47cc-117">Category</span></span>

<span data-ttu-id="d47cc-118">Podstawowe biblioteki platformy .NET</span><span class="sxs-lookup"><span data-stu-id="d47cc-118">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="d47cc-119">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="d47cc-119">Affected APIs</span></span>

- <xref:System.String.LastIndexOf%2A?displayProperty=fullName>
- <xref:System.Globalization.CompareInfo.LastIndexOf%2A?displayProperty=fullName>
- <xref:System.MemoryExtensions.LastIndexOf%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `Overload:System.String.LastIndexOf`
- `Overload:System.Globalization.CompareInfo.LastIndexOf`
- `Overload:System.MemoryExtensions.LastIndexOf`

-->
