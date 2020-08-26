---
title: Ciągi
description: 'Dowiedz się, jak typ "String" języka F # reprezentuje niezmienny tekst jako sekwencję znaków Unicode.'
ms.date: 08/15/2020
ms.openlocfilehash: f6ec36feeb197bf785c702e7b626cf5cf80696ab
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/25/2020
ms.locfileid: "88812214"
---
# <a name="strings"></a><span data-ttu-id="8ba1f-103">Ciągi</span><span class="sxs-lookup"><span data-stu-id="8ba1f-103">Strings</span></span>

<span data-ttu-id="8ba1f-104">`string`Typ reprezentuje niezmienny tekst jako sekwencję znaków Unicode.</span><span class="sxs-lookup"><span data-stu-id="8ba1f-104">The `string` type represents immutable text as a sequence of Unicode characters.</span></span> <span data-ttu-id="8ba1f-105">`string` jest aliasem dla `System.String` platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="8ba1f-105">`string` is an alias for `System.String` in .NET.</span></span>

## <a name="remarks"></a><span data-ttu-id="8ba1f-106">Uwagi</span><span class="sxs-lookup"><span data-stu-id="8ba1f-106">Remarks</span></span>

<span data-ttu-id="8ba1f-107">Literały ciągów są rozdzielane znakami cudzysłowu (").</span><span class="sxs-lookup"><span data-stu-id="8ba1f-107">String literals are delimited by the quotation mark (") character.</span></span> <span data-ttu-id="8ba1f-108">Znak ukośnika odwrotnego ( \\ ) jest używany do kodowania niektórych znaków specjalnych.</span><span class="sxs-lookup"><span data-stu-id="8ba1f-108">The backslash character ( \\ ) is used to encode certain special characters.</span></span> <span data-ttu-id="8ba1f-109">Ukośnik odwrotny i następny znak razem są znane jako *sekwencja ucieczki*.</span><span class="sxs-lookup"><span data-stu-id="8ba1f-109">The backslash and the next character together are known as an *escape sequence*.</span></span> <span data-ttu-id="8ba1f-110">W poniższej tabeli przedstawiono sekwencje unikowe obsługiwane w literałach ciągu języka F #.</span><span class="sxs-lookup"><span data-stu-id="8ba1f-110">Escape sequences supported in F# string literals are shown in the following table.</span></span>

