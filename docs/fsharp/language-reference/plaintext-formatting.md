---
title: Formatowanie zwykłego tekstu
description: 'Dowiedz się, jak używać printf i innego formatowania zwykłego tekstu w aplikacjach i skryptach w języku F #.'
ms.date: 07/22/2020
ms.openlocfilehash: 6b14633e074961757d0f0cd258d1b1667f5fd8ee
ms.sourcegitcommit: c37e8d4642fef647ebab0e1c618ecc29ddfe2a0f
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/06/2020
ms.locfileid: "87854922"
---
# <a name="plain-text-formatting"></a>Formatowanie zwykłego tekstu

Język F # obsługuje formatowanie tekstu z tekstem sprawdzonym przy `printf` użyciu `printfn` funkcji,, `sprintf` i pokrewnych.
Przykład:

```console
dotnet fsi

> printfn "Hello %s, %d + %d is %d" "world" 2 2 (2+2);;
```

zwraca dane wyjściowe

```fsharp
Hello world, 2 + 2 is 4
```

Język F # umożliwia także formatowanie wartości w postaci zwykłego tekstu.
Rozważmy na przykład poniższy przykład, który sformatuje dane wyjściowe jako sposób wyświetlania spójnych tablic.

```console
dotnet fsi

> printfn "%A" [ for i in 1 .. 5 -> [ for j in 1 .. 5 -> (i, j) ] ];;

[[(1, 1); (1, 2); (1, 3); (1, 4); (1, 5)];
 [(2, 1); (2, 2); (2, 3); (2, 4); (2, 5)];
 [(3, 1); (3, 2); (3, 3); (3, 4); (3, 5)];
 [(4, 1); (4, 2); (4, 3); (4, 4); (4, 5)];
 [(5, 1); (5, 2); (5, 3); (5, 4); (5, 5)]]
```

Formatowanie ze strukturą zwykłego tekstu jest uaktywniane, gdy używasz `%A` formatu `printf` formatowania ciągów.
Jest on również aktywowany podczas formatowania danych wyjściowych wartości w języku F # Interactive, gdzie dane wyjściowe zawierają dodatkowe informacje i są dodatkowo dostosowywane.
Formatowanie zwykłego tekstu jest również zauważalne przez wszelkie wywołania do `x.ToString()` wartości Unii i rekordów w języku F #, w tym te, które występują niejawnie w debugowaniu, rejestrowaniu i innych narzędziach.

## <a name="checking-of-printf-format-strings"></a>Sprawdzanie `printf` ciągów formatowania

Jeśli `printf` Funkcja formatowania jest używana z argumentem, który nie pasuje do specyfikatorów formatu printf w ciągu formatu, zostanie zgłoszony błąd czasu kompilacji.  Przykład:

```fsharp
sprintf "Hello %s" (2+2)
```

zwraca dane wyjściowe

```console
  sprintf "Hello %s" (2+2)
  ----------------------^

stdin(3,25): error FS0001: The type 'string' does not match the type 'int'
```

Mówiąc technicznie, w przypadku korzystania z `printf` i innych powiązanych funkcji, specjalna reguła w kompilatorze F # sprawdza literał ciągu przekazane jako ciąg formatu, upewniając się, że kolejne argumenty są poprawne, aby odpowiadały użytym specyfikatorom formatu.

## <a name="format-specifiers-for-printf"></a>Specyfikatory formatu dla`printf`

Specyfikacje formatu dla `printf` formatów są ciągami ze `%` znacznikami wskazującymi format. Symbole zastępcze formatu składają się z lokalizacji, w `%[flags][width][.precision][type]` której typ jest interpretowany w następujący sposób:

