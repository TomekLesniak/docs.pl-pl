---
title: Literały
description: 'Dowiedz się więcej o typach literałów w języku programowania F #.'
ms.date: 08/15/2020
ms.openlocfilehash: 15f73db3c36f7c60ab1eeba96c63a28ebc6d7f01
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/18/2020
ms.locfileid: "88559157"
---
# <a name="literals"></a><span data-ttu-id="bedef-103">Literały</span><span class="sxs-lookup"><span data-stu-id="bedef-103">Literals</span></span>

<span data-ttu-id="bedef-104">Ten artykuł zawiera tabelę, w której pokazano, jak określić typ literału w języku F #.</span><span class="sxs-lookup"><span data-stu-id="bedef-104">This article provides a table that shows how to specify the type of a literal in F#.</span></span>

## <a name="literal-types"></a><span data-ttu-id="bedef-105">Typy literałów</span><span class="sxs-lookup"><span data-stu-id="bedef-105">Literal types</span></span>

<span data-ttu-id="bedef-106">W poniższej tabeli przedstawiono typy literałów języka F #.</span><span class="sxs-lookup"><span data-stu-id="bedef-106">The following table shows the literal types in F#.</span></span> <span data-ttu-id="bedef-107">Znaki reprezentujące cyfry w notacji szesnastkowej nie uwzględniają wielkości liter. w znakach identyfikujących typ rozróżniana jest wielkość liter.</span><span class="sxs-lookup"><span data-stu-id="bedef-107">Characters that represent digits in hexadecimal notation are not case-sensitive; characters that identify the type are case-sensitive.</span></span>

