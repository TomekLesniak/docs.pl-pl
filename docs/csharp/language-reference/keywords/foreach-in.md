---
description: foreach, in (odwołanie w C#)
title: Instrukcja "foreach" języka C#
ms.date: 07/22/2020
f1_keywords:
- foreach
- foreach_CSharpKeyword
helpviewer_keywords:
- foreach keyword [C#]
- foreach statement [C#]
- in keyword [C#]
ms.assetid: 5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec
ms.openlocfilehash: 2ed89fa52b2d3d369d668bf79ab32eaf7be18a8a
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89142079"
---
# <a name="foreach-in-c-reference"></a><span data-ttu-id="e35ce-103">foreach, in (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="e35ce-103">foreach, in (C# reference)</span></span>

<span data-ttu-id="e35ce-104">`foreach`Instrukcja wykonuje instrukcję lub blok instrukcji dla każdego elementu w wystąpieniu typu, który implementuje <xref:System.Collections.IEnumerable?displayProperty=nameWithType> <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interfejs lub, jak pokazano w poniższym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="e35ce-104">The `foreach` statement executes a statement or a block of statements for each element in an instance of the type that implements the <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interface, as the following example shows:</span></span>

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="1" interactive="try-dotnet-method" :::

<span data-ttu-id="e35ce-105">`foreach`Instrukcja nie jest ograniczona do tych typów.</span><span class="sxs-lookup"><span data-stu-id="e35ce-105">The `foreach` statement isn't limited to those types.</span></span> <span data-ttu-id="e35ce-106">Można jej użyć z wystąpieniem dowolnego typu, który spełnia następujące warunki:</span><span class="sxs-lookup"><span data-stu-id="e35ce-106">You can use it with an instance of any type that satisfies the following conditions:</span></span>

- <span data-ttu-id="e35ce-107">Typ ma publiczną metodę bez parametrów `GetEnumerator` , której typem zwracanym jest Klasa, struktura lub typ interfejsu,</span><span class="sxs-lookup"><span data-stu-id="e35ce-107">a type has the public parameterless `GetEnumerator` method whose return type is either class, struct, or interface type,</span></span>
- <span data-ttu-id="e35ce-108">zwracany typ `GetEnumerator` metody ma właściwość publiczną `Current` i publiczną metodę bez parametrów, `MoveNext` której typem zwracanym jest <xref:System.Boolean> .</span><span class="sxs-lookup"><span data-stu-id="e35ce-108">the return type of the `GetEnumerator` method has the public `Current` property and the public parameterless `MoveNext` method whose return type is <xref:System.Boolean>.</span></span>

<span data-ttu-id="e35ce-109">Poniższy przykład używa `foreach` instrukcji z wystąpieniem <xref:System.Span%601?displayProperty=nameWithType> typu, który nie implementuje interfejsów:</span><span class="sxs-lookup"><span data-stu-id="e35ce-109">The following example uses the `foreach` statement with an instance of the <xref:System.Span%601?displayProperty=nameWithType> type, which doesn't implement any interfaces:</span></span>

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="2" :::

<span data-ttu-id="e35ce-110">Począwszy od języka C# 7,3, jeśli właściwość modułu wyliczającego `Current` zwróci [wartość zwracaną odwołania](ref.md#reference-return-values) ( `ref T` gdzie `T` jest typem elementu kolekcji), można zadeklarować zmienną iteracji z `ref` `ref readonly` modyfikatorem or, jak pokazano w poniższym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="e35ce-110">Beginning with C# 7.3, if the enumerator's `Current` property returns a [reference return value](ref.md#reference-return-values) (`ref T` where `T` is the type of a collection element), you can declare an iteration variable with the `ref` or `ref readonly` modifier, as the following example shows:</span></span>

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="RefSpan" :::

<span data-ttu-id="e35ce-111">Począwszy od języka C# 8,0, można użyć `await foreach` instrukcji, aby wykorzystać asynchroniczny strumień danych, czyli typ kolekcji implementującej <xref:System.Collections.Generic.IAsyncEnumerable%601> interfejs.</span><span class="sxs-lookup"><span data-stu-id="e35ce-111">Beginning with C# 8.0, you can use the `await foreach` statement to consume an asynchronous stream of data, that is, the collection type that implements the <xref:System.Collections.Generic.IAsyncEnumerable%601> interface.</span></span> <span data-ttu-id="e35ce-112">Każda iteracja pętli może zostać zawieszona, podczas gdy następny element jest pobierany asynchronicznie.</span><span class="sxs-lookup"><span data-stu-id="e35ce-112">Each iteration of the loop may be suspended while the next element is retrieved asynchronously.</span></span> <span data-ttu-id="e35ce-113">Poniższy przykład pokazuje, jak używać `await foreach` instrukcji:</span><span class="sxs-lookup"><span data-stu-id="e35ce-113">The following example shows how to use the `await foreach` statement:</span></span>

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="AwaitForeach" :::

<span data-ttu-id="e35ce-114">Domyślnie elementy strumienia są przetwarzane w przechwyconym kontekście.</span><span class="sxs-lookup"><span data-stu-id="e35ce-114">By default, stream elements are processed in the captured context.</span></span> <span data-ttu-id="e35ce-115">Jeśli chcesz wyłączyć przechwytywanie kontekstu, użyj <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait%2A?displayProperty=nameWithType> metody rozszerzenia.</span><span class="sxs-lookup"><span data-stu-id="e35ce-115">If you want to disable capturing of the context, use the <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait%2A?displayProperty=nameWithType> extension method.</span></span> <span data-ttu-id="e35ce-116">Aby uzyskać więcej informacji na temat kontekstów synchronizacji i przechwytywania bieżącego kontekstu, zobacz [Używanie wzorca asynchronicznego opartego na zadaniach](../../../standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="e35ce-116">For more information about synchronization contexts and capturing the current context, see [Consuming the Task-based asynchronous pattern](../../../standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md).</span></span> <span data-ttu-id="e35ce-117">Aby uzyskać więcej informacji o strumieniach asynchronicznych, zobacz sekcję " [strumienie asynchroniczne](../../whats-new/csharp-8.md#asynchronous-streams) " [w artykule Co nowego w języku C# 8,0](../../whats-new/csharp-8.md) .</span><span class="sxs-lookup"><span data-stu-id="e35ce-117">For more information about asynchronous streams, see the [Asynchronous streams](../../whats-new/csharp-8.md#asynchronous-streams) section of the [What's new in C# 8.0](../../whats-new/csharp-8.md) article.</span></span>

<span data-ttu-id="e35ce-118">W dowolnym momencie w `foreach` bloku instrukcji można przerwać pętlę przy użyciu instrukcji [Break](break.md) lub przejść do następnej iteracji w pętli przy użyciu instrukcji [Continue](continue.md) .</span><span class="sxs-lookup"><span data-stu-id="e35ce-118">At any point within the `foreach` statement block, you can break out of the loop by using the [break](break.md) statement, or step to the next iteration in the loop by using the [continue](continue.md) statement.</span></span> <span data-ttu-id="e35ce-119">Możesz również wyjść z `foreach` pętli przez instrukcje [goto](goto.md), [Return](return.md)lub [throw](throw.md) .</span><span class="sxs-lookup"><span data-stu-id="e35ce-119">You can also exit a `foreach` loop by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

<span data-ttu-id="e35ce-120">Jeśli `foreach` instrukcja jest zastosowana do `null` , <xref:System.NullReferenceException> jest zgłaszany.</span><span class="sxs-lookup"><span data-stu-id="e35ce-120">If the `foreach` statement is applied to `null`, a <xref:System.NullReferenceException> is thrown.</span></span> <span data-ttu-id="e35ce-121">Jeśli kolekcja źródłowa `foreach` instrukcji jest pusta, treść `foreach` pętli nie zostanie wykonana i pominięta.</span><span class="sxs-lookup"><span data-stu-id="e35ce-121">If the source collection of the `foreach` statement is empty, the body of the `foreach` loop isn't executed and skipped.</span></span>

## <a name="type-of-an-iteration-variable"></a><span data-ttu-id="e35ce-122">Typ zmiennej iteracji</span><span class="sxs-lookup"><span data-stu-id="e35ce-122">Type of an iteration variable</span></span>

<span data-ttu-id="e35ce-123">Możesz użyć `var` słowa kluczowego, aby zezwolić kompilatorowi na wnioskowanie typu zmiennej iteracji w `foreach` instrukcji, jak pokazano w poniższym kodzie:</span><span class="sxs-lookup"><span data-stu-id="e35ce-123">You can use the `var` keyword to let the compiler infer the type of an iteration variable in the `foreach` statement, as the following code shows:</span></span>

```csharp
foreach (var item in collection) { }
```

<span data-ttu-id="e35ce-124">Można również jawnie określić typ zmiennej iteracji, jak pokazano w poniższym kodzie:</span><span class="sxs-lookup"><span data-stu-id="e35ce-124">You can also explicitly specify the type of an iteration variable, as the following code shows:</span></span>

```csharp
IEnumerable<T> collection = new T[5];
foreach (V item in collection) { }
```

<span data-ttu-id="e35ce-125">W poprzednim formularzu typ `T` elementu kolekcji musi być niejawnie lub jawnie konwertowany na typ `V` zmiennej iteracji.</span><span class="sxs-lookup"><span data-stu-id="e35ce-125">In the preceding form, type `T` of a collection element must be implicitly or explicitly convertible to type `V` of an iteration variable.</span></span> <span data-ttu-id="e35ce-126">Jeśli jawna konwersja z elementu `T` do `V` nie powiedzie się w czasie wykonywania, `foreach` instrukcja zgłosi <xref:System.InvalidCastException> .</span><span class="sxs-lookup"><span data-stu-id="e35ce-126">If an explicit conversion from `T` to `V` fails at run time, the `foreach` statement throws an <xref:System.InvalidCastException>.</span></span> <span data-ttu-id="e35ce-127">Na przykład, jeśli `T` jest typem klasy niezapieczętowanej, `V` może być dowolnego typu interfejsu, nawet tego, który `T` nie implementuje.</span><span class="sxs-lookup"><span data-stu-id="e35ce-127">For example, if `T` is a non-sealed class type, `V` can be any interface type, even the one that `T` doesn't implement.</span></span> <span data-ttu-id="e35ce-128">W czasie wykonywania, typ elementu kolekcji może być tym, który pochodzi od `T` i faktycznie implementuje `V` .</span><span class="sxs-lookup"><span data-stu-id="e35ce-128">At run time, the type of a collection element may be the one that derives from `T` and actually implements `V`.</span></span> <span data-ttu-id="e35ce-129">Jeśli tak się nie dzieje, <xref:System.InvalidCastException> jest zgłaszany.</span><span class="sxs-lookup"><span data-stu-id="e35ce-129">If that's not the case, an <xref:System.InvalidCastException> is thrown.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="e35ce-130">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="e35ce-130">C# language specification</span></span>

<span data-ttu-id="e35ce-131">Aby uzyskać więcej informacji, zobacz sekcję [instrukcja foreach](~/_csharplang/spec/statements.md#the-foreach-statement) w [specyfikacji języka C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="e35ce-131">For more information, see [The foreach statement](~/_csharplang/spec/statements.md#the-foreach-statement) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e35ce-132">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="e35ce-132">See also</span></span>

- [<span data-ttu-id="e35ce-133">Dokumentacja języka C#</span><span class="sxs-lookup"><span data-stu-id="e35ce-133">C# reference</span></span>](../index.md)
- [<span data-ttu-id="e35ce-134">Słowa kluczowe języka C#</span><span class="sxs-lookup"><span data-stu-id="e35ce-134">C# keywords</span></span>](index.md)
- [<span data-ttu-id="e35ce-135">Używanie instrukcji foreach z tablicami</span><span class="sxs-lookup"><span data-stu-id="e35ce-135">Using foreach with arrays</span></span>](../../programming-guide/arrays/using-foreach-with-arrays.md)
- [<span data-ttu-id="e35ce-136">for, instrukcja</span><span class="sxs-lookup"><span data-stu-id="e35ce-136">for statement</span></span>](for.md)