| Specyfikator formatu   | Liczba typów:        | Uwagi                      |
|:-------------------|:---------------|:-----------------------------|
| `%b`               | wartość logiczna      | Sformatowane jako `true` lub`false`                |
| `%s`               | ciąg    | Sformatowana jako niezmieniona zawartość         |
| `%c`               | char      | Sformatowane jako literał znakowy  |
| `%d`, `%i`         | podstawowy typ Integer | Sformatowana jako dziesiętna liczba całkowita, podpisana, jeśli podstawowy typ Integer jest podpisany |
| `%u`               | podstawowy typ Integer | Sformatowane jako liczba całkowita dziesiętna bez znaku   |
| `%x`, `%X`         | podstawowy typ Integer | Sformatowana jako niepodpisana liczba szesnastkowa (a-f lub A-F dla cyfr szesnastkowych)  |
|  `%o`              | podstawowy typ Integer | Sformatowane jako liczba ósemkowa bez znaku |
| `%e`, `%E`         | podstawowy typ zmiennoprzecinkowy | Sformatowana jako wartość ze znakiem, która ma postać, `[-]d.dddde[sign]ddd` gdzie d jest pojedynczą cyfrą dziesiętną, dddd ma jedną lub więcej cyfr dziesiętnych, DDD ma dokładnie trzy cyfry dziesiętne, a znak jest `+` lub`-` |
| `%f`               | podstawowy typ zmiennoprzecinkowy | Sformatowana jako podpisana wartość mająca postać `[-]dddd.dddd` , gdzie `dddd` jest co najmniej jedną cyfrą dziesiętną. Liczba cyfr przed punktem dziesiętnym zależy od wielkości liczby, a liczba cyfr po przecinku jest zależna od wymaganej precyzji. |
| `%g`, `%G` | podstawowy typ zmiennoprzecinkowy |  Sformatowana przy użyciu jako wartości ze znakiem `%f` `%e` , która jest drukowana w formacie lub format, w zależności od tego, co jest bardziej zwarte dla danej wartości i dokładności. |
| `%M` | `System.Decimal`wartość  |    Sformatowane przy użyciu `"G"` specyfikatora formatu dla`System.Decimal.ToString(format)` |
| `%O` | dowolna wartość  |   Sformatowana przez opakowanie obiektu i wywołanie jego `System.Object.ToString()` metody |
| `%A` | dowolna wartość  |   Sformatowane przy użyciu [zwykłego formatowania tekstu strukturalnego](plaintext-formatting.md) z domyślnymi ustawieniami układu |
| `%a` | dowolna wartość  |   Wymaga dwóch argumentów: funkcja formatowania akceptująca parametr kontekstowy i wartość oraz określoną wartość do wydrukowania |
| `%t` | dowolna wartość  |   Wymaga jednego argumentu: funkcja formatowania akceptująca parametr kontekstowy, który wyprowadza lub zwraca odpowiedni tekst |

Podstawowe typy całkowite to `byte` ( `System.Byte` ), (), (), `sbyte` `System.SByte` `int16` `System.Int16` `uint16` ( `System.UInt16` ), `int32` `System.Int32` `uint32` `System.UInt32` `int64` `System.Int64` `uint64` `System.UInt64` `nativeint` `System.IntPtr` `unativeint` `System.UIntPtr` (), (), (), (), () i ().
Podstawowe typy zmiennoprzecinkowe to `float` ( `System.Double` ) i `float32` ( `System.Single` ).

Opcjonalna szerokość jest liczbą całkowitą wskazującą minimalną szerokość wyniku. Na przykład program `%6d` drukuje liczbę całkowitą, dodając prefiks do spacji, aby wypełnić co najmniej sześć znaków. Jeśli szerokość to `*` , wówczas do określenia odpowiedniej szerokości zostanie podjęta dodatkowa wartość argumentu.

Prawidłowe flagi to:

| Flaga   | Efekt        | Uwagi                      |
|:-------------------|:---------------|:-----------------------------|
| `0`  | Dodaj zera zamiast spacji, aby wprowadzić wymaganą szerokość |    |
| `-` |  Wyrównaj do lewej wynik w podanej szerokości |   |
| `+`  | Dodaj `+` znak, jeśli liczba jest dodatnia (aby dopasować `-` znak dla wartości ujemnych) |   |
| znak spacji | Dodaj dodatkowe miejsce, jeśli liczba jest dodatnia (aby dopasować znak "-" dla wartości ujemnych) |

