---
title: Cytaty kodu
description: 'Dowiedz się więcej o cytatach kodu języka F # — funkcja języka, która umożliwia programowe generowanie i Używanie wyrażeń kodu w języku F #.'
ms.date: 08/13/2020
ms.openlocfilehash: dc37fdbd6cd29e5ee94e5c0186dfe2bfeb666f32
ms.sourcegitcommit: f99115e12a5eb75638abe45072e023a3ce3351ac
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/12/2020
ms.locfileid: "94557197"
---
# <a name="code-quotations"></a><span data-ttu-id="e2ec0-103">Cytaty kodu</span><span class="sxs-lookup"><span data-stu-id="e2ec0-103">Code quotations</span></span>

<span data-ttu-id="e2ec0-104">W tym artykule opisano *notowania kodu* , funkcję języka, która umożliwia programowe generowanie i Używanie wyrażeń kodu w języku F #.</span><span class="sxs-lookup"><span data-stu-id="e2ec0-104">This article describes *code quotations* , a language feature that enables you to generate and work with F# code expressions programmatically.</span></span> <span data-ttu-id="e2ec0-105">Ta funkcja umożliwia wygenerowanie drzewa składni abstrakcyjnej, które reprezentuje kod F #.</span><span class="sxs-lookup"><span data-stu-id="e2ec0-105">This feature lets you generate an abstract syntax tree that represents F# code.</span></span> <span data-ttu-id="e2ec0-106">Drzewo składni abstrakcyjnej można następnie przetworzyć i przetwarzać w zależności od potrzeb aplikacji.</span><span class="sxs-lookup"><span data-stu-id="e2ec0-106">The abstract syntax tree can then be traversed and processed according to the needs of your application.</span></span> <span data-ttu-id="e2ec0-107">Można na przykład użyć drzewa do wygenerowania kodu F # lub wygenerowania kodu w innym języku.</span><span class="sxs-lookup"><span data-stu-id="e2ec0-107">For example, you can use the tree to generate F# code or generate code in some other language.</span></span>

## <a name="quoted-expressions"></a><span data-ttu-id="e2ec0-108">Wyrażenia cytowane</span><span class="sxs-lookup"><span data-stu-id="e2ec0-108">Quoted Expressions</span></span>

<span data-ttu-id="e2ec0-109">*Wyrażenie cytowane* jest wyrażeniem języka F # w kodzie, który jest rozdzielony w taki sposób, że nie jest kompilowany jako część programu, ale zamiast tego jest kompilowany do obiektu, który reprezentuje wyrażenie języka F #.</span><span class="sxs-lookup"><span data-stu-id="e2ec0-109">A *quoted expression* is an F# expression in your code that is delimited in such a way that it is not compiled as part of your program, but instead is compiled into an object that represents an F# expression.</span></span> <span data-ttu-id="e2ec0-110">Wyrażenie ujęte w cudzysłów można oznaczyć na jeden z dwóch sposobów: z informacjami o typie lub bez informacji o typie.</span><span class="sxs-lookup"><span data-stu-id="e2ec0-110">You can mark a quoted expression in one of two ways: either with type information or without type information.</span></span> <span data-ttu-id="e2ec0-111">Jeśli chcesz dołączyć informacje o typie, Użyj symboli i, aby rozdzielić `<@` `@>` wyrażenie ujęte w cudzysłów.</span><span class="sxs-lookup"><span data-stu-id="e2ec0-111">If you want to include type information, you use the symbols `<@` and `@>` to delimit the quoted expression.</span></span> <span data-ttu-id="e2ec0-112">Jeśli nie potrzebujesz informacji o typie, Użyj symboli `<@@` i `@@>` .</span><span class="sxs-lookup"><span data-stu-id="e2ec0-112">If you do not need type information, you use the symbols `<@@` and `@@>`.</span></span> <span data-ttu-id="e2ec0-113">Poniższy kod przedstawia wpisane i niewpisywane cudzysłowy.</span><span class="sxs-lookup"><span data-stu-id="e2ec0-113">The following code shows typed and untyped quotations.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet501.fs)]

