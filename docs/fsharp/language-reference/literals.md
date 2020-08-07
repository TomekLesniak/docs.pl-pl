---
title: Literały
description: 'Dowiedz się więcej o typach literałów w języku programowania F #.'
ms.date: 06/28/2019
ms.openlocfilehash: 98d609a1cf0beb00c0dd4d45ea343aaa2280b62e
ms.sourcegitcommit: c37e8d4642fef647ebab0e1c618ecc29ddfe2a0f
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/06/2020
ms.locfileid: "87855026"
---
# <a name="literals"></a><span data-ttu-id="94e5d-103">Literały</span><span class="sxs-lookup"><span data-stu-id="94e5d-103">Literals</span></span>

<span data-ttu-id="94e5d-104">Ten artykuł zawiera tabelę, w której pokazano, jak określić typ literału w języku F #.</span><span class="sxs-lookup"><span data-stu-id="94e5d-104">This article provides a table that shows how to specify the type of a literal in F#.</span></span>

> [!NOTE]
> <span data-ttu-id="94e5d-105">Dokumentacja interfejsu API docs.microsoft.com dla języka F # nie została ukończona.</span><span class="sxs-lookup"><span data-stu-id="94e5d-105">The docs.microsoft.com API reference for F# is not complete.</span></span> <span data-ttu-id="94e5d-106">Jeśli wystąpią jakieś przerwane linki, należy odwołać się do [dokumentacji podstawowej biblioteki języka F #](https://fsharp.github.io/fsharp-core-docs/) .</span><span class="sxs-lookup"><span data-stu-id="94e5d-106">If you encounter any broken links, reference [F# Core Library Documentation](https://fsharp.github.io/fsharp-core-docs/) instead.</span></span>

## <a name="literal-types"></a><span data-ttu-id="94e5d-107">Typy literałów</span><span class="sxs-lookup"><span data-stu-id="94e5d-107">Literal types</span></span>

<span data-ttu-id="94e5d-108">W poniższej tabeli przedstawiono typy literałów języka F #.</span><span class="sxs-lookup"><span data-stu-id="94e5d-108">The following table shows the literal types in F#.</span></span> <span data-ttu-id="94e5d-109">Znaki reprezentujące cyfry w notacji szesnastkowej nie uwzględniają wielkości liter. w znakach identyfikujących typ rozróżniana jest wielkość liter.</span><span class="sxs-lookup"><span data-stu-id="94e5d-109">Characters that represent digits in hexadecimal notation are not case-sensitive; characters that identify the type are case-sensitive.</span></span>

