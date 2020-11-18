---
title: Ciągi interpolowane
description: 'Dowiedz się więcej o ciągach interpolowanych, specjalnej formie ciągu, która umożliwia osadzanie wyrażeń F # bezpośrednio wewnątrz nich.'
ms.date: 11/12/2020
ms.openlocfilehash: a49d4e743306fd9bdabb1e019ec4e6c77e0e1f5a
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/17/2020
ms.locfileid: "94688609"
---
# <a name="interpolated-strings"></a>Ciągi interpolowane

Ciągi interpolowane są [ciągami](strings.md) , które umożliwiają osadzenie w nich wyrażeń F #. Są one przydatne w szerokim zakresie scenariuszy, w których wartość ciągu może się zmieniać w zależności od wyniku wartości lub wyrażenia.

## <a name="syntax"></a>Składnia

```fsharp
$"string-text {expr}"
$"string-text %format-specifier{expr}"
$"""string-text {"embedded string literal"}"""
```

## <a name="remarks"></a>Uwagi

Ciągi interpolowane pozwalają pisać kod w "dziurach" wewnątrz literału ciągu. Poniżej przedstawiono prosty przykład:

```fsharp
let name = "Phillip"
let age = 30
printfn $"Name: {name}, Age: {age}"

printfn $"I think {3.0 + 0.14} is close to {System.Math.PI}!"
```

Zawartość między każdą `{}` parą nawiasów klamrowych może być dowolnym wyrażeniem języka F #.

Aby wypróbować `{}` parę nawiasów klamrowych, napisz dwa z nich, tak aby:

```fsharp
let str = $"A pair of braces: {{}}"
// "A pair of braces: {}"
```

## <a name="typed-interpolated-strings"></a>Wpisane ciągi interpolowane

Ciągi interpolowane mogą także mieć specyfikatory formatu języka F #, aby wymusić bezpieczny typ.

```fsharp
let name = "Phillip"
let age = 30

printfn $"Name: %s{name}, Age: %d{age}"

// Error: type mismatch
printfn $"Name: %s{age}, Age: %d{name}"
```

W poprzednim przykładzie kod przeszedł w sposób nieprzekazywany do `age` wartości, gdzie `name` powinien być i na odwrót. Ponieważ interpolowane ciągi używają specyfikatorów formatu, jest to błąd kompilacji, a nie w przypadku niewielkiej usterki środowiska uruchomieniowego.

Wszystkie specyfikatory formatu omówione w formacie [zwykłego tekstu](plaintext-formatting.md) są prawidłowe w ciągu interpolowanym.

## <a name="verbatim-interpolated-strings"></a>Verbatim ciągi interpolowane

Język F # obsługuje Verbatim interpolowane ciągi z potrójnymi cudzysłowami, aby można było osadzić literały ciągu.

```fsharp
let age = 30

printfn $"""Name: {"Phillip"}, Age: %d{age}"""
```

## <a name="aligning-expressions-in-interpolated-strings"></a>Wyrównywanie wyrażeń w ciągach interpolowanych

Wyrażenia można wyrównać lub wyrównać do lewej w ciągach interpolowanych z `|` i specyfikacją liczby spacji. Następujący ciąg interpolowany wyrównuje lewe i prawe wyrażenie do lewej i prawej, odpowiednio, o 7 spacji.

```fsharp
printfn $"""|{"Left",-7}|{"Right",7}|"""
// |Left   |  Right|
```

## <a name="interpolated-strings-and-formattablestring-formatting"></a>Ciągi i formatowanie interpolowane `FormattableString`

Można również zastosować formatowanie zgodne z regułami dla <xref:System.FormattableString> :

```fsharp
let speedOfLight = 299792.458
printfn $"The speed of light is {speedOfLight:N3} km/s."
// "The speed of light is 299,792.458 km/s."
```

Dodatkowo ciąg interpolowany może być również typechecked jako <xref:System.FormattableString> za pośrednictwem adnotacji typu:

```fsharp
let frmtStr = $"The speed of light is {speedOfLight:N3} km/s." : FormattableString
// Type: FormattableString
// The speed of light is 299,792.458 km/s.
```

Należy zauważyć, że adnotacja typu musi znajdować się w wyrażeniu ciągu interpolowanego. Język F # nie konwertuje niejawnie ciągu interpolowanego na <xref:System.FormattableString> .

## <a name="see-also"></a>Zobacz także

* [Ciągi](strings.md)
