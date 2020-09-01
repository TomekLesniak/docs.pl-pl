---
description: 'Dowiedz się więcej na temat wbudowanego typu wartości logicznej w języku C #'
title: Typ bool — odwołanie w C#
ms.date: 11/26/2019
f1_keywords:
- bool
- bool_CSharpKeyword
- "true"
- "false"
- true_CSharpKeyword
- false_CSharpKeyword
helpviewer_keywords:
- bool data type [C#]
- Boolean [C#]
ms.assetid: 551cfe35-2632-4343-af49-33ad12da08e2
ms.openlocfilehash: 23e5bc34f1751b0a706c20dae340920239fcda9d
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89126466"
---
# <a name="bool-c-reference"></a><span data-ttu-id="e814c-103">bool (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="e814c-103">bool (C# reference)</span></span>

<span data-ttu-id="e814c-104">`bool`Słowo kluczowe type jest aliasem dla <xref:System.Boolean?displayProperty=nameWithType> typu struktury .NET, który reprezentuje wartość logiczną, która może być albo `true` `false` .</span><span class="sxs-lookup"><span data-stu-id="e814c-104">The `bool` type keyword is an alias for the .NET <xref:System.Boolean?displayProperty=nameWithType> structure type that represents a Boolean value, which can be either `true` or `false`.</span></span>

<span data-ttu-id="e814c-105">Aby wykonać operacje logiczne z wartościami `bool` typu, użyj logicznych operatorów [logicznych](../operators/boolean-logical-operators.md) .</span><span class="sxs-lookup"><span data-stu-id="e814c-105">To perform logical operations with values of the `bool` type, use [Boolean logical](../operators/boolean-logical-operators.md) operators.</span></span> <span data-ttu-id="e814c-106">`bool`Typ jest typem wyniku [porównania](../operators/comparison-operators.md) i operatory [równości](../operators/equality-operators.md) .</span><span class="sxs-lookup"><span data-stu-id="e814c-106">The `bool` type is the result type of [comparison](../operators/comparison-operators.md) and [equality](../operators/equality-operators.md) operators.</span></span> <span data-ttu-id="e814c-107">`bool`Wyrażenie może być wyrażeniem warunkowym sterującym w instrukcjach [if](../keywords/if-else.md), [do](../keywords/do.md), [while](../keywords/while.md)i [for](../keywords/for.md) oraz w [operatorze `?:` warunkowym ](../operators/conditional-operator.md).</span><span class="sxs-lookup"><span data-stu-id="e814c-107">A `bool` expression can be a controlling conditional expression in the [if](../keywords/if-else.md), [do](../keywords/do.md), [while](../keywords/while.md), and [for](../keywords/for.md) statements and in the [conditional operator `?:`](../operators/conditional-operator.md).</span></span>

<span data-ttu-id="e814c-108">Wartość domyślna `bool` typu to `false` .</span><span class="sxs-lookup"><span data-stu-id="e814c-108">The default value of the `bool` type is `false`.</span></span>

## <a name="literals"></a><span data-ttu-id="e814c-109">Literały</span><span class="sxs-lookup"><span data-stu-id="e814c-109">Literals</span></span>

<span data-ttu-id="e814c-110">Można użyć `true` `false` literałów i, aby zainicjować `bool` zmienną lub przekazać `bool` wartość:</span><span class="sxs-lookup"><span data-stu-id="e814c-110">You can use the `true` and `false` literals to initialize a `bool` variable or to pass a `bool` value:</span></span>

[!code-csharp-interactive[bool literals](snippets/BoolType.cs#Literals)]

## <a name="three-valued-boolean-logic"></a><span data-ttu-id="e814c-111">Logika logiczna z trzema wartościami</span><span class="sxs-lookup"><span data-stu-id="e814c-111">Three-valued Boolean logic</span></span>

<span data-ttu-id="e814c-112">Użyj typu dopuszczającego wartość null `bool?` , jeśli potrzebujesz obsługi logiki trójwarstwowej, na przykład podczas pracy z bazami danych, które obsługują typ Boolean o wartości 3.</span><span class="sxs-lookup"><span data-stu-id="e814c-112">Use the nullable `bool?` type, if you need to support the three-valued logic, for example, when you work with databases that support a three-valued Boolean type.</span></span> <span data-ttu-id="e814c-113">W przypadku `bool?` operandów wstępnie zdefiniowane `&` Operatory i `|` obsługują logikę z trzema wartościami.</span><span class="sxs-lookup"><span data-stu-id="e814c-113">For the `bool?` operands, the predefined `&` and `|` operators support the three-valued logic.</span></span> <span data-ttu-id="e814c-114">Aby uzyskać więcej informacji, zobacz sekcję [Operatory logiczne wartości null](../operators/boolean-logical-operators.md#nullable-boolean-logical-operators) w artykule [Operatory logiczne Boolean](../operators/boolean-logical-operators.md) .</span><span class="sxs-lookup"><span data-stu-id="e814c-114">For more information, see the [Nullable Boolean logical operators](../operators/boolean-logical-operators.md#nullable-boolean-logical-operators) section of the [Boolean logical operators](../operators/boolean-logical-operators.md) article.</span></span>

<span data-ttu-id="e814c-115">Aby uzyskać więcej informacji na temat typów wartości null, zobacz [dopuszczanie typów wartości null](nullable-value-types.md).</span><span class="sxs-lookup"><span data-stu-id="e814c-115">For more information about nullable value types, see [Nullable value types](nullable-value-types.md).</span></span>

## <a name="conversions"></a><span data-ttu-id="e814c-116">Konwersje</span><span class="sxs-lookup"><span data-stu-id="e814c-116">Conversions</span></span>

<span data-ttu-id="e814c-117">Język C# zawiera tylko dwie konwersje, które obejmują `bool` Typ.</span><span class="sxs-lookup"><span data-stu-id="e814c-117">C# provides only two conversions that involve the `bool` type.</span></span> <span data-ttu-id="e814c-118">Są to niejawne konwersje do odpowiedniego typu dopuszczającego wartość null `bool?` i jawnej konwersji z `bool?` typu.</span><span class="sxs-lookup"><span data-stu-id="e814c-118">Those are an implicit conversion to the corresponding nullable `bool?` type and an explicit conversion from the `bool?` type.</span></span> <span data-ttu-id="e814c-119">Jednak platforma .NET udostępnia dodatkowe metody, których można użyć do przekonwertowania na typ lub z tego `bool` typu.</span><span class="sxs-lookup"><span data-stu-id="e814c-119">However, .NET provides additional methods that you can use to convert to or from the `bool` type.</span></span> <span data-ttu-id="e814c-120">Aby uzyskać więcej informacji, zobacz sekcję [konwertowanie do i z wartości logicznych](/dotnet/api/system.boolean#converting-to-and-from-boolean-values) na <xref:System.Boolean?displayProperty=nameWithType> stronie Dokumentacja interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="e814c-120">For more information, see the [Converting to and from Boolean values](/dotnet/api/system.boolean#converting-to-and-from-boolean-values) section of the <xref:System.Boolean?displayProperty=nameWithType> API reference page.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="e814c-121">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="e814c-121">C# language specification</span></span>

<span data-ttu-id="e814c-122">Aby uzyskać więcej informacji, zobacz sekcję [Typ bool](~/_csharplang/spec/types.md#the-bool-type) w [specyfikacji języka C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="e814c-122">For more information, see [The bool type](~/_csharplang/spec/types.md#the-bool-type) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e814c-123">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="e814c-123">See also</span></span>

- [<span data-ttu-id="e814c-124">Dokumentacja języka C#</span><span class="sxs-lookup"><span data-stu-id="e814c-124">C# reference</span></span>](../index.md)
- [<span data-ttu-id="e814c-125">Typy wartości</span><span class="sxs-lookup"><span data-stu-id="e814c-125">Value types</span></span>](value-types.md)
- [<span data-ttu-id="e814c-126">true i false, operatory</span><span class="sxs-lookup"><span data-stu-id="e814c-126">true and false operators</span></span>](../operators/true-false-operators.md)