|<span data-ttu-id="94e5d-110">Typ</span><span class="sxs-lookup"><span data-stu-id="94e5d-110">Type</span></span>|<span data-ttu-id="94e5d-111">Opis</span><span class="sxs-lookup"><span data-stu-id="94e5d-111">Description</span></span>|<span data-ttu-id="94e5d-112">Sufiks lub prefiks</span><span class="sxs-lookup"><span data-stu-id="94e5d-112">Suffix or prefix</span></span>|<span data-ttu-id="94e5d-113">Przykłady</span><span class="sxs-lookup"><span data-stu-id="94e5d-113">Examples</span></span>|
|----|-----------|----------------|--------|
|<span data-ttu-id="94e5d-114">sbyte</span><span class="sxs-lookup"><span data-stu-id="94e5d-114">sbyte</span></span>|<span data-ttu-id="94e5d-115">8-bitowa liczba całkowita ze znakiem</span><span class="sxs-lookup"><span data-stu-id="94e5d-115">signed 8-bit integer</span></span>|<span data-ttu-id="94e5d-116">Y</span><span class="sxs-lookup"><span data-stu-id="94e5d-116">y</span></span>|`86y`<br /><br />`0b00000101y`|
|<span data-ttu-id="94e5d-117">byte</span><span class="sxs-lookup"><span data-stu-id="94e5d-117">byte</span></span>|<span data-ttu-id="94e5d-118">8-bitowa niepodpisana liczba naturalna</span><span class="sxs-lookup"><span data-stu-id="94e5d-118">unsigned 8-bit natural number</span></span>|<span data-ttu-id="94e5d-119">uy</span><span class="sxs-lookup"><span data-stu-id="94e5d-119">uy</span></span>|`86uy`<br /><br />`0b00000101uy`|
|<span data-ttu-id="94e5d-120">Int16</span><span class="sxs-lookup"><span data-stu-id="94e5d-120">int16</span></span>|<span data-ttu-id="94e5d-121">16-bitowa liczba całkowita ze znakiem</span><span class="sxs-lookup"><span data-stu-id="94e5d-121">signed 16-bit integer</span></span>|<span data-ttu-id="94e5d-122">s</span><span class="sxs-lookup"><span data-stu-id="94e5d-122">s</span></span>|`86s`|
|<span data-ttu-id="94e5d-123">UInt16</span><span class="sxs-lookup"><span data-stu-id="94e5d-123">uint16</span></span>|<span data-ttu-id="94e5d-124">16-bitowa liczba naturalna bez znaku</span><span class="sxs-lookup"><span data-stu-id="94e5d-124">unsigned 16-bit natural number</span></span>|<span data-ttu-id="94e5d-125">Prześlij</span><span class="sxs-lookup"><span data-stu-id="94e5d-125">us</span></span>|`86us`|
|<span data-ttu-id="94e5d-126">int</span><span class="sxs-lookup"><span data-stu-id="94e5d-126">int</span></span><br /><br /><span data-ttu-id="94e5d-127">elementem</span><span class="sxs-lookup"><span data-stu-id="94e5d-127">int32</span></span>|<span data-ttu-id="94e5d-128">32-bitowa liczba całkowita</span><span class="sxs-lookup"><span data-stu-id="94e5d-128">signed 32-bit integer</span></span>|<span data-ttu-id="94e5d-129">l lub brak</span><span class="sxs-lookup"><span data-stu-id="94e5d-129">l or none</span></span>|`86`<br /><br />`86l`|
|<span data-ttu-id="94e5d-130">uint</span><span class="sxs-lookup"><span data-stu-id="94e5d-130">uint</span></span><br /><br /><span data-ttu-id="94e5d-131">równ</span><span class="sxs-lookup"><span data-stu-id="94e5d-131">uint32</span></span>|<span data-ttu-id="94e5d-132">niepodpisany 32-bit liczby naturalnej</span><span class="sxs-lookup"><span data-stu-id="94e5d-132">unsigned 32-bit natural number</span></span>|<span data-ttu-id="94e5d-133">u lub ul</span><span class="sxs-lookup"><span data-stu-id="94e5d-133">u or ul</span></span>|`86u`<br /><br />`86ul`|
|<span data-ttu-id="94e5d-134">nativeint —</span><span class="sxs-lookup"><span data-stu-id="94e5d-134">nativeint</span></span>|<span data-ttu-id="94e5d-135">natywny wskaźnik do podpisanej liczby naturalnej</span><span class="sxs-lookup"><span data-stu-id="94e5d-135">native pointer to a signed natural number</span></span>|<span data-ttu-id="94e5d-136">n</span><span class="sxs-lookup"><span data-stu-id="94e5d-136">n</span></span>|`123n`|
|<span data-ttu-id="94e5d-137">unativeint —</span><span class="sxs-lookup"><span data-stu-id="94e5d-137">unativeint</span></span>|<span data-ttu-id="94e5d-138">natywny wskaźnik jako niepodpisany numer naturalny</span><span class="sxs-lookup"><span data-stu-id="94e5d-138">native pointer as an unsigned natural number</span></span>|<span data-ttu-id="94e5d-139">odinstalować</span><span class="sxs-lookup"><span data-stu-id="94e5d-139">un</span></span>|`0x00002D3Fun`|
|<span data-ttu-id="94e5d-140">Int64</span><span class="sxs-lookup"><span data-stu-id="94e5d-140">int64</span></span>|<span data-ttu-id="94e5d-141">64-bitowa liczba całkowita</span><span class="sxs-lookup"><span data-stu-id="94e5d-141">signed 64-bit integer</span></span>|<span data-ttu-id="94e5d-142">L</span><span class="sxs-lookup"><span data-stu-id="94e5d-142">L</span></span>|`86L`|
|<span data-ttu-id="94e5d-143">UInt64</span><span class="sxs-lookup"><span data-stu-id="94e5d-143">uint64</span></span>|<span data-ttu-id="94e5d-144">niepodpisany 64-bit liczby naturalnej</span><span class="sxs-lookup"><span data-stu-id="94e5d-144">unsigned 64-bit natural number</span></span>|<span data-ttu-id="94e5d-145">UL</span><span class="sxs-lookup"><span data-stu-id="94e5d-145">UL</span></span>|`86UL`|
|<span data-ttu-id="94e5d-146">Single, float32</span><span class="sxs-lookup"><span data-stu-id="94e5d-146">single, float32</span></span>|<span data-ttu-id="94e5d-147">32-bitowa liczba zmiennoprzecinkowa</span><span class="sxs-lookup"><span data-stu-id="94e5d-147">32-bit floating point number</span></span>|<span data-ttu-id="94e5d-148">F lub f</span><span class="sxs-lookup"><span data-stu-id="94e5d-148">F or f</span></span>|<span data-ttu-id="94e5d-149">`4.14F` lub `4.14f`</span><span class="sxs-lookup"><span data-stu-id="94e5d-149">`4.14F` or `4.14f`</span></span>|
|||<span data-ttu-id="94e5d-150">wiersza</span><span class="sxs-lookup"><span data-stu-id="94e5d-150">lf</span></span>|`0x00000000lf`|
|<span data-ttu-id="94e5d-151">float Double</span><span class="sxs-lookup"><span data-stu-id="94e5d-151">float; double</span></span>|<span data-ttu-id="94e5d-152">64-bitowa liczba zmiennoprzecinkowa</span><span class="sxs-lookup"><span data-stu-id="94e5d-152">64-bit floating point number</span></span>|<span data-ttu-id="94e5d-153">brak</span><span class="sxs-lookup"><span data-stu-id="94e5d-153">none</span></span>|<span data-ttu-id="94e5d-154">`4.14`lub `2.3E+32` lub`2.3e+32`</span><span class="sxs-lookup"><span data-stu-id="94e5d-154">`4.14` or `2.3E+32` or `2.3e+32`</span></span>|
|||<span data-ttu-id="94e5d-155">WIERSZA</span><span class="sxs-lookup"><span data-stu-id="94e5d-155">LF</span></span>|`0x0000000000000000LF`|
|<span data-ttu-id="94e5d-156">bigint</span><span class="sxs-lookup"><span data-stu-id="94e5d-156">bigint</span></span>|<span data-ttu-id="94e5d-157">Liczba całkowita nieograniczona do 64-bitowej reprezentacji</span><span class="sxs-lookup"><span data-stu-id="94e5d-157">integer not limited to 64-bit representation</span></span>|<span data-ttu-id="94e5d-158">I</span><span class="sxs-lookup"><span data-stu-id="94e5d-158">I</span></span>|`9999999999999999999999999999I`|
|<span data-ttu-id="94e5d-159">decimal</span><span class="sxs-lookup"><span data-stu-id="94e5d-159">decimal</span></span>|<span data-ttu-id="94e5d-160">Liczba ułamkowa reprezentowana jako stały punkt lub liczba wymierna</span><span class="sxs-lookup"><span data-stu-id="94e5d-160">fractional number represented as a fixed point or rational number</span></span>|<span data-ttu-id="94e5d-161">M lub m</span><span class="sxs-lookup"><span data-stu-id="94e5d-161">M or m</span></span>|<span data-ttu-id="94e5d-162">`0.7833M` lub `0.7833m`</span><span class="sxs-lookup"><span data-stu-id="94e5d-162">`0.7833M` or `0.7833m`</span></span>|
|<span data-ttu-id="94e5d-163">Char</span><span class="sxs-lookup"><span data-stu-id="94e5d-163">Char</span></span>|<span data-ttu-id="94e5d-164">znak Unicode</span><span class="sxs-lookup"><span data-stu-id="94e5d-164">Unicode character</span></span>|<span data-ttu-id="94e5d-165">brak</span><span class="sxs-lookup"><span data-stu-id="94e5d-165">none</span></span>|<span data-ttu-id="94e5d-166">`'a'` lub `'\u0061'`</span><span class="sxs-lookup"><span data-stu-id="94e5d-166">`'a'` or `'\u0061'`</span></span>|
|<span data-ttu-id="94e5d-167">Ciąg</span><span class="sxs-lookup"><span data-stu-id="94e5d-167">String</span></span>|<span data-ttu-id="94e5d-168">Ciąg Unicode</span><span class="sxs-lookup"><span data-stu-id="94e5d-168">Unicode string</span></span>|<span data-ttu-id="94e5d-169">brak</span><span class="sxs-lookup"><span data-stu-id="94e5d-169">none</span></span>|`"text\n"`<br /><br /><span data-ttu-id="94e5d-170">lub</span><span class="sxs-lookup"><span data-stu-id="94e5d-170">or</span></span><br /><br />`@"c:\filename"`<br /><br /><span data-ttu-id="94e5d-171">lub</span><span class="sxs-lookup"><span data-stu-id="94e5d-171">or</span></span><br /><br />`"""<book title="Paradise Lost">"""`<br /><br /><span data-ttu-id="94e5d-172">lub</span><span class="sxs-lookup"><span data-stu-id="94e5d-172">or</span></span><br /><br />`"string1" + "string2"`<br /><br /><span data-ttu-id="94e5d-173">Zobacz również [ciągi](Strings.md).</span><span class="sxs-lookup"><span data-stu-id="94e5d-173">See also [Strings](Strings.md).</span></span>|
|<span data-ttu-id="94e5d-174">byte</span><span class="sxs-lookup"><span data-stu-id="94e5d-174">byte</span></span>|<span data-ttu-id="94e5d-175">Znak ASCII</span><span class="sxs-lookup"><span data-stu-id="94e5d-175">ASCII character</span></span>|<span data-ttu-id="94e5d-176">B</span><span class="sxs-lookup"><span data-stu-id="94e5d-176">B</span></span>|`'a'B`|
|<span data-ttu-id="94e5d-177">Byte []</span><span class="sxs-lookup"><span data-stu-id="94e5d-177">byte[]</span></span>|<span data-ttu-id="94e5d-178">Ciąg ASCII</span><span class="sxs-lookup"><span data-stu-id="94e5d-178">ASCII string</span></span>|<span data-ttu-id="94e5d-179">B</span><span class="sxs-lookup"><span data-stu-id="94e5d-179">B</span></span>|`"text"B`|
|<span data-ttu-id="94e5d-180">Ciąg lub Byte []</span><span class="sxs-lookup"><span data-stu-id="94e5d-180">String or byte[]</span></span>|<span data-ttu-id="94e5d-181">ciąg Verbatim</span><span class="sxs-lookup"><span data-stu-id="94e5d-181">verbatim string</span></span>|<span data-ttu-id="94e5d-182">@ prefix</span><span class="sxs-lookup"><span data-stu-id="94e5d-182">@ prefix</span></span>|<span data-ttu-id="94e5d-183">`@"\\server\share"`Unicode</span><span class="sxs-lookup"><span data-stu-id="94e5d-183">`@"\\server\share"` (Unicode)</span></span><br /><br /><span data-ttu-id="94e5d-184">`@"\\server\share"B`ASCII</span><span class="sxs-lookup"><span data-stu-id="94e5d-184">`@"\\server\share"B` (ASCII)</span></span>|

