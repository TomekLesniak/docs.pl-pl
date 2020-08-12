---
title: Format zwykłego tekstu
description: 'Dowiedz się, jak używać printf i innego formatowania zwykłego tekstu w aplikacjach i skryptach w języku F #.'
ms.date: 07/22/2020
ms.openlocfilehash: 90a861736dae69dfbc199a19e24f587c42404737
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/11/2020
ms.locfileid: "88063786"
---
# <a name="plain-text-formatting"></a><span data-ttu-id="7300b-103">Formatowanie zwykłego tekstu</span><span class="sxs-lookup"><span data-stu-id="7300b-103">Plain text formatting</span></span>

<span data-ttu-id="7300b-104">Język F # obsługuje formatowanie tekstu z tekstem sprawdzonym przy `printf` użyciu `printfn` funkcji,, `sprintf` i pokrewnych.</span><span class="sxs-lookup"><span data-stu-id="7300b-104">F# supports type-checked formatting of plain text using `printf`, `printfn`, `sprintf`, and related functions.</span></span>
<span data-ttu-id="7300b-105">Przykład:</span><span class="sxs-lookup"><span data-stu-id="7300b-105">For example,</span></span>

```console
dotnet fsi

> printfn "Hello %s, %d + %d is %d" "world" 2 2 (2+2);;
```

<span data-ttu-id="7300b-106">zwraca dane wyjściowe</span><span class="sxs-lookup"><span data-stu-id="7300b-106">gives the output</span></span>

```fsharp
Hello world, 2 + 2 is 4
```

<span data-ttu-id="7300b-107">Język F # umożliwia także formatowanie wartości w postaci zwykłego tekstu.</span><span class="sxs-lookup"><span data-stu-id="7300b-107">F# also allows structured values to be formatted as plain text.</span></span>
<span data-ttu-id="7300b-108">Rozważmy na przykład poniższy przykład, który sformatuje dane wyjściowe jako sposób wyświetlania spójnych tablic.</span><span class="sxs-lookup"><span data-stu-id="7300b-108">For example, consider the following example that formats the output as a matrix-like display of tuples.</span></span>

```console
dotnet fsi

> printfn "%A" [ for i in 1 .. 5 -> [ for j in 1 .. 5 -> (i, j) ] ];;

[[(1, 1); (1, 2); (1, 3); (1, 4); (1, 5)];
 [(2, 1); (2, 2); (2, 3); (2, 4); (2, 5)];
 [(3, 1); (3, 2); (3, 3); (3, 4); (3, 5)];
 [(4, 1); (4, 2); (4, 3); (4, 4); (4, 5)];
 [(5, 1); (5, 2); (5, 3); (5, 4); (5, 5)]]
```

<span data-ttu-id="7300b-109">Formatowanie ze strukturą zwykłego tekstu jest uaktywniane, gdy używasz `%A` formatu `printf` formatowania ciągów.</span><span class="sxs-lookup"><span data-stu-id="7300b-109">Structured plain text formatting is activated when you use the `%A` format in `printf` formatting strings.</span></span>
<span data-ttu-id="7300b-110">Jest on również aktywowany podczas formatowania danych wyjściowych wartości w języku F # Interactive, gdzie dane wyjściowe zawierają dodatkowe informacje i są dodatkowo dostosowywane.</span><span class="sxs-lookup"><span data-stu-id="7300b-110">It's also activated when formatting the output of values in F# interactive, where the output includes extra information and is additionally customizable.</span></span>
<span data-ttu-id="7300b-111">Formatowanie zwykłego tekstu jest również zauważalne przez wszelkie wywołania do `x.ToString()` wartości Unii i rekordów w języku F #, w tym te, które występują niejawnie w debugowaniu, rejestrowaniu i innych narzędziach.</span><span class="sxs-lookup"><span data-stu-id="7300b-111">Plain text formatting is also observable through any calls to `x.ToString()` on F# union and record values, including those that occur implicitly in debugging, logging, and other tooling.</span></span>

## <a name="checking-of-printf-format-strings"></a><span data-ttu-id="7300b-112">Sprawdzanie `printf` ciągów formatowania</span><span class="sxs-lookup"><span data-stu-id="7300b-112">Checking of `printf`-format strings</span></span>

<span data-ttu-id="7300b-113">Jeśli `printf` Funkcja formatowania jest używana z argumentem, który nie pasuje do specyfikatorów formatu printf w ciągu formatu, zostanie zgłoszony błąd czasu kompilacji.</span><span class="sxs-lookup"><span data-stu-id="7300b-113">A compile-time error will be reported if a `printf` formatting function is used with an argument that doesn't match the printf format specifiers in the format string.</span></span>  <span data-ttu-id="7300b-114">Przykład:</span><span class="sxs-lookup"><span data-stu-id="7300b-114">For example,</span></span>

```fsharp
sprintf "Hello %s" (2+2)
```

<span data-ttu-id="7300b-115">zwraca dane wyjściowe</span><span class="sxs-lookup"><span data-stu-id="7300b-115">gives the output</span></span>

```console
  sprintf "Hello %s" (2+2)
  ----------------------^

stdin(3,25): error FS0001: The type 'string' does not match the type 'int'
```

<span data-ttu-id="7300b-116">Mówiąc technicznie, w przypadku korzystania z `printf` i innych powiązanych funkcji, specjalna reguła w kompilatorze F # sprawdza literał ciągu przekazane jako ciąg formatu, upewniając się, że kolejne argumenty są poprawne, aby odpowiadały użytym specyfikatorom formatu.</span><span class="sxs-lookup"><span data-stu-id="7300b-116">Technically speaking, when using `printf` and other related functions, a special rule in the F# compiler checks the string literal passed as the format string, ensuring the subsequent arguments applied are of the correct type to match the format specifiers used.</span></span>