<span data-ttu-id="e2ec0-114">Przechodzenie przez duże drzewo wyrażeń jest szybsze, jeśli nie zostaną uwzględnione informacje o typie.</span><span class="sxs-lookup"><span data-stu-id="e2ec0-114">Traversing a large expression tree is faster if you do not include type information.</span></span> <span data-ttu-id="e2ec0-115">Typ wyniku wyrażenia cytowanego za pomocą wpisanych symboli to `Expr<'T>` , gdzie parametr typu ma typ wyrażenia określony przez algorytm wnioskowania o typie kompilatora F #.</span><span class="sxs-lookup"><span data-stu-id="e2ec0-115">The resulting type of an expression quoted with the typed symbols is `Expr<'T>`, where the type parameter has the type of the expression as determined by the F# compiler's type inference algorithm.</span></span> <span data-ttu-id="e2ec0-116">W przypadku używania cudzysłowów kodu bez informacji o typie, typ wyrażenia w cudzysłowie jest [wyrażeniem](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-fsharpexpr.html)typu innego niż ogólny.</span><span class="sxs-lookup"><span data-stu-id="e2ec0-116">When you use code quotations without type information, the type of the quoted expression is the non-generic type [Expr](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-fsharpexpr.html).</span></span> <span data-ttu-id="e2ec0-117">Można wywołać Właściwość [RAW](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-fsharpexpr-1.html#Raw) klasy z określonym typem, `Expr` Aby uzyskać obiekt bez typu `Expr` .</span><span class="sxs-lookup"><span data-stu-id="e2ec0-117">You can call the [Raw](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-fsharpexpr-1.html#Raw) property on the typed `Expr` class to obtain the untyped `Expr` object.</span></span>

<span data-ttu-id="e2ec0-118">Istnieją różne metody statyczne, które umożliwiają programistyczne Generowanie obiektów wyrażeń języka F # w `Expr` klasie bez użycia wyrażeń ujętych w cudzysłów.</span><span class="sxs-lookup"><span data-stu-id="e2ec0-118">There are a variety of static methods that allow you to generate F# expression objects programmatically in the `Expr` class without using quoted expressions.</span></span>

<span data-ttu-id="e2ec0-119">Należy zauważyć, że cytat kodu musi zawierać pełne wyrażenie.</span><span class="sxs-lookup"><span data-stu-id="e2ec0-119">Note that a code quotation must include a complete expression.</span></span> <span data-ttu-id="e2ec0-120">Na `let` przykład dla powiązania, potrzebna jest zarówno definicja powiązanej nazwy, jak i dodatkowe wyrażenie, które używa powiązania.</span><span class="sxs-lookup"><span data-stu-id="e2ec0-120">For a `let` binding, for example, you need both the definition of the bound name and an additional expression that uses the binding.</span></span> <span data-ttu-id="e2ec0-121">W pełnej składni jest to wyrażenie zgodne ze `in` słowem kluczowym.</span><span class="sxs-lookup"><span data-stu-id="e2ec0-121">In verbose syntax, this is an expression that follows the `in` keyword.</span></span> <span data-ttu-id="e2ec0-122">Na najwyższego poziomu w module jest to tylko następne wyrażenie w module, ale w cudzysłowie jest to jawnie wymagane.</span><span class="sxs-lookup"><span data-stu-id="e2ec0-122">At the top-level in a module, this is just the next expression in the module, but in a quotation, it is explicitly required.</span></span>

<span data-ttu-id="e2ec0-123">W związku z tym następujące wyrażenie jest nieprawidłowe.</span><span class="sxs-lookup"><span data-stu-id="e2ec0-123">Therefore, the following expression is not valid.</span></span>

```fsharp
// Not valid:
// <@ let f x = x + 1 @>
```