|<span data-ttu-id="bedef-108">Typ</span><span class="sxs-lookup"><span data-stu-id="bedef-108">Type</span></span>|<span data-ttu-id="bedef-109">Opis</span><span class="sxs-lookup"><span data-stu-id="bedef-109">Description</span></span>|<span data-ttu-id="bedef-110">Sufiks lub prefiks</span><span class="sxs-lookup"><span data-stu-id="bedef-110">Suffix or prefix</span></span>|<span data-ttu-id="bedef-111">Przykłady</span><span class="sxs-lookup"><span data-stu-id="bedef-111">Examples</span></span>|
|----|-----------|----------------|--------|
|<span data-ttu-id="bedef-112">sbyte</span><span class="sxs-lookup"><span data-stu-id="bedef-112">sbyte</span></span>|<span data-ttu-id="bedef-113">8-bitowa liczba całkowita ze znakiem</span><span class="sxs-lookup"><span data-stu-id="bedef-113">signed 8-bit integer</span></span>|<span data-ttu-id="bedef-114">Y</span><span class="sxs-lookup"><span data-stu-id="bedef-114">y</span></span>|`86y`<br /><br />`0b00000101y`|
|<span data-ttu-id="bedef-115">byte</span><span class="sxs-lookup"><span data-stu-id="bedef-115">byte</span></span>|<span data-ttu-id="bedef-116">8-bitowa niepodpisana liczba naturalna</span><span class="sxs-lookup"><span data-stu-id="bedef-116">unsigned 8-bit natural number</span></span>|<span data-ttu-id="bedef-117">uy</span><span class="sxs-lookup"><span data-stu-id="bedef-117">uy</span></span>|`86uy`<br /><br />`0b00000101uy`|
|<span data-ttu-id="bedef-118">Int16</span><span class="sxs-lookup"><span data-stu-id="bedef-118">int16</span></span>|<span data-ttu-id="bedef-119">16-bitowa liczba całkowita ze znakiem</span><span class="sxs-lookup"><span data-stu-id="bedef-119">signed 16-bit integer</span></span>|<span data-ttu-id="bedef-120">s</span><span class="sxs-lookup"><span data-stu-id="bedef-120">s</span></span>|`86s`|
|<span data-ttu-id="bedef-121">UInt16</span><span class="sxs-lookup"><span data-stu-id="bedef-121">uint16</span></span>|<span data-ttu-id="bedef-122">16-bitowa liczba naturalna bez znaku</span><span class="sxs-lookup"><span data-stu-id="bedef-122">unsigned 16-bit natural number</span></span>|<span data-ttu-id="bedef-123">Prześlij</span><span class="sxs-lookup"><span data-stu-id="bedef-123">us</span></span>|`86us`|
|<span data-ttu-id="bedef-124">int</span><span class="sxs-lookup"><span data-stu-id="bedef-124">int</span></span><br /><br /><span data-ttu-id="bedef-125">elementem</span><span class="sxs-lookup"><span data-stu-id="bedef-125">int32</span></span>|<span data-ttu-id="bedef-126">32-bitowa liczba całkowita</span><span class="sxs-lookup"><span data-stu-id="bedef-126">signed 32-bit integer</span></span>|<span data-ttu-id="bedef-127">l lub brak</span><span class="sxs-lookup"><span data-stu-id="bedef-127">l or none</span></span>|`86`<br /><br />`86l`|
|<span data-ttu-id="bedef-128">uint</span><span class="sxs-lookup"><span data-stu-id="bedef-128">uint</span></span><br /><br /><span data-ttu-id="bedef-129">równ</span><span class="sxs-lookup"><span data-stu-id="bedef-129">uint32</span></span>|<span data-ttu-id="bedef-130">niepodpisany 32-bit liczby naturalnej</span><span class="sxs-lookup"><span data-stu-id="bedef-130">unsigned 32-bit natural number</span></span>|<span data-ttu-id="bedef-131">u lub ul</span><span class="sxs-lookup"><span data-stu-id="bedef-131">u or ul</span></span>|`86u`<br /><br />`86ul`|
|<span data-ttu-id="bedef-132">nativeint —</span><span class="sxs-lookup"><span data-stu-id="bedef-132">nativeint</span></span>|<span data-ttu-id="bedef-133">natywny wskaźnik do podpisanej liczby naturalnej</span><span class="sxs-lookup"><span data-stu-id="bedef-133">native pointer to a signed natural number</span></span>|<span data-ttu-id="bedef-134">n</span><span class="sxs-lookup"><span data-stu-id="bedef-134">n</span></span>|`123n`|
|<span data-ttu-id="bedef-135">unativeint —</span><span class="sxs-lookup"><span data-stu-id="bedef-135">unativeint</span></span>|<span data-ttu-id="bedef-136">natywny wskaźnik jako niepodpisany numer naturalny</span><span class="sxs-lookup"><span data-stu-id="bedef-136">native pointer as an unsigned natural number</span></span>|<span data-ttu-id="bedef-137">odinstalować</span><span class="sxs-lookup"><span data-stu-id="bedef-137">un</span></span>|`0x00002D3Fun`|
|<span data-ttu-id="bedef-138">Int64</span><span class="sxs-lookup"><span data-stu-id="bedef-138">int64</span></span>|<span data-ttu-id="bedef-139">64-bitowa liczba całkowita</span><span class="sxs-lookup"><span data-stu-id="bedef-139">signed 64-bit integer</span></span>|<span data-ttu-id="bedef-140">L</span><span class="sxs-lookup"><span data-stu-id="bedef-140">L</span></span>|`86L`|
|<span data-ttu-id="bedef-141">UInt64</span><span class="sxs-lookup"><span data-stu-id="bedef-141">uint64</span></span>|<span data-ttu-id="bedef-142">niepodpisany 64-bit liczby naturalnej</span><span class="sxs-lookup"><span data-stu-id="bedef-142">unsigned 64-bit natural number</span></span>|<span data-ttu-id="bedef-143">UL</span><span class="sxs-lookup"><span data-stu-id="bedef-143">UL</span></span>|`86UL`|
|<span data-ttu-id="bedef-144">Single, float32</span><span class="sxs-lookup"><span data-stu-id="bedef-144">single, float32</span></span>|<span data-ttu-id="bedef-145">32-bitowa liczba zmiennoprzecinkowa</span><span class="sxs-lookup"><span data-stu-id="bedef-145">32-bit floating point number</span></span>|<span data-ttu-id="bedef-146">F lub f</span><span class="sxs-lookup"><span data-stu-id="bedef-146">F or f</span></span>|<span data-ttu-id="bedef-147">`4.14F` lub `4.14f`</span><span class="sxs-lookup"><span data-stu-id="bedef-147">`4.14F` or `4.14f`</span></span>|
|||<span data-ttu-id="bedef-148">wiersza</span><span class="sxs-lookup"><span data-stu-id="bedef-148">lf</span></span>|`0x00000000lf`|
|<span data-ttu-id="bedef-149">float Double</span><span class="sxs-lookup"><span data-stu-id="bedef-149">float; double</span></span>|<span data-ttu-id="bedef-150">64-bitowa liczba zmiennoprzecinkowa</span><span class="sxs-lookup"><span data-stu-id="bedef-150">64-bit floating point number</span></span>|<span data-ttu-id="bedef-151">brak</span><span class="sxs-lookup"><span data-stu-id="bedef-151">none</span></span>|<span data-ttu-id="bedef-152">`4.14` lub `2.3E+32` lub `2.3e+32`</span><span class="sxs-lookup"><span data-stu-id="bedef-152">`4.14` or `2.3E+32` or `2.3e+32`</span></span>|
|||<span data-ttu-id="bedef-153">WIERSZA</span><span class="sxs-lookup"><span data-stu-id="bedef-153">LF</span></span>|`0x0000000000000000LF`|
|<span data-ttu-id="bedef-154">bigint</span><span class="sxs-lookup"><span data-stu-id="bedef-154">bigint</span></span>|<span data-ttu-id="bedef-155">Liczba całkowita nieograniczona do 64-bitowej reprezentacji</span><span class="sxs-lookup"><span data-stu-id="bedef-155">integer not limited to 64-bit representation</span></span>|<span data-ttu-id="bedef-156">I</span><span class="sxs-lookup"><span data-stu-id="bedef-156">I</span></span>|`9999999999999999999999999999I`|
|<span data-ttu-id="bedef-157">decimal</span><span class="sxs-lookup"><span data-stu-id="bedef-157">decimal</span></span>|<span data-ttu-id="bedef-158">Liczba ułamkowa reprezentowana jako stały punkt lub liczba wymierna</span><span class="sxs-lookup"><span data-stu-id="bedef-158">fractional number represented as a fixed point or rational number</span></span>|<span data-ttu-id="bedef-159">M lub m</span><span class="sxs-lookup"><span data-stu-id="bedef-159">M or m</span></span>|<span data-ttu-id="bedef-160">`0.7833M` lub `0.7833m`</span><span class="sxs-lookup"><span data-stu-id="bedef-160">`0.7833M` or `0.7833m`</span></span>|
|<span data-ttu-id="bedef-161">Char</span><span class="sxs-lookup"><span data-stu-id="bedef-161">Char</span></span>|<span data-ttu-id="bedef-162">znak Unicode</span><span class="sxs-lookup"><span data-stu-id="bedef-162">Unicode character</span></span>|<span data-ttu-id="bedef-163">brak</span><span class="sxs-lookup"><span data-stu-id="bedef-163">none</span></span>|<span data-ttu-id="bedef-164">`'a'` lub `'\u0061'`</span><span class="sxs-lookup"><span data-stu-id="bedef-164">`'a'` or `'\u0061'`</span></span>|
|<span data-ttu-id="bedef-165">String</span><span class="sxs-lookup"><span data-stu-id="bedef-165">String</span></span>|<span data-ttu-id="bedef-166">Ciąg Unicode</span><span class="sxs-lookup"><span data-stu-id="bedef-166">Unicode string</span></span>|<span data-ttu-id="bedef-167">brak</span><span class="sxs-lookup"><span data-stu-id="bedef-167">none</span></span>|`"text\n"`<br /><br /><span data-ttu-id="bedef-168">lub</span><span class="sxs-lookup"><span data-stu-id="bedef-168">or</span></span><br /><br />`@"c:\filename"`<br /><br /><span data-ttu-id="bedef-169">lub</span><span class="sxs-lookup"><span data-stu-id="bedef-169">or</span></span><br /><br />`"""<book title="Paradise Lost">"""`<br /><br /><span data-ttu-id="bedef-170">lub</span><span class="sxs-lookup"><span data-stu-id="bedef-170">or</span></span><br /><br />`"string1" + "string2"`<br /><br /><span data-ttu-id="bedef-171">Zobacz również [ciągi](Strings.md).</span><span class="sxs-lookup"><span data-stu-id="bedef-171">See also [Strings](Strings.md).</span></span>|
|<span data-ttu-id="bedef-172">byte</span><span class="sxs-lookup"><span data-stu-id="bedef-172">byte</span></span>|<span data-ttu-id="bedef-173">Znak ASCII</span><span class="sxs-lookup"><span data-stu-id="bedef-173">ASCII character</span></span>|<span data-ttu-id="bedef-174">B</span><span class="sxs-lookup"><span data-stu-id="bedef-174">B</span></span>|`'a'B`|
|<span data-ttu-id="bedef-175">Byte []</span><span class="sxs-lookup"><span data-stu-id="bedef-175">byte[]</span></span>|<span data-ttu-id="bedef-176">Ciąg ASCII</span><span class="sxs-lookup"><span data-stu-id="bedef-176">ASCII string</span></span>|<span data-ttu-id="bedef-177">B</span><span class="sxs-lookup"><span data-stu-id="bedef-177">B</span></span>|`"text"B`|
|<span data-ttu-id="bedef-178">Ciąg lub Byte []</span><span class="sxs-lookup"><span data-stu-id="bedef-178">String or byte[]</span></span>|<span data-ttu-id="bedef-179">ciąg Verbatim</span><span class="sxs-lookup"><span data-stu-id="bedef-179">verbatim string</span></span>|<span data-ttu-id="bedef-180">@ prefix</span><span class="sxs-lookup"><span data-stu-id="bedef-180">@ prefix</span></span>|<span data-ttu-id="bedef-181">`@"\\server\share"` Unicode</span><span class="sxs-lookup"><span data-stu-id="bedef-181">`@"\\server\share"` (Unicode)</span></span><br /><br /><span data-ttu-id="bedef-182">`@"\\server\share"B` ASCII</span><span class="sxs-lookup"><span data-stu-id="bedef-182">`@"\\server\share"B` (ASCII)</span></span>|