## <a name="format-specifiers-for-printf"></a><span data-ttu-id="7300b-117">Specyfikatory formatu dla`printf`</span><span class="sxs-lookup"><span data-stu-id="7300b-117">Format specifiers for `printf`</span></span>

<span data-ttu-id="7300b-118">Specyfikacje formatu dla `printf` formatów są ciągami ze `%` znacznikami wskazującymi format.</span><span class="sxs-lookup"><span data-stu-id="7300b-118">Format specifications for `printf` formats are strings with `%` markers that indicate format.</span></span> <span data-ttu-id="7300b-119">Symbole zastępcze formatu składają się z lokalizacji, w `%[flags][width][.precision][type]` której typ jest interpretowany w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="7300b-119">Format placeholders consist of `%[flags][width][.precision][type]` where the type is interpreted as follows:</span></span>

| <span data-ttu-id="7300b-120">Specyfikator formatu</span><span class="sxs-lookup"><span data-stu-id="7300b-120">Format specifier</span></span>   | <span data-ttu-id="7300b-121">Liczba typów:</span><span class="sxs-lookup"><span data-stu-id="7300b-121">Type(s)</span></span>        | <span data-ttu-id="7300b-122">Uwagi</span><span class="sxs-lookup"><span data-stu-id="7300b-122">Remarks</span></span>                      |
|:-------------------|:---------------|:-----------------------------|
| `%b`               | <span data-ttu-id="7300b-123">bool</span><span class="sxs-lookup"><span data-stu-id="7300b-123">bool</span></span>      | <span data-ttu-id="7300b-124">Sformatowane jako `true` lub`false`</span><span class="sxs-lookup"><span data-stu-id="7300b-124">Formatted as `true` or `false`</span></span>                |
| `%s`               | <span data-ttu-id="7300b-125">string</span><span class="sxs-lookup"><span data-stu-id="7300b-125">string</span></span>    | <span data-ttu-id="7300b-126">Sformatowana jako niezmieniona zawartość</span><span class="sxs-lookup"><span data-stu-id="7300b-126">Formatted as its unescaped contents</span></span>         |
| `%c`               | <span data-ttu-id="7300b-127">char</span><span class="sxs-lookup"><span data-stu-id="7300b-127">char</span></span>      | <span data-ttu-id="7300b-128">Sformatowane jako literał znakowy</span><span class="sxs-lookup"><span data-stu-id="7300b-128">Formatted as the character literal</span></span>  |
| <span data-ttu-id="7300b-129">`%d`, `%i`</span><span class="sxs-lookup"><span data-stu-id="7300b-129">`%d`, `%i`</span></span>         | <span data-ttu-id="7300b-130">podstawowy typ Integer</span><span class="sxs-lookup"><span data-stu-id="7300b-130">a basic integer type</span></span> | <span data-ttu-id="7300b-131">Sformatowana jako dziesiętna liczba całkowita, podpisana, jeśli podstawowy typ Integer jest podpisany</span><span class="sxs-lookup"><span data-stu-id="7300b-131">Formatted as a decimal integer, signed if the basic integer type is signed</span></span> |
| `%u`               | <span data-ttu-id="7300b-132">podstawowy typ Integer</span><span class="sxs-lookup"><span data-stu-id="7300b-132">a basic integer type</span></span> | <span data-ttu-id="7300b-133">Sformatowane jako liczba całkowita dziesiętna bez znaku</span><span class="sxs-lookup"><span data-stu-id="7300b-133">Formatted as an unsigned decimal integer</span></span>   |
| <span data-ttu-id="7300b-134">`%x`, `%X`</span><span class="sxs-lookup"><span data-stu-id="7300b-134">`%x`, `%X`</span></span>         | <span data-ttu-id="7300b-135">podstawowy typ Integer</span><span class="sxs-lookup"><span data-stu-id="7300b-135">a basic integer type</span></span> | <span data-ttu-id="7300b-136">Sformatowana jako niepodpisana liczba szesnastkowa (a-f lub A-F dla cyfr szesnastkowych)</span><span class="sxs-lookup"><span data-stu-id="7300b-136">Formatted as an unsigned hexadecimal number (a-f or A-F for hex digits respectively)</span></span>  |
|  `%o`              | <span data-ttu-id="7300b-137">podstawowy typ Integer</span><span class="sxs-lookup"><span data-stu-id="7300b-137">a basic integer type</span></span> | <span data-ttu-id="7300b-138">Sformatowane jako liczba ósemkowa bez znaku</span><span class="sxs-lookup"><span data-stu-id="7300b-138">Formatted as an unsigned octal number</span></span> |
| <span data-ttu-id="7300b-139">`%e`, `%E`</span><span class="sxs-lookup"><span data-stu-id="7300b-139">`%e`, `%E`</span></span>         | <span data-ttu-id="7300b-140">podstawowy typ zmiennoprzecinkowy</span><span class="sxs-lookup"><span data-stu-id="7300b-140">a basic floating point type</span></span> | <span data-ttu-id="7300b-141">Sformatowana jako wartość ze znakiem, która ma postać, `[-]d.dddde[sign]ddd` gdzie d jest pojedynczą cyfrą dziesiętną, dddd ma jedną lub więcej cyfr dziesiętnych, DDD ma dokładnie trzy cyfry dziesiętne, a znak jest `+` lub`-`</span><span class="sxs-lookup"><span data-stu-id="7300b-141">Formatted as a signed value having the form `[-]d.dddde[sign]ddd` where d is a single decimal digit, dddd is one or more decimal digits, ddd is exactly three decimal digits, and sign is `+` or `-`</span></span> |
| `%f`               | <span data-ttu-id="7300b-142">podstawowy typ zmiennoprzecinkowy</span><span class="sxs-lookup"><span data-stu-id="7300b-142">a basic floating point type</span></span> | <span data-ttu-id="7300b-143">Sformatowana jako podpisana wartość mająca postać `[-]dddd.dddd` , gdzie `dddd` jest co najmniej jedną cyfrą dziesiętną.</span><span class="sxs-lookup"><span data-stu-id="7300b-143">Formatted as a signed value having the form `[-]dddd.dddd`, where `dddd` is one or more decimal digits.</span></span> <span data-ttu-id="7300b-144">Liczba cyfr przed punktem dziesiętnym zależy od wielkości liczby, a liczba cyfr po przecinku jest zależna od wymaganej precyzji.</span><span class="sxs-lookup"><span data-stu-id="7300b-144">The number of digits before the decimal point depends on the magnitude of the number, and the number of digits after the decimal point depends on the requested precision.</span></span> |
| <span data-ttu-id="7300b-145">`%g`, `%G`</span><span class="sxs-lookup"><span data-stu-id="7300b-145">`%g`, `%G`</span></span> | <span data-ttu-id="7300b-146">podstawowy typ zmiennoprzecinkowy</span><span class="sxs-lookup"><span data-stu-id="7300b-146">a basic floating point type</span></span> |  <span data-ttu-id="7300b-147">Sformatowana przy użyciu jako wartości ze znakiem `%f` `%e` , która jest drukowana w formacie lub format, w zależności od tego, co jest bardziej zwarte dla danej wartości i dokładności.</span><span class="sxs-lookup"><span data-stu-id="7300b-147">Formatted using as a signed value printed in `%f` or `%e` format, whichever is more compact for the given value and precision.</span></span> |
| `%M` | <span data-ttu-id="7300b-148">`System.Decimal`wartość</span><span class="sxs-lookup"><span data-stu-id="7300b-148">a `System.Decimal` value</span></span>  |    <span data-ttu-id="7300b-149">Sformatowane przy użyciu `"G"` specyfikatora formatu dla`System.Decimal.ToString(format)`</span><span class="sxs-lookup"><span data-stu-id="7300b-149">Formatted using the `"G"` format specifier for `System.Decimal.ToString(format)`</span></span> |
| `%O` | <span data-ttu-id="7300b-150">dowolna wartość</span><span class="sxs-lookup"><span data-stu-id="7300b-150">any value</span></span>  |   <span data-ttu-id="7300b-151">Sformatowana przez opakowanie obiektu i wywołanie jego `System.Object.ToString()` metody</span><span class="sxs-lookup"><span data-stu-id="7300b-151">Formatted by boxing the object and calling its `System.Object.ToString()` method</span></span> |
| `%A` | <span data-ttu-id="7300b-152">dowolna wartość</span><span class="sxs-lookup"><span data-stu-id="7300b-152">any value</span></span>  |   <span data-ttu-id="7300b-153">Sformatowane przy użyciu [zwykłego formatowania tekstu strukturalnego](plaintext-formatting.md) z domyślnymi ustawieniami układu</span><span class="sxs-lookup"><span data-stu-id="7300b-153">Formatted using [structured plain text formatting](plaintext-formatting.md) with the default layout settings</span></span> |
| `%a` | <span data-ttu-id="7300b-154">dowolna wartość</span><span class="sxs-lookup"><span data-stu-id="7300b-154">any value</span></span>  |   <span data-ttu-id="7300b-155">Wymaga dwóch argumentów: funkcja formatowania akceptująca parametr kontekstowy i wartość oraz określoną wartość do wydrukowania</span><span class="sxs-lookup"><span data-stu-id="7300b-155">Requires two arguments: a formatting function accepting a context parameter and the value, and the particular value to print</span></span> |
| `%t` | <span data-ttu-id="7300b-156">dowolna wartość</span><span class="sxs-lookup"><span data-stu-id="7300b-156">any value</span></span>  |   <span data-ttu-id="7300b-157">Wymaga jednego argumentu: funkcja formatowania akceptująca parametr kontekstowy, który wyprowadza lub zwraca odpowiedni tekst</span><span class="sxs-lookup"><span data-stu-id="7300b-157">Requires one argument: a formatting function accepting a context parameter that either outputs or returns the appropriate text</span></span> |
| `%%` | <span data-ttu-id="7300b-158">(brak)</span><span class="sxs-lookup"><span data-stu-id="7300b-158">(none)</span></span>  |   <span data-ttu-id="7300b-159">Nie wymaga żadnych argumentów i drukuje zwykły znak procentu:`%`</span><span class="sxs-lookup"><span data-stu-id="7300b-159">Requires no arguments and prints a plain percent sign: `%`</span></span> |

