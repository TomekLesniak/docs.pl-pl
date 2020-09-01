---
description: operator delegata — odwołanie w C#
title: operator delegata — odwołanie w C#
ms.date: 07/18/2019
helpviewer_keywords:
- delegate [C#]
- anonymous method [C#]
ms.openlocfilehash: 1dfaaf40c0f5a19534adef3be7e3c917bc95c4a8
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89122254"
---
# <a name="delegate-operator-c-reference"></a><span data-ttu-id="9cad7-103">Delegate — operator (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="9cad7-103">delegate operator (C# reference)</span></span>

<span data-ttu-id="9cad7-104">`delegate`Operator tworzy anonimową metodę, która może zostać przekonwertowana na typ delegata:</span><span class="sxs-lookup"><span data-stu-id="9cad7-104">The `delegate` operator creates an anonymous method that can be converted to a delegate type:</span></span>

[!code-csharp-interactive[anonymous method](snippets/shared/DelegateOperator.cs#AnonymousMethod)]

> [!NOTE]
> <span data-ttu-id="9cad7-105">Począwszy od języka C# 3 wyrażenia lambda zapewniają bardziej zwięzły i jednoznaczny sposób tworzenia anonimowej funkcji.</span><span class="sxs-lookup"><span data-stu-id="9cad7-105">Beginning with C# 3, lambda expressions provide a more concise and expressive way to create an anonymous function.</span></span> <span data-ttu-id="9cad7-106">Użyj [operatora =>](lambda-operator.md) , aby utworzyć wyrażenie lambda:</span><span class="sxs-lookup"><span data-stu-id="9cad7-106">Use the [=> operator](lambda-operator.md) to construct a lambda expression:</span></span>
>
> [!code-csharp-interactive[lambda expression](snippets/shared/DelegateOperator.cs#Lambda)]
>
> <span data-ttu-id="9cad7-107">Aby uzyskać więcej informacji na temat funkcji wyrażeń lambda, na przykład przechwytywania zmiennych zewnętrznych, zobacz [lambda Expressions](lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="9cad7-107">For more information about features of lambda expressions, for example, capturing outer variables, see [Lambda expressions](lambda-expressions.md).</span></span>

<span data-ttu-id="9cad7-108">Gdy używasz `delegate` operatora, możesz pominąć listę parametrów.</span><span class="sxs-lookup"><span data-stu-id="9cad7-108">When you use the `delegate` operator, you might omit the parameter list.</span></span> <span data-ttu-id="9cad7-109">W takim przypadku utworzona Metoda anonimowa może zostać przekonwertowana na typ delegata z dowolną listą parametrów, co ilustruje poniższy przykład:</span><span class="sxs-lookup"><span data-stu-id="9cad7-109">If you do that, the created anonymous method can be converted to a delegate type with any list of  parameters, as the following example shows:</span></span>

[!code-csharp-interactive[no parameter list](snippets/shared/DelegateOperator.cs#WithoutParameterList)]

<span data-ttu-id="9cad7-110">Jest to jedyna funkcja metod anonimowych, które nie są obsługiwane przez wyrażenia lambda.</span><span class="sxs-lookup"><span data-stu-id="9cad7-110">That's the only functionality of anonymous methods that is not supported by lambda expressions.</span></span> <span data-ttu-id="9cad7-111">We wszystkich innych przypadkach wyrażenie lambda jest preferowanym sposobem pisania kodu śródwierszowego.</span><span class="sxs-lookup"><span data-stu-id="9cad7-111">In all other cases, a lambda expression is a preferred way to write inline code.</span></span>

<span data-ttu-id="9cad7-112">Możesz również użyć `delegate` słowa kluczowego, aby zadeklarować [typ delegata](../builtin-types/reference-types.md#the-delegate-type).</span><span class="sxs-lookup"><span data-stu-id="9cad7-112">You also use the `delegate` keyword to declare a [delegate type](../builtin-types/reference-types.md#the-delegate-type).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="9cad7-113">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="9cad7-113">C# language specification</span></span>

<span data-ttu-id="9cad7-114">Aby uzyskać więcej informacji, zobacz sekcję [wyrażenia funkcji anonimowej](~/_csharplang/spec/expressions.md#anonymous-function-expressions) [specyfikacji języka C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="9cad7-114">For more information, see the [Anonymous function expressions](~/_csharplang/spec/expressions.md#anonymous-function-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9cad7-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="9cad7-115">See also</span></span>

- [<span data-ttu-id="9cad7-116">Dokumentacja języka C#</span><span class="sxs-lookup"><span data-stu-id="9cad7-116">C# reference</span></span>](../index.md)
- [<span data-ttu-id="9cad7-117">Operatory i wyrażenia języka C#</span><span class="sxs-lookup"><span data-stu-id="9cad7-117">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="9cad7-118">=> — operator</span><span class="sxs-lookup"><span data-stu-id="9cad7-118">=> operator</span></span>](lambda-operator.md)
