---
description: Odwołanie do języka C#
title: Odwołanie do języka C#
ms.date: 05/28/2018
f1_keywords:
- do_CSharpKeyword
- do
helpviewer_keywords:
- do keyword [C#]
ms.assetid: 50725f79-9ba6-4898-aa78-6e331568a1bb
ms.openlocfilehash: 601231f23a58e8af8339a733677f0bbd92bb4ffc
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89126960"
---
# <a name="do-c-reference"></a><span data-ttu-id="5f808-103">do (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="5f808-103">do (C# Reference)</span></span>

<span data-ttu-id="5f808-104">`do`Instrukcja wykonuje instrukcję lub blok instrukcji, gdy określone wyrażenie logiczne zwraca wartość `true` .</span><span class="sxs-lookup"><span data-stu-id="5f808-104">The `do` statement executes a statement or a block of statements while a specified Boolean expression evaluates to `true`.</span></span> <span data-ttu-id="5f808-105">Ponieważ to wyrażenie jest oceniane po każdym wykonaniu pętli, `do-while` Pętla wykonuje jeden lub więcej razy.</span><span class="sxs-lookup"><span data-stu-id="5f808-105">Because that expression is evaluated after each execution of the loop, a `do-while` loop executes one or more times.</span></span> <span data-ttu-id="5f808-106">Różni się to od pętli [while](while.md) , która wykonuje zero lub więcej razy.</span><span class="sxs-lookup"><span data-stu-id="5f808-106">This differs from the [while](while.md) loop, which executes zero or more times.</span></span>

<span data-ttu-id="5f808-107">W dowolnym momencie w `do` bloku instrukcji można przerwać pętlę przy użyciu instrukcji [Break](break.md) .</span><span class="sxs-lookup"><span data-stu-id="5f808-107">At any point within the `do` statement block, you can break out of the loop by using the [break](break.md) statement.</span></span>

<span data-ttu-id="5f808-108">Możesz przejść bezpośrednio do oceny `while` wyrażenia przy użyciu instrukcji [Continue](continue.md) .</span><span class="sxs-lookup"><span data-stu-id="5f808-108">You can step directly to the evaluation of the `while` expression by using the [continue](continue.md) statement.</span></span> <span data-ttu-id="5f808-109">Jeśli wyrażenie zwróci wartość `true` , wykonywanie jest kontynuowane na pierwszej instrukcji w pętli.</span><span class="sxs-lookup"><span data-stu-id="5f808-109">If the expression evaluates to `true`, execution continues at the first statement in the loop.</span></span> <span data-ttu-id="5f808-110">W przeciwnym razie wykonywanie jest kontynuowane po pierwszej instrukcji po pętli.</span><span class="sxs-lookup"><span data-stu-id="5f808-110">Otherwise, execution continues at the first statement after the loop.</span></span>

<span data-ttu-id="5f808-111">Możesz również wyjść z `do-while` pętli przez instrukcje [goto](goto.md), [Return](return.md)lub [throw](throw.md) .</span><span class="sxs-lookup"><span data-stu-id="5f808-111">You can also exit a `do-while` loop by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

## <a name="example"></a><span data-ttu-id="5f808-112">Przykład</span><span class="sxs-lookup"><span data-stu-id="5f808-112">Example</span></span>

<span data-ttu-id="5f808-113">W poniższym przykładzie pokazano sposób użycia `do` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="5f808-113">The following example shows the usage of the `do` statement.</span></span> <span data-ttu-id="5f808-114">Wybierz pozycję **Uruchom** , aby uruchomić przykładowy kod.</span><span class="sxs-lookup"><span data-stu-id="5f808-114">Select **Run** to run the example code.</span></span> <span data-ttu-id="5f808-115">Następnie można zmodyfikować kod i uruchomić go ponownie.</span><span class="sxs-lookup"><span data-stu-id="5f808-115">After that you can modify the code and run it again.</span></span>

[!code-csharp-interactive[do loop example](snippets/IterationKeywordsExamples.cs#4)]

## <a name="c-language-specification"></a><span data-ttu-id="5f808-116">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="5f808-116">C# language specification</span></span>

<span data-ttu-id="5f808-117">Aby uzyskać więcej informacji, zobacz sekcję do [instrukcji](~/_csharplang/spec/statements.md#the-do-statement) w [specyfikacji języka C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="5f808-117">For more information, see [The do statement](~/_csharplang/spec/statements.md#the-do-statement) section of the [C# language specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span>

## <a name="see-also"></a><span data-ttu-id="5f808-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="5f808-118">See also</span></span>

- [<span data-ttu-id="5f808-119">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="5f808-119">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="5f808-120">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="5f808-120">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="5f808-121">Słowa kluczowe języka C#</span><span class="sxs-lookup"><span data-stu-id="5f808-121">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="5f808-122">while, instrukcja</span><span class="sxs-lookup"><span data-stu-id="5f808-122">while statement</span></span>](while.md)
