---
title: Ciągi interpolowane
description: 'Dowiedz się więcej o ciągach interpolowanych, specjalnej formie ciągu, która umożliwia osadzanie wyrażeń F # bezpośrednio wewnątrz nich.'
ms.date: 11/12/2020
ms.openlocfilehash: 8c552b44cea7d6c51ec333b6bdd4d407c6f10da7
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94829690"
---
# <a name="interpolated-strings"></a><span data-ttu-id="762cb-103">Ciągi interpolowane</span><span class="sxs-lookup"><span data-stu-id="762cb-103">Interpolated strings</span></span>

<span data-ttu-id="762cb-104">Ciągi interpolowane są [ciągami](strings.md) , które umożliwiają osadzenie w nich wyrażeń F #.</span><span class="sxs-lookup"><span data-stu-id="762cb-104">Interpolated strings are [strings](strings.md) that allow you to embed F# expressions into them.</span></span> <span data-ttu-id="762cb-105">Są one przydatne w szerokim zakresie scenariuszy, w których wartość ciągu może się zmieniać w zależności od wyniku wartości lub wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="762cb-105">They are helpful in a wide range of scenarios where the value of a string may change based on the result of a value or expression.</span></span>

## <a name="syntax"></a><span data-ttu-id="762cb-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="762cb-106">Syntax</span></span>

```fsharp
$"string-text {expr}"
$"string-text %format-specifier{expr}"
$"""string-text {"embedded string literal"}"""
```

## <a name="remarks"></a><span data-ttu-id="762cb-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="762cb-107">Remarks</span></span>

<span data-ttu-id="762cb-108">Ciągi interpolowane pozwalają pisać kod w "dziurach" wewnątrz literału ciągu.</span><span class="sxs-lookup"><span data-stu-id="762cb-108">Interpolated strings let you write code in "holes" inside of a string literal.</span></span> <span data-ttu-id="762cb-109">Poniżej przedstawiono prosty przykład:</span><span class="sxs-lookup"><span data-stu-id="762cb-109">Here's a basic example:</span></span>

```fsharp
let name = "Phillip"
let age = 30
printfn $"Name: {name}, Age: {age}"

printfn $"I think {3.0 + 0.14} is close to {System.Math.PI}!"
```

<span data-ttu-id="762cb-110">Zawartość między każdą `{}` parą nawiasów klamrowych może być dowolnym wyrażeniem języka F #.</span><span class="sxs-lookup"><span data-stu-id="762cb-110">The contents in between each `{}` brace pair can be any F# expression.</span></span>

<span data-ttu-id="762cb-111">Aby wypróbować `{}` parę nawiasów klamrowych, napisz dwa z nich, tak aby:</span><span class="sxs-lookup"><span data-stu-id="762cb-111">To escape a `{}` brace pair, write two of them like so:</span></span>

```fsharp
let str = $"A pair of braces: {{}}"
// "A pair of braces: {}"
```

## <a name="typed-interpolated-strings"></a><span data-ttu-id="762cb-112">Wpisane ciągi interpolowane</span><span class="sxs-lookup"><span data-stu-id="762cb-112">Typed interpolated strings</span></span>

<span data-ttu-id="762cb-113">Ciągi interpolowane mogą także mieć specyfikatory formatu języka F #, aby wymusić bezpieczeństwo typu.</span><span class="sxs-lookup"><span data-stu-id="762cb-113">Interpolated strings can also have F# format specifiers to enforce type safety.</span></span>

```fsharp
let name = "Phillip"
let age = 30

printfn $"Name: %s{name}, Age: %d{age}"

// Error: type mismatch
printfn $"Name: %s{age}, Age: %d{name}"
```

<span data-ttu-id="762cb-114">W poprzednim przykładzie kod przeszedł w sposób nieprzekazywany do `age` wartości, gdzie `name` powinien być i na odwrót.</span><span class="sxs-lookup"><span data-stu-id="762cb-114">In the previous example, the code mistakenly passes the `age` value where `name` should be, and vice/versa.</span></span> <span data-ttu-id="762cb-115">Ponieważ interpolowane ciągi używają specyfikatorów formatu, jest to błąd kompilacji, a nie w przypadku niewielkiej usterki środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="762cb-115">Because the interpolated strings use format specifiers, this is a compile error instead of a subtle runtime bug.</span></span>

