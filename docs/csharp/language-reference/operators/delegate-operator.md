---
title: operator delegata — odwołanie w C#
ms.date: 07/18/2019
helpviewer_keywords:
- delegate [C#]
- anonymous method [C#]
ms.openlocfilehash: 33c438b88f1e993f4648786da9b20b91961b7ee1
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/11/2020
ms.locfileid: "88062993"
---
# <a name="delegate-operator-c-reference"></a><span data-ttu-id="5d329-102">Delegate — operator (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="5d329-102">delegate operator (C# reference)</span></span>

<span data-ttu-id="5d329-103">`delegate`Operator tworzy anonimową metodę, która może zostać przekonwertowana na typ delegata:</span><span class="sxs-lookup"><span data-stu-id="5d329-103">The `delegate` operator creates an anonymous method that can be converted to a delegate type:</span></span>

[!code-csharp-interactive[anonymous method](snippets/shared/DelegateOperator.cs#AnonymousMethod)]

> [!NOTE]
> <span data-ttu-id="5d329-104">Począwszy od języka C# 3 wyrażenia lambda zapewniają bardziej zwięzły i jednoznaczny sposób tworzenia anonimowej funkcji.</span><span class="sxs-lookup"><span data-stu-id="5d329-104">Beginning with C# 3, lambda expressions provide a more concise and expressive way to create an anonymous function.</span></span> <span data-ttu-id="5d329-105">Użyj [operatora =>](lambda-operator.md) , aby utworzyć wyrażenie lambda:</span><span class="sxs-lookup"><span data-stu-id="5d329-105">Use the [=> operator](lambda-operator.md) to construct a lambda expression:</span></span>
>
> [!code-csharp-interactive[lambda expression](snippets/shared/DelegateOperator.cs#Lambda)]
>
> <span data-ttu-id="5d329-106">Aby uzyskać więcej informacji na temat funkcji wyrażeń lambda, na przykład przechwytywania zmiennych zewnętrznych, zobacz [lambda Expressions](lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="5d329-106">For more information about features of lambda expressions, for example, capturing outer variables, see [Lambda expressions](lambda-expressions.md).</span></span>

<span data-ttu-id="5d329-107">Gdy używasz `delegate` operatora, możesz pominąć listę parametrów.</span><span class="sxs-lookup"><span data-stu-id="5d329-107">When you use the `delegate` operator, you might omit the parameter list.</span></span> <span data-ttu-id="5d329-108">W takim przypadku utworzona Metoda anonimowa może zostać przekonwertowana na typ delegata z dowolną listą parametrów, co ilustruje poniższy przykład:</span><span class="sxs-lookup"><span data-stu-id="5d329-108">If you do that, the created anonymous method can be converted to a delegate type with any list of  parameters, as the following example shows:</span></span>

[!code-csharp-interactive[no parameter list](snippets/shared/DelegateOperator.cs#WithoutParameterList)]

<span data-ttu-id="5d329-109">Jest to jedyna funkcja metod anonimowych, które nie są obsługiwane przez wyrażenia lambda.</span><span class="sxs-lookup"><span data-stu-id="5d329-109">That's the only functionality of anonymous methods that is not supported by lambda expressions.</span></span> <span data-ttu-id="5d329-110">We wszystkich innych przypadkach wyrażenie lambda jest preferowanym sposobem pisania kodu śródwierszowego.</span><span class="sxs-lookup"><span data-stu-id="5d329-110">In all other cases, a lambda expression is a preferred way to write inline code.</span></span>

<span data-ttu-id="5d329-111">Możesz również użyć `delegate` słowa kluczowego, aby zadeklarować [typ delegata](../builtin-types/reference-types.md#the-delegate-type).</span><span class="sxs-lookup"><span data-stu-id="5d329-111">You also use the `delegate` keyword to declare a [delegate type](../builtin-types/reference-types.md#the-delegate-type).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="5d329-112">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="5d329-112">C# language specification</span></span>

<span data-ttu-id="5d329-113">Aby uzyskać więcej informacji, zobacz sekcję [wyrażenia funkcji anonimowej](~/_csharplang/spec/expressions.md#anonymous-function-expressions) [specyfikacji języka C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="5d329-113">For more information, see the [Anonymous function expressions](~/_csharplang/spec/expressions.md#anonymous-function-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5d329-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="5d329-114">See also</span></span>

- [<span data-ttu-id="5d329-115">Dokumentacja języka C#</span><span class="sxs-lookup"><span data-stu-id="5d329-115">C# reference</span></span>](../index.md)
- [<span data-ttu-id="5d329-116">Operatory i wyrażenia języka C#</span><span class="sxs-lookup"><span data-stu-id="5d329-116">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="5d329-117">=> — operator</span><span class="sxs-lookup"><span data-stu-id="5d329-117">=> operator</span></span>](lambda-operator.md)