## <a name="named-literals"></a><span data-ttu-id="bedef-183">Nazwane literały</span><span class="sxs-lookup"><span data-stu-id="bedef-183">Named literals</span></span>

<span data-ttu-id="bedef-184">Wartości, które mają być stałymi, mogą być oznaczone atrybutem [literału](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-literalattribute.html) .</span><span class="sxs-lookup"><span data-stu-id="bedef-184">Values that are intended to be constants can be marked with the [Literal](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-literalattribute.html) attribute.</span></span> <span data-ttu-id="bedef-185">Ten atrybut ma wpływ na sposób kompilowania wartości jako stałej.</span><span class="sxs-lookup"><span data-stu-id="bedef-185">This attribute has the effect of causing a value to be compiled as a constant.</span></span>

<span data-ttu-id="bedef-186">W wyrażeniach dopasowania wzorców identyfikatory zaczynające się od małych liter są zawsze traktowane jako zmienne do powiązania, a nie jako literały, więc zazwyczaj należy używać początkowych wersalików podczas definiowania literałów.</span><span class="sxs-lookup"><span data-stu-id="bedef-186">In pattern matching expressions, identifiers that begin with lowercase characters are always treated as variables to be bound, rather than as literals, so you should generally use initial capitals when you define literals.</span></span>

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

