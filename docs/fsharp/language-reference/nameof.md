---
title: Nameof
description: Dowiedz się więcej o operatorze nameof, funkcjach, które umożliwiają tworzenie nazw symboli w kodzie źródłowym.
ms.date: 11/12/2020
ms.openlocfilehash: 9947d7172d1b73db5c181297ec8b1131382e1f5e
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/17/2020
ms.locfileid: "94688615"
---
# <a name="nameof"></a><span data-ttu-id="dc1f6-103">Nameof</span><span class="sxs-lookup"><span data-stu-id="dc1f6-103">Nameof</span></span>

<span data-ttu-id="dc1f6-104">`nameof`Wyrażenie generuje stałą typu String, która pasuje do nazwy w źródle dla niemal każdej konstrukcji języka F # w źródle.</span><span class="sxs-lookup"><span data-stu-id="dc1f6-104">The `nameof` expression produces a string constant that matches the name in source for nearly any F# construct in source.</span></span>

## <a name="syntax"></a><span data-ttu-id="dc1f6-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="dc1f6-105">Syntax</span></span>

```fsharp
nameof symbol
nameof<'TGeneric>
```

## <a name="remarks"></a><span data-ttu-id="dc1f6-106">Uwagi</span><span class="sxs-lookup"><span data-stu-id="dc1f6-106">Remarks</span></span>

<span data-ttu-id="dc1f6-107">`nameof` działa przez rozpoznanie symbolicznego symbolu i tworzy nazwę tego symbolu, ponieważ jest on zadeklarowany w kodzie źródłowym.</span><span class="sxs-lookup"><span data-stu-id="dc1f6-107">`nameof` works by resolving the symbol passed to it and produces the name of that symbol as it is declared in your source code.</span></span> <span data-ttu-id="dc1f6-108">Jest to przydatne w różnych scenariuszach, takich jak rejestrowanie i ochrona rejestrowania przed zmianami w kodzie źródłowym.</span><span class="sxs-lookup"><span data-stu-id="dc1f6-108">This is useful in various scenarios, such as logging, and protects your logging against changes in source code.</span></span>

```fsharp
let months =
    [
        "January"; "February"; "March"; "April";
        "May"; "June"; "July"; "August"; "September";
        "October"; "November"; "December"
    ]

let lookupMonth month =
    if (month > 12 || month < 1) then
        invalidArg (nameof month) ($"Value passed in was %d{month}.")

    months.[month-1]

printfn "%s" (lookupMonth 12)
printfn "%s" (lookupMonth 1)
printfn "%s" (lookupMonth 13)
```

<span data-ttu-id="dc1f6-109">Ostatni wiersz zgłosi wyjątek i `"month"` zostanie wyświetlony w komunikacie o błędzie.</span><span class="sxs-lookup"><span data-stu-id="dc1f6-109">The last line will throw an exception and `"month"` will be shown in the error message.</span></span>

<span data-ttu-id="dc1f6-110">Można przyjąć nazwę niemal każdej konstrukcji F #:</span><span class="sxs-lookup"><span data-stu-id="dc1f6-110">You can take a name of nearly every F# construct:</span></span>

```fsharp
module M =
    let f x = nameof x

printfn $"{(M.f 12)]}"
printfn $"{(nameof M)}"
printfn $"{(nameof M.f)}"
```

<span data-ttu-id="dc1f6-111">`nameof` nie jest funkcją pierwszej klasy i nie można jej użyć.</span><span class="sxs-lookup"><span data-stu-id="dc1f6-111">`nameof` is not a first-class function and cannot be used as such.</span></span> <span data-ttu-id="dc1f6-112">Oznacza to, że nie można go częściowo zastosować, a wartości nie mogą być potokowe za pomocą operatorów potoku języka F #.</span><span class="sxs-lookup"><span data-stu-id="dc1f6-112">That means it cannot be partially applied and values cannot be piped into it via F# pipeline operators.</span></span>