## <a name="named-literals"></a><span data-ttu-id="94e5d-185">Nazwane literały</span><span class="sxs-lookup"><span data-stu-id="94e5d-185">Named literals</span></span>

<span data-ttu-id="94e5d-186">Wartości, które mają być stałymi, mogą być oznaczone atrybutem [literału](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) .</span><span class="sxs-lookup"><span data-stu-id="94e5d-186">Values that are intended to be constants can be marked with the [Literal](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) attribute.</span></span> <span data-ttu-id="94e5d-187">Ten atrybut ma wpływ na sposób kompilowania wartości jako stałej.</span><span class="sxs-lookup"><span data-stu-id="94e5d-187">This attribute has the effect of causing a value to be compiled as a constant.</span></span>

<span data-ttu-id="94e5d-188">W wyrażeniach dopasowania wzorców identyfikatory zaczynające się od małych liter są zawsze traktowane jako zmienne do powiązania, a nie jako literały, więc zazwyczaj należy używać początkowych wersalików podczas definiowania literałów.</span><span class="sxs-lookup"><span data-stu-id="94e5d-188">In pattern matching expressions, identifiers that begin with lowercase characters are always treated as variables to be bound, rather than as literals, so you should generally use initial capitals when you define literals.</span></span>

```fsharp
[<Literal>]
let SomeJson = """{"numbers":[1,2,3,4,5]}"""

[<Literal>]
let Literal1 = "a" + "b"

[<Literal>]
let FileLocation =   __SOURCE_DIRECTORY__ + "/" + __SOURCE_FILE__

[<Literal>]
let Literal2 = 1 ||| 64

[<Literal>]
let Literal3 = System.IO.FileAccess.Read ||| System.IO.FileAccess.Write
```

