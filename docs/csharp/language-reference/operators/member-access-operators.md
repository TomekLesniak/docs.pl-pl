---
title: Operatory dostępu do elementów członkowskich i wyrażenia — odwołanie w C#
description: Informacje na temat operatorów języka C#, których można użyć w celu uzyskania dostępu do elementów członkowskich typu.
ms.date: 11/13/2020
author: pkulikov
f1_keywords:
- ._CSharpKeyword
- '[]_CSharpKeyword'
- ()_CSharpKeyword
- ^_CSharpKeyword
- .._CSharpKeyword
helpviewer_keywords:
- member access operators [C#]
- member access operator [C#]
- dot operator [C#]
- . operator [C#]
- subscript operator [C#]
- square brackets [] operator [C#]
- indexer operator [C#]
- '[] operator [C#]'
- null-conditional operators [C#]
- Elvis operator [C#]
- ?. operator [C#]
- ?[] operator [C#]
- invocation operator [C#]
- method call [C#]
- method invocation [C#]
- delegate invocation [C#]
- () operator [C#]
- ^ operator [C#]
- index from end operator [C#]
- hat operator [C#]
- .. operator [C#]
- range operator [C#]
ms.openlocfilehash: 28d3d9c3261f1a852d16f2637309b21412611c10
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95691243"
---
# <a name="member-access-operators-and-expressions-c-reference"></a><span data-ttu-id="c5af2-103">Operatory i wyrażenia dostępu do składowych (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="c5af2-103">Member access operators and expressions (C# reference)</span></span>

<span data-ttu-id="c5af2-104">Podczas uzyskiwania dostępu do elementu członkowskiego typu można użyć następujących operatorów i wyrażeń:</span><span class="sxs-lookup"><span data-stu-id="c5af2-104">You can use the following operators and expressions when you access a type member:</span></span>

- <span data-ttu-id="c5af2-105">[ `.` (dostęp do elementu członkowskiego)](#member-access-expression-): Aby uzyskać dostęp do elementu członkowskiego przestrzeni nazw lub typu</span><span class="sxs-lookup"><span data-stu-id="c5af2-105">[`.` (member access)](#member-access-expression-): to access a member of a namespace or a type</span></span>
- <span data-ttu-id="c5af2-106">[ `[]` (dostęp do elementu tablicy lub indeksatora)](#indexer-operator-): Aby uzyskać dostęp do elementu tablicy lub indeksatora typu</span><span class="sxs-lookup"><span data-stu-id="c5af2-106">[`[]` (array element or indexer access)](#indexer-operator-): to access an array element or a type indexer</span></span>
- <span data-ttu-id="c5af2-107">[ `?.` and `?[]` (operatory warunkowe o wartości null)](#null-conditional-operators--and-): do wykonywania operacji dostępu do elementu członkowskiego lub elementów tylko wtedy, gdy operand ma wartość różną od null</span><span class="sxs-lookup"><span data-stu-id="c5af2-107">[`?.` and `?[]` (null-conditional operators)](#null-conditional-operators--and-): to perform a member or element access operation only if an operand is non-null</span></span>
- <span data-ttu-id="c5af2-108">[ `()` (wywołanie)](#invocation-expression-): aby wywołać metodę dostępu lub wywołać delegata</span><span class="sxs-lookup"><span data-stu-id="c5af2-108">[`()` (invocation)](#invocation-expression-): to call an accessed method or invoke a delegate</span></span>
- <span data-ttu-id="c5af2-109">[ `^` (indeks od końca)](#index-from-end-operator-): wskazuje, że pozycja elementu jest z końca sekwencji</span><span class="sxs-lookup"><span data-stu-id="c5af2-109">[`^` (index from end)](#index-from-end-operator-): to indicate that the element position is from the end of a sequence</span></span>
- <span data-ttu-id="c5af2-110">[ `..` (zakres)](#range-operator-): aby określić zakres indeksów, których można użyć w celu uzyskania zakresu elementów sekwencji</span><span class="sxs-lookup"><span data-stu-id="c5af2-110">[`..` (range)](#range-operator-): to specify a range of indices that you can use to obtain a range of sequence elements</span></span>

## <a name="member-access-expression-"></a><span data-ttu-id="c5af2-111">Wyrażenie dostępu do elementu członkowskiego.</span><span class="sxs-lookup"><span data-stu-id="c5af2-111">Member access expression .</span></span>

<span data-ttu-id="c5af2-112">`.`Token służy do uzyskiwania dostępu do składowej przestrzeni nazw lub typu, jak pokazano w poniższych przykładach:</span><span class="sxs-lookup"><span data-stu-id="c5af2-112">You use the `.` token to access a member of a namespace or a type, as the following examples demonstrate:</span></span>

- <span data-ttu-id="c5af2-113">Użyj `.` , aby uzyskać dostęp do zagnieżdżonej przestrzeni nazw w przestrzeni nazw, jak pokazano w poniższym przykładzie [ `using` dyrektywy](../keywords/using-directive.md) :</span><span class="sxs-lookup"><span data-stu-id="c5af2-113">Use `.` to access a nested namespace within a namespace, as the following example of a [`using` directive](../keywords/using-directive.md) shows:</span></span>

  [!code-csharp[nested namespaces](snippets/shared/MemberAccessOperators.cs#NestedNamespace)]

- <span data-ttu-id="c5af2-114">Użyj, `.` Aby utworzyć *kwalifikowaną nazwę* do uzyskania dostępu do typu w przestrzeni nazw, jak pokazano w poniższym kodzie:</span><span class="sxs-lookup"><span data-stu-id="c5af2-114">Use `.` to form a *qualified name* to access a type within a namespace, as the following code shows:</span></span>

  [!code-csharp[qualified name](snippets/shared/MemberAccessOperators.cs#QualifiedName)]

  <span data-ttu-id="c5af2-115">Użyj [ `using` dyrektywy](../keywords/using-directive.md) , aby użyć kwalifikujących się nazw jako opcjonalnych.</span><span class="sxs-lookup"><span data-stu-id="c5af2-115">Use a [`using` directive](../keywords/using-directive.md) to make the use of qualified names optional.</span></span>

- <span data-ttu-id="c5af2-116">Służy `.` do uzyskiwania dostępu do [składowych typu](../../programming-guide/classes-and-structs/index.md#members)statycznego i niestatycznego, jak pokazano w poniższym kodzie:</span><span class="sxs-lookup"><span data-stu-id="c5af2-116">Use `.` to access [type members](../../programming-guide/classes-and-structs/index.md#members), static and non-static, as the following code shows:</span></span>

  [!code-csharp-interactive[type members](snippets/shared/MemberAccessOperators.cs#TypeMemberAccess)]

<span data-ttu-id="c5af2-117">Można również użyć, `.` Aby uzyskać dostęp do [metody rozszerzenia](../../programming-guide/classes-and-structs/extension-methods.md).</span><span class="sxs-lookup"><span data-stu-id="c5af2-117">You can also use `.` to access an [extension method](../../programming-guide/classes-and-structs/extension-methods.md).</span></span>

## <a name="indexer-operator-"></a><span data-ttu-id="c5af2-118">Indeksator — operator []</span><span class="sxs-lookup"><span data-stu-id="c5af2-118">Indexer operator []</span></span>

<span data-ttu-id="c5af2-119">Nawiasy kwadratowe, `[]` , są zwykle używane dla dostępu do elementu Array, indeksatora lub wskaźnika.</span><span class="sxs-lookup"><span data-stu-id="c5af2-119">Square brackets, `[]`, are typically used for array, indexer, or pointer element access.</span></span>

### <a name="array-access"></a><span data-ttu-id="c5af2-120">Dostęp do tablicy</span><span class="sxs-lookup"><span data-stu-id="c5af2-120">Array access</span></span>

<span data-ttu-id="c5af2-121">W poniższym przykładzie pokazano, jak uzyskać dostęp do elementów tablicy:</span><span class="sxs-lookup"><span data-stu-id="c5af2-121">The following example demonstrates how to access array elements:</span></span>

[!code-csharp-interactive[array access](snippets/shared/MemberAccessOperators.cs#Arrays)]

<span data-ttu-id="c5af2-122">Jeśli indeks tablicy znajduje się poza granicami odpowiedniego wymiaru tablicy, <xref:System.IndexOutOfRangeException> jest zgłaszany.</span><span class="sxs-lookup"><span data-stu-id="c5af2-122">If an array index is outside the bounds of the corresponding dimension of an array, an <xref:System.IndexOutOfRangeException> is thrown.</span></span>

<span data-ttu-id="c5af2-123">Jak pokazano w powyższym przykładzie, można również użyć nawiasów kwadratowych w przypadku deklarowania typu tablicy lub wystąpienia instancji Array.</span><span class="sxs-lookup"><span data-stu-id="c5af2-123">As the preceding example shows, you also use square brackets when you declare an array type or instantiate an array instance.</span></span>

<span data-ttu-id="c5af2-124">Aby uzyskać więcej informacji na temat tablic, zobacz [tablice](../../programming-guide/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="c5af2-124">For more information about arrays, see [Arrays](../../programming-guide/arrays/index.md).</span></span>

### <a name="indexer-access"></a><span data-ttu-id="c5af2-125">Dostęp indeksatora</span><span class="sxs-lookup"><span data-stu-id="c5af2-125">Indexer access</span></span>

<span data-ttu-id="c5af2-126">Poniższy przykład używa <xref:System.Collections.Generic.Dictionary%602> typu .NET do zademonstrowania dostępu indeksatora:</span><span class="sxs-lookup"><span data-stu-id="c5af2-126">The following example uses the .NET <xref:System.Collections.Generic.Dictionary%602> type to demonstrate indexer access:</span></span>

[!code-csharp-interactive[indexer access](snippets/shared/MemberAccessOperators.cs#Indexers)]

<span data-ttu-id="c5af2-127">Indeksatory umożliwiają indeksowanie wystąpień typu zdefiniowanego przez użytkownika w podobny sposób jak indeksowanie tablicy.</span><span class="sxs-lookup"><span data-stu-id="c5af2-127">Indexers allow you to index instances of a user-defined type in the similar way as array indexing.</span></span> <span data-ttu-id="c5af2-128">W przeciwieństwie do indeksów tablicowych, które muszą być liczbami całkowitymi, parametry indeksatora mogą być zadeklarowane jako dowolnego typu.</span><span class="sxs-lookup"><span data-stu-id="c5af2-128">Unlike array indices, which must be integer, the indexer parameters can be declared to be of any type.</span></span>

<span data-ttu-id="c5af2-129">Aby uzyskać więcej informacji na temat indeksatorów, zobacz [indeksatory](../../programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="c5af2-129">For more information about indexers, see [Indexers](../../programming-guide/indexers/index.md).</span></span>

### <a name="other-usages-of-"></a><span data-ttu-id="c5af2-130">Inne użycie []</span><span class="sxs-lookup"><span data-stu-id="c5af2-130">Other usages of []</span></span>

<span data-ttu-id="c5af2-131">Aby uzyskać informacje o dostępie do elementów wskaźnika, zobacz sekcję [wskaźnik dostępu do elementu wskaźnika []](pointer-related-operators.md#pointer-element-access-operator-) w artykule [Operatory pokrewne wskaźnika](pointer-related-operators.md) .</span><span class="sxs-lookup"><span data-stu-id="c5af2-131">For information about pointer element access, see the [Pointer element access operator []](pointer-related-operators.md#pointer-element-access-operator-) section of the [Pointer related operators](pointer-related-operators.md) article.</span></span>

<span data-ttu-id="c5af2-132">Aby określić [atrybuty](../../programming-guide/concepts/attributes/index.md), należy również użyć nawiasów kwadratowych:</span><span class="sxs-lookup"><span data-stu-id="c5af2-132">You also use square brackets to specify [attributes](../../programming-guide/concepts/attributes/index.md):</span></span>

```csharp
[System.Diagnostics.Conditional("DEBUG")]
void TraceMethod() {}
```

## <a name="null-conditional-operators--and-"></a><span data-ttu-id="c5af2-133">Operatory warunkowe o wartości null?.</span><span class="sxs-lookup"><span data-stu-id="c5af2-133">Null-conditional operators ?.</span></span> <span data-ttu-id="c5af2-134">lub? []</span><span class="sxs-lookup"><span data-stu-id="c5af2-134">and ?[]</span></span>

<span data-ttu-id="c5af2-135">W języku C# 6 i nowszych operator warunkowy o wartości null stosuje dostęp do elementu [Członkowskiego](#member-access-expression-), `?.` lub [dostęp do elementów](#indexer-operator-), `?[]` do jego operandu tylko wtedy, gdy ten operand ma wartość inną niż null; w przeciwnym razie zwraca wartość `null` .</span><span class="sxs-lookup"><span data-stu-id="c5af2-135">Available in C# 6 and later, a null-conditional operator applies a [member access](#member-access-expression-), `?.`, or [element access](#indexer-operator-), `?[]`, operation to its operand only if that operand evaluates to non-null; otherwise, it returns `null`.</span></span> <span data-ttu-id="c5af2-136">Czyli</span><span class="sxs-lookup"><span data-stu-id="c5af2-136">That is,</span></span>

- <span data-ttu-id="c5af2-137">Jeśli `a` jest wynikiem obliczenia `null` , wynik `a?.x` lub `a?[x]` jest `null` .</span><span class="sxs-lookup"><span data-stu-id="c5af2-137">If `a` evaluates to `null`, the result of `a?.x` or `a?[x]` is `null`.</span></span>
- <span data-ttu-id="c5af2-138">Jeśli `a` ma wartość różną od null, wynik `a?.x` lub `a?[x]` jest taki sam jak wynik `a.x` lub `a[x]` , odpowiednio.</span><span class="sxs-lookup"><span data-stu-id="c5af2-138">If `a` evaluates to non-null, the result of `a?.x` or `a?[x]` is the same as the result of `a.x` or `a[x]`, respectively.</span></span>

  > [!NOTE]
  > <span data-ttu-id="c5af2-139">Jeśli `a.x` lub `a[x]` zgłasza wyjątek lub zgłosi ten `a?.x` `a?[x]` sam wyjątek dla wartości innej niż null `a` .</span><span class="sxs-lookup"><span data-stu-id="c5af2-139">If `a.x` or `a[x]` throws an exception, `a?.x` or `a?[x]` would throw the same exception for non-null `a`.</span></span> <span data-ttu-id="c5af2-140">Na przykład jeśli `a` jest wystąpieniem tablicy o wartości innej niż null i `x` znajduje się poza granicami `a` , `a?[x]` zostałby zgłosić <xref:System.IndexOutOfRangeException> .</span><span class="sxs-lookup"><span data-stu-id="c5af2-140">For example, if `a` is a non-null array instance and `x` is outside the bounds of `a`, `a?[x]` would throw an <xref:System.IndexOutOfRangeException>.</span></span>

<span data-ttu-id="c5af2-141">Operatory warunkowe o wartości null są krótkimi obwodami.</span><span class="sxs-lookup"><span data-stu-id="c5af2-141">The null-conditional operators are short-circuiting.</span></span> <span data-ttu-id="c5af2-142">Oznacza to, że jeśli jedna operacja w łańcuchu operacji warunkowego elementu członkowskiego lub dostępu do elementu zwraca `null` , reszta łańcucha nie jest wykonywana.</span><span class="sxs-lookup"><span data-stu-id="c5af2-142">That is, if one operation in a chain of conditional member or element access operations returns `null`, the rest of the chain doesn't execute.</span></span> <span data-ttu-id="c5af2-143">W poniższym przykładzie `B` nie jest oceniana, jeśli jest obliczana `A` wartość `null` i `C` nie jest szacowana, jeśli `A` lub `B` szacuje `null` :</span><span class="sxs-lookup"><span data-stu-id="c5af2-143">In the following example, `B` is not evaluated if `A` evaluates to `null` and `C` is not evaluated if `A` or `B` evaluates to `null`:</span></span>

```csharp
A?.B?.Do(C);
A?.B?[C];
```

<span data-ttu-id="c5af2-144">Poniższy przykład ilustruje użycie `?.` `?[]` operatorów i:</span><span class="sxs-lookup"><span data-stu-id="c5af2-144">The following example demonstrates the usage of the `?.` and `?[]` operators:</span></span>

[!code-csharp-interactive[null-conditional operators](snippets/shared/MemberAccessOperators.cs#NullConditional)]

<span data-ttu-id="c5af2-145">Poprzedni przykład używa również [operatora `??` łączenia wartości null](null-coalescing-operator.md) , aby określić alternatywne wyrażenie do obliczenia w przypadku, gdy wynikiem operacji warunkowej jest wartość null `null` .</span><span class="sxs-lookup"><span data-stu-id="c5af2-145">The preceding example also uses the [null-coalescing operator `??`](null-coalescing-operator.md) to specify an alternative expression to evaluate in case the result of a null-conditional operation is `null`.</span></span>

<span data-ttu-id="c5af2-146">Jeśli `a.x` lub `a[x]` ma typ wartości niedopuszczający wartości null `T` `a?.x` lub `a?[x]` ma odpowiedni [Typ wartości null](../builtin-types/nullable-value-types.md) `T?` .</span><span class="sxs-lookup"><span data-stu-id="c5af2-146">If `a.x` or `a[x]` is of a non-nullable value type `T`, `a?.x` or `a?[x]` is of the corresponding [nullable value type](../builtin-types/nullable-value-types.md) `T?`.</span></span> <span data-ttu-id="c5af2-147">Jeśli potrzebujesz wyrażenia typu `T` , Zastosuj operator łączenia wartości null `??` do wyrażenia warunkowego null, jak pokazano w poniższym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="c5af2-147">If you need an expression of type `T`, apply the null-coalescing operator `??` to a null-conditional expression, as the following example shows:</span></span>

[!code-csharp-interactive[null-conditional with null-coalescing](snippets/shared/MemberAccessOperators.cs#NullConditionalWithNullCoalescing)]

<span data-ttu-id="c5af2-148">W powyższym przykładzie, jeśli nie używasz `??` operatora, program `numbers?.Length < 2` oblicza wartość, `false` gdy `numbers` jest `null` .</span><span class="sxs-lookup"><span data-stu-id="c5af2-148">In the preceding example, if you don't use the `??` operator, `numbers?.Length < 2` evaluates to `false` when `numbers` is `null`.</span></span>

<span data-ttu-id="c5af2-149">Operator dostępu warunkowego o wartości null `?.` jest również znany jako operator Elvis.</span><span class="sxs-lookup"><span data-stu-id="c5af2-149">The null-conditional member access operator `?.` is also known as the Elvis operator.</span></span>

### <a name="thread-safe-delegate-invocation"></a><span data-ttu-id="c5af2-150">Wywołanie delegowania bezpiecznego wątku</span><span class="sxs-lookup"><span data-stu-id="c5af2-150">Thread-safe delegate invocation</span></span>

<span data-ttu-id="c5af2-151">Użyj `?.` operatora, aby sprawdzić, czy delegat ma wartość różną od null i wywołać go w sposób bezpieczny dla wątków (na przykład po [podniesieniu zdarzenia](../../../standard/events/how-to-raise-and-consume-events.md)), jak poniższy kod ilustruje:</span><span class="sxs-lookup"><span data-stu-id="c5af2-151">Use the `?.` operator to check if a delegate is non-null and invoke it in a thread-safe way (for example, when you [raise an event](../../../standard/events/how-to-raise-and-consume-events.md)), as the following code shows:</span></span>

```csharp
PropertyChanged?.Invoke(…)
```

<span data-ttu-id="c5af2-152">Ten kod jest odpowiednikiem poniższego kodu, który będzie używany w języku C# 5 lub wcześniejszym:</span><span class="sxs-lookup"><span data-stu-id="c5af2-152">That code is equivalent to the following code that you would use in C# 5 or earlier:</span></span>

```csharp
var handler = this.PropertyChanged;
if (handler != null)
{
    handler(…);
}
```

<span data-ttu-id="c5af2-153">Jest to bezpieczny wątkowo sposób, aby upewnić się, że wywoływany jest tylko element inny niż null `handler` .</span><span class="sxs-lookup"><span data-stu-id="c5af2-153">That is a thread-safe way to ensure that only a non-null `handler` is invoked.</span></span> <span data-ttu-id="c5af2-154">Ponieważ wystąpienia delegatów są niezmienne, żaden wątek nie może zmienić obiektu, do którego odwołuje się `handler` zmienna lokalna.</span><span class="sxs-lookup"><span data-stu-id="c5af2-154">Because delegate instances are immutable, no thread can change the object referenced by the `handler` local variable.</span></span> <span data-ttu-id="c5af2-155">W szczególności, jeśli kod wykonywany przez inny wątek anuluje subskrypcję `PropertyChanged` zdarzenia i `PropertyChanged` pozostanie `null` przed `handler` wywołaniem, obiekt, do którego się odwołuje, `handler` pozostaje bez zmian.</span><span class="sxs-lookup"><span data-stu-id="c5af2-155">In particular, if the code executed by another thread unsubscribes from the `PropertyChanged` event and `PropertyChanged` becomes `null` before `handler` is invoked, the object referenced by `handler` remains unaffected.</span></span> <span data-ttu-id="c5af2-156">`?.`Operator oblicza swój argument operacji po lewej stronie nie więcej niż raz, gwarantując, że nie można go zmienić do `null` po sprawdzeniu wartości innej niż null.</span><span class="sxs-lookup"><span data-stu-id="c5af2-156">The `?.` operator evaluates its left-hand operand no more than once, guaranteeing that it cannot be changed to `null` after being verified as non-null.</span></span>

## <a name="invocation-expression-"></a><span data-ttu-id="c5af2-157">Wyrażenie wywołania ()</span><span class="sxs-lookup"><span data-stu-id="c5af2-157">Invocation expression ()</span></span>

<span data-ttu-id="c5af2-158">Użyj nawiasów, `()` ,, aby wywołać [metodę](../../programming-guide/classes-and-structs/methods.md) lub wywołać [delegata](../../programming-guide/delegates/index.md).</span><span class="sxs-lookup"><span data-stu-id="c5af2-158">Use parentheses, `()`, to call a [method](../../programming-guide/classes-and-structs/methods.md) or invoke a [delegate](../../programming-guide/delegates/index.md).</span></span>

<span data-ttu-id="c5af2-159">Poniższy przykład ilustruje sposób wywołania metody z argumentami lub bez nich i Wywołaj delegata:</span><span class="sxs-lookup"><span data-stu-id="c5af2-159">The following example demonstrates how to call a method, with or without arguments, and invoke a delegate:</span></span>

[!code-csharp-interactive[invocation with ()](snippets/shared/MemberAccessOperators.cs#Invocation)]

<span data-ttu-id="c5af2-160">Po wywołaniu [konstruktora](../../programming-guide/classes-and-structs/constructors.md) za pomocą operatora należy również użyć nawiasów [`new`](new-operator.md) .</span><span class="sxs-lookup"><span data-stu-id="c5af2-160">You also use parentheses when you invoke a [constructor](../../programming-guide/classes-and-structs/constructors.md) with the [`new`](new-operator.md) operator.</span></span>

### <a name="other-usages-of-"></a><span data-ttu-id="c5af2-161">Inne użycie ()</span><span class="sxs-lookup"><span data-stu-id="c5af2-161">Other usages of ()</span></span>

<span data-ttu-id="c5af2-162">Należy również użyć nawiasów, aby dostosować kolejność, w której mają być oceniane operacje w wyrażeniu.</span><span class="sxs-lookup"><span data-stu-id="c5af2-162">You also use parentheses to adjust the order in which to evaluate operations in an expression.</span></span> <span data-ttu-id="c5af2-163">Aby uzyskać więcej informacji, zobacz [operatory języka C#](index.md).</span><span class="sxs-lookup"><span data-stu-id="c5af2-163">For more information, see [C# operators](index.md).</span></span>

<span data-ttu-id="c5af2-164">[Wyrażenia rzutowania](type-testing-and-cast.md#cast-expression), które wykonują jawne konwersje typów, również używają nawiasów.</span><span class="sxs-lookup"><span data-stu-id="c5af2-164">[Cast expressions](type-testing-and-cast.md#cast-expression), which perform explicit type conversions, also use parentheses.</span></span>

## <a name="index-from-end-operator-"></a><span data-ttu-id="c5af2-165">Indeks z operatora końcowego ^</span><span class="sxs-lookup"><span data-stu-id="c5af2-165">Index from end operator ^</span></span>

<span data-ttu-id="c5af2-166">Dostępne w języku C# 8,0 i nowszych, `^` operator wskazuje położenie elementu od końca sekwencji.</span><span class="sxs-lookup"><span data-stu-id="c5af2-166">Available in C# 8.0 and later, the `^` operator indicates the element position from the end of a sequence.</span></span> <span data-ttu-id="c5af2-167">Dla sekwencji o długości `length` `^n` wskazuje element z przesunięciem `length - n` od początku sekwencji.</span><span class="sxs-lookup"><span data-stu-id="c5af2-167">For a sequence of length `length`, `^n` points to the element with offset `length - n` from the start of a sequence.</span></span> <span data-ttu-id="c5af2-168">Na przykład `^1` wskazuje ostatni element sekwencji i `^length` wskazuje na pierwszy element sekwencji.</span><span class="sxs-lookup"><span data-stu-id="c5af2-168">For example, `^1` points to the last element of a sequence and `^length` points to the first element of a sequence.</span></span>

[!code-csharp[index from end](snippets/shared/MemberAccessOperators.cs#IndexFromEnd)]

<span data-ttu-id="c5af2-169">Jak pokazano w powyższym przykładzie, wyrażenie `^e` jest <xref:System.Index?displayProperty=nameWithType> typu.</span><span class="sxs-lookup"><span data-stu-id="c5af2-169">As the preceding example shows, expression `^e` is of the <xref:System.Index?displayProperty=nameWithType> type.</span></span> <span data-ttu-id="c5af2-170">W wyrażeniu `^e` wynik `e` musi być niejawnie konwertowany na `int` .</span><span class="sxs-lookup"><span data-stu-id="c5af2-170">In expression `^e`, the result of `e` must be implicitly convertible to `int`.</span></span>

<span data-ttu-id="c5af2-171">Można również użyć `^` operatora z [operatorem zakresu](#range-operator-) , aby utworzyć zakres indeksów.</span><span class="sxs-lookup"><span data-stu-id="c5af2-171">You can also use the `^` operator with the [range operator](#range-operator-) to create a range of indices.</span></span> <span data-ttu-id="c5af2-172">Aby uzyskać więcej informacji, zobacz [indeksy i zakresy](../../tutorials/ranges-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="c5af2-172">For more information, see [Indices and ranges](../../tutorials/ranges-indexes.md).</span></span>

## <a name="range-operator-"></a><span data-ttu-id="c5af2-173">Operator zakresu..</span><span class="sxs-lookup"><span data-stu-id="c5af2-173">Range operator ..</span></span>

<span data-ttu-id="c5af2-174">Dostępne w języku C# 8,0 i nowszych, `..` operator określa początek i koniec zakresu indeksów jako operandy.</span><span class="sxs-lookup"><span data-stu-id="c5af2-174">Available in C# 8.0 and later, the `..` operator specifies the start and end of a range of indices as its operands.</span></span> <span data-ttu-id="c5af2-175">Argument operacji po lewej stronie *jest początkową* częścią zakresu.</span><span class="sxs-lookup"><span data-stu-id="c5af2-175">The left-hand operand is an *inclusive* start of a range.</span></span> <span data-ttu-id="c5af2-176">Prawy operand jest *wyłącznym* końcem zakresu.</span><span class="sxs-lookup"><span data-stu-id="c5af2-176">The right-hand operand is an *exclusive* end of a range.</span></span> <span data-ttu-id="c5af2-177">Jeden z operandów może być indeksem od początku lub od końca sekwencji, jak pokazano w poniższym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="c5af2-177">Either of operands can be an index from the start or from the end of a sequence, as the following example shows:</span></span>

[!code-csharp[range examples](snippets/shared/MemberAccessOperators.cs#Ranges)]

<span data-ttu-id="c5af2-178">Jak pokazano w powyższym przykładzie, wyrażenie `a..b` jest <xref:System.Range?displayProperty=nameWithType> typu.</span><span class="sxs-lookup"><span data-stu-id="c5af2-178">As the preceding example shows, expression `a..b` is of the <xref:System.Range?displayProperty=nameWithType> type.</span></span> <span data-ttu-id="c5af2-179">W wyrażeniu `a..b` wyniki `a` i `b` muszą być niejawnie konwertowane na `int` lub <xref:System.Index> .</span><span class="sxs-lookup"><span data-stu-id="c5af2-179">In expression `a..b`, the results of `a` and `b` must be implicitly convertible to `int` or <xref:System.Index>.</span></span>

<span data-ttu-id="c5af2-180">Możesz pominąć dowolny operand `..` operatora, aby uzyskać otwarty zakres:</span><span class="sxs-lookup"><span data-stu-id="c5af2-180">You can omit any of the operands of the `..` operator to obtain an open-ended range:</span></span>

- <span data-ttu-id="c5af2-181">`a..` jest równoważne `a..^0`</span><span class="sxs-lookup"><span data-stu-id="c5af2-181">`a..` is equivalent to `a..^0`</span></span>
- <span data-ttu-id="c5af2-182">`..b` jest równoważne `0..b`</span><span class="sxs-lookup"><span data-stu-id="c5af2-182">`..b` is equivalent to `0..b`</span></span>
- <span data-ttu-id="c5af2-183">`..` jest równoważne `0..^0`</span><span class="sxs-lookup"><span data-stu-id="c5af2-183">`..` is equivalent to `0..^0`</span></span>

[!code-csharp[ranges with omitted operands](snippets/shared/MemberAccessOperators.cs#RangesOptional)]

<span data-ttu-id="c5af2-184">Aby uzyskać więcej informacji, zobacz [indeksy i zakresy](../../tutorials/ranges-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="c5af2-184">For more information, see [Indices and ranges](../../tutorials/ranges-indexes.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="c5af2-185">Przeciążanie operatora</span><span class="sxs-lookup"><span data-stu-id="c5af2-185">Operator overloadability</span></span>

<span data-ttu-id="c5af2-186">`.`Operatory, `()` , `^` i `..` nie mogą być przeciążone.</span><span class="sxs-lookup"><span data-stu-id="c5af2-186">The `.`, `()`, `^`, and `..` operators cannot be overloaded.</span></span> <span data-ttu-id="c5af2-187">`[]`Operator jest również traktowany jako operator niepodlegający obciążeniu.</span><span class="sxs-lookup"><span data-stu-id="c5af2-187">The `[]` operator is also considered a non-overloadable operator.</span></span> <span data-ttu-id="c5af2-188">Używanie [indeksatorów](../../programming-guide/indexers/index.md) do obsługi indeksowania z typami zdefiniowanymi przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="c5af2-188">Use [indexers](../../programming-guide/indexers/index.md) to support indexing with user-defined types.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="c5af2-189">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="c5af2-189">C# language specification</span></span>

<span data-ttu-id="c5af2-190">Aby uzyskać więcej informacji, zobacz następujące sekcje [specyfikacji języka C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="c5af2-190">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="c5af2-191">Dostęp do elementu członkowskiego</span><span class="sxs-lookup"><span data-stu-id="c5af2-191">Member access</span></span>](~/_csharplang/spec/expressions.md#member-access)
- [<span data-ttu-id="c5af2-192">Dostęp do elementu</span><span class="sxs-lookup"><span data-stu-id="c5af2-192">Element access</span></span>](~/_csharplang/spec/expressions.md#element-access)
- [<span data-ttu-id="c5af2-193">Operator warunkowy o wartości null</span><span class="sxs-lookup"><span data-stu-id="c5af2-193">Null-conditional operator</span></span>](~/_csharplang/spec/expressions.md#null-conditional-operator)
- [<span data-ttu-id="c5af2-194">Wyrażenia wywołania</span><span class="sxs-lookup"><span data-stu-id="c5af2-194">Invocation expressions</span></span>](~/_csharplang/spec/expressions.md#invocation-expressions)

<span data-ttu-id="c5af2-195">Aby uzyskać więcej informacji na temat indeksów i zakresów, zobacz [Uwaga dotycząca oferty funkcji](~/_csharplang/proposals/csharp-8.0/ranges.md).</span><span class="sxs-lookup"><span data-stu-id="c5af2-195">For more information about indices and ranges, see the [feature proposal note](~/_csharplang/proposals/csharp-8.0/ranges.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c5af2-196">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="c5af2-196">See also</span></span>

- [<span data-ttu-id="c5af2-197">Dokumentacja języka C#</span><span class="sxs-lookup"><span data-stu-id="c5af2-197">C# reference</span></span>](../index.md)
- [<span data-ttu-id="c5af2-198">Operatory i wyrażenia języka C#</span><span class="sxs-lookup"><span data-stu-id="c5af2-198">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="c5af2-199">?? (operator łączenia wartości null)</span><span class="sxs-lookup"><span data-stu-id="c5af2-199">?? (null-coalescing operator)</span></span>](null-coalescing-operator.md)
- [<span data-ttu-id="c5af2-200">:: — Operator</span><span class="sxs-lookup"><span data-stu-id="c5af2-200">:: operator</span></span>](namespace-alias-qualifier.md)