## <a name="nameof-on-operators"></a><span data-ttu-id="dc1f6-113">Nameof na operatorach</span><span class="sxs-lookup"><span data-stu-id="dc1f6-113">Nameof on operators</span></span>

<span data-ttu-id="dc1f6-114">Operatory w języku F # mogą być używane na dwa sposoby jako tekst operatora lub symbol reprezentujący skompilowany formularz.</span><span class="sxs-lookup"><span data-stu-id="dc1f6-114">Operators in F# can be used in two ways, as an operator text itself, or a symbol representing the compiled form.</span></span> <span data-ttu-id="dc1f6-115">`nameof` w operatorze zostanie wygenerowane nazwisko operatora, ponieważ jest on zadeklarowany w źródle.</span><span class="sxs-lookup"><span data-stu-id="dc1f6-115">`nameof` on an operator will produce the name of the operator as it is declared in source.</span></span> <span data-ttu-id="dc1f6-116">Aby uzyskać skompilowaną nazwę, użyj skompilowanej nazwy w źródle:</span><span class="sxs-lookup"><span data-stu-id="dc1f6-116">To get the compiled name, use the compiled name in source:</span></span>

```fsharp
nameof(+) // "+"
nameof op_Addition // "op_Addition"
```

## <a name="nameof-on-generics"></a><span data-ttu-id="dc1f6-117">Nameof na typach ogólnych</span><span class="sxs-lookup"><span data-stu-id="dc1f6-117">Nameof on generics</span></span>

<span data-ttu-id="dc1f6-118">Można również przyjąć nazwę parametru typu ogólnego, ale składnia jest różna:</span><span class="sxs-lookup"><span data-stu-id="dc1f6-118">You can also take a name of a generic type parameter, but the syntax is different:</span></span>

```fsharp
let f<'a> () = nameof<'a>
f() // "a"
```

<span data-ttu-id="dc1f6-119">`nameof<'TGeneric>` przyjmuje nazwę symbolu, zgodnie z definicją w źródle, a nie nazwę typu zastępują w miejscu wywołania.</span><span class="sxs-lookup"><span data-stu-id="dc1f6-119">`nameof<'TGeneric>` will take the name of the symbol as defined in source, not the name of the type substituted at a call site.</span></span>

<span data-ttu-id="dc1f6-120">Przyczyna, dlaczego Składnia różni się od innych wewnętrznych operatorów F #, takich jak `typeof<>` i `typedefof<>` .</span><span class="sxs-lookup"><span data-stu-id="dc1f6-120">The reason why the syntax is different is to align with other F# intrinsic operators like `typeof<>` and `typedefof<>`.</span></span> <span data-ttu-id="dc1f6-121">To sprawia, że F # w odniesieniu do operatorów, które działają na typach ogólnych i innych elementów w źródle.</span><span class="sxs-lookup"><span data-stu-id="dc1f6-121">This makes F# consistent with respect to operators that act on generic types and anything else in source.</span></span>

## <a name="nameof-in-pattern-matching"></a><span data-ttu-id="dc1f6-122">Nameof we wzorcu dopasowania</span><span class="sxs-lookup"><span data-stu-id="dc1f6-122">Nameof in pattern matching</span></span>

<span data-ttu-id="dc1f6-123">[ `nameof` Wzorzec](pattern-matching.md#nameof-pattern) pozwala używać `nameof` w wyrażeniach dopasowania do wzorca, takich jak:</span><span class="sxs-lookup"><span data-stu-id="dc1f6-123">The [`nameof` pattern](pattern-matching.md#nameof-pattern) lets you use `nameof` in a pattern match expression like so:</span></span>

```fsharp
let f (str: string) =
    match str with
    | nameof str -> "It's 'str'!"
    | _ -> "It is not 'str'!"

f "str" // matches
f "asdf" // does not match
```
