---
description: '! operator (null-łagodniejszej) — odwołanie w C#'
title: '! operator (null-łagodniejszej) — odwołanie w C#'
ms.date: 10/11/2019
f1_keywords:
- '!_CSharpKeyword'
helpviewer_keywords:
- null-forgiving operator [C#]
- '! operator [C#]'
ms.openlocfilehash: 7ae35f4741e1ef377b73a15066dddd243c94d8fe
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89118224"
---
# <a name="-null-forgiving-operator-c-reference"></a><span data-ttu-id="043a5-105">!</span><span class="sxs-lookup"><span data-stu-id="043a5-105">!</span></span> <span data-ttu-id="043a5-106">(null-łagodniejszej) — operator (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="043a5-106">(null-forgiving) operator (C# reference)</span></span>

<span data-ttu-id="043a5-107">Dostępne w języku C# 8,0 i nowszych, jednoargumentowy operator przyrostkowy `!` jest operatorem łagodniejszej o wartości null.</span><span class="sxs-lookup"><span data-stu-id="043a5-107">Available in C# 8.0 and later, the unary postfix `!` operator is the null-forgiving operator.</span></span> <span data-ttu-id="043a5-108">W włączonym [kontekście dopuszczającym wartość null](../../nullable-references.md#nullable-annotation-context)należy użyć operatora null-łagodniejszej, aby zadeklarować wyrażenie `x` typu referencyjnego nie jest `null` : `x!` .</span><span class="sxs-lookup"><span data-stu-id="043a5-108">In an enabled [nullable annotation context](../../nullable-references.md#nullable-annotation-context), you use the null-forgiving operator to declare that expression `x` of a reference type isn't `null`: `x!`.</span></span> <span data-ttu-id="043a5-109">Jednoargumentowy `!` operator prefiksu jest [logicznym operatorem negacji](boolean-logical-operators.md#logical-negation-operator-).</span><span class="sxs-lookup"><span data-stu-id="043a5-109">The unary prefix `!` operator is the [logical negation operator](boolean-logical-operators.md#logical-negation-operator-).</span></span>

<span data-ttu-id="043a5-110">Operator null-łagodniejszej nie ma wpływu w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="043a5-110">The null-forgiving operator has no effect at run time.</span></span> <span data-ttu-id="043a5-111">Ma wpływ tylko na analizę przepływu statycznego kompilatora przez zmianę stanu null wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="043a5-111">It only affects the compiler's static flow analysis by changing the null state of the expression.</span></span> <span data-ttu-id="043a5-112">W czasie wykonywania wyrażenie `x!` oblicza wynik wyrażenia bazowego `x` .</span><span class="sxs-lookup"><span data-stu-id="043a5-112">At run time, expression `x!` evaluates to the result of the underlying expression `x`.</span></span>

> [!NOTE]
> <span data-ttu-id="043a5-113">W języku C# 8 operator łagodniejszej o wartości null kończy listę poprzednich operacji [warunkowych o wartości null](member-access-operators.md#null-conditional-operators--and-) .</span><span class="sxs-lookup"><span data-stu-id="043a5-113">In C# 8, the null-forgiving operator terminates the list of preceding [null-conditional](member-access-operators.md#null-conditional-operators--and-) operations.</span></span> <span data-ttu-id="043a5-114">Na przykład wyrażenie `x?.y!.z` jest analizowane jako `(x?.y)!.z` .</span><span class="sxs-lookup"><span data-stu-id="043a5-114">For example, the expression `x?.y!.z` is parsed as `(x?.y)!.z`.</span></span> <span data-ttu-id="043a5-115">Ze względu na tę interpretację, `z` jest oceniane, nawet jeśli `x` jest `null` , co może skutkować <xref:System.NullReferenceException> .</span><span class="sxs-lookup"><span data-stu-id="043a5-115">Due to this interpretation, `z` is evaluated even if `x` is `null`, which may result in a <xref:System.NullReferenceException>.</span></span>

<span data-ttu-id="043a5-116">Aby uzyskać więcej informacji na temat funkcji typów referencyjnych dopuszczających wartość null, zobacz [typy referencyjne dopuszczające wartość null](../builtin-types/nullable-reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="043a5-116">For more information about the nullable reference types feature, see [Nullable reference types](../builtin-types/nullable-reference-types.md).</span></span>

## <a name="examples"></a><span data-ttu-id="043a5-117">Przykłady</span><span class="sxs-lookup"><span data-stu-id="043a5-117">Examples</span></span>

<span data-ttu-id="043a5-118">Jednym z przypadków użycia operatora null-łagodniejszej jest Testowanie logiki walidacji argumentów.</span><span class="sxs-lookup"><span data-stu-id="043a5-118">One of the use cases of the null-forgiving operator is in testing the argument validation logic.</span></span> <span data-ttu-id="043a5-119">Rozważmy na przykład następujące klasy:</span><span class="sxs-lookup"><span data-stu-id="043a5-119">For example, consider the following class:</span></span>

[!code-csharp[Person class](snippets/shared/NullForgivingOperator.cs#PersonClass)]

<span data-ttu-id="043a5-120">Używając [platformy testów MSTest](../../../core/testing/unit-testing-with-mstest.md), można utworzyć następujący test dla logiki walidacji w konstruktorze:</span><span class="sxs-lookup"><span data-stu-id="043a5-120">Using the [MSTest test framework](../../../core/testing/unit-testing-with-mstest.md), you can create the following test for the validation logic in the constructor:</span></span>

[!code-csharp[Person test](snippets/shared/NullForgivingOperator.cs#TestPerson)]

<span data-ttu-id="043a5-121">Bez operatora null łagodniejszej kompilator generuje następujące ostrzeżenie dla poprzedniego kodu: `Warning CS8625: Cannot convert null literal to non-nullable reference type` .</span><span class="sxs-lookup"><span data-stu-id="043a5-121">Without the null-forgiving operator, the compiler generates the following warning for the preceding code: `Warning CS8625: Cannot convert null literal to non-nullable reference type`.</span></span> <span data-ttu-id="043a5-122">Za pomocą operatora null-łagodniejszej, należy poinformować kompilator, że `null` oczekiwano, i nie powinien być ostrzegany o.</span><span class="sxs-lookup"><span data-stu-id="043a5-122">By using the null-forgiving operator, you inform the compiler that passing `null` is expected and shouldn't be warned about.</span></span>

<span data-ttu-id="043a5-123">Można również użyć operatora o wartości null-łagodniejszej, gdy wiadomo, że wyrażenie nie może być, `null` ale kompilator nie rozpoznaje tego elementu.</span><span class="sxs-lookup"><span data-stu-id="043a5-123">You can also use the null-forgiving operator when you definitely know that an expression cannot be `null` but the compiler doesn't manage to recognize that.</span></span> <span data-ttu-id="043a5-124">W poniższym przykładzie, jeśli `IsValid` Metoda zwraca `true` , jego argument nie jest `null` i można bezpiecznie odwoływać się do niego:</span><span class="sxs-lookup"><span data-stu-id="043a5-124">In the following example, if the `IsValid` method returns `true`, its argument is not `null` and you can safely dereference it:</span></span>

[!code-csharp[Use null-forgiving operator](snippets/shared/NullForgivingOperator.cs#UseNullForgiving)]

<span data-ttu-id="043a5-125">Bez operatora null łagodniejszej kompilator generuje następujące ostrzeżenie dla `p.Name` kodu: `Warning CS8602: Dereference of a possibly null reference` .</span><span class="sxs-lookup"><span data-stu-id="043a5-125">Without the null-forgiving operator, the compiler generates the following warning for the `p.Name` code: `Warning CS8602: Dereference of a possibly null reference`.</span></span>

<span data-ttu-id="043a5-126">Jeśli można zmodyfikować `IsValid` metodę, można użyć atrybutu [NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute) do informowania kompilatora, że argument `IsValid` metody nie może być, `null` gdy metoda zwraca `true` :</span><span class="sxs-lookup"><span data-stu-id="043a5-126">If you can modify the `IsValid` method, you can use the [NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute) attribute to inform the compiler that an argument of the `IsValid` method cannot be `null` when the method returns `true`:</span></span>

[!code-csharp[Use an attribute](snippets/shared/NullForgivingOperator.cs#UseAttribute)]

<span data-ttu-id="043a5-127">W poprzednim przykładzie nie trzeba używać operatora o wartości null-łagodniejszej, ponieważ kompilator ma wystarczającą ilość informacji, aby dowiedzieć się, że `p` nie może znajdować się `null` wewnątrz `if` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="043a5-127">In the preceding example, you don't need to use the null-forgiving operator because the compiler has enough information to find out that `p` cannot be `null` inside the `if` statement.</span></span> <span data-ttu-id="043a5-128">Aby uzyskać więcej informacji o atrybutach, które umożliwiają podanie dodatkowych informacji o stanie null zmiennej, zobacz [uaktualnianie interfejsów API z atrybutami w celu zdefiniowania oczekiwań o wartości null](../attributes/nullable-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="043a5-128">For more information about the attributes that allow you to provide additional information about the null state of a variable, see [Upgrade APIs with attributes to define null expectations](../attributes/nullable-analysis.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="043a5-129">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="043a5-129">C# language specification</span></span>

<span data-ttu-id="043a5-130">Aby uzyskać więcej informacji, zobacz sekcję [operator null-łagodniejszej](~/_csharplang/proposals/csharp-8.0/nullable-reference-types-specification.md#the-null-forgiving-operator) w [wersji roboczej specyfikacji typów odwołań dopuszczających wartość null](~/_csharplang/proposals/csharp-8.0/nullable-reference-types-specification.md).</span><span class="sxs-lookup"><span data-stu-id="043a5-130">For more information, see [The null-forgiving operator](~/_csharplang/proposals/csharp-8.0/nullable-reference-types-specification.md#the-null-forgiving-operator) section of the [draft of the nullable reference types specification](~/_csharplang/proposals/csharp-8.0/nullable-reference-types-specification.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="043a5-131">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="043a5-131">See also</span></span>

- [<span data-ttu-id="043a5-132">Dokumentacja języka C#</span><span class="sxs-lookup"><span data-stu-id="043a5-132">C# reference</span></span>](../index.md)
- [<span data-ttu-id="043a5-133">Operatory i wyrażenia języka C#</span><span class="sxs-lookup"><span data-stu-id="043a5-133">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="043a5-134">Samouczek: Projektowanie przy użyciu typów referencyjnych dopuszczających wartość null</span><span class="sxs-lookup"><span data-stu-id="043a5-134">Tutorial: Design with nullable reference types</span></span>](../../tutorials/nullable-reference-types.md)
