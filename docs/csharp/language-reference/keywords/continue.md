---
description: Continue — instrukcja — odwołanie w C#
title: Continue — instrukcja — odwołanie w C#
ms.date: 07/20/2015
f1_keywords:
- continue_CSharpKeyword
- continue
helpviewer_keywords:
- continue keyword [C#]
ms.assetid: 8a5ac96f-f98a-4519-b32d-345847ed7be0
ms.openlocfilehash: 76578b0ad7e2b969609fbf50df1f9ab7de6e5097
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89128442"
---
# <a name="continue-c-reference"></a><span data-ttu-id="778e4-103">continue (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="778e4-103">continue (C# Reference)</span></span>

<span data-ttu-id="778e4-104">`continue`Instrukcja przekazuje formant do następnej iteracji otaczającej instrukcji [while](./while.md), [do](./do.md), [for](./for.md)lub [foreach](./foreach-in.md) , w której występuje.</span><span class="sxs-lookup"><span data-stu-id="778e4-104">The `continue` statement passes control to the next iteration of the enclosing [while](./while.md), [do](./do.md), [for](./for.md), or [foreach](./foreach-in.md) statement in which it appears.</span></span>

## <a name="example"></a><span data-ttu-id="778e4-105">Przykład</span><span class="sxs-lookup"><span data-stu-id="778e4-105">Example</span></span>

<span data-ttu-id="778e4-106">W tym przykładzie licznik jest zainicjowany do zliczenia z 1 do 10.</span><span class="sxs-lookup"><span data-stu-id="778e4-106">In this example, a counter is initialized to count from 1 to 10.</span></span> <span data-ttu-id="778e4-107">Używając `continue` instrukcji w połączeniu z wyrażeniem `(i < 9)` , instrukcje między `continue` i końcem `for` treści są pomijane.</span><span class="sxs-lookup"><span data-stu-id="778e4-107">By using the `continue` statement in conjunction with the expression `(i < 9)`, the statements between `continue` and the end of the `for` body are skipped.</span></span>

[!code-csharp[csrefKeywordsJump#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#3)]

## <a name="c-language-specification"></a><span data-ttu-id="778e4-108">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="778e4-108">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="778e4-109">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="778e4-109">See also</span></span>

- [<span data-ttu-id="778e4-110">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="778e4-110">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="778e4-111">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="778e4-111">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="778e4-112">Słowa kluczowe języka C#</span><span class="sxs-lookup"><span data-stu-id="778e4-112">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="778e4-113">Break, instrukcja</span><span class="sxs-lookup"><span data-stu-id="778e4-113">break Statement</span></span>](/cpp/cpp/break-statement-cpp)