|<span data-ttu-id="8ba1f-111">Znak</span><span class="sxs-lookup"><span data-stu-id="8ba1f-111">Character</span></span>|<span data-ttu-id="8ba1f-112">Sekwencja ucieczki</span><span class="sxs-lookup"><span data-stu-id="8ba1f-112">Escape sequence</span></span>|
|---------|---------------|
|<span data-ttu-id="8ba1f-113">Alerty</span><span class="sxs-lookup"><span data-stu-id="8ba1f-113">Alert</span></span>|`\a`|
|<span data-ttu-id="8ba1f-114">Backspace</span><span class="sxs-lookup"><span data-stu-id="8ba1f-114">Backspace</span></span>|`\b`|
|<span data-ttu-id="8ba1f-115">Kanał informacyjny formularza</span><span class="sxs-lookup"><span data-stu-id="8ba1f-115">Form feed</span></span>|`\f`|
|<span data-ttu-id="8ba1f-116">Ani</span><span class="sxs-lookup"><span data-stu-id="8ba1f-116">Newline</span></span>|`\n`|
|<span data-ttu-id="8ba1f-117">Znak powrotu karetki</span><span class="sxs-lookup"><span data-stu-id="8ba1f-117">Carriage return</span></span>|`\r`|
|<span data-ttu-id="8ba1f-118">Tab</span><span class="sxs-lookup"><span data-stu-id="8ba1f-118">Tab</span></span>|`\t`|
|<span data-ttu-id="8ba1f-119">Tabulator pionowy</span><span class="sxs-lookup"><span data-stu-id="8ba1f-119">Vertical tab</span></span>|`\v`|
|<span data-ttu-id="8ba1f-120">Ukośnika odwrotnego</span><span class="sxs-lookup"><span data-stu-id="8ba1f-120">Backslash</span></span>|`\\`|
|<span data-ttu-id="8ba1f-121">Cudzysłów</span><span class="sxs-lookup"><span data-stu-id="8ba1f-121">Quotation mark</span></span>|`\"`|
|<span data-ttu-id="8ba1f-122">Apostrof</span><span class="sxs-lookup"><span data-stu-id="8ba1f-122">Apostrophe</span></span>|`\'`|
|<span data-ttu-id="8ba1f-123">znak Unicode</span><span class="sxs-lookup"><span data-stu-id="8ba1f-123">Unicode character</span></span>|<span data-ttu-id="8ba1f-124">`\DDD` (gdzie `D` wskazuje cyfrę dziesiętną; zakres 000-255; na przykład `\231` = "ç")</span><span class="sxs-lookup"><span data-stu-id="8ba1f-124">`\DDD` (where `D` indicates a decimal digit; range of 000 - 255; for example, `\231` = "ç")</span></span>|
|<span data-ttu-id="8ba1f-125">znak Unicode</span><span class="sxs-lookup"><span data-stu-id="8ba1f-125">Unicode character</span></span>|<span data-ttu-id="8ba1f-126">`\xHH` (gdzie `H` wskazuje cyfrę szesnastkową; zakres 00-FF; na przykład `\xE7` = "ç")</span><span class="sxs-lookup"><span data-stu-id="8ba1f-126">`\xHH` (where `H` indicates a hexadecimal digit; range of 00 - FF; for example, `\xE7` = "ç")</span></span>|
|<span data-ttu-id="8ba1f-127">znak Unicode</span><span class="sxs-lookup"><span data-stu-id="8ba1f-127">Unicode character</span></span>|<span data-ttu-id="8ba1f-128">`\uHHHH` (UTF-16) (gdzie `H` wskazuje cyfrę szesnastkową; zakres 0000-FFFF;  na przykład `\u00E7` = "ç")</span><span class="sxs-lookup"><span data-stu-id="8ba1f-128">`\uHHHH` (UTF-16) (where `H` indicates a hexadecimal digit; range of 0000 - FFFF;  for example, `\u00E7` = "ç")</span></span>|
|<span data-ttu-id="8ba1f-129">znak Unicode</span><span class="sxs-lookup"><span data-stu-id="8ba1f-129">Unicode character</span></span>|<span data-ttu-id="8ba1f-130">`\U00HHHHHH` (UTF-32) (gdzie `H` wskazuje cyfrę szesnastkową; zakres 000000-10FFFF;  na przykład `\U0001F47D` = " 👽 ")</span><span class="sxs-lookup"><span data-stu-id="8ba1f-130">`\U00HHHHHH` (UTF-32) (where `H` indicates a hexadecimal digit; range of 000000 - 10FFFF;  for example, `\U0001F47D` = "👽")</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="8ba1f-131">`\DDD`Sekwencja ucieczki jest notacją dziesiętną, a nie notacją ósemkową, taką jak w większości innych języków.</span><span class="sxs-lookup"><span data-stu-id="8ba1f-131">The `\DDD` escape sequence is decimal notation, not octal notation like in most other languages.</span></span> <span data-ttu-id="8ba1f-132">W związku z tym cyfry `8` i `9` są prawidłowe, a sekwencja `\032` reprezentuje spację (U + 0020), natomiast ten sam punkt kodu w notacji ósemkowej będzie `\040` .</span><span class="sxs-lookup"><span data-stu-id="8ba1f-132">Therefore, digits `8` and `9` are valid, and a sequence of `\032` represents a space (U+0020), whereas that same code point in octal notation would be `\040`.</span></span>

> [!NOTE]
> <span data-ttu-id="8ba1f-133">Są ograniczone do zakresu 0-255 (0xFF), `\DDD` a `\x` Sekwencje ucieczki są efektywnie zestawem znaków [ISO-8859-1](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout) , ponieważ dopasowuje pierwsze 256 punktów kodowych Unicode.</span><span class="sxs-lookup"><span data-stu-id="8ba1f-133">Being constrained to a range of 0 - 255 (0xFF), the `\DDD` and `\x` escape sequences are effectively the [ISO-8859-1](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout) character set, since that matches the first 256 Unicode code points.</span></span>

## <a name="verbatim-strings"></a><span data-ttu-id="8ba1f-134">Verbatim ciągi</span><span class="sxs-lookup"><span data-stu-id="8ba1f-134">Verbatim Strings</span></span>

<span data-ttu-id="8ba1f-135">Jeśli poprzedzany przez symbol @, literał jest ciągiem Verbatim.</span><span class="sxs-lookup"><span data-stu-id="8ba1f-135">If preceded by the @ symbol, the literal is a verbatim string.</span></span> <span data-ttu-id="8ba1f-136">Oznacza to, że wszystkie sekwencje ucieczki są ignorowane, z tą różnicą, że dwa znaki cudzysłowu są interpretowane jako jeden znak cudzysłowu.</span><span class="sxs-lookup"><span data-stu-id="8ba1f-136">This means that any escape sequences are ignored, except that two quotation mark characters are interpreted as one quotation mark character.</span></span>

## <a name="triple-quoted-strings"></a><span data-ttu-id="8ba1f-137">Potrójne ciągi ujęte w cudzysłów</span><span class="sxs-lookup"><span data-stu-id="8ba1f-137">Triple Quoted Strings</span></span>