Flaga printf `#` jest nieprawidłowa i zostanie zgłoszony błąd czasu kompilacji, jeśli jest używany.

Wartości są formatowane przy użyciu niezmiennej kultury. Ustawienia kultury nie mają znaczenia dla `printf` formatowania, chyba że mają wpływ na wyniki `%O` i `%A` Formatowanie. Aby uzyskać więcej informacji, zobacz [strukturalne formatowanie zwykłego tekstu](plaintext-formatting.md).

## <a name="a-formatting"></a>`%A`Grubi

`%A`Specyfikator formatu jest używany do formatowania wartości w sposób czytelny dla człowieka i może być również przydatny do raportowania informacji diagnostycznych.

### <a name="primitive-values"></a>Wartości pierwotne

Podczas formatowania zwykłego tekstu przy użyciu `%A` specyfikatora wartości liczbowe języka F # są formatowane przy użyciu ich sufiksu i niezmiennej kultury. Wartości zmiennoprzecinkowe są formatowane przy użyciu 10 miejsc dokładności zmiennoprzecinkowej. Przykład:

```fsharp
printfn "%A" (1L, 3n, 5u, 7, 4.03f, 5.000000001, 5.0000000001)
```

Wyświetla

```console
(1L, 3n, 5u, 7, 4.03000021f, 5.000000001, 5.0)
```

Używając `%A` specyfikatora, ciągi są formatowane przy użyciu cudzysłowów. Kody ucieczki nie są dodawane i zamiast nich są drukowane znaki RAW. Przykład:

```fsharp
printfn "%A" ("abc", "a\tb\nc\"d")

```

Wyświetla

```console
("abc", "a      b
c"d")
```

### <a name="net-values"></a>Wartości .NET

Podczas formatowania zwykłego tekstu przy użyciu `%A` specyfikatora obiekty programu .NET w języku innym niż F # są formatowane przy użyciu `x.ToString()` ustawień domyślnych platformy .NET określonych przez `System.Globalization.CultureInfo.CurrentCulture` i `System.Globalization.CultureInfo.CurrentUICulture` .  Przykład:

```fsharp
open System.Globalization

let date = System.DateTime(1999, 12, 31)

CultureInfo.CurrentCulture <- CultureInfo.GetCultureInfo("de-DE")
printfn "Culture 1: %A" date

CultureInfo.CurrentCulture <- CultureInfo.GetCultureInfo("en-US")
printfn "Culture 2: %A" date
```

Wyświetla

```console
Culture 1: 31.12.1999 00:00:00
Culture 2: 12/31/1999 12:00:00 AM
```

### <a name="structured-values"></a>Wartości strukturalne

Podczas formatowania zwykłego tekstu przy użyciu `%A` specyfikatora, wcięcie bloku jest używane dla list i krotek języka F #. Pokazano to w poprzednim przykładzie.
Struktura tablic jest również używana, w tym wielowymiarowych tablic.  Tablice jednowymiarowe są wyświetlane ze `[| ... |]` składnią. Przykład:

```fsharp
printfn "%A" [| for i in 1 .. 20 -> (i, i*i) |]
```

Wyświetla

```console
[|(1, 1); (2, 4); (3, 9); (4, 16); (5, 25); (6, 36); (7, 49); (8, 64); (9, 81);
  (10, 100); (11, 121); (12, 144); (13, 169); (14, 196); (15, 225); (16, 256);
  (17, 289); (18, 324); (19, 361); (20, 400)|]
```

Domyślna szerokość drukowania to 80.  Tę Szerokość można dostosować przy użyciu szerokości wydruku w specyfikatorze formatu. Przykład:

```fsharp
printfn "%10A" [| for i in 1 .. 5 -> (i, i*i) |]

printfn "%20A" [| for i in 1 .. 5 -> (i, i*i) |]

printfn "%50A" [| for i in 1 .. 5 -> (i, i*i) |]
```

Wyświetla

```console
[|(1, 1);
  (2, 4);
  (3, 9);
  (4, 16);
  (5, 25)|]
[|(1, 1); (2, 4);
  (3, 9); (4, 16);
  (5, 25)|]
[|(1, 1); (2, 4); (3, 9); (4, 16); (5, 25)|]
```

