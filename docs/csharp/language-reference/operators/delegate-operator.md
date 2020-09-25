---
description: operator delegata — odwołanie w C#
title: operator delegata — odwołanie w C#
ms.date: 09/25/2020
helpviewer_keywords:
- delegate [C#]
- anonymous method [C#]
ms.openlocfilehash: db2bf673db12e4a10741a26112820726a4b8aaee
ms.sourcegitcommit: c04535ad05e374fb269fcfc6509217755fbc0d54
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/25/2020
ms.locfileid: "91247660"
---
# <a name="delegate-operator-c-reference"></a><span data-ttu-id="10041-103">Delegate — operator (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="10041-103">delegate operator (C# reference)</span></span>

<span data-ttu-id="10041-104">`delegate`Operator tworzy anonimową metodę, która może zostać przekonwertowana na typ delegata:</span><span class="sxs-lookup"><span data-stu-id="10041-104">The `delegate` operator creates an anonymous method that can be converted to a delegate type:</span></span>

[!code-csharp-interactive[anonymous method](snippets/shared/DelegateOperator.cs#AnonymousMethod)]

> [!NOTE]
> <span data-ttu-id="10041-105">Począwszy od języka C# 3 wyrażenia lambda zapewniają bardziej zwięzły i jednoznaczny sposób tworzenia anonimowej funkcji.</span><span class="sxs-lookup"><span data-stu-id="10041-105">Beginning with C# 3, lambda expressions provide a more concise and expressive way to create an anonymous function.</span></span> <span data-ttu-id="10041-106">Użyj [operatora =>](lambda-operator.md) , aby utworzyć wyrażenie lambda:</span><span class="sxs-lookup"><span data-stu-id="10041-106">Use the [=> operator](lambda-operator.md) to construct a lambda expression:</span></span>
>
> [!code-csharp-interactive[lambda expression](snippets/shared/DelegateOperator.cs#Lambda)]
>
> <span data-ttu-id="10041-107">Aby uzyskać więcej informacji na temat funkcji wyrażeń lambda, na przykład przechwytywania zmiennych zewnętrznych, zobacz [lambda Expressions](lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="10041-107">For more information about features of lambda expressions, for example, capturing outer variables, see [Lambda expressions](lambda-expressions.md).</span></span>

<span data-ttu-id="10041-108">Gdy używasz `delegate` operatora, możesz pominąć listę parametrów.</span><span class="sxs-lookup"><span data-stu-id="10041-108">When you use the `delegate` operator, you might omit the parameter list.</span></span> <span data-ttu-id="10041-109">W takim przypadku utworzona Metoda anonimowa może zostać przekonwertowana na typ delegata z dowolną listą parametrów, co ilustruje poniższy przykład:</span><span class="sxs-lookup"><span data-stu-id="10041-109">If you do that, the created anonymous method can be converted to a delegate type with any list of  parameters, as the following example shows:</span></span>

[!code-csharp-interactive[no parameter list](snippets/shared/DelegateOperator.cs#WithoutParameterList)]

<span data-ttu-id="10041-110">Jest to jedyna funkcja metod anonimowych, które nie są obsługiwane przez wyrażenia lambda.</span><span class="sxs-lookup"><span data-stu-id="10041-110">That's the only functionality of anonymous methods that is not supported by lambda expressions.</span></span> <span data-ttu-id="10041-111">We wszystkich innych przypadkach wyrażenie lambda jest preferowanym sposobem pisania kodu śródwierszowego.</span><span class="sxs-lookup"><span data-stu-id="10041-111">In all other cases, a lambda expression is a preferred way to write inline code.</span></span>

<span data-ttu-id="10041-112">Począwszy od języka C# 9,0, można użyć [odrzucania](../../discards.md) , aby określić dwa lub więcej parametrów wejściowych metody anonimowej, które nie są używane przez metodę:</span><span class="sxs-lookup"><span data-stu-id="10041-112">Beginning with C# 9.0, you can use [discards](../../discards.md) to specify two or more input parameters of an anonymous method that aren't used by the method:</span></span>

:::code language="csharp" source="snippets/shared/DelegateOperator.cs" id="SnippetDiscards" :::

<span data-ttu-id="10041-113">W celu zapewnienia zgodności z poprzednimi wersjami, jeśli tylko jeden parametr ma `_` `_` nazwę, jest traktowany jako nazwa tego parametru w metodzie anonimowej.</span><span class="sxs-lookup"><span data-stu-id="10041-113">For backwards compatibility, if only a single parameter is named `_`, `_` is treated as the name of that parameter within an anonymous method.</span></span>

<span data-ttu-id="10041-114">Począwszy od języka C# 9,0, można użyć `static` modyfikatora w deklaracji metody anonimowej:</span><span class="sxs-lookup"><span data-stu-id="10041-114">Also beginning with C# 9.0, you can use the `static` modifier at the declaration of an anonymous method:</span></span>

:::code language="csharp" source="snippets/shared/DelegateOperator.cs" id="SnippetStatic" :::

<span data-ttu-id="10041-115">Statyczna metoda anonimowa nie może przechwycić lokalnych zmiennych lub stanu wystąpienia z otaczających zakresów.</span><span class="sxs-lookup"><span data-stu-id="10041-115">A static anonymous method can't capture local variables or instance state from enclosing scopes.</span></span>

<span data-ttu-id="10041-116">Możesz również użyć `delegate` słowa kluczowego, aby zadeklarować [typ delegata](../builtin-types/reference-types.md#the-delegate-type).</span><span class="sxs-lookup"><span data-stu-id="10041-116">You also use the `delegate` keyword to declare a [delegate type](../builtin-types/reference-types.md#the-delegate-type).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="10041-117">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="10041-117">C# language specification</span></span>

<span data-ttu-id="10041-118">Aby uzyskać więcej informacji, zobacz sekcję [wyrażenia funkcji anonimowej](~/_csharplang/spec/expressions.md#anonymous-function-expressions) [specyfikacji języka C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="10041-118">For more information, see the [Anonymous function expressions](~/_csharplang/spec/expressions.md#anonymous-function-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="10041-119">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="10041-119">See also</span></span>

- [<span data-ttu-id="10041-120">Dokumentacja języka C#</span><span class="sxs-lookup"><span data-stu-id="10041-120">C# reference</span></span>](../index.md)
- [<span data-ttu-id="10041-121">Operatory i wyrażenia języka C#</span><span class="sxs-lookup"><span data-stu-id="10041-121">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="10041-122">=> — operator</span><span class="sxs-lookup"><span data-stu-id="10041-122">=> operator</span></span>](lambda-operator.md)
