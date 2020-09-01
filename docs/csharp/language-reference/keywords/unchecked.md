---
description: unchecked — odwołanie w C#
title: unchecked — odwołanie w C#
ms.date: 07/20/2015
f1_keywords:
- unchecked_CSharpKeyword
- unchecked
helpviewer_keywords:
- unchecked keyword [C#]
ms.assetid: 0c021f7c-923f-4b3d-a58f-55336f5ac27e
ms.openlocfilehash: bb66639e3657b247b9ebcad1594daf1f57a5c76b
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89141988"
---
# <a name="unchecked-c-reference"></a><span data-ttu-id="72a73-103">unchecked (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="72a73-103">unchecked (C# Reference)</span></span>

<span data-ttu-id="72a73-104">`unchecked`Słowo kluczowe jest używane do pomijania sprawdzania przepełnienia dla operacji arytmetycznych i konwersji typu całkowitego.</span><span class="sxs-lookup"><span data-stu-id="72a73-104">The `unchecked` keyword is used to suppress overflow-checking for integral-type arithmetic operations and conversions.</span></span>

<span data-ttu-id="72a73-105">W niesprawdzonym kontekście, jeśli wyrażenie generuje wartość spoza zakresu typu docelowego, przepełnienie nie jest oflagowane.</span><span class="sxs-lookup"><span data-stu-id="72a73-105">In an unchecked context, if an expression produces a value that is outside the range of the destination type, the overflow is not flagged.</span></span> <span data-ttu-id="72a73-106">Na przykład, ponieważ obliczenia w poniższym przykładzie są wykonywane w `unchecked` bloku lub wyrażeniu, fakt, że wynik jest za duży dla liczby całkowitej, jest ignorowany i `int1` ma przypisaną wartość-2 147 483 639.</span><span class="sxs-lookup"><span data-stu-id="72a73-106">For example, because the calculation in the following example is performed in an `unchecked` block or expression, the fact that the result is too large for an integer is ignored, and `int1` is assigned the value -2,147,483,639.</span></span>

[!code-csharp[csrefKeywordsChecked#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsChecked/CS/csrefKeywordsChecked.cs#5)]

<span data-ttu-id="72a73-107">Jeśli `unchecked` środowisko zostanie usunięte, wystąpi błąd kompilacji.</span><span class="sxs-lookup"><span data-stu-id="72a73-107">If the `unchecked` environment is removed, a compilation error occurs.</span></span> <span data-ttu-id="72a73-108">Przepełnienie można wykryć w czasie kompilacji, ponieważ wszystkie warunki wyrażenia są stałymi.</span><span class="sxs-lookup"><span data-stu-id="72a73-108">The overflow can be detected at compile time because all the terms of the expression are constants.</span></span>

<span data-ttu-id="72a73-109">Wyrażenia zawierające warunki niestałe są domyślnie niezaznaczone w czasie kompilacji i w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="72a73-109">Expressions that contain non-constant terms are unchecked by default at compile time and run time.</span></span> <span data-ttu-id="72a73-110">Zobacz [zaewidencjonowano](checked.md) , aby uzyskać informacje na temat włączania sprawdzonego środowiska.</span><span class="sxs-lookup"><span data-stu-id="72a73-110">See [checked](checked.md) for information about enabling a checked environment.</span></span>

<span data-ttu-id="72a73-111">Ze względu na to, że sprawdzanie przepełnienia jest czasochłonne, użycie niesprawdzonego kodu w sytuacjach, gdy nie ma żadnych niebezpieczeństwa przepełnienia może zwiększyć wydajność.</span><span class="sxs-lookup"><span data-stu-id="72a73-111">Because checking for overflow takes time, the use of unchecked code in situations where there is no danger of overflow might improve performance.</span></span> <span data-ttu-id="72a73-112">Jeśli jednak przepełnienie jest możliwe, należy użyć zaznaczonego środowiska.</span><span class="sxs-lookup"><span data-stu-id="72a73-112">However, if overflow is a possibility, a checked environment should be used.</span></span>

## <a name="example"></a><span data-ttu-id="72a73-113">Przykład</span><span class="sxs-lookup"><span data-stu-id="72a73-113">Example</span></span>

<span data-ttu-id="72a73-114">Ten przykład pokazuje, jak używać `unchecked` słowa kluczowego.</span><span class="sxs-lookup"><span data-stu-id="72a73-114">This sample shows how to use the `unchecked` keyword.</span></span>

[!code-csharp[csrefKeywordsChecked#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsChecked/CS/csrefKeywordsChecked.cs#2)]

## <a name="c-language-specification"></a><span data-ttu-id="72a73-115">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="72a73-115">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="72a73-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="72a73-116">See also</span></span>

- [<span data-ttu-id="72a73-117">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="72a73-117">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="72a73-118">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="72a73-118">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="72a73-119">Słowa kluczowe języka C#</span><span class="sxs-lookup"><span data-stu-id="72a73-119">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="72a73-120">checked i unchecked</span><span class="sxs-lookup"><span data-stu-id="72a73-120">Checked and Unchecked</span></span>](checked-and-unchecked.md)
- [<span data-ttu-id="72a73-121">dane</span><span class="sxs-lookup"><span data-stu-id="72a73-121">checked</span></span>](checked.md)