<span data-ttu-id="8ba1f-138">Ponadto ciąg może być ujęty w potrójne cudzysłowy.</span><span class="sxs-lookup"><span data-stu-id="8ba1f-138">Additionally, a string may be enclosed by triple quotes.</span></span> <span data-ttu-id="8ba1f-139">W takim przypadku wszystkie sekwencje ucieczki są ignorowane, w tym znaki podwójnego cudzysłowu.</span><span class="sxs-lookup"><span data-stu-id="8ba1f-139">In this case, all escape sequences are ignored, including double quotation mark characters.</span></span> <span data-ttu-id="8ba1f-140">Aby określić ciąg zawierający osadzony ciąg ujęty w cudzysłów, można użyć ciągu Verbatim lub ciągu z potrójnym cudzysłowem.</span><span class="sxs-lookup"><span data-stu-id="8ba1f-140">To specify a string that contains an embedded quoted string, you can either use a verbatim string or a triple-quoted string.</span></span> <span data-ttu-id="8ba1f-141">W przypadku używania ciągu Verbatim należy określić dwa znaki cudzysłowu, aby wskazać znak pojedynczego cudzysłowu.</span><span class="sxs-lookup"><span data-stu-id="8ba1f-141">If you use a verbatim string, you  must specify two quotation mark characters to indicate a single quotation mark character.</span></span> <span data-ttu-id="8ba1f-142">Jeśli używasz ciągu z potrójnym cudzysłowem, możesz użyć znaków pojedynczego cudzysłowu bez ich analizowania jako końca ciągu.</span><span class="sxs-lookup"><span data-stu-id="8ba1f-142">If you use a triple-quoted string, you can use the single quotation mark characters without them being parsed as the end of the string.</span></span> <span data-ttu-id="8ba1f-143">Ta technika może być przydatna podczas pracy z danymi XML lub innymi strukturami, które zawierają osadzone znaki cudzysłowu.</span><span class="sxs-lookup"><span data-stu-id="8ba1f-143">This technique can be useful when you work with XML or other structures that include embedded quotation marks.</span></span>

```fsharp
// Using a verbatim string
let xmlFragment1 = @"<book author=""Milton, John"" title=""Paradise Lost"">"

// Using a triple-quoted string
let xmlFragment2 = """<book author="Milton, John" title="Paradise Lost">"""
```

<span data-ttu-id="8ba1f-144">W kodzie, ciągi, które mają podziały wierszy są akceptowane, a podziały wierszy są interpretowane dosłownie jako znaki nowego wiersza, chyba że znak ukośnika odwrotnego jest ostatnim znakiem przed przerwaniem.</span><span class="sxs-lookup"><span data-stu-id="8ba1f-144">In code, strings that have line breaks are accepted and the line breaks are interpreted literally as newlines, unless a backslash character is the last character before the line break.</span></span> <span data-ttu-id="8ba1f-145">Wiodący biały znak w następnym wierszu jest ignorowany, gdy jest używany ukośnik odwrotny.</span><span class="sxs-lookup"><span data-stu-id="8ba1f-145">Leading white space on the next line is ignored when the backslash character is used.</span></span> <span data-ttu-id="8ba1f-146">Poniższy kod generuje ciąg `str1` , który ma wartość `"abc\ndef"` i ciąg `str2` , który ma wartość `"abcdef"` .</span><span class="sxs-lookup"><span data-stu-id="8ba1f-146">The following code produces a string `str1` that has value `"abc\ndef"` and a string `str2` that has value `"abcdef"`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1001.fs)]

## <a name="string-indexing-and-slicing"></a><span data-ttu-id="8ba1f-147">Indeksowanie ciągów i skalowanie</span><span class="sxs-lookup"><span data-stu-id="8ba1f-147">String Indexing and Slicing</span></span>

<span data-ttu-id="8ba1f-148">Można uzyskać dostęp do pojedynczych znaków w ciągu za pomocą składni podobnej do tablicy, jak pokazano poniżej.</span><span class="sxs-lookup"><span data-stu-id="8ba1f-148">You can access individual characters in a string by using array-like syntax, as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1002.fs)]

<span data-ttu-id="8ba1f-149">Wynik to `b`.</span><span class="sxs-lookup"><span data-stu-id="8ba1f-149">The output is `b`.</span></span>

<span data-ttu-id="8ba1f-150">Lub można wyodrębnić podciągi przy użyciu składni wycinka tablicy, jak pokazano w poniższym kodzie.</span><span class="sxs-lookup"><span data-stu-id="8ba1f-150">Or you can extract substrings by using array slice syntax, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1003.fs)]