<span data-ttu-id="e2ec0-124">Ale poniższe wyrażenia są prawidłowe.</span><span class="sxs-lookup"><span data-stu-id="e2ec0-124">But the following expressions are valid.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet502.fs)]

<span data-ttu-id="e2ec0-125">Aby oszacować Cytaty w języku F #, należy użyć [ewaluatora oferty f #](https://github.com/fsprojects/FSharp.Quotations.Evaluator).</span><span class="sxs-lookup"><span data-stu-id="e2ec0-125">To evaluate F# quotations, you must use the [F# Quotation Evaluator](https://github.com/fsprojects/FSharp.Quotations.Evaluator).</span></span> <span data-ttu-id="e2ec0-126">Zapewnia obsługę oceniania i wykonywania obiektów wyrażeń języka F #.</span><span class="sxs-lookup"><span data-stu-id="e2ec0-126">It provides support for evaluating and executing F# expression objects.</span></span>

<span data-ttu-id="e2ec0-127">Cytaty języka F # zachowują również informacje dotyczące ograniczenia typu.</span><span class="sxs-lookup"><span data-stu-id="e2ec0-127">F# quotations also retain type constraint information.</span></span> <span data-ttu-id="e2ec0-128">Rozpatrzmy następujący przykład:</span><span class="sxs-lookup"><span data-stu-id="e2ec0-128">Consider the following example:</span></span>

```fsharp
open FSharp.Linq.RuntimeHelpers

let eval q = LeafExpressionConverter.EvaluateQuotation q

let inline negate x = -x
// val inline negate: x: ^a ->  ^a when  ^a : (static member ( ~- ) :  ^a ->  ^a)

<@ negate 1.0 @>  |> eval
```

<span data-ttu-id="e2ec0-129">Ograniczenie generowane przez `inline` funkcję jest zachowywane w kodzie qutoation.</span><span class="sxs-lookup"><span data-stu-id="e2ec0-129">The constraint generated by the `inline` function is retained in the code qutoation.</span></span> <span data-ttu-id="e2ec0-130">`negate`Można teraz ocenić formularz quotated funkcji.</span><span class="sxs-lookup"><span data-stu-id="e2ec0-130">The `negate` function's quotated form can now be evaluated.</span></span>

## <a name="expr-type"></a><span data-ttu-id="e2ec0-131">Typ wyrażenia</span><span class="sxs-lookup"><span data-stu-id="e2ec0-131">Expr Type</span></span>

<span data-ttu-id="e2ec0-132">Wystąpienie `Expr` typu reprezentuje wyrażenie języka F #.</span><span class="sxs-lookup"><span data-stu-id="e2ec0-132">An instance of the `Expr` type represents an F# expression.</span></span> <span data-ttu-id="e2ec0-133">Typy ogólne i nieogólne `Expr` są udokumentowane w dokumentacji biblioteki języka F #.</span><span class="sxs-lookup"><span data-stu-id="e2ec0-133">Both the generic and the non-generic `Expr` types are documented in the F# library documentation.</span></span> <span data-ttu-id="e2ec0-134">Aby uzyskać więcej informacji, zobacz [FSharp. cudzysłóws i Namespace](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations.html) [. Expr klasy](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-fsharpexpr.html).</span><span class="sxs-lookup"><span data-stu-id="e2ec0-134">For more information, see [FSharp.Quotations Namespace](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations.html) and [Quotations.Expr Class](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-fsharpexpr.html).</span></span>

## <a name="splicing-operators"></a><span data-ttu-id="e2ec0-135">Łączenie operatorów</span><span class="sxs-lookup"><span data-stu-id="e2ec0-135">Splicing Operators</span></span>