<span data-ttu-id="762cb-116">Wszystkie specyfikatory formatu omówione w formacie [zwykłego tekstu](plaintext-formatting.md) są prawidłowe w ciągu interpolowanym.</span><span class="sxs-lookup"><span data-stu-id="762cb-116">All format specifiers covered in [plaintext formatting](plaintext-formatting.md) are valid inside of an interpolated string.</span></span>

## <a name="verbatim-interpolated-strings"></a><span data-ttu-id="762cb-117">Verbatim ciągi interpolowane</span><span class="sxs-lookup"><span data-stu-id="762cb-117">Verbatim interpolated strings</span></span>

<span data-ttu-id="762cb-118">Język F # obsługuje Verbatim interpolowane ciągi z potrójnymi cudzysłowami, aby można było osadzić literały ciągu.</span><span class="sxs-lookup"><span data-stu-id="762cb-118">F# supports verbatim interpolated strings with triple quotes so that you can embed string literals.</span></span>

```fsharp
let age = 30

printfn $"""Name: {"Phillip"}, Age: %d{age}"""
```

## <a name="aligning-expressions-in-interpolated-strings"></a><span data-ttu-id="762cb-119">Wyrównywanie wyrażeń w ciągach interpolowanych</span><span class="sxs-lookup"><span data-stu-id="762cb-119">Aligning expressions in interpolated strings</span></span>

<span data-ttu-id="762cb-120">Wyrażenia można wyrównać lub wyrównać do lewej w ciągach interpolowanych z `|` i specyfikacją liczby spacji.</span><span class="sxs-lookup"><span data-stu-id="762cb-120">You can left-align or right-align expressions inside interpolated strings with `|` and a specification of how many spaces.</span></span> <span data-ttu-id="762cb-121">Następujący ciąg interpolowany wyrównuje lewe i prawe wyrażenie do lewej i prawej, odpowiednio o siedem spacji.</span><span class="sxs-lookup"><span data-stu-id="762cb-121">The following interpolated string aligns the left and right expressions to the left and right, respectively, by seven spaces.</span></span>

```fsharp
printfn $"""|{"Left",-7}|{"Right",7}|"""
// |Left   |  Right|
```

## <a name="interpolated-strings-and-formattablestring-formatting"></a><span data-ttu-id="762cb-122">Ciągi i formatowanie interpolowane `FormattableString`</span><span class="sxs-lookup"><span data-stu-id="762cb-122">Interpolated strings and `FormattableString` formatting</span></span>

<span data-ttu-id="762cb-123">Można również zastosować formatowanie zgodne z regułami dla <xref:System.FormattableString> :</span><span class="sxs-lookup"><span data-stu-id="762cb-123">You can also apply formatting that adheres to the rules for <xref:System.FormattableString>:</span></span>

```fsharp
let speedOfLight = 299792.458
printfn $"The speed of light is {speedOfLight:N3} km/s."
// "The speed of light is 299,792.458 km/s."
```

<span data-ttu-id="762cb-124">Dodatkowo ciąg interpolowany może być również typem sprawdzonym jako <xref:System.FormattableString> za pośrednictwem adnotacji typu:</span><span class="sxs-lookup"><span data-stu-id="762cb-124">Additionally, an interpolated string can also be type checked as a <xref:System.FormattableString> via a type annotation:</span></span>

```fsharp
let frmtStr = $"The speed of light is {speedOfLight:N3} km/s." : FormattableString
// Type: FormattableString
// The speed of light is 299,792.458 km/s.
```

<span data-ttu-id="762cb-125">Należy zauważyć, że adnotacja typu musi znajdować się w wyrażeniu ciągu interpolowanego.</span><span class="sxs-lookup"><span data-stu-id="762cb-125">Note that the type annotation must be on the interpolated string expression itself.</span></span> <span data-ttu-id="762cb-126">Język F # nie konwertuje niejawnie ciągu interpolowanego na <xref:System.FormattableString> .</span><span class="sxs-lookup"><span data-stu-id="762cb-126">F# does not implicitly convert an interpolated string into a <xref:System.FormattableString>.</span></span>

## <a name="see-also"></a><span data-ttu-id="762cb-127">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="762cb-127">See also</span></span>

* [<span data-ttu-id="762cb-128">Ciągi</span><span class="sxs-lookup"><span data-stu-id="762cb-128">Strings</span></span>](strings.md)