Określanie szerokości wydruku 0 spowoduje, że nie jest używana szerokość wydruku. Zostanie wyznaczony pojedynczy wiersz tekstu, z wyjątkiem tego, gdzie osadzone ciągi w danych wyjściowych zawierają podziały wierszy.  Na przykład

```fsharp
printfn "%0A" [| for i in 1 .. 5 -> (i, i*i) |]

printfn "%0A" [| for i in 1 .. 5 -> "abc\ndef" |]
```

Wyświetla

```console
[|(1, 1); (2, 4); (3, 9); (4, 16); (5, 25)|]
[|"abc
def"; "abc
def"; "abc
def"; "abc
def"; "abc
def"|]
```

Limit głębokości 4 jest używany dla wartości Sequence ( `IEnumerable` ), które są wyświetlane jako `seq { ...}` . W przypadku wartości list i tablic jest używany limit głębokości 100.
Przykład:

```fsharp
printfn "%A" (seq { for i in 1 .. 10 -> (i, i*i) })
```

Wyświetla

```console
seq [(1, 1); (2, 4); (3, 9); (4, 16); ...]
```

Wcięcie bloku jest również używane dla struktury rekordu publicznego i wartości Unii. Przykład:

```fsharp
type R = { X : int list; Y : string list }

printfn "%A" { X =  [ 1;2;3 ]; Y = ["one"; "two"; "three"] }
```

Wyświetla

```console
{ X = [1; 2; 3]
  Y = ["one"; "two"; "three"] }
```

Jeśli `%+A` jest używany, prywatna struktura rekordów i Unii jest również ujawniana przy użyciu odbicia. Na przykład

```fsharp
type internal R =
    { X : int list; Y : string list }
    override _.ToString() = "R"

let internal data = { X = [ 1;2;3 ]; Y = ["one"; "two"; "three"] }

printfn "external view:\n%A" data

printfn "internal view:\n%+A" data

```

Wyświetla

```console
external view:
R

internal view:
{ X = [1; 2; 3]
  Y = ["one"; "two"; "three"] }
```

### <a name="large-cyclic-or-deeply-nested-values"></a>Duże, cykliczne lub głęboko zagnieżdżone wartości

Duże wartości strukturalne są sformatowane do maksymalnej ogólnej liczby węzłów obiektów 10000.
Głęboko zagnieżdżone wartości są sformatowane do głębokości 100.  W obu przypadkach `...` jest używany do Elide niektórych danych wyjściowych.  Przykład:

```fsharp
type Tree =
    | Tip
    | Node of Tree * Tree

let rec make n =
    if n = 0 then
        Tip
    else
        Node(Tip, make (n-1))

printfn "%A" (make 1000)
```

tworzy duże dane wyjściowe z opuszczony Konstruktor kopiujący części:

```console
Node(Tip, Node(Tip, ....Node (..., ...)...))
```

Na wykresach obiektów są wykrywane cykle, które są `...` używane w miejscach, w których wykryto cykle. Na przykład

```fsharp
type R = { mutable Links: R list }
let r = { Links = [] }
r.Links <- [r]
printfn "%A" r
```

Wyświetla

```console
{ Links = [...] }
```

### <a name="lazy-null-and-function-values"></a>Wartości z opóźnieniem, wartością null i funkcją

Wartości opóźnione są drukowane jako `Value is not created` lub równoważne tekst, gdy wartość nie została jeszcze oceniona.

Wartości null są drukowane jako, `null` chyba że typ statyczny wartości jest określony jako typ złożenia, gdzie `null` jest dozwolonym reprezentacją.

Wartości funkcji języka F # są drukowane jako ich wewnętrznie wygenerowane nazwy zamknięcia, na przykład `<fun:it@43-7>` .

### <a name="customize-plain-text-formatting-with-structuredformatdisplay"></a>Dostosuj formatowanie zwykłego tekstu za pomocą`StructuredFormatDisplay`

