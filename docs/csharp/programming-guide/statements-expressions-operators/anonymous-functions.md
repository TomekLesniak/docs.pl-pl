---
title: Funkcje anonimowe — Przewodnik programowania w języku C#
description: Dowiedz się więcej na temat funkcji anonimowych. Aby utworzyć anonimową funkcję, można użyć wyrażenia lambda lub metody anonimowej.
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [C#], as anonymous functions
- anonymous functions [C#]
- anonymous methods [C#]
ms.assetid: 6ce3f04d-0c71-4728-9127-634c7e9a8365
ms.openlocfilehash: ae8bda3c68542637b1430587ca4a537980c028bc
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381674"
---
# <a name="anonymous-functions-c-programming-guide"></a><span data-ttu-id="c80af-104">Funkcje anonimowe (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="c80af-104">Anonymous functions (C# Programming Guide)</span></span>

<span data-ttu-id="c80af-105">Funkcja anonimowa jest instrukcją "inline" lub wyrażeniem, które może być używane wszędzie tam, gdzie oczekiwany jest typ delegata.</span><span class="sxs-lookup"><span data-stu-id="c80af-105">An anonymous function is an "inline" statement or expression that can be used wherever a delegate type is expected.</span></span> <span data-ttu-id="c80af-106">Można go użyć do zainicjowania nazwanego delegata lub przekazać go zamiast nazwanego typu delegata jako parametru metody.</span><span class="sxs-lookup"><span data-stu-id="c80af-106">You can use it to initialize a named delegate or pass it instead of a named delegate type as a method parameter.</span></span>

<span data-ttu-id="c80af-107">Możesz użyć [wyrażenia lambda](lambda-expressions.md) lub [metody anonimowej](../../language-reference/operators/delegate-operator.md) , aby utworzyć funkcję anonimową.</span><span class="sxs-lookup"><span data-stu-id="c80af-107">You can use a [lambda expression](lambda-expressions.md) or an [anonymous method](../../language-reference/operators/delegate-operator.md) to create an anonymous function.</span></span> <span data-ttu-id="c80af-108">Zalecamy używanie wyrażeń lambda, ponieważ zapewniają one bardziej zwięzły i jednoznaczny sposób pisania kodu śródwierszowego.</span><span class="sxs-lookup"><span data-stu-id="c80af-108">We recommend using lambda expressions as they provide more concise and expressive way to write inline code.</span></span> <span data-ttu-id="c80af-109">W przeciwieństwie do metod anonimowych niektóre typy wyrażeń lambda można przekonwertować na typy drzewa wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="c80af-109">Unlike anonymous methods, some types of lambda expressions can be converted to the expression tree types.</span></span>

## <a name="the-evolution-of-delegates-in-c"></a><span data-ttu-id="c80af-110">Ewolucja delegatów w języku C\#</span><span class="sxs-lookup"><span data-stu-id="c80af-110">The Evolution of Delegates in C\#</span></span>

 <span data-ttu-id="c80af-111">W języku C# 1,0 utworzono wystąpienie delegata, jawnie inicjując go za pomocą metody, która została zdefiniowana w innym miejscu w kodzie.</span><span class="sxs-lookup"><span data-stu-id="c80af-111">In C# 1.0, you created an instance of a delegate by explicitly initializing it with a method that was defined elsewhere in the code.</span></span> <span data-ttu-id="c80af-112">W języku C# 2,0 wprowadzono koncepcję metod anonimowych jako sposób pisania nienazwanych bloków instrukcji wbudowanych, które mogą być wykonywane w wywołaniu delegata.</span><span class="sxs-lookup"><span data-stu-id="c80af-112">C# 2.0 introduced the concept of anonymous methods as a way to write unnamed inline statement blocks that can be executed in a delegate invocation.</span></span> <span data-ttu-id="c80af-113">W języku C# 3,0 wprowadzono wyrażenia lambda, które są podobne w koncepcji metod anonimowych, ale bardziej wyraźne i zwięzłe.</span><span class="sxs-lookup"><span data-stu-id="c80af-113">C# 3.0 introduced lambda expressions, which are similar in concept to anonymous methods but more expressive and concise.</span></span> <span data-ttu-id="c80af-114">Te dwie funkcje są określane zbiorczo jako *funkcje anonimowe*.</span><span class="sxs-lookup"><span data-stu-id="c80af-114">These two features are known collectively as *anonymous functions*.</span></span> <span data-ttu-id="c80af-115">Ogólnie rzecz biorąc, aplikacje przeznaczone dla .NET Framework 3,5 lub nowszych powinny używać wyrażeń lambda.</span><span class="sxs-lookup"><span data-stu-id="c80af-115">In general, applications that target .NET Framework 3.5 or later should use lambda expressions.</span></span>  
  
 <span data-ttu-id="c80af-116">Poniższy przykład ilustruje ewolucję tworzenia delegatów z C# 1,0 do C# 3,0:</span><span class="sxs-lookup"><span data-stu-id="c80af-116">The following example demonstrates the evolution of delegate creation from C# 1.0 to C# 3.0:</span></span>  
  
 [!code-csharp[csProgGuideLINQ#65](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#65)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="c80af-117">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="c80af-117">C# language specification</span></span>

<span data-ttu-id="c80af-118">Aby uzyskać więcej informacji, zobacz sekcję [wyrażenia funkcji anonimowej](~/_csharplang/spec/expressions.md#anonymous-function-expressions) [specyfikacji języka C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="c80af-118">For more information, see the [Anonymous function expressions](~/_csharplang/spec/expressions.md#anonymous-function-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c80af-119">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="c80af-119">See also</span></span>

- [<span data-ttu-id="c80af-120">Instrukcje, wyrażenia i operatory</span><span class="sxs-lookup"><span data-stu-id="c80af-120">Statements, Expressions, and Operators</span></span>](./index.md)
- [<span data-ttu-id="c80af-121">Wyrażenia lambda</span><span class="sxs-lookup"><span data-stu-id="c80af-121">Lambda Expressions</span></span>](./lambda-expressions.md)
- [<span data-ttu-id="c80af-122">Delegaci</span><span class="sxs-lookup"><span data-stu-id="c80af-122">Delegates</span></span>](../delegates/index.md)
- [<span data-ttu-id="c80af-123">Drzewa wyrażeń (C#)</span><span class="sxs-lookup"><span data-stu-id="c80af-123">Expression Trees (C#)</span></span>](../concepts/expression-trees/index.md)
