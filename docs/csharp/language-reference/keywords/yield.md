---
description: Yield kontekstowego słowa kluczowego — odwołanie w C#
title: Yield kontekstowego słowa kluczowego — odwołanie w C#
ms.date: 07/20/2015
f1_keywords:
- yield
- yield_CSharpKeyword
helpviewer_keywords:
- yield keyword [C#]
ms.assetid: 1089194f-9e53-46a2-8642-53ccbe9d414d
ms.openlocfilehash: c8caf7e34397faf9f7085d6634287cffcb37eb08
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89141884"
---
# <a name="yield-c-reference"></a><span data-ttu-id="0a758-103">yield (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="0a758-103">yield (C# Reference)</span></span>

<span data-ttu-id="0a758-104">W przypadku użycia `yield` [kontekstowego słowa kluczowego](index.md#contextual-keywords) w instrukcji wskazuje, że metoda, operator lub akcesor, `get` w którym występuje, jest iteratorem.</span><span class="sxs-lookup"><span data-stu-id="0a758-104">When you use the `yield` [contextual keyword](index.md#contextual-keywords) in a statement, you indicate that the method, operator, or `get` accessor in which it appears is an iterator.</span></span> <span data-ttu-id="0a758-105">Użycie `yield` do zdefiniowania iteratora eliminuje potrzebę jawnej dodatkowej klasy (klasy, która przechowuje stan wyliczenia, zobacz <xref:System.Collections.Generic.IEnumerator%601> na przykład) podczas implementowania <xref:System.Collections.IEnumerable> <xref:System.Collections.IEnumerator> wzorca i dla niestandardowego typu kolekcji.</span><span class="sxs-lookup"><span data-stu-id="0a758-105">Using `yield` to define an iterator removes the need for an explicit extra class (the class that holds the state for an enumeration, see <xref:System.Collections.Generic.IEnumerator%601> for an example) when you implement the <xref:System.Collections.IEnumerable> and <xref:System.Collections.IEnumerator> pattern for a custom collection type.</span></span>

<span data-ttu-id="0a758-106">Poniższy przykład pokazuje dwie formy `yield` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="0a758-106">The following example shows the two forms of the `yield` statement.</span></span>

```csharp
yield return <expression>;
yield break;
```

## <a name="remarks"></a><span data-ttu-id="0a758-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="0a758-107">Remarks</span></span>

<span data-ttu-id="0a758-108">Używasz instrukcji, `yield return` Aby zwrócić każdy element po jednym naraz.</span><span class="sxs-lookup"><span data-stu-id="0a758-108">You use a `yield return` statement to return each element one at a time.</span></span>

<span data-ttu-id="0a758-109">Sekwencja zwrócona przez metodę iteratora może być używana przy użyciu instrukcji [foreach](foreach-in.md) lub zapytania LINQ.</span><span class="sxs-lookup"><span data-stu-id="0a758-109">The sequence returned from an iterator method can be consumed by using a [foreach](foreach-in.md) statement or LINQ query.</span></span> <span data-ttu-id="0a758-110">Każda iteracja `foreach` pętli wywołuje metodę iteratora.</span><span class="sxs-lookup"><span data-stu-id="0a758-110">Each iteration of the `foreach` loop calls the iterator method.</span></span> <span data-ttu-id="0a758-111">Gdy `yield return` instrukcja zostanie osiągnięta w metodzie iteratora, `expression` jest zwracana, a bieżąca lokalizacja w kodzie jest zachowywana.</span><span class="sxs-lookup"><span data-stu-id="0a758-111">When a `yield return` statement is reached in the iterator method, `expression` is returned, and the current location in code is retained.</span></span> <span data-ttu-id="0a758-112">Wykonanie jest uruchamiane ponownie z tej lokalizacji przy następnym wywołaniu funkcji iteratora.</span><span class="sxs-lookup"><span data-stu-id="0a758-112">Execution is restarted from that location the next time that the iterator function is called.</span></span>

<span data-ttu-id="0a758-113">Możesz użyć instrukcji, `yield break` Aby zakończyć iterację.</span><span class="sxs-lookup"><span data-stu-id="0a758-113">You can use a `yield break` statement to end the iteration.</span></span>

<span data-ttu-id="0a758-114">Aby uzyskać więcej informacji na temat iteratorów, zobacz [Iteratory](../../iterators.md).</span><span class="sxs-lookup"><span data-stu-id="0a758-114">For more information about iterators, see [Iterators](../../iterators.md).</span></span>

## <a name="iterator-methods-and-get-accessors"></a><span data-ttu-id="0a758-115">Metody iteratorów i uzyskiwania dostępu</span><span class="sxs-lookup"><span data-stu-id="0a758-115">Iterator methods and get accessors</span></span>

<span data-ttu-id="0a758-116">Deklaracja iteratora musi spełniać następujące wymagania:</span><span class="sxs-lookup"><span data-stu-id="0a758-116">The declaration of an iterator must meet the following requirements:</span></span>

- <span data-ttu-id="0a758-117">Typem zwracanym musi być <xref:System.Collections.IEnumerable> , <xref:System.Collections.Generic.IEnumerable%601> ,, <xref:System.Collections.IEnumerator> lub <xref:System.Collections.Generic.IEnumerator%601> .</span><span class="sxs-lookup"><span data-stu-id="0a758-117">The return type must be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>

- <span data-ttu-id="0a758-118">Deklaracja nie może [zawierać żadnych parametrów](in-parameter-modifier.md) [ref](ref.md) ani [out](out-parameter-modifier.md) .</span><span class="sxs-lookup"><span data-stu-id="0a758-118">The declaration can't have any [in](in-parameter-modifier.md) [ref](ref.md) or [out](out-parameter-modifier.md) parameters.</span></span>

<span data-ttu-id="0a758-119">`yield`Typ iteratora, który zwraca <xref:System.Collections.IEnumerable> lub <xref:System.Collections.IEnumerator> jest `object` .</span><span class="sxs-lookup"><span data-stu-id="0a758-119">The `yield` type of an iterator that returns <xref:System.Collections.IEnumerable> or <xref:System.Collections.IEnumerator> is `object`.</span></span>  <span data-ttu-id="0a758-120">Jeśli iterator zwraca <xref:System.Collections.Generic.IEnumerable%601> lub <xref:System.Collections.Generic.IEnumerator%601> , musi istnieć niejawna konwersja z typu wyrażenia w `yield return` instrukcji do parametru typu ogólnego.</span><span class="sxs-lookup"><span data-stu-id="0a758-120">If the iterator returns <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Collections.Generic.IEnumerator%601>, there must be an implicit conversion from the type of the expression in the `yield return` statement to the generic type parameter .</span></span>

<span data-ttu-id="0a758-121">Nie można uwzględnić `yield return` instrukcji or `yield break` w:</span><span class="sxs-lookup"><span data-stu-id="0a758-121">You can't include a `yield return` or `yield break` statement in:</span></span>

- <span data-ttu-id="0a758-122">[Wyrażenia lambda](../operators/lambda-expressions.md) i [metody anonimowe](../operators/delegate-operator.md).</span><span class="sxs-lookup"><span data-stu-id="0a758-122">[Lambda expressions](../operators/lambda-expressions.md) and [anonymous methods](../operators/delegate-operator.md).</span></span>

- <span data-ttu-id="0a758-123">Metody, które zawierają bloki ze słowem kluczowym unsafe.</span><span class="sxs-lookup"><span data-stu-id="0a758-123">Methods that contain unsafe blocks.</span></span> <span data-ttu-id="0a758-124">Aby uzyskać więcej informacji, zobacz artykuł [niebezpieczny](unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="0a758-124">For more information, see [unsafe](unsafe.md).</span></span>

## <a name="exception-handling"></a><span data-ttu-id="0a758-125">Obsługa wyjątków</span><span class="sxs-lookup"><span data-stu-id="0a758-125">Exception handling</span></span>

<span data-ttu-id="0a758-126">`yield return`Instrukcja nie może znajdować się w bloku try-catch.</span><span class="sxs-lookup"><span data-stu-id="0a758-126">A `yield return` statement can't be located in a try-catch block.</span></span> <span data-ttu-id="0a758-127">`yield return`Instrukcja może znajdować się w bloku try instrukcji try-finally.</span><span class="sxs-lookup"><span data-stu-id="0a758-127">A `yield return` statement can be located in the try block of a try-finally statement.</span></span>

<span data-ttu-id="0a758-128">`yield break`Instrukcja może znajdować się w bloku try lub bloku catch, ale nie w bloku finally.</span><span class="sxs-lookup"><span data-stu-id="0a758-128">A `yield break` statement can be located in a try block or a catch block but not a finally block.</span></span>

<span data-ttu-id="0a758-129">Jeśli `foreach` treść (poza metodą iteratora) zgłasza wyjątek, `finally` zostaje wykonany blok w metodzie iteratora.</span><span class="sxs-lookup"><span data-stu-id="0a758-129">If the `foreach` body (outside of the iterator method) throws an exception, a `finally` block in the iterator method is executed.</span></span>

## <a name="technical-implementation"></a><span data-ttu-id="0a758-130">Implementacja techniczna</span><span class="sxs-lookup"><span data-stu-id="0a758-130">Technical implementation</span></span>

<span data-ttu-id="0a758-131">Poniższy kod zwraca `IEnumerable<string>` metodę z metody iteratora, a następnie wykonuje iterację za pośrednictwem jej elementów.</span><span class="sxs-lookup"><span data-stu-id="0a758-131">The following code returns an `IEnumerable<string>` from an iterator method and then iterates through its elements.</span></span>

```csharp
IEnumerable<string> elements = MyIteratorMethod();
foreach (string element in elements)
{
   ...
}
```

<span data-ttu-id="0a758-132">Wywołanie `MyIteratorMethod` nie wykonuje treści metody.</span><span class="sxs-lookup"><span data-stu-id="0a758-132">The call to `MyIteratorMethod` doesn't execute the body of the method.</span></span> <span data-ttu-id="0a758-133">Zamiast tego wywołanie zwraca `IEnumerable<string>` `elements` zmienną.</span><span class="sxs-lookup"><span data-stu-id="0a758-133">Instead the call returns an `IEnumerable<string>` into the `elements` variable.</span></span>

<span data-ttu-id="0a758-134">W iteracji `foreach` pętli <xref:System.Collections.IEnumerator.MoveNext%2A> Metoda jest wywoływana dla `elements` .</span><span class="sxs-lookup"><span data-stu-id="0a758-134">On an iteration of the `foreach` loop, the <xref:System.Collections.IEnumerator.MoveNext%2A> method is called for `elements`.</span></span> <span data-ttu-id="0a758-135">To wywołanie wykonuje treść `MyIteratorMethod` przed `yield return` osiągnięciem następnej instrukcji.</span><span class="sxs-lookup"><span data-stu-id="0a758-135">This call executes the body of `MyIteratorMethod` until the next `yield return` statement is reached.</span></span> <span data-ttu-id="0a758-136">Wyrażenie zwrócone przez `yield return` instrukcję określa nie tylko wartość `element` zmiennej do użycia przez treść pętli, ale również <xref:System.Collections.Generic.IEnumerator%601.Current%2A> Właściwość `elements` , która jest `IEnumerable<string>` .</span><span class="sxs-lookup"><span data-stu-id="0a758-136">The expression returned by the `yield return` statement determines not only the value of the `element` variable for consumption by the loop body but also the <xref:System.Collections.Generic.IEnumerator%601.Current%2A> property of `elements`, which is an `IEnumerable<string>`.</span></span>

<span data-ttu-id="0a758-137">W każdej kolejnej iteracji `foreach` pętli wykonywanie treści iteratora jest kontynuowane od miejsca, w którym została pozostawiona, po osiągnięciu `yield return` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="0a758-137">On each subsequent iteration of the `foreach` loop, the execution of the iterator body continues from where it left off, again stopping when it reaches a `yield return` statement.</span></span> <span data-ttu-id="0a758-138">`foreach`Pętla kończy się, gdy zostanie osiągnięty koniec metody iteratora lub `yield break` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="0a758-138">The `foreach` loop completes when the end of the iterator method or a `yield break` statement is reached.</span></span>

## <a name="example"></a><span data-ttu-id="0a758-139">Przykład</span><span class="sxs-lookup"><span data-stu-id="0a758-139">Example</span></span>

<span data-ttu-id="0a758-140">Poniższy przykład zawiera `yield return` instrukcję, która znajduje się wewnątrz `for` pętli.</span><span class="sxs-lookup"><span data-stu-id="0a758-140">The following example has a `yield return` statement that's inside a `for` loop.</span></span> <span data-ttu-id="0a758-141">Każda iteracja `foreach` treści instrukcji w `Main` metodzie tworzy wywołanie `Power` funkcji iteratora.</span><span class="sxs-lookup"><span data-stu-id="0a758-141">Each iteration of the `foreach` statement body in the `Main` method creates a call to the `Power` iterator function.</span></span> <span data-ttu-id="0a758-142">Każde wywołanie funkcji iteratora przechodzi do następnego wykonania `yield return` instrukcji, która występuje w następnej iteracji `for` pętli.</span><span class="sxs-lookup"><span data-stu-id="0a758-142">Each call to the iterator function proceeds to the next execution of the `yield return` statement, which occurs during the next iteration of the `for` loop.</span></span>

<span data-ttu-id="0a758-143">Zwracanym typem metody iteratora jest <xref:System.Collections.IEnumerable> , który jest typem interfejsu iteratora.</span><span class="sxs-lookup"><span data-stu-id="0a758-143">The return type of the iterator method is <xref:System.Collections.IEnumerable>, which is an iterator interface type.</span></span> <span data-ttu-id="0a758-144">Kiedy metoda iteratora jest wywoływana, zwraca obiekt wyliczeniowy, który zawiera potęgi liczb.</span><span class="sxs-lookup"><span data-stu-id="0a758-144">When the iterator method is called, it returns an enumerable object that contains the powers of a number.</span></span>

[!code-csharp[csrefKeywordsContextual#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#5)]

## <a name="example"></a><span data-ttu-id="0a758-145">Przykład</span><span class="sxs-lookup"><span data-stu-id="0a758-145">Example</span></span>

<span data-ttu-id="0a758-146">Poniższy przykład ilustruje `get` metodę dostępu, która jest iteratorem.</span><span class="sxs-lookup"><span data-stu-id="0a758-146">The following example demonstrates a `get` accessor that is an iterator.</span></span> <span data-ttu-id="0a758-147">W przykładzie każda `yield return` instrukcja zwraca wystąpienie klasy zdefiniowanej przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="0a758-147">In the example, each `yield return` statement returns an instance of a user-defined class.</span></span>

[!code-csharp[csrefKeywordsContextual#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#21)]

## <a name="c-language-specification"></a><span data-ttu-id="0a758-148">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="0a758-148">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="0a758-149">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="0a758-149">See also</span></span>

- [<span data-ttu-id="0a758-150">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="0a758-150">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="0a758-151">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="0a758-151">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="0a758-152">foreach, in</span><span class="sxs-lookup"><span data-stu-id="0a758-152">foreach, in</span></span>](foreach-in.md)
- [<span data-ttu-id="0a758-153">Iteratory</span><span class="sxs-lookup"><span data-stu-id="0a758-153">Iterators</span></span>](../../iterators.md)
