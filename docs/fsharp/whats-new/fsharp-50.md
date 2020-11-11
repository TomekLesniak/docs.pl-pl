---
title: 'Co nowego w języku F # 5,0 — Przewodnik po języku f #'
description: 'Zapoznaj się z omówieniem nowych funkcji dostępnych w języku F # 5,0.'
ms.date: 11/06/2020
ms.openlocfilehash: 0c4c9f42c63a1dc8c90213c43edbadd4061c132d
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/10/2020
ms.locfileid: "94445833"
---
# <a name="whats-new-in-f-50"></a><span data-ttu-id="aa258-103">Co nowego w języku F # 5,0</span><span class="sxs-lookup"><span data-stu-id="aa258-103">What's new in F# 5.0</span></span>

<span data-ttu-id="aa258-104">F # 5,0 dodaje kilka ulepszeń języka F # i F# Interactive.</span><span class="sxs-lookup"><span data-stu-id="aa258-104">F# 5.0 adds several improvements to the F# language and F# Interactive.</span></span> <span data-ttu-id="aa258-105">Jest on publikowany z **platformą .NET 5**.</span><span class="sxs-lookup"><span data-stu-id="aa258-105">It is released with **.NET 5**.</span></span>

## <a name="get-started"></a><span data-ttu-id="aa258-106">Wprowadzenie</span><span class="sxs-lookup"><span data-stu-id="aa258-106">Get started</span></span>

<span data-ttu-id="aa258-107">Język F # 5,0 jest dostępny we wszystkich dystrybucjach .NET Core i narzędziach programu Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="aa258-107">F# 5.0 is available in all .NET Core distributions and Visual Studio tooling.</span></span> <span data-ttu-id="aa258-108">Aby uzyskać więcej informacji, zobacz [wprowadzenie do języka F #](../get-started/index.md) , aby dowiedzieć się więcej.</span><span class="sxs-lookup"><span data-stu-id="aa258-108">For more information, see [Get started with F#](../get-started/index.md) to learn more.</span></span>

## <a name="package-references-in-f-scripts"></a><span data-ttu-id="aa258-109">Odwołania do pakietów w skryptach języka F #</span><span class="sxs-lookup"><span data-stu-id="aa258-109">Package references in F# scripts</span></span>

<span data-ttu-id="aa258-110">Język f # 5 zapewnia obsługę odwołań do pakietów w skryptach języka F # z `#r "nuget:..."` składnią.</span><span class="sxs-lookup"><span data-stu-id="aa258-110">F# 5 brings support for package references in F# scripts with `#r "nuget:..."` syntax.</span></span> <span data-ttu-id="aa258-111">Rozważmy na przykład następujące odwołanie do pakietu:</span><span class="sxs-lookup"><span data-stu-id="aa258-111">For example, consider the following package reference:</span></span>

```fsharp
#r "nuget: Newtonsoft.Json"

open Newtonsoft.Json

let o = {| X = 2; Y = "Hello" |}

printfn "%s" (JsonConvert.SerializeObject o)
```

<span data-ttu-id="aa258-112">Możesz również podać wersję jawną po nazwie pakietu w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="aa258-112">You can also supply an explicit version after the name of the package like this:</span></span>

```fsharp
#r "nuget: Newtonsoft.Json,11.0.1"
```

<span data-ttu-id="aa258-113">Pakiet zawiera odwołania do pakietów z natywnymi zależnościami, takimi jak ML.NET.</span><span class="sxs-lookup"><span data-stu-id="aa258-113">Package references support packages with native dependencies, such as ML.NET.</span></span>

