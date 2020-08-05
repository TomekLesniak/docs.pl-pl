---
title: '! operator (null-łagodniejszej) — odwołanie w C#'
ms.date: 10/11/2019
f1_keywords:
- '!_CSharpKeyword'
helpviewer_keywords:
- null-forgiving operator [C#]
- '! operator [C#]'
ms.openlocfilehash: b21b8a1f3c182fdc58d297424e0e70885e209e94
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/04/2020
ms.locfileid: "87555152"
---
# <a name="-null-forgiving-operator-c-reference"></a><span data-ttu-id="db87d-103">!</span><span class="sxs-lookup"><span data-stu-id="db87d-103">!</span></span> <span data-ttu-id="db87d-104">(null-łagodniejszej) — operator (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="db87d-104">(null-forgiving) operator (C# reference)</span></span>

<span data-ttu-id="db87d-105">Dostępne w języku C# 8,0 i nowszych, jednoargumentowy operator przyrostkowy `!` jest operatorem łagodniejszej o wartości null.</span><span class="sxs-lookup"><span data-stu-id="db87d-105">Available in C# 8.0 and later, the unary postfix `!` operator is the null-forgiving operator.</span></span> <span data-ttu-id="db87d-106">W włączonym [kontekście dopuszczającym wartość null](../../nullable-references.md#nullable-annotation-context)należy użyć operatora null-łagodniejszej, aby zadeklarować wyrażenie `x` typu referencyjnego nie jest `null` : `x!` .</span><span class="sxs-lookup"><span data-stu-id="db87d-106">In an enabled [nullable annotation context](../../nullable-references.md#nullable-annotation-context), you use the null-forgiving operator to declare that expression `x` of a reference type isn't `null`: `x!`.</span></span> <span data-ttu-id="db87d-107">Jednoargumentowy `!` operator prefiksu jest [logicznym operatorem negacji](boolean-logical-operators.md#logical-negation-operator-).</span><span class="sxs-lookup"><span data-stu-id="db87d-107">The unary prefix `!` operator is the [logical negation operator](boolean-logical-operators.md#logical-negation-operator-).</span></span>

<span data-ttu-id="db87d-108">Operator null-łagodniejszej nie ma wpływu w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="db87d-108">The null-forgiving operator has no effect at run time.</span></span> <span data-ttu-id="db87d-109">Ma wpływ tylko na analizę przepływu statycznego kompilatora przez zmianę stanu null wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="db87d-109">It only affects the compiler's static flow analysis by changing the null state of the expression.</span></span> <span data-ttu-id="db87d-110">W czasie wykonywania wyrażenie `x!` oblicza wynik wyrażenia bazowego `x` .</span><span class="sxs-lookup"><span data-stu-id="db87d-110">At run time, expression `x!` evaluates to the result of the underlying expression `x`.</span></span>

> [!NOTE]
> <span data-ttu-id="db87d-111">W języku C# 8 operator łagodniejszej o wartości null kończy listę poprzednich operacji [warunkowych o wartości null](member-access-operators.md#null-conditional-operators--and-) .</span><span class="sxs-lookup"><span data-stu-id="db87d-111">In C# 8, the null-forgiving operator terminates the list of preceding [null-conditional](member-access-operators.md#null-conditional-operators--and-) operations.</span></span> <span data-ttu-id="db87d-112">Na przykład wyrażenie `x?.y!.z` jest analizowane jako `(x?.y)!.z` .</span><span class="sxs-lookup"><span data-stu-id="db87d-112">For example, the expression `x?.y!.z` is parsed as `(x?.y)!.z`.</span></span> <span data-ttu-id="db87d-113">Ze względu na tę interpretację, `z` jest oceniane, nawet jeśli `x` jest `null` , co może skutkować <xref:System.NullReferenceException> .</span><span class="sxs-lookup"><span data-stu-id="db87d-113">Due to this interpretation, `z` is evaluated even if `x` is `null`, which may result in a <xref:System.NullReferenceException>.</span></span>

<span data-ttu-id="db87d-114">Aby uzyskać więcej informacji na temat funkcji typów referencyjnych dopuszczających wartość null, zobacz [typy referencyjne dopuszczające wartość null](../builtin-types/nullable-reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="db87d-114">For more information about the nullable reference types feature, see [Nullable reference types](../builtin-types/nullable-reference-types.md).</span></span>

## <a name="examples"></a><span data-ttu-id="db87d-115">Przykłady</span><span class="sxs-lookup"><span data-stu-id="db87d-115">Examples</span></span>

<span data-ttu-id="db87d-116">Jednym z przypadków użycia operatora null-łagodniejszej jest Testowanie logiki walidacji argumentów.</span><span class="sxs-lookup"><span data-stu-id="db87d-116">One of the use cases of the null-forgiving operator is in testing the argument validation logic.</span></span> <span data-ttu-id="db87d-117">Rozważmy na przykład następujące klasy:</span><span class="sxs-lookup"><span data-stu-id="db87d-117">For example, consider the following class:</span></span>

[!code-csharp[Person class](snippets/NullForgivingOperator.cs#PersonClass)]

<span data-ttu-id="db87d-118">Używając [platformy testów MSTest](../../../core/testing/unit-testing-with-mstest.md), można utworzyć następujący test dla logiki walidacji w konstruktorze:</span><span class="sxs-lookup"><span data-stu-id="db87d-118">Using the [MSTest test framework](../../../core/testing/unit-testing-with-mstest.md), you can create the following test for the validation logic in the constructor:</span></span>

[!code-csharp[Person test](snippets/NullForgivingOperator.cs#TestPerson)]

<span data-ttu-id="db87d-119">Bez operatora null łagodniejszej kompilator generuje następujące ostrzeżenie dla poprzedniego kodu: `Warning CS8625: Cannot convert null literal to non-nullable reference type` .</span><span class="sxs-lookup"><span data-stu-id="db87d-119">Without the null-forgiving operator, the compiler generates the following warning for the preceding code: `Warning CS8625: Cannot convert null literal to non-nullable reference type`.</span></span> <span data-ttu-id="db87d-120">Za pomocą operatora null-łagodniejszej, należy poinformować kompilator, że `null` oczekiwano, i nie powinien być ostrzegany o.</span><span class="sxs-lookup"><span data-stu-id="db87d-120">By using the null-forgiving operator, you inform the compiler that passing `null` is expected and shouldn't be warned about.</span></span>

<span data-ttu-id="db87d-121">Można również użyć operatora o wartości null-łagodniejszej, gdy wiadomo, że wyrażenie nie może być, `null` ale kompilator nie rozpoznaje tego elementu.</span><span class="sxs-lookup"><span data-stu-id="db87d-121">You can also use the null-forgiving operator when you definitely know that an expression cannot be `null` but the compiler doesn't manage to recognize that.</span></span> <span data-ttu-id="db87d-122">W poniższym przykładzie, jeśli `IsValid` Metoda zwraca `true` , jego argument nie jest `null` i można bezpiecznie odwoływać się do niego:</span><span class="sxs-lookup"><span data-stu-id="db87d-122">In the following example, if the `IsValid` method returns `true`, its argument is not `null` and you can safely dereference it:</span></span>

[!code-csharp[Use null-forgiving operator](snippets/NullForgivingOperator.cs#UseNullForgiving)]

<span data-ttu-id="db87d-123">Bez operatora null łagodniejszej kompilator generuje następujące ostrzeżenie dla `p.Name` kodu: `Warning CS8602: Dereference of a possibly null reference` .</span><span class="sxs-lookup"><span data-stu-id="db87d-123">Without the null-forgiving operator, the compiler generates the following warning for the `p.Name` code: `Warning CS8602: Dereference of a possibly null reference`.</span></span>

<span data-ttu-id="db87d-124">Jeśli można zmodyfikować `IsValid` metodę, można użyć atrybutu [NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute) do informowania kompilatora, że argument `IsValid` metody nie może być, `null` gdy metoda zwraca `true` :</span><span class="sxs-lookup"><span data-stu-id="db87d-124">If you can modify the `IsValid` method, you can use the [NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute) attribute to inform the compiler that an argument of the `IsValid` method cannot be `null` when the method returns `true`:</span></span>

[!code-csharp[Use an attribute](snippets/NullForgivingOperator.cs#UseAttribute)]

<span data-ttu-id="db87d-125">W poprzednim przykładzie nie trzeba używać operatora o wartości null-łagodniejszej, ponieważ kompilator ma wystarczającą ilość informacji, aby dowiedzieć się, że `p` nie może znajdować się `null` wewnątrz `if` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="db87d-125">In the preceding example, you don't need to use the null-forgiving operator because the compiler has enough information to find out that `p` cannot be `null` inside the `if` statement.</span></span> <span data-ttu-id="db87d-126">Aby uzyskać więcej informacji o atrybutach, które umożliwiają podanie dodatkowych informacji o stanie null zmiennej, zobacz [uaktualnianie interfejsów API z atrybutami w celu zdefiniowania oczekiwań o wartości null](../attributes/nullable-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="db87d-126">For more information about the attributes that allow you to provide additional information about the null state of a variable, see [Upgrade APIs with attributes to define null expectations](../attributes/nullable-analysis.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="db87d-127">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="db87d-127">C# language specification</span></span>

<span data-ttu-id="db87d-128">Aby uzyskać więcej informacji, zobacz sekcję [operator null-łagodniejszej](~/_csharplang/proposals/csharp-8.0/nullable-reference-types-specification.md#the-null-forgiving-operator) w [wersji roboczej specyfikacji typów odwołań dopuszczających wartość null](~/_csharplang/proposals/csharp-8.0/nullable-reference-types-specification.md).</span><span class="sxs-lookup"><span data-stu-id="db87d-128">For more information, see [The null-forgiving operator](~/_csharplang/proposals/csharp-8.0/nullable-reference-types-specification.md#the-null-forgiving-operator) section of the [draft of the nullable reference types specification](~/_csharplang/proposals/csharp-8.0/nullable-reference-types-specification.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="db87d-129">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="db87d-129">See also</span></span>

- [<span data-ttu-id="db87d-130">Dokumentacja języka C#</span><span class="sxs-lookup"><span data-stu-id="db87d-130">C# reference</span></span>](../index.md)
- [<span data-ttu-id="db87d-131">Operatory i wyrażenia języka C#</span><span class="sxs-lookup"><span data-stu-id="db87d-131">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="db87d-132">Samouczek: Projektowanie przy użyciu typów referencyjnych dopuszczających wartość null</span><span class="sxs-lookup"><span data-stu-id="db87d-132">Tutorial: Design with nullable reference types</span></span>](../../tutorials/nullable-reference-types.md)