<span data-ttu-id="e2ec0-136">Metoda łączenia umożliwia łączenie literałów kodu w znakach z wyrażeniami utworzonymi programowo lub z innej oferty kodu.</span><span class="sxs-lookup"><span data-stu-id="e2ec0-136">Splicing enables you to combine literal code quotations with expressions that you have created programmatically or from another code quotation.</span></span> <span data-ttu-id="e2ec0-137">`%`Operatory i `%%` umożliwiają dodanie obiektu wyrażenia F # do cudzysłowu kodu.</span><span class="sxs-lookup"><span data-stu-id="e2ec0-137">The `%` and `%%` operators enable you to add an F# expression object into a code quotation.</span></span> <span data-ttu-id="e2ec0-138">Możesz użyć `%` operatora, aby wstawić obiekt wyrażenia z wpisaną do wpisanej cudzysłowu. Użyj `%%` operatora, aby wstawić nieokreślony obiekt wyrażenia do cudzysłowu nietypu.</span><span class="sxs-lookup"><span data-stu-id="e2ec0-138">You use the `%` operator to insert a typed expression object into a typed quotation; you use the `%%` operator to insert an untyped expression object into an untyped quotation.</span></span> <span data-ttu-id="e2ec0-139">Oba operatory są jednoargumentowymi operatorami prefiksu.</span><span class="sxs-lookup"><span data-stu-id="e2ec0-139">Both operators are unary prefix operators.</span></span> <span data-ttu-id="e2ec0-140">W takim przypadku `expr` , jeśli jest wyrażeniem typu untyped `Expr` , poniższy kod jest prawidłowy.</span><span class="sxs-lookup"><span data-stu-id="e2ec0-140">Thus if `expr` is an untyped expression of type `Expr`, the following code is valid.</span></span>

```fsharp
<@@ 1 + %%expr @@>
```

<span data-ttu-id="e2ec0-141">A jeśli `expr` jest wpisanym cytatem typu `Expr<int>` , poniższy kod jest prawidłowy.</span><span class="sxs-lookup"><span data-stu-id="e2ec0-141">And if `expr` is a typed quotation of type `Expr<int>`, the following code is valid.</span></span>

```fsharp
<@ 1 + %expr @>
```

## <a name="example"></a><span data-ttu-id="e2ec0-142">Przykład</span><span class="sxs-lookup"><span data-stu-id="e2ec0-142">Example</span></span>

### <a name="description"></a><span data-ttu-id="e2ec0-143">Opis</span><span class="sxs-lookup"><span data-stu-id="e2ec0-143">Description</span></span>

<span data-ttu-id="e2ec0-144">Poniższy przykład ilustruje użycie cytatów kodu w celu umieszczenia kodu F # w obiekcie Expression, a następnie drukuje kod F #, który reprezentuje wyrażenie.</span><span class="sxs-lookup"><span data-stu-id="e2ec0-144">The following example illustrates the use of code quotations to put F# code into an expression object and then print the F# code that represents the expression.</span></span> <span data-ttu-id="e2ec0-145">`println`Zdefiniowano funkcję, która zawiera funkcję cykliczną `print` , która wyświetla obiekt wyrażenia F # (typu `Expr` ) w przyjaznym formacie.</span><span class="sxs-lookup"><span data-stu-id="e2ec0-145">A function `println` is defined that contains a recursive function `print` that displays an F# expression object (of type `Expr`) in a friendly format.</span></span> <span data-ttu-id="e2ec0-146">Istnieje kilka aktywnych wzorców w modułach [FSharp. Patterns. wzorców](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-patternsmodule.html) i [FSharp. cytats. DerivedPatterns](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-derivedpatternsmodule.html) , których można użyć do analizowania obiektów wyrażeń.</span><span class="sxs-lookup"><span data-stu-id="e2ec0-146">There are several active patterns in the [FSharp.Quotations.Patterns](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-patternsmodule.html) and [FSharp.Quotations.DerivedPatterns](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-derivedpatternsmodule.html) modules that can be used to analyze expression objects.</span></span> <span data-ttu-id="e2ec0-147">Ten przykład nie obejmuje wszystkich możliwych wzorców, które mogą być wyświetlane w wyrażeniu języka F #.</span><span class="sxs-lookup"><span data-stu-id="e2ec0-147">This example does not include all the possible patterns that might appear in an F# expression.</span></span> <span data-ttu-id="e2ec0-148">Każdy nierozpoznany wzorzec wyzwala dopasowanie do wzorca wieloznacznego ( `_` ) i jest renderowany przy użyciu `ToString` metody, która w `Expr` typie, pozwala znać Aktywny wzorzec do dodania do wyrażenia dopasowania.</span><span class="sxs-lookup"><span data-stu-id="e2ec0-148">Any unrecognized pattern triggers a match to the wildcard pattern (`_`) and is rendered by using the `ToString` method, which, on the `Expr` type, lets you know the active pattern to add to your match expression.</span></span>