<span data-ttu-id="aa258-114">Odwołania do pakietów obsługują również pakiety z specjalnymi wymaganiami dotyczącymi odwoływania się do elementów zależnych `.dll` .</span><span class="sxs-lookup"><span data-stu-id="aa258-114">Package references also support packages with special requirements about referencing dependent `.dll`s.</span></span> <span data-ttu-id="aa258-115">Na przykład pakiet [FParsec](https://www.nuget.org/packages/FParsec/) używany do wymagania, aby użytkownicy ręcznie upewnili się, że jego odwołanie `FParsecCS.dll` zostało odwołane jako pierwsze przed `FParsec.dll` odwołaniem do F# Interactive.</span><span class="sxs-lookup"><span data-stu-id="aa258-115">For example, the [FParsec](https://www.nuget.org/packages/FParsec/) package used to require that users manually ensure that its dependent `FParsecCS.dll` was referenced first before `FParsec.dll` was referenced in F# Interactive.</span></span> <span data-ttu-id="aa258-116">Nie jest to już potrzebne i można odwołać się do pakietu w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="aa258-116">This is no longer needed, and you can reference the package as follows:</span></span>

```fsharp
#r "nuget: FParsec"

open FParsec

let test p str =
    match run p str with
    | Success(result, _, _)   -> printfn "Success: %A" result
    | Failure(errorMsg, _, _) -> printfn "Failure: %s" errorMsg

test pfloat "1.234"
```

<span data-ttu-id="aa258-117">Aby uzyskać więcej informacji na temat odwołań do pakietów, zobacz samouczek [F# Interactive](../tutorials/fsharp-interactive/index.md) .</span><span class="sxs-lookup"><span data-stu-id="aa258-117">For more information on package references, see the [F# Interactive](../tutorials/fsharp-interactive/index.md) tutorial.</span></span>

## <a name="string-interpolation"></a><span data-ttu-id="aa258-118">Interpolacja ciągów</span><span class="sxs-lookup"><span data-stu-id="aa258-118">String interpolation</span></span>

<span data-ttu-id="aa258-119">Ciągi interpolowane języka F # są stosunkowo podobne do interpolowanych ciągów języka C# lub JavaScript, w tym, że umożliwiają pisanie kodu w "dziurach" wewnątrz literału ciągu.</span><span class="sxs-lookup"><span data-stu-id="aa258-119">F# interpolated strings are fairly similar to C# or JavaScript interpolated strings, in that they let you write code in "holes" inside of a string literal.</span></span> <span data-ttu-id="aa258-120">Poniżej przedstawiono prosty przykład:</span><span class="sxs-lookup"><span data-stu-id="aa258-120">Here's a basic example:</span></span>

```fsharp
let name = "Phillip"
let age = 29
printfn $"Name: {name}, Age: {age}"

printfn $"I think {3.0 + 0.14} is close to {System.Math.PI}!"
```

<span data-ttu-id="aa258-121">Jednakże interpolowane ciągi F # umożliwiają również wpisywanie typów interpolacji, podobnie jak `sprintf` Funkcja, aby wymusić, że wyrażenie wewnątrz interpolowanego kontekstu jest zgodne z określonym typem.</span><span class="sxs-lookup"><span data-stu-id="aa258-121">However, F# interpolated strings also allow for typed interpolations, just like the `sprintf` function, to enforce that an expression inside of an interpolated context conforms to a particular type.</span></span> <span data-ttu-id="aa258-122">Używa tego samego specyfikatora formatu.</span><span class="sxs-lookup"><span data-stu-id="aa258-122">It uses the same format specifiers.</span></span>

```fsharp
let name = "Phillip"
let age = 29

printfn $"Name: %s{name}, Age: %d{age}"

// Error: type mismatch
printfn $"Name: %s{age}, Age: %d{name}"
```

<span data-ttu-id="aa258-123">W powyższym przykładzie interpolacji, `%s` wymaga interpolacji jako typu `string` , natomiast `%d` wymaga interpolacji jako `integer` .</span><span class="sxs-lookup"><span data-stu-id="aa258-123">In the preceding typed interpolation example, the `%s` requires the interpolation to be of type `string`, whereas the `%d` requires the interpolation to be an `integer`.</span></span>

<span data-ttu-id="aa258-124">Ponadto dowolne dowolne wyrażenie F # (lub wyrażenia) można umieścić po stronie kontekstu interpolacji.</span><span class="sxs-lookup"><span data-stu-id="aa258-124">Additionally, any arbitrary F# expression (or expressions) can be placed in side of an interpolation context.</span></span> <span data-ttu-id="aa258-125">Istnieje nawet możliwość napisania bardziej skomplikowanego wyrażenia, takiego jak:</span><span class="sxs-lookup"><span data-stu-id="aa258-125">It is even possible to write a more complicated expression, like so:</span></span>

```fsharp
let str =
    $"""The result of squaring each odd item in {[1..10]} is:
{
    let square x = x * x
    let isOdd x = x % 2 <> 0
    let oddSquares xs =
        xs
        |> List.filter isOdd
        |> List.map square
    oddSquares [1..10]
}
"""
```

<span data-ttu-id="aa258-126">Chociaż nie zalecamy tego, aby to zrobić zbyt wiele.</span><span class="sxs-lookup"><span data-stu-id="aa258-126">Although we don't recommend doing this too much in practice.</span></span>

## <a name="support-for-nameof"></a><span data-ttu-id="aa258-127">Obsługa nameof</span><span class="sxs-lookup"><span data-stu-id="aa258-127">Support for nameof</span></span>

<span data-ttu-id="aa258-128">F # 5 obsługuje `nameof` operator, który rozwiązuje symbol używany do i tworzy jego nazwę w źródle F #.</span><span class="sxs-lookup"><span data-stu-id="aa258-128">F# 5 supports the `nameof` operator, which resolves the symbol it's being used for and produces its name in F# source.</span></span> <span data-ttu-id="aa258-129">Jest to przydatne w różnych scenariuszach, takich jak rejestrowanie i ochrona rejestrowania przed zmianami w kodzie źródłowym.</span><span class="sxs-lookup"><span data-stu-id="aa258-129">This is useful in various scenarios, such as logging, and protects your logging against changes in source code.</span></span>

```fsharp
let months =
    [
        "January"; "February"; "March"; "April";
        "May"; "June"; "July"; "August"; "September";
        "October"; "November"; "December"
    ]

let lookupMonth month =
    if (month > 12 || month < 1) then
        invalidArg (nameof month) (sprintf "Value passed in was %d." month)

    months.[month-1]

printfn "%s" (lookupMonth 12)
printfn "%s" (lookupMonth 1)
printfn "%s" (lookupMonth 13)
```

<span data-ttu-id="aa258-130">Ostatni wiersz zgłosi wyjątek, a "miesiąc" zostanie wyświetlony w komunikacie o błędzie.</span><span class="sxs-lookup"><span data-stu-id="aa258-130">The last line will throw an exception and "month" will be shown in the error message.</span></span>

<span data-ttu-id="aa258-131">Można przyjąć nazwę niemal każdej konstrukcji F #:</span><span class="sxs-lookup"><span data-stu-id="aa258-131">You can take a name of nearly every F# construct:</span></span>

```fsharp
module M =
    let f x = nameof x

printfn "%s" (M.f 12)
printfn "%s" (nameof M)
printfn "%s" (nameof M.f)
```

<span data-ttu-id="aa258-132">Trzy końcowe dodatki to zmiany wykonywane przez operatorów: dodanie `nameof<'type-parameter>` formularza dla parametrów typu ogólnego i możliwość użycia `nameof` jako wzorca w wyrażeniu dopasowania do wzorca.</span><span class="sxs-lookup"><span data-stu-id="aa258-132">Three final additions are changes to how operators work: the addition of the `nameof<'type-parameter>` form for generic type parameters, and the ability to use `nameof` as a pattern in a pattern match expression.</span></span>

<span data-ttu-id="aa258-133">Pobranie nazwy operatora powoduje powstanie jego ciągu źródłowego.</span><span class="sxs-lookup"><span data-stu-id="aa258-133">Taking a name of an operator gives its source string.</span></span> <span data-ttu-id="aa258-134">Jeśli potrzebujesz skompilowanego formularza, użyj skompilowanej nazwy operatora:</span><span class="sxs-lookup"><span data-stu-id="aa258-134">If you need the compiled form, use the compiled name of an operator:</span></span>

```fsharp
nameof(+) // "+"
nameof op_Addition // "op_Addition"
```

<span data-ttu-id="aa258-135">Pobranie nazwy parametru typu wymaga nieco innej składni:</span><span class="sxs-lookup"><span data-stu-id="aa258-135">Taking the name of a type parameter requires a slightly different syntax:</span></span>

```fsharp

type C<'TType> =
    member _.TypeName = nameof<'TType>
```

<span data-ttu-id="aa258-136">Jest to podobne do `typeof<'T>` operatorów i `typedefof<'T>` .</span><span class="sxs-lookup"><span data-stu-id="aa258-136">This is similar to the `typeof<'T>` and `typedefof<'T>` operators.</span></span>

<span data-ttu-id="aa258-137">F # 5 dodaje również obsługę `nameof` wzorca, który może być używany w `match` wyrażeniach:</span><span class="sxs-lookup"><span data-stu-id="aa258-137">F# 5 also adds support for a `nameof` pattern that can be used in `match` expressions:</span></span>

```fsharp
[<Struct; IsByRefLike>]
type RecordedEvent = { EventType: string; Data: ReadOnlySpan<byte> }

type MyEvent =
    | AData of int
    | BData of string

let deserialize (e: RecordedEvent) : MyEvent =
    match e.EventType with
    | nameof AData -> AData (JsonSerializer.Deserialize<int> e.Data)
    | nameof BData -> BData (JsonSerializer.Deserialize<string> e.Data)
    | t -> failwithf "Invalid EventType: %s" t
```

<span data-ttu-id="aa258-138">Poprzedzający kod używa elementu "nameof" zamiast literału ciągu w wyrażeniu Match.</span><span class="sxs-lookup"><span data-stu-id="aa258-138">The preceding code uses 'nameof' instead of the string literal in the match expression.</span></span>

## <a name="open-type-declarations"></a><span data-ttu-id="aa258-139">Otwieranie deklaracji typu</span><span class="sxs-lookup"><span data-stu-id="aa258-139">Open type declarations</span></span>

<span data-ttu-id="aa258-140">F # 5 dodaje również obsługę dla deklaracji typu Open.</span><span class="sxs-lookup"><span data-stu-id="aa258-140">F# 5 also adds support for open type declarations.</span></span> <span data-ttu-id="aa258-141">Deklaracja typu Open jest taka sama jak otwieranie klasy statycznej w języku C#, z wyjątkiem sytuacji, w której inna składnia i nieco inne zachowanie dopasowuje semantykę języka F #.</span><span class="sxs-lookup"><span data-stu-id="aa258-141">An open type declaration is like opening a static class in C#, except with some different syntax and some slightly different behavior to fit F# semantics.</span></span>

<span data-ttu-id="aa258-142">Za pomocą deklaracji typu Open można `open` udostępniać zawartość statyczną w obrębie tego typu.</span><span class="sxs-lookup"><span data-stu-id="aa258-142">With open type declarations, you can `open` any type to expose static contents inside of it.</span></span> <span data-ttu-id="aa258-143">Ponadto, możesz określić, że `open` w języku F # definicje i rekordy mają być ujawnione.</span><span class="sxs-lookup"><span data-stu-id="aa258-143">Additionally, you can `open` F#-defined unions and records to expose their contents.</span></span> <span data-ttu-id="aa258-144">Na przykład może to być przydatne, jeśli masz Unię zdefiniowaną w module i chcesz uzyskać do nich dostęp, ale nie chcesz otwierać całego modułu.</span><span class="sxs-lookup"><span data-stu-id="aa258-144">For example, this can be useful if you have a union defined in a module and want to access its cases, but don't want to open the entire module.</span></span>

```fsharp
open type System.Math

let x = Min(1.0, 2.0)

module M =
    type DU = A | B | C

    let someOtherFunction x = x + 1

// Open only the type inside the module
open type M.DU

printfn "%A" A
```

<span data-ttu-id="aa258-145">W przeciwieństwie do języka C#, `open type` w przypadku dwóch typów, które uwidaczniają składową o tej samej nazwie, element członkowski z ostatniego typu jest `open` zasłaniał inną nazwę.</span><span class="sxs-lookup"><span data-stu-id="aa258-145">Unlike C#, when you `open type` on two types that expose a member with the same name, the member from the last type being `open`ed shadows the other name.</span></span> <span data-ttu-id="aa258-146">Jest to zgodne z semantyką języka F # otaczającą już istniejące cieniowanie.</span><span class="sxs-lookup"><span data-stu-id="aa258-146">This is consistent with F# semantics around shadowing that exist already.</span></span>

## <a name="consistent-slicing-behavior-for-built-in-data-types"></a><span data-ttu-id="aa258-147">Spójne zachowanie tworzenia wycinków dla wbudowanych typów danych</span><span class="sxs-lookup"><span data-stu-id="aa258-147">Consistent slicing behavior for built-in data types</span></span>

<span data-ttu-id="aa258-148">Zachowanie tworzenia wycinków wbudowanych `FSharp.Core` typów danych (Array, list, String, Array 2D, tablica 3W, 4D Array) używanych jako niespójne przed F # 5.</span><span class="sxs-lookup"><span data-stu-id="aa258-148">Behavior for slicing the built-in `FSharp.Core` data types (array, list, string, 2D array, 3D array, 4D array) used to not be consistent prior to F# 5.</span></span> <span data-ttu-id="aa258-149">Niektóre zachowania w przypadku krawędzi wywołało wyjątek i niektóre nie.</span><span class="sxs-lookup"><span data-stu-id="aa258-149">Some edge-case behavior threw an exception and some wouldn't.</span></span> <span data-ttu-id="aa258-150">W języku F # 5 wszystkie wbudowane typy zwracają teraz puste wycinki dla wycinków, które nie są możliwe do wygenerowania:</span><span class="sxs-lookup"><span data-stu-id="aa258-150">In F# 5, all built-in types now return empty slices for slices that are impossible to generate:</span></span>

```fsharp
let l = [ 1..10 ]
let a = [| 1..10 |]
let s = "hello!"

// Before: would return empty list
// F# 5: same
let emptyList = l.[-2..(-1)]

// Before: would throw exception
// F# 5: returns empty array
let emptyArray = a.[-2..(-1)]

// Before: would throw exception
// F# 5: returns empty string
let emptyString = s.[-2..(-1)]
```

## <a name="fixed-index-slices-for-3d-and-4d-arrays-in-fsharpcore"></a><span data-ttu-id="aa258-151">Wycinków o stałym indeksie dla tablic 3W i 4D w FSharp. Core</span><span class="sxs-lookup"><span data-stu-id="aa258-151">Fixed-index slices for 3D and 4D arrays in FSharp.Core</span></span>

<span data-ttu-id="aa258-152">Język F # 5,0 zapewnia obsługę tworzenia wycinków ze stałym indeksem w wbudowanych typach tablic 3W i 4D.</span><span class="sxs-lookup"><span data-stu-id="aa258-152">F# 5.0 brings support for slicing with a fixed index in the built-in 3D and 4D array types.</span></span>

<span data-ttu-id="aa258-153">Aby to zilustrować, weź pod uwagę następującą tablicę 3W:</span><span class="sxs-lookup"><span data-stu-id="aa258-153">To illustrate this, consider the following 3D array:</span></span>

<span data-ttu-id="aa258-154">*z = 0*</span><span class="sxs-lookup"><span data-stu-id="aa258-154">*z = 0*</span></span>
|<span data-ttu-id="aa258-155">x\y</span><span class="sxs-lookup"><span data-stu-id="aa258-155">x\y</span></span>|<span data-ttu-id="aa258-156">0</span><span class="sxs-lookup"><span data-stu-id="aa258-156">0</span></span>|<span data-ttu-id="aa258-157">1</span><span class="sxs-lookup"><span data-stu-id="aa258-157">1</span></span>|
|---|-|-|
|<span data-ttu-id="aa258-158">**0**</span><span class="sxs-lookup"><span data-stu-id="aa258-158">**0**</span></span>|<span data-ttu-id="aa258-159">0</span><span class="sxs-lookup"><span data-stu-id="aa258-159">0</span></span>|<span data-ttu-id="aa258-160">1</span><span class="sxs-lookup"><span data-stu-id="aa258-160">1</span></span>|
|<span data-ttu-id="aa258-161">**1**</span><span class="sxs-lookup"><span data-stu-id="aa258-161">**1**</span></span>|<span data-ttu-id="aa258-162">2</span><span class="sxs-lookup"><span data-stu-id="aa258-162">2</span></span>|<span data-ttu-id="aa258-163">3</span><span class="sxs-lookup"><span data-stu-id="aa258-163">3</span></span>|

<span data-ttu-id="aa258-164">*z = 1*</span><span class="sxs-lookup"><span data-stu-id="aa258-164">*z = 1*</span></span>
|<span data-ttu-id="aa258-165">x\y</span><span class="sxs-lookup"><span data-stu-id="aa258-165">x\y</span></span>|<span data-ttu-id="aa258-166">0</span><span class="sxs-lookup"><span data-stu-id="aa258-166">0</span></span>|<span data-ttu-id="aa258-167">1</span><span class="sxs-lookup"><span data-stu-id="aa258-167">1</span></span>|
|---|-|-|
|<span data-ttu-id="aa258-168">**0**</span><span class="sxs-lookup"><span data-stu-id="aa258-168">**0**</span></span>|<span data-ttu-id="aa258-169">4</span><span class="sxs-lookup"><span data-stu-id="aa258-169">4</span></span>|<span data-ttu-id="aa258-170">5</span><span class="sxs-lookup"><span data-stu-id="aa258-170">5</span></span>|
|<span data-ttu-id="aa258-171">**1**</span><span class="sxs-lookup"><span data-stu-id="aa258-171">**1**</span></span>|<span data-ttu-id="aa258-172">6</span><span class="sxs-lookup"><span data-stu-id="aa258-172">6</span></span>|<span data-ttu-id="aa258-173">7</span><span class="sxs-lookup"><span data-stu-id="aa258-173">7</span></span>|

<span data-ttu-id="aa258-174">Co zrobić, jeśli chcesz wyodrębnić wycinek `[| 4; 5 |]` z tablicy?</span><span class="sxs-lookup"><span data-stu-id="aa258-174">What if you wanted to extract the slice `[| 4; 5 |]` from the array?</span></span> <span data-ttu-id="aa258-175">Jest to teraz bardzo proste!</span><span class="sxs-lookup"><span data-stu-id="aa258-175">This is now very simple!</span></span>

```fsharp
// First, create a 3D array to slice

let dim = 2
let m = Array3D.zeroCreate<int> dim dim dim

let mutable count = 0

for z in 0..dim-1 do
    for y in 0..dim-1 do
        for x in 0..dim-1 do
            m.[x,y,z] <- count
            count <- count + 1

// Now let's get the [4;5] slice!
m.[*, 0, 1]
```

## <a name="applicative-computation-expressions"></a><span data-ttu-id="aa258-176">Wyrażenia obliczeń Applicative</span><span class="sxs-lookup"><span data-stu-id="aa258-176">Applicative Computation Expressions</span></span>

<span data-ttu-id="aa258-177">[Wyrażenia obliczeń (CE)](../language-reference/computation-expressions.md) są używane dzisiaj do modelowania "obliczeń kontekstowych" lub w bardziej funkcjonalnej terminologii programowania, monadic obliczeń.</span><span class="sxs-lookup"><span data-stu-id="aa258-177">[Computation expressions (CEs)](../language-reference/computation-expressions.md) are used today to model "contextual computations", or in more functional programming friendly terminology, monadic computations.</span></span>

<span data-ttu-id="aa258-178">W języku F # 5 wprowadzono applicative CE, który oferuje inny model obliczeniowy.</span><span class="sxs-lookup"><span data-stu-id="aa258-178">F# 5 introduces applicative CEs, which offer a different computational model.</span></span> <span data-ttu-id="aa258-179">Applicative ce zezwala na bardziej wydajne obliczenia pod warunkiem, że każde obliczenie jest niezależne, a ich wyniki są gromadzone na końcu.</span><span class="sxs-lookup"><span data-stu-id="aa258-179">Applicative CEs allow for more efficient computations provided that every computation is independent, and their results are accumulated at the end.</span></span> <span data-ttu-id="aa258-180">Gdy obliczenia są niezależne od siebie, są one również proste działania równoległego, co umożliwia autorom CE pisanie bardziej wydajnych bibliotek.</span><span class="sxs-lookup"><span data-stu-id="aa258-180">When computations are independent of one another, they are also trivially parallelizable, allowing CE authors to write more efficient libraries.</span></span> <span data-ttu-id="aa258-181">Ta korzyść ma ograniczenie, chociaż: obliczenia zależne od wcześniej obliczonych wartości są niedozwolone.</span><span class="sxs-lookup"><span data-stu-id="aa258-181">This benefit comes at a restriction, though: computations that depend on previously-computed values are not allowed.</span></span>

<span data-ttu-id="aa258-182">W poniższym przykładzie przedstawiono podstawowe applicative CE dla `Result` typu.</span><span class="sxs-lookup"><span data-stu-id="aa258-182">The follow example shows a basic applicative CE for the `Result` type.</span></span>

```fsharp
// First, define a 'zip' function
module Result =
    let zip x1 x2 =
        match x1,x2 with
        | Ok x1res, Ok x2res -> Ok (x1res, x2res)
        | Error e, _ -> Error e
        | _, Error e -> Error e

// Next, define a builder with 'MergeSources' and 'BindReturn'
type ResultBuilder() =
    member _.MergeSources(t1: Result<'T,'U>, t2: Result<'T1,'U>) = Result.zip t1 t2
    member _.BindReturn(x: Result<'T,'U>, f) = Result.map f x

let result = ResultBuilder()

let run r1 r2 r3 =
    // And here is our applicative!
    let res1: Result<int, string> =
        result {
            let! a = r1
            and! b = r2
            and! c = r3
            return a + b - c
        }

    match res1 with
    | Ok x -> printfn "%s is: %d" (nameof res1) x
    | Error e -> printfn "%s is: %s" (nameof res1) e

let printApplicatives () =
    let r1 = Ok 2
    let r2 = Ok 3 // Error "fail!"
    let r3 = Ok 4

    run r1 r2 r3
    run r1 (Error "failure!") r3
```

<span data-ttu-id="aa258-183">Jeśli jesteś autorem biblioteki, który obecnie udostępnia w swojej bibliotece usługi rejestracji certyfikatów, musisz wiedzieć kilka dodatkowych zagadnień.</span><span class="sxs-lookup"><span data-stu-id="aa258-183">If you're a library author who exposes CEs in their library today, there are some additional considerations you'll need to be aware of.</span></span>

## <a name="interfaces-can-be-implemeneted-at-different-generic-instantiations"></a><span data-ttu-id="aa258-184">Interfejsy mogą być implemeneted w różnych ogólnych wystąpieniach</span><span class="sxs-lookup"><span data-stu-id="aa258-184">Interfaces can be implemeneted at different generic instantiations</span></span>

<span data-ttu-id="aa258-185">Teraz można zaimplementować ten sam interfejs w różnych wystąpieniach ogólnych:</span><span class="sxs-lookup"><span data-stu-id="aa258-185">You can now implement the same interface at different generic instantiations:</span></span>

```fsharp
type IA<'T> =
    abstract member Get : unit -> 'T

type MyClass() =
    interface IA<int> with
        member x.Get() = 1
    interface IA<string> with
        member x.Get() = "hello"

let mc = MyClass()
let iaInt = mc :> IA<int>
let iaString = mc :> IA<string>

iaInt.Get() // 1
iaString.Get() // "hello"
```

## <a name="default-interface-member-consumption"></a><span data-ttu-id="aa258-186">Użycie domyślnego interfejsu</span><span class="sxs-lookup"><span data-stu-id="aa258-186">Default interface member consumption</span></span>

<span data-ttu-id="aa258-187">Język F # 5 umożliwia korzystanie [z interfejsów z domyślnymi implementacjami](../../csharp/tutorials/default-interface-methods-versions.md).</span><span class="sxs-lookup"><span data-stu-id="aa258-187">F# 5 lets you consume [interfaces with default implementations](../../csharp/tutorials/default-interface-methods-versions.md).</span></span>

<span data-ttu-id="aa258-188">Rozważ użycie interfejsu zdefiniowanego w języku C# w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="aa258-188">Consider an interface defined in C# like this:</span></span>

```csharp
using System;

namespace CSharp
{
    public interface MyDimasd
    {
        public int Z => 0;
    }
}
```

<span data-ttu-id="aa258-189">Można go wykorzystać w F # za pomocą dowolnego standardowego sposobu implementacji interfejsu:</span><span class="sxs-lookup"><span data-stu-id="aa258-189">You can consume it in F# through any of the standard means of implementing an interface:</span></span>

```fsharp
open CSharp

// You can implement the interface via a class
type MyType() =
    member _.M() = ()

    interface MyDim

let md = MyType() :> MyDim
printfn "DIM from C#: %d" md.Z

// You can also implement it via an object expression
let md' = { new MyDim }
printfn "DIM from C# but via Object Expression: %d" md'.Z
```

<span data-ttu-id="aa258-190">Dzięki temu można bezpiecznie korzystać z kodu w języku C# i składników .NET zapisanych w nowoczesnej C#, gdy użytkownicy będą mogli korzystać z implementacji domyślnej.</span><span class="sxs-lookup"><span data-stu-id="aa258-190">This lets you safely take advantage of C# code and .NET components written in modern C# when they expect users to be able to consume a default implementation.</span></span>

## <a name="simplified-interop-with-nullable-value-types"></a><span data-ttu-id="aa258-191">Uproszczona międzyoperacyjna z typami wartości null</span><span class="sxs-lookup"><span data-stu-id="aa258-191">Simplified interop with nullable value types</span></span>

<span data-ttu-id="aa258-192">[Typy dopuszczające wartości null (o wartościach](https://docs.microsoft.com/dotnet/api/system.nullable-1) dopuszczających wartość null) były obsługiwane przez język F #, ale współpracujące z nimi są tradycyjnie nieco nieznacznie odbiegać, ponieważ trzeba utworzyć `Nullable` `Nullable<SomeType>` otokę lub za każdym razem, gdy chcesz przekazać wartość.</span><span class="sxs-lookup"><span data-stu-id="aa258-192">[Nullable (value) types](https://docs.microsoft.com/dotnet/api/system.nullable-1) (called Nullable Types historically) have long been supported by F#, but interacting with them has traditionally been somewhat of a pain since you'd have to construct a `Nullable` or `Nullable<SomeType>` wrapper every time you wanted to pass a value.</span></span> <span data-ttu-id="aa258-193">Teraz kompilator niejawnie przekonwertuje typ wartości na, `Nullable<ThatValueType>` Jeśli typ docelowy jest zgodny.</span><span class="sxs-lookup"><span data-stu-id="aa258-193">Now the compiler will implicitly convert a value type into a `Nullable<ThatValueType>` if the target type matches.</span></span> <span data-ttu-id="aa258-194">Teraz można wykonać następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="aa258-194">The following code is now possible:</span></span>

```fsharp
#r "nuget: Microsoft.Data.Analysis"

open Microsoft.Data.Analysis

let dateTimes = PrimitiveDataFrameColumn<DateTime>("DateTimes")

// The following line used to fail to compile
dateTimes.Append(DateTime.Parse("2019/01/01"))

// The previous line is now equivalent to this line
dateTimes.Append(Nullable<DateTime>(DateTime.Parse("2019/01/01")))
```

## <a name="preview-reverse-indexes"></a><span data-ttu-id="aa258-195">Wersja zapoznawcza: przewracanie indeksów</span><span class="sxs-lookup"><span data-stu-id="aa258-195">Preview: reverse indexes</span></span>

<span data-ttu-id="aa258-196">W języku F # 5 wprowadzono również podgląd zezwalający na odwracanie indeksów.</span><span class="sxs-lookup"><span data-stu-id="aa258-196">F# 5 also introduces a preview for allowing reverse indexes.</span></span> <span data-ttu-id="aa258-197">Składnia jest następująca: `^idx`</span><span class="sxs-lookup"><span data-stu-id="aa258-197">The syntax is `^idx`.</span></span> <span data-ttu-id="aa258-198">Oto jak można określić wartość elementu 1 z końca listy:</span><span class="sxs-lookup"><span data-stu-id="aa258-198">Here’s how you can an element 1 value from the end of a list:</span></span>

```fsharp
let xs = [1..10]

// Get element 1 from the end:
xs.[^1]

// From the end slices

let lastTwoOldStyle = xs.[(xs.Length-2)..]

let lastTwoNewStyle = xs.[^1..]

lastTwoOldStyle = lastTwoNewStyle // true
```

<span data-ttu-id="aa258-199">Można także definiować Odwróć indeksy dla własnych typów.</span><span class="sxs-lookup"><span data-stu-id="aa258-199">You can also define reverse indexes for your own types.</span></span> <span data-ttu-id="aa258-200">Aby to zrobić, należy wdrożyć następującą metodę:</span><span class="sxs-lookup"><span data-stu-id="aa258-200">To do so, you’ll need to implement the following method:</span></span>

```fsharp
GetReverseIndex: dimension: int -> offset: int
```

<span data-ttu-id="aa258-201">Oto przykład dla `Span<'T>` typu:</span><span class="sxs-lookup"><span data-stu-id="aa258-201">Here’s an example for the `Span<'T>` type:</span></span>

```fsharp
open System

type Span<'T> with
    member sp.GetSlice(startIdx, endIdx) =
        let s = defaultArg startIdx 0
        let e = defaultArg endIdx sp.Length
        sp.Slice(s, e - s)

    member sp.GetReverseIndex(_, offset: int) =
        sp.Length - offset

let printSpan (sp: Span<int>) =
    let arr = sp.ToArray()
    printfn "%A" arr

let run () =
    let sp = [| 1; 2; 3; 4; 5 |].AsSpan()

    // Pre-# 5.0 slicing on a Span<'T>
    printSpan sp.[0..] // [|1; 2; 3; 4; 5|]
    printSpan sp.[..3] // [|1; 2; 3|]
    printSpan sp.[1..3] // |2; 3|]

    // Same slices, but only using from-the-end index
    printSpan sp.[..^0] // [|1; 2; 3; 4; 5|]
    printSpan sp.[..^2] // [|1; 2; 3|]
    printSpan sp.[^4..^2] // [|2; 3|]

run() // Prints the same thing twice
```

## <a name="preview-overloads-of-custom-keywords-in-computation-expressions"></a><span data-ttu-id="aa258-202">Wersja zapoznawcza: przeciążenia niestandardowych słów kluczowych w wyrażeniach obliczeń</span><span class="sxs-lookup"><span data-stu-id="aa258-202">Preview: overloads of custom keywords in computation expressions</span></span>

<span data-ttu-id="aa258-203">Wyrażenia obliczeń to zaawansowana funkcja dla autorów bibliotek i struktur.</span><span class="sxs-lookup"><span data-stu-id="aa258-203">Computation expressions are a powerful feature for library and framework authors.</span></span> <span data-ttu-id="aa258-204">Pozwalają one znacząco ulepszyć wyrazistości składników, umożliwiając zdefiniowanie dobrze znanych elementów członkowskich i tworzą DSL dla domeny, w której pracujesz.</span><span class="sxs-lookup"><span data-stu-id="aa258-204">They allow you to greatly improve the expressiveness of your components by letting you define well-known members and form a DSL for the domain you're working in.</span></span>

<span data-ttu-id="aa258-205">F # 5 dodaje obsługę w wersji zapoznawczej w celu przeładowania niestandardowych operacji w wyrażeniach obliczeniowych.</span><span class="sxs-lookup"><span data-stu-id="aa258-205">F# 5 adds preview support for overloading custom operations in Computation Expressions.</span></span> <span data-ttu-id="aa258-206">Umożliwia WRITEN i użycie następującego kodu:</span><span class="sxs-lookup"><span data-stu-id="aa258-206">It allows the following code to be writen and consumed:</span></span>

```fsharp
open System

type InputKind =
    | Text of placeholder:string option
    | Password of placeholder: string option

type InputOptions =
  { Label: string option
    Kind : InputKind
    Validators : (string -> bool) array }

type InputBuilder() =
    member t.Yield(_) =
      { Label = None
        Kind = Text None
        Validators = [||] }

    [<CustomOperation("text")>]
    member this.Text(io, ?placeholder) =
        { io with Kind = Text placeholder }

    [<CustomOperation("password")>]
    member this.Password(io, ?placeholder) =
        { io with Kind = Password placeholder }

    [<CustomOperation("label")>]
    member this.Label(io, label) =
        { io with Label = Some label }

    [<CustomOperation("with_validators")>]
    member this.Validators(io, [<ParamArray>] validators) =
        { io with Validators = validators }

let input = InputBuilder()

let name =
    input {
    label "Name"
    text
    with_validators
        (String.IsNullOrWhiteSpace >> not)
    }

let email =
    input {
    label "Email"
    text "Your email"
    with_validators
        (String.IsNullOrWhiteSpace >> not)
        (fun s -> s.Contains "@")
    }

let password =
    input {
    label "Password"
    password "Must contains at least 6 characters, one number and one uppercase"
    with_validators
        (String.exists Char.IsUpper)
        (String.exists Char.IsDigit)
        (fun s -> s.Length >= 6)
    }
```

<span data-ttu-id="aa258-207">Przed wprowadzeniem tej zmiany można napisać `InputBuilder` Typ w takiej postaci, w jakiej jest, ale nie można go użyć w tym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="aa258-207">Prior to this change, you could write the `InputBuilder` type as it is, but you couldn't use it the way it's used in the example.</span></span> <span data-ttu-id="aa258-208">Ponieważ przeciążenia, parametry opcjonalne i teraz `System.ParamArray` są dozwolone, wszystko działa zgodnie z oczekiwaniami.</span><span class="sxs-lookup"><span data-stu-id="aa258-208">Since overloads, optional parameters, and now `System.ParamArray` types are allowed, everything just works as you'd expect it to.</span></span>