## <a name="remarks"></a><span data-ttu-id="94e5d-189">Uwagi</span><span class="sxs-lookup"><span data-stu-id="94e5d-189">Remarks</span></span>

<span data-ttu-id="94e5d-190">Ciągi Unicode mogą zawierać jawne kodowania, które można określić przy użyciu, `\u` po którym następuje 16-bitowy kod szesnastkowy (0000-FFFF) lub kodowanie UTF-32, które można określić przy użyciu, `\U` a następnie kod szesnastkowy 32-bitowy, który reprezentuje dowolny punkt kodu Unicode (00000000-0010FFFF).</span><span class="sxs-lookup"><span data-stu-id="94e5d-190">Unicode strings can contain explicit encodings that you can specify by using `\u` followed by a 16-bit hexadecimal code (0000 - FFFF), or UTF-32 encodings that you can specify by using `\U` followed by a 32-bit hexadecimal code that represents any Unicode code point (00000000 - 0010FFFF).</span></span>

<span data-ttu-id="94e5d-191">Użycie innych operatorów bitowych innych niż `|||` jest niedozwolone.</span><span class="sxs-lookup"><span data-stu-id="94e5d-191">The use of other bitwise operators other than `|||` isn't allowed.</span></span>

## <a name="integers-in-other-bases"></a><span data-ttu-id="94e5d-192">Liczby całkowite w innych bazach</span><span class="sxs-lookup"><span data-stu-id="94e5d-192">Integers in other bases</span></span>

