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
ms.openlocfilehash: 6c70934c3b861e1a1433e5c0b95bb32e9d717c53
ms.sourcegitcommit: eb7e87496f42361b1da98562dd75b516c9d58bbc
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/09/2020
ms.locfileid: "91877655"
---
# <a name="continue-c-reference"></a><span data-ttu-id="dc2e1-103">continue (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="dc2e1-103">continue (C# Reference)</span></span>

<span data-ttu-id="dc2e1-104">`continue`Instrukcja przekazuje formant do następnej iteracji otaczającej instrukcji [while](./while.md), [do](./do.md), [for](./for.md)lub [foreach](./foreach-in.md) , w której występuje.</span><span class="sxs-lookup"><span data-stu-id="dc2e1-104">The `continue` statement passes control to the next iteration of the enclosing [while](./while.md), [do](./do.md), [for](./for.md), or [foreach](./foreach-in.md) statement in which it appears.</span></span>

## <a name="example"></a><span data-ttu-id="dc2e1-105">Przykład</span><span class="sxs-lookup"><span data-stu-id="dc2e1-105">Example</span></span>

<span data-ttu-id="dc2e1-106">W tym przykładzie licznik jest zainicjowany do zliczenia z 1 do 10.</span><span class="sxs-lookup"><span data-stu-id="dc2e1-106">In this example, a counter is initialized to count from 1 to 10.</span></span> <span data-ttu-id="dc2e1-107">Używając `continue` instrukcji w połączeniu z wyrażeniem `(i < 9)` , instrukcje między `continue` i końcem `for` treści są pomijane w iteracjach, gdzie `i` jest mniejsza niż 9.</span><span class="sxs-lookup"><span data-stu-id="dc2e1-107">By using the `continue` statement in conjunction with the expression `(i < 9)`, the statements between `continue` and the end of the `for` body are skipped in the iterations where `i` is less than 9.</span></span> <span data-ttu-id="dc2e1-108">W ciągu ostatnich dwóch iteracji `for` pętli (gdzie i = = 9 i i = 10) `continue` instrukcja nie jest wykonywana, a wartość `i` jest drukowana w konsoli.</span><span class="sxs-lookup"><span data-stu-id="dc2e1-108">In the last two iterations of the `for` loop (where i == 9 and i == 10), the `continue` statement is not executed and the value of `i` is printed to the console.</span></span>

[!code-csharp[csrefKeywordsJump#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#3)]

## <a name="c-language-specification"></a><span data-ttu-id="dc2e1-109">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="dc2e1-109">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="dc2e1-110">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="dc2e1-110">See also</span></span>

- [<span data-ttu-id="dc2e1-111">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="dc2e1-111">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="dc2e1-112">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="dc2e1-112">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="dc2e1-113">Słowa kluczowe języka C#</span><span class="sxs-lookup"><span data-stu-id="dc2e1-113">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="dc2e1-114">Break, instrukcja</span><span class="sxs-lookup"><span data-stu-id="dc2e1-114">break Statement</span></span>](/cpp/cpp/break-statement-cpp)