### <a name="code"></a><span data-ttu-id="e2ec0-149">Kod</span><span class="sxs-lookup"><span data-stu-id="e2ec0-149">Code</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet601.fs)]

### <a name="output"></a><span data-ttu-id="e2ec0-150">Dane wyjściowe</span><span class="sxs-lookup"><span data-stu-id="e2ec0-150">Output</span></span>

```fsharp
fun (x:System.Int32) -> x + 1
a + 1
let f = fun (x:System.Int32) -> x + 10 in f 10
```

## <a name="example"></a><span data-ttu-id="e2ec0-151">Przykład</span><span class="sxs-lookup"><span data-stu-id="e2ec0-151">Example</span></span>

### <a name="description"></a><span data-ttu-id="e2ec0-152">Opis</span><span class="sxs-lookup"><span data-stu-id="e2ec0-152">Description</span></span>

<span data-ttu-id="e2ec0-153">Można również użyć trzech aktywnych wzorców w [module ExprShape](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-exprshapemodule.html) do przechodzenia między drzewami wyrażeń i mniejszą liczbą aktywnych wzorców.</span><span class="sxs-lookup"><span data-stu-id="e2ec0-153">You can also use the three active patterns in the [ExprShape module](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-exprshapemodule.html) to traverse expression trees with fewer active patterns.</span></span> <span data-ttu-id="e2ec0-154">Te aktywne wzorce mogą być przydatne, gdy chcesz przechodzenie przez drzewo, ale nie potrzebujesz wszystkich informacji w większości węzłów.</span><span class="sxs-lookup"><span data-stu-id="e2ec0-154">These active patterns can be useful when you want to traverse a tree but you do not need all the information in most of the nodes.</span></span> <span data-ttu-id="e2ec0-155">W przypadku używania tych wzorców każde wyrażenie F # pasuje do jednego z następujących trzech wzorców: `ShapeVar` Jeśli wyrażenie jest zmienną, `ShapeLambda` Jeśli wyrażenie jest wyrażeniem lambda lub `ShapeCombination` wyrażenie jest inne.</span><span class="sxs-lookup"><span data-stu-id="e2ec0-155">When you use these patterns, any F# expression matches one of the following three patterns: `ShapeVar` if the expression is a variable, `ShapeLambda` if the expression is a lambda expression, or `ShapeCombination` if the expression is anything else.</span></span> <span data-ttu-id="e2ec0-156">Jeśli przejdziesz do drzewa wyrażenia przy użyciu aktywnych wzorców, jak w poprzednim przykładzie kodu, musisz użyć więcej wzorców, aby obsłużyć wszystkie możliwe typy wyrażeń języka F #, a kod będzie bardziej skomplikowany.</span><span class="sxs-lookup"><span data-stu-id="e2ec0-156">If you traverse an expression tree by using the active patterns as in the previous code example, you have to use many more patterns to handle all possible F# expression types, and your code will be more complex.</span></span> <span data-ttu-id="e2ec0-157">Aby uzyskać więcej informacji, zobacz [ExprShape. ShapeVar&#124;ShapeLambda&#124;ShapeCombination — Active Pattern](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-exprshapemodule.html#(%20|ShapeVar|ShapeLambda|ShapeCombination|%20)).</span><span class="sxs-lookup"><span data-stu-id="e2ec0-157">For more information, see [ExprShape.ShapeVar&#124;ShapeLambda&#124;ShapeCombination Active Pattern](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-exprshapemodule.html#(%20|ShapeVar|ShapeLambda|ShapeCombination|%20)).</span></span>

