---
description: operator delegata — odwołanie w C#
title: operator delegata — odwołanie w C#
ms.date: 09/22/2020
helpviewer_keywords:
- delegate [C#]
- anonymous method [C#]
ms.openlocfilehash: 6c087d9bdb2f526cf7d94c3a0f2c1a929b0343ef
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874913"
---
# <a name="delegate-operator-c-reference"></a><span data-ttu-id="e04d4-103">Delegate — operator (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="e04d4-103">delegate operator (C# reference)</span></span>

<span data-ttu-id="e04d4-104">`delegate`Operator tworzy anonimową metodę, która może zostać przekonwertowana na typ delegata:</span><span class="sxs-lookup"><span data-stu-id="e04d4-104">The `delegate` operator creates an anonymous method that can be converted to a delegate type:</span></span>

[!code-csharp-interactive[anonymous method](snippets/shared/DelegateOperator.cs#AnonymousMethod)]

> [!NOTE]
> <span data-ttu-id="e04d4-105">Począwszy od języka C# 3 wyrażenia lambda zapewniają bardziej zwięzły i jednoznaczny sposób tworzenia anonimowej funkcji.</span><span class="sxs-lookup"><span data-stu-id="e04d4-105">Beginning with C# 3, lambda expressions provide a more concise and expressive way to create an anonymous function.</span></span> <span data-ttu-id="e04d4-106">Użyj [operatora =>](lambda-operator.md) , aby utworzyć wyrażenie lambda:</span><span class="sxs-lookup"><span data-stu-id="e04d4-106">Use the [=> operator](lambda-operator.md) to construct a lambda expression:</span></span>
>
> [!code-csharp-interactive[lambda expression](snippets/shared/DelegateOperator.cs#Lambda)]
>
> <span data-ttu-id="e04d4-107">Aby uzyskać więcej informacji na temat funkcji wyrażeń lambda, na przykład przechwytywania zmiennych zewnętrznych, zobacz [lambda Expressions](lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="e04d4-107">For more information about features of lambda expressions, for example, capturing outer variables, see [Lambda expressions](lambda-expressions.md).</span></span>

<span data-ttu-id="e04d4-108">Gdy używasz `delegate` operatora, możesz pominąć listę parametrów.</span><span class="sxs-lookup"><span data-stu-id="e04d4-108">When you use the `delegate` operator, you might omit the parameter list.</span></span> <span data-ttu-id="e04d4-109">W takim przypadku utworzona Metoda anonimowa może zostać przekonwertowana na typ delegata z dowolną listą parametrów, co ilustruje poniższy przykład:</span><span class="sxs-lookup"><span data-stu-id="e04d4-109">If you do that, the created anonymous method can be converted to a delegate type with any list of  parameters, as the following example shows:</span></span>

[!code-csharp-interactive[no parameter list](snippets/shared/DelegateOperator.cs#WithoutParameterList)]

<span data-ttu-id="e04d4-110">Jest to jedyna funkcja metod anonimowych, które nie są obsługiwane przez wyrażenia lambda.</span><span class="sxs-lookup"><span data-stu-id="e04d4-110">That's the only functionality of anonymous methods that is not supported by lambda expressions.</span></span> <span data-ttu-id="e04d4-111">We wszystkich innych przypadkach wyrażenie lambda jest preferowanym sposobem pisania kodu śródwierszowego.</span><span class="sxs-lookup"><span data-stu-id="e04d4-111">In all other cases, a lambda expression is a preferred way to write inline code.</span></span>

<span data-ttu-id="e04d4-112">Począwszy od języka C# 9,0, można użyć [odrzucania](../../discards.md) , aby określić dwa lub więcej parametrów wejściowych metody anonimowej, które nie są używane przez metodę:</span><span class="sxs-lookup"><span data-stu-id="e04d4-112">Beginning with C# 9.0, you can use [discards](../../discards.md) to specify two or more input parameters of an anonymous method that aren't used by the method:</span></span>

:::code language="csharp" source="snippets/shared/DelegateOperator.cs" id="SnippetDiscards" :::

<span data-ttu-id="e04d4-113">W celu zapewnienia zgodności z poprzednimi wersjami, jeśli tylko jeden parametr ma `_` `_` nazwę, jest traktowany jako nazwa tego parametru w metodzie anonimowej.</span><span class="sxs-lookup"><span data-stu-id="e04d4-113">For backwards compatibility, if only a single parameter is named `_`, `_` is treated as the name of that parameter within an anonymous method.</span></span>

<span data-ttu-id="e04d4-114">Możesz również użyć `delegate` słowa kluczowego, aby zadeklarować [typ delegata](../builtin-types/reference-types.md#the-delegate-type).</span><span class="sxs-lookup"><span data-stu-id="e04d4-114">You also use the `delegate` keyword to declare a [delegate type](../builtin-types/reference-types.md#the-delegate-type).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="e04d4-115">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="e04d4-115">C# language specification</span></span>

<span data-ttu-id="e04d4-116">Aby uzyskać więcej informacji, zobacz sekcję [wyrażenia funkcji anonimowej](~/_csharplang/spec/expressions.md#anonymous-function-expressions) [specyfikacji języka C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="e04d4-116">For more information, see the [Anonymous function expressions](~/_csharplang/spec/expressions.md#anonymous-function-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e04d4-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="e04d4-117">See also</span></span>

- [<span data-ttu-id="e04d4-118">Dokumentacja języka C#</span><span class="sxs-lookup"><span data-stu-id="e04d4-118">C# reference</span></span>](../index.md)
- [<span data-ttu-id="e04d4-119">Operatory i wyrażenia języka C#</span><span class="sxs-lookup"><span data-stu-id="e04d4-119">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="e04d4-120">=> — operator</span><span class="sxs-lookup"><span data-stu-id="e04d4-120">=> operator</span></span>](lambda-operator.md)
