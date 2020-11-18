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
# <a name="nameof"></a>Nameof

`nameof`Wyrażenie generuje stałą typu String, która pasuje do nazwy w źródle dla niemal każdej konstrukcji języka F # w źródle.

## <a name="syntax"></a>Składnia

```fsharp
nameof symbol
nameof<'TGeneric>
```

## <a name="remarks"></a>Uwagi

`nameof` działa przez rozpoznanie symbolicznego symbolu i tworzy nazwę tego symbolu, ponieważ jest on zadeklarowany w kodzie źródłowym. Jest to przydatne w różnych scenariuszach, takich jak rejestrowanie i ochrona rejestrowania przed zmianami w kodzie źródłowym.

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

Ostatni wiersz zgłosi wyjątek i `"month"` zostanie wyświetlony w komunikacie o błędzie.

Można przyjąć nazwę niemal każdej konstrukcji F #:

```fsharp
module M =
    let f x = nameof x

printfn $"{(M.f 12)]}"
printfn $"{(nameof M)}"
printfn $"{(nameof M.f)}"
```

`nameof` nie jest funkcją pierwszej klasy i nie można jej użyć. Oznacza to, że nie można go częściowo zastosować, a wartości nie mogą być potokowe za pomocą operatorów potoku języka F #.

## <a name="nameof-on-operators"></a>Nameof na operatorach

Operatory w języku F # mogą być używane na dwa sposoby jako tekst operatora lub symbol reprezentujący skompilowany formularz. `nameof` w operatorze zostanie wygenerowane nazwisko operatora, ponieważ jest on zadeklarowany w źródle. Aby uzyskać skompilowaną nazwę, użyj skompilowanej nazwy w źródle:

```fsharp
nameof(+) // "+"
nameof op_Addition // "op_Addition"
```

## <a name="nameof-on-generics"></a>Nameof na typach ogólnych

Można również przyjąć nazwę parametru typu ogólnego, ale składnia jest różna:

```fsharp
let f<'a> () = nameof<'a>
f() // "a"
```

`nameof<'TGeneric>` przyjmuje nazwę symbolu, zgodnie z definicją w źródle, a nie nazwę typu zastępują w miejscu wywołania.

Przyczyna, dlaczego Składnia różni się od innych wewnętrznych operatorów F #, takich jak `typeof<>` i `typedefof<>` . To sprawia, że F # w odniesieniu do operatorów, które działają na typach ogólnych i innych elementów w źródle.

## <a name="nameof-in-pattern-matching"></a>Nameof we wzorcu dopasowania

[ `nameof` Wzorzec](pattern-matching.md#nameof-pattern) pozwala używać `nameof` w wyrażeniach dopasowania do wzorca, takich jak:

```fsharp
let f (str: string) =
    match str with
    | nameof str -> "It's 'str'!"
    | _ -> "It is not 'str'!"

f "str" // matches
f "asdf" // does not match
```