<span data-ttu-id="e2ec0-158">Poniższy przykład kodu może służyć jako podstawa dla bardziej złożonych przechodzenia.</span><span class="sxs-lookup"><span data-stu-id="e2ec0-158">The following code example can be used as a basis for more complex traversals.</span></span> <span data-ttu-id="e2ec0-159">W tym kodzie jest tworzone drzewo wyrażenia dla wyrażenia, które obejmuje wywołanie funkcji `add` .</span><span class="sxs-lookup"><span data-stu-id="e2ec0-159">In this code, an expression tree is created for an expression that involves a function call, `add`.</span></span> <span data-ttu-id="e2ec0-160">Aktywny wzorzec [SpecificCall —](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-derivedpatternsmodule.html#(%20|SpecificCall|_|%20)) jest używany do wykrywania dowolnego wywołania `add` w drzewie wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="e2ec0-160">The [SpecificCall](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-derivedpatternsmodule.html#(%20|SpecificCall|_|%20)) active pattern is used to detect any call to `add` in the expression tree.</span></span> <span data-ttu-id="e2ec0-161">Ten Aktywny wzorzec przypisuje argumenty wywołania do `exprList` wartości.</span><span class="sxs-lookup"><span data-stu-id="e2ec0-161">This active pattern assigns the arguments of the call to the `exprList` value.</span></span> <span data-ttu-id="e2ec0-162">W tym przypadku istnieją tylko dwa, więc są one ściągane i funkcja jest wywoływana cyklicznie na argumentach.</span><span class="sxs-lookup"><span data-stu-id="e2ec0-162">In this case, there are only two, so these are pulled out and the function is called recursively on the arguments.</span></span> <span data-ttu-id="e2ec0-163">Wyniki są wstawiane do cudzysłowu kodu, który reprezentuje wywołanie przy `mul` użyciu operatora splice ( `%%` ).</span><span class="sxs-lookup"><span data-stu-id="e2ec0-163">The results are inserted into a code quotation that represents a call to `mul` by using the splice operator (`%%`).</span></span> <span data-ttu-id="e2ec0-164">`println`Funkcja z poprzedniego przykładu służy do wyświetlania wyników.</span><span class="sxs-lookup"><span data-stu-id="e2ec0-164">The `println` function from the previous example is used to display the results.</span></span>

<span data-ttu-id="e2ec0-165">Kod w innych gałęziach aktywnego wzorca tylko generuje to samo drzewo wyrażenia, więc jedyną zmianą w wyrażeniu wynikiem jest zmiana z `add` na `mul` .</span><span class="sxs-lookup"><span data-stu-id="e2ec0-165">The code in the other active pattern branches just regenerates the same expression tree, so the only change in the resulting expression is the change from `add` to `mul`.</span></span>

### <a name="code"></a><span data-ttu-id="e2ec0-166">Kod</span><span class="sxs-lookup"><span data-stu-id="e2ec0-166">Code</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet701.fs)]

### <a name="output"></a><span data-ttu-id="e2ec0-167">Dane wyjściowe</span><span class="sxs-lookup"><span data-stu-id="e2ec0-167">Output</span></span>

```fsharp
1 + Module1.add(2,Module1.add(3,4))
1 + Module1.mul(2,Module1.mul(3,4))
```

## <a name="see-also"></a><span data-ttu-id="e2ec0-168">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="e2ec0-168">See also</span></span>

- [<span data-ttu-id="e2ec0-169">Dokumentacja języka F #</span><span class="sxs-lookup"><span data-stu-id="e2ec0-169">F# Language Reference</span></span>](index.md)