<span data-ttu-id="7300b-160">Podstawowe typy całkowite to `byte` ( `System.Byte` ), (), (), `sbyte` `System.SByte` `int16` `System.Int16` `uint16` ( `System.UInt16` ), `int32` `System.Int32` `uint32` `System.UInt32` `int64` `System.Int64` `uint64` `System.UInt64` `nativeint` `System.IntPtr` `unativeint` `System.UIntPtr` (), (), (), (), () i ().</span><span class="sxs-lookup"><span data-stu-id="7300b-160">Basic integer types are `byte` (`System.Byte`), `sbyte` (`System.SByte`), `int16` (`System.Int16`), `uint16` (`System.UInt16`), `int32` (`System.Int32`), `uint32` (`System.UInt32`), `int64` (`System.Int64`), `uint64` (`System.UInt64`), `nativeint`  (`System.IntPtr`), and `unativeint`  (`System.UIntPtr`).</span></span>
<span data-ttu-id="7300b-161">Podstawowe typy zmiennoprzecinkowe to `float` ( `System.Double` ) i `float32` ( `System.Single` ).</span><span class="sxs-lookup"><span data-stu-id="7300b-161">Basic floating point types are `float` (`System.Double`) and `float32` (`System.Single`).</span></span>

<span data-ttu-id="7300b-162">Opcjonalna szerokość jest liczbą całkowitą wskazującą minimalną szerokość wyniku.</span><span class="sxs-lookup"><span data-stu-id="7300b-162">The optional width is an integer indicating the minimal width of the result.</span></span> <span data-ttu-id="7300b-163">Na przykład program `%6d` drukuje liczbę całkowitą, dodając prefiks do spacji, aby wypełnić co najmniej sześć znaków.</span><span class="sxs-lookup"><span data-stu-id="7300b-163">For instance, `%6d` prints an integer, prefixing it with spaces to fill at least six characters.</span></span> <span data-ttu-id="7300b-164">Jeśli szerokość to `*` , wówczas do określenia odpowiedniej szerokości zostanie podjęta dodatkowa wartość argumentu.</span><span class="sxs-lookup"><span data-stu-id="7300b-164">If width is `*`, then an extra integer  argument is taken to specify the corresponding width.</span></span>

