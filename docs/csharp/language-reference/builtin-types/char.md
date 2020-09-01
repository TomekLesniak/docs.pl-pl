---
description: 'Dowiedz się abouot wbudowany typ znaku w języku C #'
title: Typ char — odwołanie w C#
ms.date: 05/11/2020
f1_keywords:
- char
- char_CSharpKeyword
helpviewer_keywords:
- char data type [C#]
ms.assetid: b51cf4fb-124c-4067-af48-afbac122b228
ms.openlocfilehash: 5c15cfb8050bc93e055dbde53308f9460ff90bc8
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89126388"
---
# <a name="char-c-reference"></a><span data-ttu-id="0c2ec-103">char (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="0c2ec-103">char (C# reference)</span></span>

<span data-ttu-id="0c2ec-104">`char`Słowo kluczowe type jest aliasem dla <xref:System.Char?displayProperty=nameWithType> typu struktury .NET, który reprezentuje znak Unicode UTF-16.</span><span class="sxs-lookup"><span data-stu-id="0c2ec-104">The `char` type keyword is an alias for the .NET <xref:System.Char?displayProperty=nameWithType> structure type that represents a Unicode UTF-16 character.</span></span>

|<span data-ttu-id="0c2ec-105">Typ</span><span class="sxs-lookup"><span data-stu-id="0c2ec-105">Type</span></span>|<span data-ttu-id="0c2ec-106">Zakres</span><span class="sxs-lookup"><span data-stu-id="0c2ec-106">Range</span></span>|<span data-ttu-id="0c2ec-107">Rozmiar</span><span class="sxs-lookup"><span data-stu-id="0c2ec-107">Size</span></span>|<span data-ttu-id="0c2ec-108">Typ .NET</span><span class="sxs-lookup"><span data-stu-id="0c2ec-108">.NET type</span></span>|
|----------|-----------|----------|-------------------------|
|`char`|<span data-ttu-id="0c2ec-109">U + 0000 do U + FFFF</span><span class="sxs-lookup"><span data-stu-id="0c2ec-109">U+0000 to U+FFFF</span></span>|<span data-ttu-id="0c2ec-110">16 bitów</span><span class="sxs-lookup"><span data-stu-id="0c2ec-110">16 bit</span></span>|<xref:System.Char?displayProperty=nameWithType>|

<span data-ttu-id="0c2ec-111">Wartość domyślna `char` typu to `\0` , czyli U + 0000.</span><span class="sxs-lookup"><span data-stu-id="0c2ec-111">The default value of the `char` type is `\0`, that is, U+0000.</span></span>

<span data-ttu-id="0c2ec-112">`char`Typ obsługuje operatory [porównania](../operators/comparison-operators.md), [równości](../operators/equality-operators.md), [zwiększania](../operators/arithmetic-operators.md#increment-operator-)i [zmniejszania](../operators/arithmetic-operators.md#decrement-operator---) .</span><span class="sxs-lookup"><span data-stu-id="0c2ec-112">The `char` type supports [comparison](../operators/comparison-operators.md), [equality](../operators/equality-operators.md), [increment](../operators/arithmetic-operators.md#increment-operator-), and [decrement](../operators/arithmetic-operators.md#decrement-operator---) operators.</span></span> <span data-ttu-id="0c2ec-113">Ponadto w przypadku `char` operandów, [arytmetyczne](../operators/arithmetic-operators.md) i [bitowe operatory logiczne](../operators/bitwise-and-shift-operators.md) wykonują operacje na odpowiednich kodach znaków i tworzą wynik `int` typu.</span><span class="sxs-lookup"><span data-stu-id="0c2ec-113">Moreover, for `char` operands, [arithmetic](../operators/arithmetic-operators.md) and [bitwise logical](../operators/bitwise-and-shift-operators.md) operators perform an operation on the corresponding character codes and produce the result of the `int` type.</span></span>

<span data-ttu-id="0c2ec-114">Typ [ciągu](reference-types.md#the-string-type) reprezentuje tekst jako sekwencję `char` wartości.</span><span class="sxs-lookup"><span data-stu-id="0c2ec-114">The [string](reference-types.md#the-string-type) type represents text as a sequence of `char` values.</span></span>

## <a name="literals"></a><span data-ttu-id="0c2ec-115">Literały</span><span class="sxs-lookup"><span data-stu-id="0c2ec-115">Literals</span></span>

<span data-ttu-id="0c2ec-116">Możesz określić `char` wartość przy użyciu:</span><span class="sxs-lookup"><span data-stu-id="0c2ec-116">You can specify a `char` value with:</span></span>

- <span data-ttu-id="0c2ec-117">literał znakowy.</span><span class="sxs-lookup"><span data-stu-id="0c2ec-117">a character literal.</span></span>
- <span data-ttu-id="0c2ec-118">sekwencja unikowa Unicode, która `\u` następuje po czterech symbolach szesnastkowej reprezentacji kodu znaku.</span><span class="sxs-lookup"><span data-stu-id="0c2ec-118">a Unicode escape sequence, which is `\u` followed by the four-symbol hexadecimal representation of a character code.</span></span>
- <span data-ttu-id="0c2ec-119">szesnastkowa sekwencja ucieczki, `\x` po której następuje reprezentacja szesnastkowa kodu znaku.</span><span class="sxs-lookup"><span data-stu-id="0c2ec-119">a hexadecimal escape sequence, which is `\x` followed by the hexadecimal representation of a character code.</span></span>

[!code-csharp-interactive[char literals](snippets/CharType.cs#Literals)]

<span data-ttu-id="0c2ec-120">Jak pokazano w powyższym przykładzie, można także rzutować wartość kodu znaku na odpowiadającą `char` wartość.</span><span class="sxs-lookup"><span data-stu-id="0c2ec-120">As the preceding example shows, you can also cast the value of a character code into the corresponding `char` value.</span></span>

> [!NOTE]
> <span data-ttu-id="0c2ec-121">W przypadku sekwencji unikowej Unicode należy określić wszystkie cztery cyfry szesnastkowe.</span><span class="sxs-lookup"><span data-stu-id="0c2ec-121">In the case of a Unicode escape sequence, you must specify all four hexadecimal digits.</span></span> <span data-ttu-id="0c2ec-122">Oznacza to, że `\u006A` jest prawidłową sekwencją ucieczki, `\u06A` a i `\u6A` są nieprawidłowe.</span><span class="sxs-lookup"><span data-stu-id="0c2ec-122">That is, `\u006A` is a valid escape sequence, while `\u06A` and `\u6A` are not valid.</span></span>
>
> <span data-ttu-id="0c2ec-123">W przypadku szesnastkowej sekwencji ucieczki można pominąć zera wiodące.</span><span class="sxs-lookup"><span data-stu-id="0c2ec-123">In the case of a hexadecimal escape sequence, you can omit the leading zeros.</span></span> <span data-ttu-id="0c2ec-124">Oznacza to, że `\x006A` `\x06A` `\x6A` sekwencje, i Escape są prawidłowe i odpowiadają temu samemu znakowi.</span><span class="sxs-lookup"><span data-stu-id="0c2ec-124">That is, the `\x006A`, `\x06A`, and `\x6A` escape sequences are valid and correspond to the same character.</span></span>

## <a name="conversions"></a><span data-ttu-id="0c2ec-125">Konwersje</span><span class="sxs-lookup"><span data-stu-id="0c2ec-125">Conversions</span></span>

<span data-ttu-id="0c2ec-126">`char`Typ jest niejawnie konwertowany na następujące typy [całkowite](integral-numeric-types.md) : `ushort` ,, `int` , `uint` `long` i `ulong` .</span><span class="sxs-lookup"><span data-stu-id="0c2ec-126">The `char` type is implicitly convertible to the following [integral](integral-numeric-types.md) types: `ushort`, `int`, `uint`, `long`, and `ulong`.</span></span> <span data-ttu-id="0c2ec-127">Jest on również niejawnie konwertowany na wbudowane typy liczbowe [zmiennoprzecinkowe](floating-point-numeric-types.md) : `float` , `double` , i `decimal` .</span><span class="sxs-lookup"><span data-stu-id="0c2ec-127">It's also implicitly convertible to the built-in [floating-point](floating-point-numeric-types.md) numeric types: `float`, `double`, and `decimal`.</span></span> <span data-ttu-id="0c2ec-128">Jest on jawnie konwertowany na `sbyte` `byte` typy, i `short` .</span><span class="sxs-lookup"><span data-stu-id="0c2ec-128">It's explicitly convertible to `sbyte`, `byte`, and `short` integral types.</span></span>

<span data-ttu-id="0c2ec-129">Nie istnieją niejawne konwersje z innych typów do `char` typu.</span><span class="sxs-lookup"><span data-stu-id="0c2ec-129">There are no implicit conversions from other types to the `char` type.</span></span> <span data-ttu-id="0c2ec-130">Jednak każdy typ liczbowy [całkowitego](integral-numeric-types.md) lub [zmiennoprzecinkowego](floating-point-numeric-types.md) jest jawnie konwertowany na `char` .</span><span class="sxs-lookup"><span data-stu-id="0c2ec-130">However, any [integral](integral-numeric-types.md) or [floating-point](floating-point-numeric-types.md) numeric type is explicitly convertible to `char`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="0c2ec-131">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="0c2ec-131">C# language specification</span></span>

<span data-ttu-id="0c2ec-132">Aby uzyskać więcej informacji, zobacz sekcję [Typy całkowite](~/_csharplang/spec/types.md#integral-types) [specyfikacji języka C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="0c2ec-132">For more information, see the [Integral types](~/_csharplang/spec/types.md#integral-types) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0c2ec-133">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="0c2ec-133">See also</span></span>

- [<span data-ttu-id="0c2ec-134">Dokumentacja języka C#</span><span class="sxs-lookup"><span data-stu-id="0c2ec-134">C# reference</span></span>](../index.md)
- [<span data-ttu-id="0c2ec-135">Typy wartości</span><span class="sxs-lookup"><span data-stu-id="0c2ec-135">Value types</span></span>](value-types.md)
- [<span data-ttu-id="0c2ec-136">Ciągi</span><span class="sxs-lookup"><span data-stu-id="0c2ec-136">Strings</span></span>](../../programming-guide/strings/index.md)
- <xref:System.Text.Rune?displayProperty=nameWithType>
- [<span data-ttu-id="0c2ec-137">Kodowanie znaków na platformie .NET</span><span class="sxs-lookup"><span data-stu-id="0c2ec-137">Character encoding in .NET</span></span>](../../../standard/base-types/character-encoding-introduction.md)
