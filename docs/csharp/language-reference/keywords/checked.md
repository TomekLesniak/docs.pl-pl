---
description: Checked — odwołanie w C#
title: Checked — odwołanie w C#
ms.date: 07/20/2015
f1_keywords:
- checked_CSharpKeyword
- checked
helpviewer_keywords:
- checked keyword [C#]
ms.assetid: 718a1194-988d-48a3-b089-d6ee8bd1608d
ms.openlocfilehash: 4dd8bc02d3af89d6bab3aef55a88cb8b40704da6
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89138283"
---
# <a name="checked-c-reference"></a><span data-ttu-id="95da4-103">checked (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="95da4-103">checked (C# Reference)</span></span>

<span data-ttu-id="95da4-104">`checked`Słowo kluczowe jest używane do jawnego włączania sprawdzania przepełnienia dla operacji arytmetycznych i konwersji typu całkowitego.</span><span class="sxs-lookup"><span data-stu-id="95da4-104">The `checked` keyword is used to explicitly enable overflow checking for integral-type arithmetic operations and conversions.</span></span>

<span data-ttu-id="95da4-105">Domyślnie wyrażenie zawierające tylko stałe wartości powoduje błąd kompilatora, jeśli wyrażenie generuje wartość spoza zakresu typu docelowego.</span><span class="sxs-lookup"><span data-stu-id="95da4-105">By default, an expression that contains only constant values causes a compiler error if the expression produces a value that is outside the range of the destination type.</span></span> <span data-ttu-id="95da4-106">Jeśli wyrażenie zawiera jedną lub więcej wartości niestałych, kompilator nie wykrywa przepełnienia.</span><span class="sxs-lookup"><span data-stu-id="95da4-106">If the expression contains one or more non-constant values, the compiler does not detect the overflow.</span></span> <span data-ttu-id="95da4-107">Obliczenie wyrażenia przypisanego do `i2` w poniższym przykładzie nie powoduje błędu kompilatora.</span><span class="sxs-lookup"><span data-stu-id="95da4-107">Evaluating the expression assigned to `i2` in the following example does not cause a compiler error.</span></span>

[!code-csharp[csrefKeywordsChecked#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsChecked/CS/csrefKeywordsChecked.cs#3)]

<span data-ttu-id="95da4-108">Domyślnie te wyrażenia niestałe nie są sprawdzane w celu przepełnienia w czasie wykonywania i nie powodują wyjątków przepełnienia.</span><span class="sxs-lookup"><span data-stu-id="95da4-108">By default, these non-constant expressions are not checked for overflow at run time either, and they do not raise overflow exceptions.</span></span> <span data-ttu-id="95da4-109">W poprzednim przykładzie przedstawiono wartość-2 147 483 639 jako sumę dwóch dodatnich liczb całkowitych.</span><span class="sxs-lookup"><span data-stu-id="95da4-109">The previous example displays -2,147,483,639 as the sum of two positive integers.</span></span>

<span data-ttu-id="95da4-110">Sprawdzanie przepełnienia można włączyć przez opcje kompilatora, konfigurację środowiska lub użycie `checked` słowa kluczowego.</span><span class="sxs-lookup"><span data-stu-id="95da4-110">Overflow checking can be enabled by compiler options, environment configuration, or use of the `checked` keyword.</span></span> <span data-ttu-id="95da4-111">W poniższych przykładach pokazano, jak używać `checked` wyrażenia lub `checked` bloku do wykrywania przepełnienia, który jest generowany przez poprzednią sumę w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="95da4-111">The following examples demonstrate how to use a `checked` expression or a `checked` block to detect the overflow that is produced by the previous sum at run time.</span></span> <span data-ttu-id="95da4-112">Oba przykłady powodują wyjątek przepełnienia.</span><span class="sxs-lookup"><span data-stu-id="95da4-112">Both examples raise an overflow exception.</span></span>

[!code-csharp[csrefKeywordsChecked#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsChecked/CS/csrefKeywordsChecked.cs#4)]

<span data-ttu-id="95da4-113">[Niesprawdzone](./unchecked.md) słowo kluczowe może służyć do zapobiegania sprawdzaniu przepełnienia.</span><span class="sxs-lookup"><span data-stu-id="95da4-113">The [unchecked](./unchecked.md) keyword can be used to prevent overflow checking.</span></span>

## <a name="example"></a><span data-ttu-id="95da4-114">Przykład</span><span class="sxs-lookup"><span data-stu-id="95da4-114">Example</span></span>

<span data-ttu-id="95da4-115">Ten przykład pokazuje, jak używać `checked` do włączania sprawdzania przepełnienia w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="95da4-115">This sample shows how to use `checked` to enable overflow checking at run time.</span></span>

[!code-csharp[csrefKeywordsChecked#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsChecked/CS/csrefKeywordsChecked.cs#1)]

## <a name="c-language-specification"></a><span data-ttu-id="95da4-116">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="95da4-116">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="95da4-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="95da4-117">See also</span></span>

- [<span data-ttu-id="95da4-118">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="95da4-118">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="95da4-119">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="95da4-119">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="95da4-120">Słowa kluczowe języka C#</span><span class="sxs-lookup"><span data-stu-id="95da4-120">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="95da4-121">checked i unchecked</span><span class="sxs-lookup"><span data-stu-id="95da4-121">Checked and Unchecked</span></span>](./checked-and-unchecked.md)
- [<span data-ttu-id="95da4-122">unchecked</span><span class="sxs-lookup"><span data-stu-id="95da4-122">unchecked</span></span>](./unchecked.md)