<span data-ttu-id="7300b-165">Prawidłowe flagi to:</span><span class="sxs-lookup"><span data-stu-id="7300b-165">Valid flags are:</span></span>

| <span data-ttu-id="7300b-166">Flaga</span><span class="sxs-lookup"><span data-stu-id="7300b-166">Flag</span></span>   | <span data-ttu-id="7300b-167">Efekt</span><span class="sxs-lookup"><span data-stu-id="7300b-167">Effect</span></span>        | <span data-ttu-id="7300b-168">Uwagi</span><span class="sxs-lookup"><span data-stu-id="7300b-168">Remarks</span></span>                      |
|:-------------------|:---------------|:-----------------------------|
| `0`  | <span data-ttu-id="7300b-169">Dodaj zera zamiast spacji, aby wprowadzić wymaganą szerokość</span><span class="sxs-lookup"><span data-stu-id="7300b-169">Add zeros instead of spaces to make up the required width</span></span> |    |
| `-` |  <span data-ttu-id="7300b-170">Wyrównaj do lewej wynik w podanej szerokości</span><span class="sxs-lookup"><span data-stu-id="7300b-170">Left justify the result within the specified width</span></span> |   |
| `+`  | <span data-ttu-id="7300b-171">Dodaj `+` znak, jeśli liczba jest dodatnia (aby dopasować `-` znak dla wartości ujemnych)</span><span class="sxs-lookup"><span data-stu-id="7300b-171">Add a `+` character if the number is positive (to match a `-` sign for negatives)</span></span> |   |
| <span data-ttu-id="7300b-172">znak spacji</span><span class="sxs-lookup"><span data-stu-id="7300b-172">space character</span></span> | <span data-ttu-id="7300b-173">Dodaj dodatkowe miejsce, jeśli liczba jest dodatnia (aby dopasować znak "-" dla wartości ujemnych)</span><span class="sxs-lookup"><span data-stu-id="7300b-173">Add an extra space if the number is positive (to match a '-' sign for negatives)</span></span> |

<span data-ttu-id="7300b-174">Flaga printf `#` jest nieprawidłowa i zostanie zgłoszony błąd czasu kompilacji, jeśli jest używany.</span><span class="sxs-lookup"><span data-stu-id="7300b-174">The printf `#` flag is invalid and a compile-time error will be reported if it is used.</span></span>