W przypadku korzystania ze `%A` specyfikatora `StructuredFormatDisplay` jest przestrzegana obecność atrybutu w deklaracjach typu.  Służy do określania tekstu zastępczego i właściwości w celu wyświetlenia wartości. Na przykład:

```fsharp
[<StructuredFormatDisplay("Counts({Clicks})")>]
type Counts = { Clicks:int list}

printfn "%20A" {Clicks=[0..20]}
```

Wyświetla

```console
Counts([0; 1; 2; 3;
        4; 5; 6; 7;
        8; 9; 10; 11;
        12; 13; 14;
        15; 16; 17;
        18; 19; 20])
```

### <a name="customize-plain-text-formatting-by-overriding-tostring"></a>Dostosowywanie formatowania zwykłego tekstu przez zastępowanie`ToString`

Domyślna implementacja programu `ToString` jest zauważalna w programowaniu języka F #. Często domyślne wyniki nie są odpowiednie do użycia w przypadku wyświetlania informacji lub danych wyjściowych przez programistę, a w związku z tym często przesłonić implementację domyślną.  

Domyślnie rekordy i typy Unii języka F # zastępują implementację programu `ToString` z implementacją używaną przez program `sprintf "%+A"` .  Przykład:

```fsharp
type Counts = { Clicks:int list }

printfn "%s" ({Clicks=[0..10]}.ToString())
```

Wyświetla

```console
{ Clicks = [0; 1; 2; 3; 4; 5; 6; 7; 8; 9; 10] }
```

W przypadku typów klas nie `ToString` jest dostępna domyślna implementacja i jest używana wartość domyślna platformy .NET, która wyświetla nazwę typu. Przykład:

```fsharp
type MyClassType(clicks: int list) =
   member _.Clicks = clicks

let data = [ MyClassType([1..5]); MyClassType([1..5]) ]
printfn "Default structured print gives this:\n%A" data
printfn "Default ToString gives:\n%s" (data.ToString())
```

Wyświetla

```console
Default structured print gives this:
[MyClassType; MyClassType]
Default ToString gives:
[MyClassType; MyClassType]
```

Dodanie przesłonięcia dla programu `ToString` może zapewnić lepsze formatowanie.

```fsharp
type MyClassType(clicks: int list) =
   member _.Clicks = clicks
   override _.ToString() = sprintf "MyClassType(%0A)" clicks

let data = [ MyClassType([1..5]); MyClassType([1..5]) ]
printfn "Now structured print gives this:\n%A" data
printfn "Now ToString gives:\n%s" (data.ToString())
```

Wyświetla

```console
Now structured print gives this:
[MyClassType([1; 2; 3; 4; 5]); MyClassType([1; 2; 3; 4; 5])]
Now ToString gives:
[MyClassType([1; 2; 3; 4; 5]); MyClassType([1; 2; 3; 4; 5])]
```

## <a name="f-interactive-structured-printing"></a>F# Interactive drukowanie strukturalne

F# Interactive ( `dotnet fsi` ) używa rozszerzonej wersji strukturalnego formatowania tekstu do raportowania wartości i zezwala na dodatkowe szerszym. Aby uzyskać więcej informacji, zobacz [F# Interactive](fsharp-interactive-options.md).

## <a name="customize-debug-displays"></a>Dostosowywanie ekranów debugowania

Debugery dla platformy .NET respektują użycie atrybutów, takich jak `DebuggerDisplay` i `DebuggerTypeProxy` , i mają wpływ na strukturę wyświetlania obiektów w oknach inspekcji debugera.
Kompilator F # automatycznie wygenerował te atrybuty dla typu Unii rozłącznych i typów rekordów, ale nie klasy, interfejsu lub struktury.

Te atrybuty są ignorowane w formacie zwykłego tekstu F #, ale mogą być przydatne do wdrożenia tych metod w celu usprawnienia wyświetlania podczas debugowania typów F #.

## <a name="see-also"></a>Zobacz także

- [Ciągi](strings.md)
- [Rekordy](records.md)
- [Sumy rozłączne](discriminated-unions.md)
- [F# Interactive](fsharp-interactive-options.md)
