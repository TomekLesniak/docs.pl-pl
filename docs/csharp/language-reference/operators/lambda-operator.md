---
description: Operator> — odwołanie w C#
title: Operator> — odwołanie w C#
ms.date: 01/22/2019
f1_keywords:
- =>_CSharpKeyword
helpviewer_keywords:
- lambda operator [C#]
- => operator [C#]
- lambda expressions [C#], => operator
ms.openlocfilehash: 6a4df3a4bd358b87f98ff1bd5a3f624b1029a73b
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89128364"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="49934-103">=> — operator (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="49934-103">=> operator (C# reference)</span></span>

<span data-ttu-id="49934-104">`=>`Token jest obsługiwany w dwóch formach: jako [operator lambda](#lambda-operator) oraz jako separator nazwy elementu członkowskiego i implementacji elementu członkowskiego w [definicji treści wyrażenia](#expression-body-definition).</span><span class="sxs-lookup"><span data-stu-id="49934-104">The `=>` token is supported in two forms: as the [lambda operator](#lambda-operator) and as a separator of a member name and the member implementation in an [expression body definition](#expression-body-definition).</span></span>

## <a name="lambda-operator"></a><span data-ttu-id="49934-105">Operator lambda</span><span class="sxs-lookup"><span data-stu-id="49934-105">Lambda operator</span></span>

<span data-ttu-id="49934-106">W [wyrażeniach lambda](lambda-expressions.md)operator lambda `=>` oddziela parametry wejściowe po lewej stronie od treści lambda po prawej stronie.</span><span class="sxs-lookup"><span data-stu-id="49934-106">In [lambda expressions](lambda-expressions.md), the lambda operator `=>` separates the input parameters on the left side from the lambda body on the right side.</span></span>

<span data-ttu-id="49934-107">W poniższym przykładzie użyto funkcji [LINQ](../../programming-guide/concepts/linq/index.md) z składnią metody, aby pokazać użycie wyrażeń lambda:</span><span class="sxs-lookup"><span data-stu-id="49934-107">The following example uses the [LINQ](../../programming-guide/concepts/linq/index.md) feature with method syntax to demonstrate the usage of lambda expressions:</span></span>

[!code-csharp-interactive[infer types of input variables](snippets/shared/LambdaOperator.cs#InferredTypes)]

<span data-ttu-id="49934-108">Parametry wejściowe wyrażenia lambda są silnie wpisywane w czasie kompilacji.</span><span class="sxs-lookup"><span data-stu-id="49934-108">Input parameters of a lambda expression are strongly typed at compile time.</span></span> <span data-ttu-id="49934-109">Gdy kompilator może wywnioskować typy parametrów wejściowych, jak w poprzednim przykładzie, można pominąć deklaracje typu.</span><span class="sxs-lookup"><span data-stu-id="49934-109">When the compiler can infer the types of input parameters, like in the preceding example, you may omit type declarations.</span></span> <span data-ttu-id="49934-110">Jeśli musisz określić typ parametrów wejściowych, należy to zrobić dla każdego parametru, jak pokazano w poniższym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="49934-110">If you need to specify the type of input parameters, you must do that for each parameter, as the following example shows:</span></span>

[!code-csharp-interactive[specify types of input variables](snippets/shared/LambdaOperator.cs#ExplicitTypes)]

<span data-ttu-id="49934-111">Poniższy przykład pokazuje, jak zdefiniować wyrażenie lambda bez parametrów wejściowych:</span><span class="sxs-lookup"><span data-stu-id="49934-111">The following example shows how to define a lambda expression without input parameters:</span></span>

[!code-csharp-interactive[without input variables](snippets/shared/LambdaOperator.cs#WithoutInput)]

<span data-ttu-id="49934-112">Aby uzyskać więcej informacji, zobacz [wyrażenia lambda](lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="49934-112">For more information, see [Lambda expressions](lambda-expressions.md).</span></span>

## <a name="expression-body-definition"></a><span data-ttu-id="49934-113">Definicja treści wyrażenia</span><span class="sxs-lookup"><span data-stu-id="49934-113">Expression body definition</span></span>

<span data-ttu-id="49934-114">Definicja treści wyrażenia ma następującą składnię ogólną:</span><span class="sxs-lookup"><span data-stu-id="49934-114">An expression body definition has the following general syntax:</span></span>

```csharp
member => expression;
```

<span data-ttu-id="49934-115">gdzie `expression` jest prawidłowym wyrażeniem.</span><span class="sxs-lookup"><span data-stu-id="49934-115">where `expression` is a valid expression.</span></span> <span data-ttu-id="49934-116">Zwracany typ elementu `expression` musi być niejawnie konwertowany na typ zwracany elementu członkowskiego.</span><span class="sxs-lookup"><span data-stu-id="49934-116">The return type of `expression` must be implicitly convertible to the member's return type.</span></span> <span data-ttu-id="49934-117">Jeśli typem zwracanym elementu członkowskiego jest `void` lub, jeśli element członkowski jest konstruktorem, finalizatorem lub właściwością, lub typem `set` dostępu indeksatora, `expression` musi być [*wyrażeniem instrukcji*](~/_csharplang/spec/statements.md#expression-statements).</span><span class="sxs-lookup"><span data-stu-id="49934-117">If the member's return type is `void` or if the member is a constructor, a finalizer, or a property or indexer `set` accessor, `expression` must be a [*statement expression*](~/_csharplang/spec/statements.md#expression-statements).</span></span> <span data-ttu-id="49934-118">Ze względu na to, że wynik wyrażenia jest odrzucany, zwracany typ wyrażenia może być dowolnym typem.</span><span class="sxs-lookup"><span data-stu-id="49934-118">Because the expression's result is discarded, the return type of that expression can be any type.</span></span>

<span data-ttu-id="49934-119">W poniższym przykładzie przedstawiono definicję treści wyrażenia dla `Person.ToString` metody:</span><span class="sxs-lookup"><span data-stu-id="49934-119">The following example shows an expression body definition for a `Person.ToString` method:</span></span>

```csharp
public override string ToString() => $"{fname} {lname}".Trim();
```

<span data-ttu-id="49934-120">Jest to skrócona wersja następującej definicji metody:</span><span class="sxs-lookup"><span data-stu-id="49934-120">It's a shorthand version of the following method definition:</span></span>

```csharp
public override string ToString()
{
   return $"{fname} {lname}".Trim();
}
```

<span data-ttu-id="49934-121">Definicje treści wyrażenia dla metod, operatorów i właściwości tylko do odczytu są obsługiwane począwszy od języka C# 6.</span><span class="sxs-lookup"><span data-stu-id="49934-121">Expression body definitions for methods, operators, and read-only properties are supported beginning with C# 6.</span></span> <span data-ttu-id="49934-122">Definicje treści wyrażenia dla konstruktorów, finalizatorów i metod dostępu właściwości i indeksatora są obsługiwane począwszy od języka C# 7,0.</span><span class="sxs-lookup"><span data-stu-id="49934-122">Expression body definitions for constructors, finalizers, and property and indexer accessors are supported beginning with C# 7.0.</span></span>

<span data-ttu-id="49934-123">Aby uzyskać więcej informacji, zobacz [elementy członkowskie z wyrażeniami](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span><span class="sxs-lookup"><span data-stu-id="49934-123">For more information, see [Expression-bodied members](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="49934-124">Przeciążanie operatora</span><span class="sxs-lookup"><span data-stu-id="49934-124">Operator overloadability</span></span>

<span data-ttu-id="49934-125">`=>`Operator nie może być przeciążony.</span><span class="sxs-lookup"><span data-stu-id="49934-125">The `=>` operator cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="49934-126">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="49934-126">C# language specification</span></span>

<span data-ttu-id="49934-127">Aby uzyskać więcej informacji na temat operatora lambda, zobacz sekcję [wyrażenia funkcji anonimowej](~/_csharplang/spec/expressions.md#anonymous-function-expressions) [specyfikacji języka C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="49934-127">For more information about the lambda operator, see the [Anonymous function expressions](~/_csharplang/spec/expressions.md#anonymous-function-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="49934-128">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="49934-128">See also</span></span>

- [<span data-ttu-id="49934-129">Dokumentacja języka C#</span><span class="sxs-lookup"><span data-stu-id="49934-129">C# reference</span></span>](../index.md)
- [<span data-ttu-id="49934-130">Operatory i wyrażenia języka C#</span><span class="sxs-lookup"><span data-stu-id="49934-130">C# operators and expressions</span></span>](index.md)