<span data-ttu-id="94e5d-193">Podpisane 32-bitowe liczby całkowite można także określić w formacie szesnastkowym, ósemkowym lub binarnym przy `0x` użyciu `0o` `0b` prefiksu lub odpowiednio.</span><span class="sxs-lookup"><span data-stu-id="94e5d-193">Signed 32-bit integers can also be specified in hexadecimal, octal, or binary using a `0x`, `0o` or `0b` prefix respectively.</span></span>

```fsharp
let numbers = (0x9F, 0o77, 0b1010)
// Result: numbers : int * int * int = (159, 63, 10)
```

## <a name="underscores-in-numeric-literals"></a><span data-ttu-id="94e5d-194">Znaki podkreślenia w literałach numerycznych</span><span class="sxs-lookup"><span data-stu-id="94e5d-194">Underscores in numeric literals</span></span>

<span data-ttu-id="94e5d-195">Możesz oddzielić cyfry znakiem podkreślenia ( `_` ).</span><span class="sxs-lookup"><span data-stu-id="94e5d-195">You can separate digits with the underscore character (`_`).</span></span>

```fsharp
let value = 0xDEAD_BEEF

let valueAsBits = 0b1101_1110_1010_1101_1011_1110_1110_1111

let exampleSSN = 123_456_7890
```

## <a name="see-also"></a><span data-ttu-id="94e5d-196">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="94e5d-196">See also</span></span>

- [<span data-ttu-id="94e5d-197">Core. LiteralAttribute — Klasa</span><span class="sxs-lookup"><span data-stu-id="94e5d-197">Core.LiteralAttribute Class</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.literalattribute-class-%5bfsharp%5d)