## <a name="remarks"></a><span data-ttu-id="bedef-187">Uwagi</span><span class="sxs-lookup"><span data-stu-id="bedef-187">Remarks</span></span>

<span data-ttu-id="bedef-188">Ciągi Unicode mogą zawierać jawne kodowania, które można określić przy użyciu, `\u` po którym następuje 16-bitowy kod szesnastkowy (0000-FFFF) lub kodowanie UTF-32, które można określić przy użyciu, `\U` a następnie kod szesnastkowy 32-bitowy, który reprezentuje dowolny punkt kodu Unicode (00000000-0010FFFF).</span><span class="sxs-lookup"><span data-stu-id="bedef-188">Unicode strings can contain explicit encodings that you can specify by using `\u` followed by a 16-bit hexadecimal code (0000 - FFFF), or UTF-32 encodings that you can specify by using `\U` followed by a 32-bit hexadecimal code that represents any Unicode code point (00000000 - 0010FFFF).</span></span>

<span data-ttu-id="bedef-189">Użycie innych operatorów bitowych innych niż `|||` jest niedozwolone.</span><span class="sxs-lookup"><span data-stu-id="bedef-189">The use of other bitwise operators other than `|||` isn't allowed.</span></span>

## <a name="integers-in-other-bases"></a><span data-ttu-id="bedef-190">Liczby całkowite w innych bazach</span><span class="sxs-lookup"><span data-stu-id="bedef-190">Integers in other bases</span></span>

<span data-ttu-id="bedef-191">Podpisane 32-bitowe liczby całkowite można także określić w formacie szesnastkowym, ósemkowym lub binarnym przy `0x` użyciu `0o` `0b` prefiksu lub odpowiednio.</span><span class="sxs-lookup"><span data-stu-id="bedef-191">Signed 32-bit integers can also be specified in hexadecimal, octal, or binary using a `0x`, `0o` or `0b` prefix respectively.</span></span>

```fsharp
let numbers = (0x9F, 0o77, 0b1010)
// Result: numbers : int * int * int = (159, 63, 10)
```

## <a name="underscores-in-numeric-literals"></a><span data-ttu-id="bedef-192">Znaki podkreślenia w literałach numerycznych</span><span class="sxs-lookup"><span data-stu-id="bedef-192">Underscores in numeric literals</span></span>

<span data-ttu-id="bedef-193">Możesz oddzielić cyfry znakiem podkreślenia ( `_` ).</span><span class="sxs-lookup"><span data-stu-id="bedef-193">You can separate digits with the underscore character (`_`).</span></span>

```fsharp
let value = 0xDEAD_BEEF

let valueAsBits = 0b1101_1110_1010_1101_1011_1110_1110_1111

let exampleSSN = 123_456_7890
```