<span data-ttu-id="8ba1f-151">Dane wyjściowe są następujące:</span><span class="sxs-lookup"><span data-stu-id="8ba1f-151">The output is as follows.</span></span>

```console
abc
def
```

<span data-ttu-id="8ba1f-152">Ciągi ASCII można reprezentować według tablic bajtów bez znaku `byte[]` .</span><span class="sxs-lookup"><span data-stu-id="8ba1f-152">You can represent ASCII strings by arrays of unsigned bytes, type `byte[]`.</span></span> <span data-ttu-id="8ba1f-153">Należy dodać sufiks `B` do literału ciągu, aby wskazać, że jest to ciąg ASCII.</span><span class="sxs-lookup"><span data-stu-id="8ba1f-153">You add the suffix `B` to a string literal to indicate that it is an ASCII string.</span></span> <span data-ttu-id="8ba1f-154">Literały ciągu ASCII używane z tablicami bajtowymi obsługują te same sekwencje unikowe co ciągi Unicode, z wyjątkiem sekwencji unikowych Unicode.</span><span class="sxs-lookup"><span data-stu-id="8ba1f-154">ASCII string literals used with byte arrays support the same escape sequences as Unicode strings, except for the Unicode escape sequences.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1004.fs)]

## <a name="string-operators"></a><span data-ttu-id="8ba1f-155">Operatory ciągów</span><span class="sxs-lookup"><span data-stu-id="8ba1f-155">String Operators</span></span>

<span data-ttu-id="8ba1f-156">`+`Operatora można używać do łączenia ciągów, zapewniając zgodność z funkcjami obsługi ciągów .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8ba1f-156">The `+` operator can be used to concatenate strings, maintaining compatibility with the .NET Framework string handling features.</span></span> <span data-ttu-id="8ba1f-157">Poniższy przykład ilustruje łączenie ciągów.</span><span class="sxs-lookup"><span data-stu-id="8ba1f-157">The following example illustrates string concatenation.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1006.fs)]

## <a name="string-class"></a><span data-ttu-id="8ba1f-158">String — Klasa</span><span class="sxs-lookup"><span data-stu-id="8ba1f-158">String Class</span></span>

<span data-ttu-id="8ba1f-159">Ponieważ typ ciągu w F # jest w rzeczywistości typem .NET Framework `System.String` , wszystkie `System.String` elementy członkowskie są dostępne.</span><span class="sxs-lookup"><span data-stu-id="8ba1f-159">Because the string type in F# is actually a .NET Framework `System.String` type, all the `System.String` members are available.</span></span> <span data-ttu-id="8ba1f-160">Obejmuje `+` operator, który jest używany do łączenia ciągów, `Length` Właściwość i `Chars` Właściwość, która zwraca ciąg jako tablicę znaków Unicode.</span><span class="sxs-lookup"><span data-stu-id="8ba1f-160">This includes the `+` operator, which is used to concatenate strings, the `Length` property, and the `Chars` property, which returns the string as an array of Unicode characters.</span></span> <span data-ttu-id="8ba1f-161">Aby uzyskać więcej informacji na temat ciągów, zobacz `System.String` .</span><span class="sxs-lookup"><span data-stu-id="8ba1f-161">For more information about strings, see `System.String`.</span></span>

<span data-ttu-id="8ba1f-162">Za pomocą `Chars` właściwości `System.String` , można uzyskać dostęp do poszczególnych znaków w ciągu, określając indeks, jak pokazano w poniższym kodzie.</span><span class="sxs-lookup"><span data-stu-id="8ba1f-162">By using the `Chars` property of `System.String`, you can access the individual characters in a string by specifying an index, as is shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1005.fs)]

## <a name="string-module"></a><span data-ttu-id="8ba1f-163">Moduł String</span><span class="sxs-lookup"><span data-stu-id="8ba1f-163">String Module</span></span>

<span data-ttu-id="8ba1f-164">Dodatkowe funkcje obsługi ciągów są zawarte w `String` module w `FSharp.Core` przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="8ba1f-164">Additional functionality for string handling is included in the `String` module in the `FSharp.Core` namespace.</span></span> <span data-ttu-id="8ba1f-165">Aby uzyskać więcej informacji, zobacz temat [String module](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-stringmodule.html).</span><span class="sxs-lookup"><span data-stu-id="8ba1f-165">For more information, see [String Module](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-stringmodule.html).</span></span>

## <a name="see-also"></a><span data-ttu-id="8ba1f-166">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="8ba1f-166">See also</span></span>

- [<span data-ttu-id="8ba1f-167">Dokumentacja języka F #</span><span class="sxs-lookup"><span data-stu-id="8ba1f-167">F# Language Reference</span></span>](index.md)
