---
description: Informacje o czasie wykonywania w języku C#
title: Informacje o czasie wykonywania w języku C#
ms.date: 05/28/2018
f1_keywords:
- while_CSharpKeyword
- while
helpviewer_keywords:
- while keyword [C#]
ms.assetid: 72a0765c-6852-4aca-b327-4a11cb7f5c59
ms.openlocfilehash: 97299f9ac6f2cdd6bbddf831b3ee2ad711935fbe
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89141871"
---
# <a name="while-c-reference"></a><span data-ttu-id="2ddc2-103">while (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="2ddc2-103">while (C# Reference)</span></span>

<span data-ttu-id="2ddc2-104">`while`Instrukcja wykonuje instrukcję lub blok instrukcji, gdy określone wyrażenie logiczne zwraca wartość `true` .</span><span class="sxs-lookup"><span data-stu-id="2ddc2-104">The `while` statement executes a statement or a block of statements while a specified Boolean expression evaluates to `true`.</span></span> <span data-ttu-id="2ddc2-105">Ponieważ to wyrażenie jest oceniane przed każdym wykonaniem pętli, `while` Pętla wykonuje zero lub więcej razy.</span><span class="sxs-lookup"><span data-stu-id="2ddc2-105">Because that expression is evaluated before each execution of the loop, a `while` loop executes zero or more times.</span></span> <span data-ttu-id="2ddc2-106">Różni się to od [pętli do](do.md) , która wykonuje jeden lub więcej razy.</span><span class="sxs-lookup"><span data-stu-id="2ddc2-106">This differs from the [do](do.md) loop, which executes one or more times.</span></span>

<span data-ttu-id="2ddc2-107">W dowolnym momencie w `while` bloku instrukcji można przerwać pętlę przy użyciu instrukcji [Break](break.md) .</span><span class="sxs-lookup"><span data-stu-id="2ddc2-107">At any point within the `while` statement block, you can break out of the loop by using the [break](break.md) statement.</span></span>

<span data-ttu-id="2ddc2-108">Możesz przejść bezpośrednio do oceny `while` wyrażenia przy użyciu instrukcji [Continue](continue.md) .</span><span class="sxs-lookup"><span data-stu-id="2ddc2-108">You can step directly to the evaluation of the `while` expression by using the [continue](continue.md) statement.</span></span> <span data-ttu-id="2ddc2-109">Jeśli wyrażenie zwróci wartość `true` , wykonywanie jest kontynuowane na pierwszej instrukcji w pętli.</span><span class="sxs-lookup"><span data-stu-id="2ddc2-109">If the expression evaluates to `true`, execution continues at the first statement in the loop.</span></span> <span data-ttu-id="2ddc2-110">W przeciwnym razie wykonywanie jest kontynuowane po pierwszej instrukcji po pętli.</span><span class="sxs-lookup"><span data-stu-id="2ddc2-110">Otherwise, execution continues at the first statement after the loop.</span></span>

<span data-ttu-id="2ddc2-111">Możesz również wyjść z `while` pętli przez instrukcje [goto](goto.md), [Return](return.md)lub [throw](throw.md) .</span><span class="sxs-lookup"><span data-stu-id="2ddc2-111">You can also exit a `while` loop by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

## <a name="example"></a><span data-ttu-id="2ddc2-112">Przykład</span><span class="sxs-lookup"><span data-stu-id="2ddc2-112">Example</span></span>

<span data-ttu-id="2ddc2-113">W poniższym przykładzie pokazano sposób użycia `while` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="2ddc2-113">The following example shows the usage of the `while` statement.</span></span> <span data-ttu-id="2ddc2-114">Wybierz pozycję **Uruchom** , aby uruchomić przykładowy kod.</span><span class="sxs-lookup"><span data-stu-id="2ddc2-114">Select **Run** to run the example code.</span></span> <span data-ttu-id="2ddc2-115">Następnie można zmodyfikować kod i uruchomić go ponownie.</span><span class="sxs-lookup"><span data-stu-id="2ddc2-115">After that you can modify the code and run it again.</span></span>

[!code-csharp-interactive[while loop example](snippets/IterationKeywordsExamples.cs#3)]

## <a name="c-language-specification"></a><span data-ttu-id="2ddc2-116">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="2ddc2-116">C# language specification</span></span>

<span data-ttu-id="2ddc2-117">Aby uzyskać więcej informacji, zobacz sekcję [While instrukcji](~/_csharplang/spec/statements.md#the-while-statement) w [specyfikacji języka C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="2ddc2-117">For more information, see [The while statement](~/_csharplang/spec/statements.md#the-while-statement) section of the [C# language specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span>

## <a name="see-also"></a><span data-ttu-id="2ddc2-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="2ddc2-118">See also</span></span>

- [<span data-ttu-id="2ddc2-119">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="2ddc2-119">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="2ddc2-120">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="2ddc2-120">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="2ddc2-121">Słowa kluczowe języka C#</span><span class="sxs-lookup"><span data-stu-id="2ddc2-121">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="2ddc2-122">do — instrukcja</span><span class="sxs-lookup"><span data-stu-id="2ddc2-122">do statement</span></span>](do.md)