<span data-ttu-id="7300b-175">Wartości są formatowane przy użyciu niezmiennej kultury.</span><span class="sxs-lookup"><span data-stu-id="7300b-175">Values are formatted using invariant culture.</span></span> <span data-ttu-id="7300b-176">Ustawienia kultury nie mają znaczenia dla `printf` formatowania, chyba że mają wpływ na wyniki `%O` i `%A` Formatowanie.</span><span class="sxs-lookup"><span data-stu-id="7300b-176">Culture settings are irrelevant to `printf` formatting except when they affect the results of `%O` and `%A` formatting.</span></span> <span data-ttu-id="7300b-177">Aby uzyskać więcej informacji, zobacz [strukturalne formatowanie zwykłego tekstu](plaintext-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="7300b-177">For more information, see [structured plain text formatting](plaintext-formatting.md).</span></span>

## <a name="a-formatting"></a><span data-ttu-id="7300b-178">`%A`Grubi</span><span class="sxs-lookup"><span data-stu-id="7300b-178">`%A` formatting</span></span>

<span data-ttu-id="7300b-179">`%A`Specyfikator formatu jest używany do formatowania wartości w sposób czytelny dla człowieka i może być również przydatny do raportowania informacji diagnostycznych.</span><span class="sxs-lookup"><span data-stu-id="7300b-179">The `%A` format specifier is used to format values in a human-readable way, and can also be useful for reporting diagnostic information.</span></span>

### <a name="primitive-values"></a><span data-ttu-id="7300b-180">Wartości pierwotne</span><span class="sxs-lookup"><span data-stu-id="7300b-180">Primitive values</span></span>

<span data-ttu-id="7300b-181">Podczas formatowania zwykłego tekstu przy użyciu `%A` specyfikatora wartości liczbowe języka F # są formatowane przy użyciu ich sufiksu i niezmiennej kultury.</span><span class="sxs-lookup"><span data-stu-id="7300b-181">When formatting plain text using the `%A` specifier, F# numeric values are formatted with their suffix and invariant culture.</span></span> <span data-ttu-id="7300b-182">Wartości zmiennoprzecinkowe są formatowane przy użyciu 10 miejsc dokładności zmiennoprzecinkowej.</span><span class="sxs-lookup"><span data-stu-id="7300b-182">Floating point values are formatted using 10 places of floating point precision.</span></span> <span data-ttu-id="7300b-183">Przykład:</span><span class="sxs-lookup"><span data-stu-id="7300b-183">For example,</span></span>

```fsharp
printfn "%A" (1L, 3n, 5u, 7, 4.03f, 5.000000001, 5.0000000001)
```

<span data-ttu-id="7300b-184">Wyświetla</span><span class="sxs-lookup"><span data-stu-id="7300b-184">produces</span></span>

```console
(1L, 3n, 5u, 7, 4.03000021f, 5.000000001, 5.0)
```

<span data-ttu-id="7300b-185">Używając `%A` specyfikatora, ciągi są formatowane przy użyciu cudzysłowów.</span><span class="sxs-lookup"><span data-stu-id="7300b-185">When using the `%A` specifier, strings are formatted using quotes.</span></span> <span data-ttu-id="7300b-186">Kody ucieczki nie są dodawane i zamiast nich są drukowane znaki RAW.</span><span class="sxs-lookup"><span data-stu-id="7300b-186">Escape codes are not added and instead the raw characters are printed.</span></span> <span data-ttu-id="7300b-187">Przykład:</span><span class="sxs-lookup"><span data-stu-id="7300b-187">For example,</span></span>

```fsharp
printfn "%A" ("abc", "a\tb\nc\"d")

```

<span data-ttu-id="7300b-188">Wyświetla</span><span class="sxs-lookup"><span data-stu-id="7300b-188">produces</span></span>

```console
("abc", "a      b
c"d")
```

### <a name="net-values"></a><span data-ttu-id="7300b-189">Wartości .NET</span><span class="sxs-lookup"><span data-stu-id="7300b-189">.NET values</span></span>

<span data-ttu-id="7300b-190">Podczas formatowania zwykłego tekstu przy użyciu `%A` specyfikatora obiekty programu .NET w języku innym niż F # są formatowane przy użyciu `x.ToString()` ustawień domyślnych platformy .NET określonych przez `System.Globalization.CultureInfo.CurrentCulture` i `System.Globalization.CultureInfo.CurrentUICulture` .</span><span class="sxs-lookup"><span data-stu-id="7300b-190">When formatting plain text using the `%A` specifier, non-F# .NET objects are formatted by using `x.ToString()` using the default settings of .NET given by `System.Globalization.CultureInfo.CurrentCulture` and `System.Globalization.CultureInfo.CurrentUICulture`.</span></span>  <span data-ttu-id="7300b-191">Przykład:</span><span class="sxs-lookup"><span data-stu-id="7300b-191">For example,</span></span>

```fsharp
open System.Globalization

let date = System.DateTime(1999, 12, 31)

CultureInfo.CurrentCulture <- CultureInfo.GetCultureInfo("de-DE")
printfn "Culture 1: %A" date

CultureInfo.CurrentCulture <- CultureInfo.GetCultureInfo("en-US")
printfn "Culture 2: %A" date
```

<span data-ttu-id="7300b-192">Wyświetla</span><span class="sxs-lookup"><span data-stu-id="7300b-192">produces</span></span>

```console
Culture 1: 31.12.1999 00:00:00
Culture 2: 12/31/1999 12:00:00 AM
```

### <a name="structured-values"></a><span data-ttu-id="7300b-193">Wartości strukturalne</span><span class="sxs-lookup"><span data-stu-id="7300b-193">Structured values</span></span>

<span data-ttu-id="7300b-194">Podczas formatowania zwykłego tekstu przy użyciu `%A` specyfikatora, wcięcie bloku jest używane dla list i krotek języka F #.</span><span class="sxs-lookup"><span data-stu-id="7300b-194">When formatting plain text using the `%A` specifier, block indentation is used for F# lists and tuples.</span></span> <span data-ttu-id="7300b-195">Pokazano to w poprzednim przykładzie.</span><span class="sxs-lookup"><span data-stu-id="7300b-195">This shown in the previous example.</span></span>
<span data-ttu-id="7300b-196">Struktura tablic jest również używana, w tym wielowymiarowych tablic.</span><span class="sxs-lookup"><span data-stu-id="7300b-196">The structure of arrays is also used, including multi-dimensional arrays.</span></span>  <span data-ttu-id="7300b-197">Tablice jednowymiarowe są wyświetlane ze `[| ... |]` składnią.</span><span class="sxs-lookup"><span data-stu-id="7300b-197">Single-dimensional arrays are shown with `[| ... |]` syntax.</span></span> <span data-ttu-id="7300b-198">Przykład:</span><span class="sxs-lookup"><span data-stu-id="7300b-198">For example,</span></span>

```fsharp
printfn "%A" [| for i in 1 .. 20 -> (i, i*i) |]
```

<span data-ttu-id="7300b-199">Wyświetla</span><span class="sxs-lookup"><span data-stu-id="7300b-199">produces</span></span>

```console
[|(1, 1); (2, 4); (3, 9); (4, 16); (5, 25); (6, 36); (7, 49); (8, 64); (9, 81);
  (10, 100); (11, 121); (12, 144); (13, 169); (14, 196); (15, 225); (16, 256);
  (17, 289); (18, 324); (19, 361); (20, 400)|]
```

<span data-ttu-id="7300b-200">Domyślna szerokość drukowania to 80.</span><span class="sxs-lookup"><span data-stu-id="7300b-200">The default print width is 80.</span></span>  <span data-ttu-id="7300b-201">Tę Szerokość można dostosować przy użyciu szerokości wydruku w specyfikatorze formatu.</span><span class="sxs-lookup"><span data-stu-id="7300b-201">This width can be customized by using a print width in the format specifier.</span></span> <span data-ttu-id="7300b-202">Przykład:</span><span class="sxs-lookup"><span data-stu-id="7300b-202">For example,</span></span>

```fsharp
printfn "%10A" [| for i in 1 .. 5 -> (i, i*i) |]

printfn "%20A" [| for i in 1 .. 5 -> (i, i*i) |]

printfn "%50A" [| for i in 1 .. 5 -> (i, i*i) |]
```

<span data-ttu-id="7300b-203">Wyświetla</span><span class="sxs-lookup"><span data-stu-id="7300b-203">produces</span></span>

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

<span data-ttu-id="7300b-204">Określanie szerokości wydruku 0 spowoduje, że nie jest używana szerokość wydruku.</span><span class="sxs-lookup"><span data-stu-id="7300b-204">Specifying a print width of 0 results in no print width being used.</span></span> <span data-ttu-id="7300b-205">Zostanie wyznaczony pojedynczy wiersz tekstu, z wyjątkiem tego, gdzie osadzone ciągi w danych wyjściowych zawierają podziały wierszy.</span><span class="sxs-lookup"><span data-stu-id="7300b-205">A single line of text will result, except where embedded strings in the output contain line breaks.</span></span>  <span data-ttu-id="7300b-206">Na przykład</span><span class="sxs-lookup"><span data-stu-id="7300b-206">For example</span></span>

```fsharp
printfn "%0A" [| for i in 1 .. 5 -> (i, i*i) |]

printfn "%0A" [| for i in 1 .. 5 -> "abc\ndef" |]
```

<span data-ttu-id="7300b-207">Wyświetla</span><span class="sxs-lookup"><span data-stu-id="7300b-207">produces</span></span>

```console
[|(1, 1); (2, 4); (3, 9); (4, 16); (5, 25)|]
[|"abc
def"; "abc
def"; "abc
def"; "abc
def"; "abc
def"|]
```

<span data-ttu-id="7300b-208">Limit głębokości 4 jest używany dla wartości Sequence ( `IEnumerable` ), które są wyświetlane jako `seq { ...}` .</span><span class="sxs-lookup"><span data-stu-id="7300b-208">A depth limit of 4 is used for sequence (`IEnumerable`) values, which are shown as `seq { ...}`.</span></span> <span data-ttu-id="7300b-209">W przypadku wartości list i tablic jest używany limit głębokości 100.</span><span class="sxs-lookup"><span data-stu-id="7300b-209">A depth limit of 100 is used for list and array values.</span></span>
<span data-ttu-id="7300b-210">Przykład:</span><span class="sxs-lookup"><span data-stu-id="7300b-210">For example,</span></span>

```fsharp
printfn "%A" (seq { for i in 1 .. 10 -> (i, i*i) })
```

<span data-ttu-id="7300b-211">Wyświetla</span><span class="sxs-lookup"><span data-stu-id="7300b-211">produces</span></span>

```console
seq [(1, 1); (2, 4); (3, 9); (4, 16); ...]
```

<span data-ttu-id="7300b-212">Wcięcie bloku jest również używane dla struktury rekordu publicznego i wartości Unii.</span><span class="sxs-lookup"><span data-stu-id="7300b-212">Block indentation is also used for the structure of public record and union values.</span></span> <span data-ttu-id="7300b-213">Przykład:</span><span class="sxs-lookup"><span data-stu-id="7300b-213">For example,</span></span>

```fsharp
type R = { X : int list; Y : string list }

printfn "%A" { X =  [ 1;2;3 ]; Y = ["one"; "two"; "three"] }
```

<span data-ttu-id="7300b-214">Wyświetla</span><span class="sxs-lookup"><span data-stu-id="7300b-214">produces</span></span>

```console
{ X = [1; 2; 3]
  Y = ["one"; "two"; "three"] }
```

<span data-ttu-id="7300b-215">Jeśli `%+A` jest używany, prywatna struktura rekordów i Unii jest również ujawniana przy użyciu odbicia.</span><span class="sxs-lookup"><span data-stu-id="7300b-215">If `%+A` is used, then the private structure of records and unions is also revealed by using reflection.</span></span> <span data-ttu-id="7300b-216">Na przykład</span><span class="sxs-lookup"><span data-stu-id="7300b-216">For example</span></span>

```fsharp
type internal R =
    { X : int list; Y : string list }
    override _.ToString() = "R"

let internal data = { X = [ 1;2;3 ]; Y = ["one"; "two"; "three"] }

printfn "external view:\n%A" data

printfn "internal view:\n%+A" data

```

<span data-ttu-id="7300b-217">Wyświetla</span><span class="sxs-lookup"><span data-stu-id="7300b-217">produces</span></span>

```console
external view:
R

internal view:
{ X = [1; 2; 3]
  Y = ["one"; "two"; "three"] }
```

### <a name="large-cyclic-or-deeply-nested-values"></a><span data-ttu-id="7300b-218">Duże, cykliczne lub głęboko zagnieżdżone wartości</span><span class="sxs-lookup"><span data-stu-id="7300b-218">Large, cyclic, or deeply nested values</span></span>

<span data-ttu-id="7300b-219">Duże wartości strukturalne są sformatowane do maksymalnej ogólnej liczby węzłów obiektów 10000.</span><span class="sxs-lookup"><span data-stu-id="7300b-219">Large structured values are formatted to a maximum overall object node count of 10000.</span></span>
<span data-ttu-id="7300b-220">Głęboko zagnieżdżone wartości są sformatowane do głębokości 100.</span><span class="sxs-lookup"><span data-stu-id="7300b-220">Deeply nested values are formatted to a depth of 100.</span></span>  <span data-ttu-id="7300b-221">W obu przypadkach `...` jest używany do Elide niektórych danych wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="7300b-221">In both cases `...` is used to elide some of the output.</span></span>  <span data-ttu-id="7300b-222">Przykład:</span><span class="sxs-lookup"><span data-stu-id="7300b-222">For example,</span></span>

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

<span data-ttu-id="7300b-223">tworzy duże dane wyjściowe z opuszczony Konstruktor kopiujący części:</span><span class="sxs-lookup"><span data-stu-id="7300b-223">produces a large output with some parts elided:</span></span>

```console
Node(Tip, Node(Tip, ....Node (..., ...)...))
```

<span data-ttu-id="7300b-224">Na wykresach obiektów są wykrywane cykle, które są `...` używane w miejscach, w których wykryto cykle.</span><span class="sxs-lookup"><span data-stu-id="7300b-224">Cycles are detected in the object graphs and `...` is used at places where cycles are detected.</span></span> <span data-ttu-id="7300b-225">Na przykład</span><span class="sxs-lookup"><span data-stu-id="7300b-225">For example</span></span>

```fsharp
type R = { mutable Links: R list }
let r = { Links = [] }
r.Links <- [r]
printfn "%A" r
```

<span data-ttu-id="7300b-226">Wyświetla</span><span class="sxs-lookup"><span data-stu-id="7300b-226">produces</span></span>

```console
{ Links = [...] }
```

### <a name="lazy-null-and-function-values"></a><span data-ttu-id="7300b-227">Wartości z opóźnieniem, wartością null i funkcją</span><span class="sxs-lookup"><span data-stu-id="7300b-227">Lazy, null, and function values</span></span>

<span data-ttu-id="7300b-228">Wartości opóźnione są drukowane jako `Value is not created` lub równoważne tekst, gdy wartość nie została jeszcze oceniona.</span><span class="sxs-lookup"><span data-stu-id="7300b-228">Lazy values are printed as `Value is not created` or equivalent text when the value has not yet been evaluated.</span></span>

<span data-ttu-id="7300b-229">Wartości null są drukowane jako, `null` chyba że typ statyczny wartości jest określony jako typ złożenia, gdzie `null` jest dozwolonym reprezentacją.</span><span class="sxs-lookup"><span data-stu-id="7300b-229">Null values are printed as `null` unless the static type of the value is determined to be a union type where `null` is a permitted representation.</span></span>

<span data-ttu-id="7300b-230">Wartości funkcji języka F # są drukowane jako ich wewnętrznie wygenerowane nazwy zamknięcia, na przykład `<fun:it@43-7>` .</span><span class="sxs-lookup"><span data-stu-id="7300b-230">F# function values are printed as their internally generated closure name, for example, `<fun:it@43-7>`.</span></span>

### <a name="customize-plain-text-formatting-with-structuredformatdisplay"></a><span data-ttu-id="7300b-231">Dostosuj formatowanie zwykłego tekstu za pomocą`StructuredFormatDisplay`</span><span class="sxs-lookup"><span data-stu-id="7300b-231">Customize plain text formatting with `StructuredFormatDisplay`</span></span>

<span data-ttu-id="7300b-232">W przypadku korzystania ze `%A` specyfikatora `StructuredFormatDisplay` jest przestrzegana obecność atrybutu w deklaracjach typu.</span><span class="sxs-lookup"><span data-stu-id="7300b-232">When using the `%A` specifier, the presence of the `StructuredFormatDisplay` attribute on type declarations is respected.</span></span>  <span data-ttu-id="7300b-233">Służy do określania tekstu zastępczego i właściwości w celu wyświetlenia wartości.</span><span class="sxs-lookup"><span data-stu-id="7300b-233">This can be used to specify surrogate text and property to display a value.</span></span> <span data-ttu-id="7300b-234">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="7300b-234">For example:</span></span>

```fsharp
[<StructuredFormatDisplay("Counts({Clicks})")>]
type Counts = { Clicks:int list}

printfn "%20A" {Clicks=[0..20]}
```

<span data-ttu-id="7300b-235">Wyświetla</span><span class="sxs-lookup"><span data-stu-id="7300b-235">produces</span></span>

```console
Counts([0; 1; 2; 3;
        4; 5; 6; 7;
        8; 9; 10; 11;
        12; 13; 14;
        15; 16; 17;
        18; 19; 20])
```

### <a name="customize-plain-text-formatting-by-overriding-tostring"></a><span data-ttu-id="7300b-236">Dostosowywanie formatowania zwykłego tekstu przez zastępowanie`ToString`</span><span class="sxs-lookup"><span data-stu-id="7300b-236">Customize plain text formatting by overriding `ToString`</span></span>

<span data-ttu-id="7300b-237">Domyślna implementacja programu `ToString` jest zauważalna w programowaniu języka F #.</span><span class="sxs-lookup"><span data-stu-id="7300b-237">The default implementation of `ToString` is observable in F# programming.</span></span> <span data-ttu-id="7300b-238">Często domyślne wyniki nie są odpowiednie do użycia w przypadku wyświetlania informacji lub danych wyjściowych przez programistę, a w związku z tym często przesłonić implementację domyślną.</span><span class="sxs-lookup"><span data-stu-id="7300b-238">Often, the default results aren't suitable for use in either programmer-facing information display or user output, and as a result it is common to override the default implementation.</span></span>  

<span data-ttu-id="7300b-239">Domyślnie rekordy i typy Unii języka F # zastępują implementację programu `ToString` z implementacją używaną przez program `sprintf "%+A"` .</span><span class="sxs-lookup"><span data-stu-id="7300b-239">By default, F# record and union types override the implementation of `ToString` with an implementation that uses `sprintf "%+A"`.</span></span>  <span data-ttu-id="7300b-240">Przykład:</span><span class="sxs-lookup"><span data-stu-id="7300b-240">For example,</span></span>

```fsharp
type Counts = { Clicks:int list }

printfn "%s" ({Clicks=[0..10]}.ToString())
```

<span data-ttu-id="7300b-241">Wyświetla</span><span class="sxs-lookup"><span data-stu-id="7300b-241">produces</span></span>

```console
{ Clicks = [0; 1; 2; 3; 4; 5; 6; 7; 8; 9; 10] }
```

<span data-ttu-id="7300b-242">W przypadku typów klas nie `ToString` jest dostępna domyślna implementacja i jest używana wartość domyślna platformy .NET, która wyświetla nazwę typu.</span><span class="sxs-lookup"><span data-stu-id="7300b-242">For class types, no default implementation of `ToString` is provided and the .NET default is used, which reports the name of the type.</span></span> <span data-ttu-id="7300b-243">Przykład:</span><span class="sxs-lookup"><span data-stu-id="7300b-243">For example,</span></span>

```fsharp
type MyClassType(clicks: int list) =
   member _.Clicks = clicks

let data = [ MyClassType([1..5]); MyClassType([1..5]) ]
printfn "Default structured print gives this:\n%A" data
printfn "Default ToString gives:\n%s" (data.ToString())
```

<span data-ttu-id="7300b-244">Wyświetla</span><span class="sxs-lookup"><span data-stu-id="7300b-244">produces</span></span>

```console
Default structured print gives this:
[MyClassType; MyClassType]
Default ToString gives:
[MyClassType; MyClassType]
```

<span data-ttu-id="7300b-245">Dodanie przesłonięcia dla programu `ToString` może zapewnić lepsze formatowanie.</span><span class="sxs-lookup"><span data-stu-id="7300b-245">Adding an override for `ToString` can give better formatting.</span></span>

```fsharp
type MyClassType(clicks: int list) =
   member _.Clicks = clicks
   override _.ToString() = sprintf "MyClassType(%0A)" clicks

let data = [ MyClassType([1..5]); MyClassType([1..5]) ]
printfn "Now structured print gives this:\n%A" data
printfn "Now ToString gives:\n%s" (data.ToString())
```

<span data-ttu-id="7300b-246">Wyświetla</span><span class="sxs-lookup"><span data-stu-id="7300b-246">produces</span></span>

```console
Now structured print gives this:
[MyClassType([1; 2; 3; 4; 5]); MyClassType([1; 2; 3; 4; 5])]
Now ToString gives:
[MyClassType([1; 2; 3; 4; 5]); MyClassType([1; 2; 3; 4; 5])]
```

## <a name="f-interactive-structured-printing"></a><span data-ttu-id="7300b-247">F# Interactive drukowanie strukturalne</span><span class="sxs-lookup"><span data-stu-id="7300b-247">F# Interactive structured printing</span></span>

<span data-ttu-id="7300b-248">F# Interactive ( `dotnet fsi` ) używa rozszerzonej wersji strukturalnego formatowania tekstu do raportowania wartości i zezwala na dodatkowe szerszym.</span><span class="sxs-lookup"><span data-stu-id="7300b-248">F# Interactive (`dotnet fsi`) uses an extended version of structured plain text formatting to report values and allows additional customizability.</span></span> <span data-ttu-id="7300b-249">Aby uzyskać więcej informacji, zobacz [F# Interactive](fsharp-interactive-options.md).</span><span class="sxs-lookup"><span data-stu-id="7300b-249">For more information, see [F# Interactive](fsharp-interactive-options.md).</span></span>

## <a name="customize-debug-displays"></a><span data-ttu-id="7300b-250">Dostosowywanie ekranów debugowania</span><span class="sxs-lookup"><span data-stu-id="7300b-250">Customize debug displays</span></span>

<span data-ttu-id="7300b-251">Debugery dla platformy .NET respektują użycie atrybutów, takich jak `DebuggerDisplay` i `DebuggerTypeProxy` , i mają wpływ na strukturę wyświetlania obiektów w oknach inspekcji debugera.</span><span class="sxs-lookup"><span data-stu-id="7300b-251">Debuggers for .NET respect the use of attributes such as `DebuggerDisplay` and `DebuggerTypeProxy`, and these affect the structured display of objects in debugger inspection windows.</span></span>
<span data-ttu-id="7300b-252">Kompilator F # automatycznie wygenerował te atrybuty dla typu Unii rozłącznych i typów rekordów, ale nie klasy, interfejsu lub struktury.</span><span class="sxs-lookup"><span data-stu-id="7300b-252">The F# compiler automatically generated these attributes for discriminated union and record types, but not class, interface, or struct types.</span></span>

<span data-ttu-id="7300b-253">Te atrybuty są ignorowane w formacie zwykłego tekstu F #, ale mogą być przydatne do wdrożenia tych metod w celu usprawnienia wyświetlania podczas debugowania typów F #.</span><span class="sxs-lookup"><span data-stu-id="7300b-253">These attributes are ignored in F# plain text formatting, but it can be useful to implement these methods to improve displays when debugging F# types.</span></span>

## <a name="see-also"></a><span data-ttu-id="7300b-254">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="7300b-254">See also</span></span>

- [<span data-ttu-id="7300b-255">Ciągi</span><span class="sxs-lookup"><span data-stu-id="7300b-255">Strings</span></span>](strings.md)
- [<span data-ttu-id="7300b-256">Rekordy</span><span class="sxs-lookup"><span data-stu-id="7300b-256">Records</span></span>](records.md)
- [<span data-ttu-id="7300b-257">Sumy rozłączne</span><span class="sxs-lookup"><span data-stu-id="7300b-257">Discriminated Unions</span></span>](discriminated-unions.md)
- [<span data-ttu-id="7300b-258">Interaktywny F#</span><span class="sxs-lookup"><span data-stu-id="7300b-258">F# Interactive</span></span>](fsharp-interactive-options.md)
