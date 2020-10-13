---
description: Switch (odwołanie w C#)
title: Instrukcja Switch języka C#
ms.date: 04/09/2019
f1_keywords:
- switch_CSharpKeyword
- switch
- case
- case_CSharpKeyword
- defaultcase_CSharpKeyword
helpviewer_keywords:
- switch statement [C#]
- switch keyword [C#]
- case statement [C#]
- default keyword [C#]
ms.assetid: 44bae8b8-8841-4d85-826b-8a94277daecb
ms.openlocfilehash: 2d12091f3c3f10048a98f5f0ecf6a381087faf41
ms.sourcegitcommit: e078b7540a8293ca1b604c9c0da1ff1506f0170b
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "91997686"
---
# <a name="switch-c-reference"></a><span data-ttu-id="ca4ac-103">Switch (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="ca4ac-103">switch (C# reference)</span></span>

<span data-ttu-id="ca4ac-104">Ten artykuł dotyczy `switch` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="ca4ac-104">This article covers the `switch` statement.</span></span> <span data-ttu-id="ca4ac-105">Aby uzyskać informacje na temat `switch` wyrażenia (wprowadzonego w języku C# 8,0), zobacz artykuł dotyczący [ `switch` wyrażeń](../operators/switch-expression.md) w sekcji [wyrażenia i operatory](../operators/index.md) .</span><span class="sxs-lookup"><span data-stu-id="ca4ac-105">For information on the `switch` expression (introduced in C# 8.0), see the article on [`switch` expressions](../operators/switch-expression.md) in the [expressions and operators](../operators/index.md) section.</span></span>

<span data-ttu-id="ca4ac-106">`switch` jest instrukcją wyboru, która wybiera pojedynczy *przełącznik* , który ma zostać wykonany z listy kandydatów na podstawie dopasowania wzorca z *wyrażeniem Match*.</span><span class="sxs-lookup"><span data-stu-id="ca4ac-106">`switch` is a selection statement that chooses a single *switch section* to execute from a list of candidates based on a pattern match with the *match expression*.</span></span>

[!code-csharp[switch#1](~/samples/snippets/csharp/language-reference/keywords/switch/switch1.cs#1)]

<span data-ttu-id="ca4ac-107">`switch`Instrukcja jest często używana jako alternatywa dla konstrukcji [if-else](if-else.md) , jeśli pojedyncze wyrażenie jest testowane w oparciu o trzy lub więcej warunków.</span><span class="sxs-lookup"><span data-stu-id="ca4ac-107">The `switch` statement is often used as an alternative to an [if-else](if-else.md) construct if a single expression is tested against three or more conditions.</span></span> <span data-ttu-id="ca4ac-108">Na przykład Poniższa `switch` instrukcja określa, czy zmienna typu `Color` ma jedną z trzech wartości:</span><span class="sxs-lookup"><span data-stu-id="ca4ac-108">For example, the following `switch` statement determines whether a variable of type `Color` has one of three values:</span></span>

[!code-csharp[switch#3](~/samples/snippets/csharp/language-reference/keywords/switch/switch3.cs#1)]

<span data-ttu-id="ca4ac-109">Jest to odpowiednik poniższego przykładu korzystającego z `if` - `else` konstrukcji.</span><span class="sxs-lookup"><span data-stu-id="ca4ac-109">It's equivalent to the following example that uses an `if`-`else` construct.</span></span>

[!code-csharp[switch#3a](~/samples/snippets/csharp/language-reference/keywords/switch/switch3a.cs#1)]

## <a name="the-match-expression"></a><span data-ttu-id="ca4ac-110">Wyrażenie dopasowania</span><span class="sxs-lookup"><span data-stu-id="ca4ac-110">The match expression</span></span>

<span data-ttu-id="ca4ac-111">Wyrażenie Match zawiera wartość do dopasowania względem wzorców w `case` etykietach.</span><span class="sxs-lookup"><span data-stu-id="ca4ac-111">The match expression provides the value to match against the patterns in `case` labels.</span></span> <span data-ttu-id="ca4ac-112">Jego składnia to:</span><span class="sxs-lookup"><span data-stu-id="ca4ac-112">Its syntax is:</span></span>

```csharp
   switch (expr)
```

<span data-ttu-id="ca4ac-113">W języku C# 6 i wcześniejszych wyrażenie Match musi być wyrażeniem zwracającym wartość następujących typów:</span><span class="sxs-lookup"><span data-stu-id="ca4ac-113">In C# 6 and earlier, the match expression must be an expression that returns a value of the following types:</span></span>

- <span data-ttu-id="ca4ac-114">[znak](../builtin-types/char.md).</span><span class="sxs-lookup"><span data-stu-id="ca4ac-114">a [char](../builtin-types/char.md).</span></span>
- <span data-ttu-id="ca4ac-115">[ciąg](../builtin-types/reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="ca4ac-115">a [string](../builtin-types/reference-types.md).</span></span>
- <span data-ttu-id="ca4ac-116">wartość [logiczna](../builtin-types/bool.md).</span><span class="sxs-lookup"><span data-stu-id="ca4ac-116">a [bool](../builtin-types/bool.md).</span></span>
- <span data-ttu-id="ca4ac-117">wartość [całkowita](../builtin-types/integral-numeric-types.md) , taka jak `int` lub `long` .</span><span class="sxs-lookup"><span data-stu-id="ca4ac-117">an [integral](../builtin-types/integral-numeric-types.md) value, such as an `int` or a `long`.</span></span>
- <span data-ttu-id="ca4ac-118">wartość [wyliczenia](../builtin-types/enum.md) .</span><span class="sxs-lookup"><span data-stu-id="ca4ac-118">an [enum](../builtin-types/enum.md) value.</span></span>

<span data-ttu-id="ca4ac-119">Począwszy od języka C# 7,0 wyrażenie Match może być dowolnym wyrażeniem o wartości innej niż null.</span><span class="sxs-lookup"><span data-stu-id="ca4ac-119">Starting with C# 7.0, the match expression can be any non-null expression.</span></span>

## <a name="the-switch-section"></a><span data-ttu-id="ca4ac-120">Sekcja Switch</span><span class="sxs-lookup"><span data-stu-id="ca4ac-120">The switch section</span></span>

<span data-ttu-id="ca4ac-121">`switch`Instrukcja zawiera jedną lub więcej sekcji przełączników.</span><span class="sxs-lookup"><span data-stu-id="ca4ac-121">A `switch` statement includes one or more switch sections.</span></span> <span data-ttu-id="ca4ac-122">Każda sekcja przełącznika zawiera jedną lub więcej *etykiet przypadków* (literę lub etykietę domyślną), po której następuje jedna lub więcej instrukcji.</span><span class="sxs-lookup"><span data-stu-id="ca4ac-122">Each switch section contains one or more *case labels* (either a case or default label) followed by one or more statements.</span></span> <span data-ttu-id="ca4ac-123">`switch`Instrukcja może zawierać co najwyżej jedną etykietę domyślną umieszczoną w dowolnej sekcji Switch.</span><span class="sxs-lookup"><span data-stu-id="ca4ac-123">The `switch` statement may include at most one default label placed in any switch section.</span></span> <span data-ttu-id="ca4ac-124">Poniższy przykład pokazuje prostą `switch` instrukcję, która ma trzy sekcje przełączników, z których każda zawiera dwie instrukcje.</span><span class="sxs-lookup"><span data-stu-id="ca4ac-124">The following example shows a simple `switch` statement that has three switch sections, each containing two statements.</span></span> <span data-ttu-id="ca4ac-125">Druga sekcja Switch zawiera `case 2:` `case 3:` etykiety i.</span><span class="sxs-lookup"><span data-stu-id="ca4ac-125">The second switch section contains the `case 2:` and `case 3:` labels.</span></span>

<span data-ttu-id="ca4ac-126">`switch`Instrukcja może zawierać dowolną liczbę sekcji przełączników, a Każda sekcja może mieć jedną lub więcej etykiet wielkości liter, jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="ca4ac-126">A `switch` statement can include any number of switch sections, and each section can have one or more case labels, as shown in the following example.</span></span> <span data-ttu-id="ca4ac-127">Jednak żadne dwie etykiety wielkości liter nie mogą zawierać tego samego wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="ca4ac-127">However, no two case labels may contain the same expression.</span></span>

[!code-csharp[switch#2](~/samples/snippets/csharp/language-reference/keywords/switch/switch2.cs#1)]

<span data-ttu-id="ca4ac-128">W instrukcji switch jest wykonywana tylko jedna sekcja Switch.</span><span class="sxs-lookup"><span data-stu-id="ca4ac-128">Only one switch section in a switch statement executes.</span></span> <span data-ttu-id="ca4ac-129">Język C# nie zezwala na kontynuowanie wykonywania z jednej sekcji przełącznika do następnej.</span><span class="sxs-lookup"><span data-stu-id="ca4ac-129">C# doesn't allow execution to continue from one switch section to the next.</span></span> <span data-ttu-id="ca4ac-130">W związku z tym Poniższy kod generuje błąd kompilatora, CS0163: "kontrolka nie może przechodzić z jednej etykiety case ( \<case label> ) do innej".</span><span class="sxs-lookup"><span data-stu-id="ca4ac-130">Because of this, the following code generates a compiler error, CS0163: "Control cannot fall through from one case label (\<case label>) to another."</span></span>

```csharp
switch (caseSwitch)
{
    // The following switch section causes an error.
    case 1:
        Console.WriteLine("Case 1...");
        // Add a break or other jump statement here.
    case 2:
        Console.WriteLine("... and/or Case 2");
        break;
}
```

<span data-ttu-id="ca4ac-131">To wymaganie jest zwykle spełnione przez jawne opuszczenie sekcji Switch za pomocą instrukcji [Break](break.md), [goto](goto.md)lub [Return](return.md) .</span><span class="sxs-lookup"><span data-stu-id="ca4ac-131">This requirement is usually met by explicitly exiting the switch section by using a [break](break.md), [goto](goto.md), or [return](return.md) statement.</span></span> <span data-ttu-id="ca4ac-132">Jednak następujący kod jest również prawidłowy, ponieważ zapewnia, że Kontrolka programu nie może przechodzić do `default` sekcji Switch.</span><span class="sxs-lookup"><span data-stu-id="ca4ac-132">However, the following code is also valid, because it ensures that program control can't fall through to the `default` switch section.</span></span>

[!code-csharp[switch#4](~/samples/snippets/csharp/language-reference/keywords/switch/switch4.cs#1)]

<span data-ttu-id="ca4ac-133">Wykonanie listy instrukcji w sekcji Switch z etykietą Case, która pasuje do wyrażenia Match rozpoczyna się od pierwszej instrukcji i przechodzi przez listę instrukcji, zwykle do momentu osiągnięcia instrukcji skoku, takiej jak,,,, `break` `goto case` `goto label` `return` lub `throw` .</span><span class="sxs-lookup"><span data-stu-id="ca4ac-133">Execution of the statement list in the switch section with a case label that matches the match expression begins with the first statement and proceeds through the statement list, typically until a jump statement, such as a `break`, `goto case`, `goto label`, `return`, or `throw`, is reached.</span></span> <span data-ttu-id="ca4ac-134">W tym momencie formant jest transferowany poza `switch` instrukcją lub inną etykietą przypadku.</span><span class="sxs-lookup"><span data-stu-id="ca4ac-134">At that point, control is transferred outside the `switch` statement or to another case label.</span></span> <span data-ttu-id="ca4ac-135">`goto`Instrukcja, jeśli jest używana, musi przekazywać kontrolę do etykiety stałej.</span><span class="sxs-lookup"><span data-stu-id="ca4ac-135">A `goto` statement, if it's used, must transfer control to a constant label.</span></span> <span data-ttu-id="ca4ac-136">To ograniczenie jest konieczne, ponieważ próba przetransferowania kontroli do etykiety niestałej może mieć niepożądane efekty uboczne, takie przeniesienie kontroli do niezamierzonej lokalizacji w kodzie lub utworzenie pętli nieskończonej.</span><span class="sxs-lookup"><span data-stu-id="ca4ac-136">This restriction is necessary, since attempting to transfer control to a non-constant label can have undesirable side-effects, such transferring control to an unintended location in code or creating an endless loop.</span></span>

## <a name="case-labels"></a><span data-ttu-id="ca4ac-137">Etykiety przypadku</span><span class="sxs-lookup"><span data-stu-id="ca4ac-137">Case labels</span></span>

<span data-ttu-id="ca4ac-138">Każda etykieta przypadku określa wzorzec do porównania z wyrażeniem dopasowania ( `caseSwitch` zmienna w poprzednich przykładach).</span><span class="sxs-lookup"><span data-stu-id="ca4ac-138">Each case label specifies a pattern to compare to the match expression (the `caseSwitch` variable in the previous examples).</span></span> <span data-ttu-id="ca4ac-139">Jeśli są one zgodne, sterowanie jest przekazywane do sekcji Switch, która zawiera **pierwszą** pasującą etykietę case.</span><span class="sxs-lookup"><span data-stu-id="ca4ac-139">If they match, control is transferred to the switch section that contains the **first** matching case label.</span></span> <span data-ttu-id="ca4ac-140">Jeśli żaden wzorzec etykiety case nie jest zgodny z wyrażeniem Match, formant jest przenoszony do sekcji z `default` etykietą przypadku, jeśli istnieje.</span><span class="sxs-lookup"><span data-stu-id="ca4ac-140">If no case label pattern matches the match expression, control is transferred to the section with the `default` case label, if there's one.</span></span> <span data-ttu-id="ca4ac-141">Jeśli nie ma żadnego `default` przypadku, nie są wykonywane żadne instrukcje, a kontrolka jest transferowana poza `switch` instrukcją.</span><span class="sxs-lookup"><span data-stu-id="ca4ac-141">If there's no `default` case, no statements in any switch section are executed, and control is transferred outside the `switch` statement.</span></span>

<span data-ttu-id="ca4ac-142">Aby uzyskać informacje na temat `switch` dopasowania do instrukcji i wzorca, zobacz Zgodność [wzorca z sekcją `switch` instrukcji](#pattern-matching-with-the-switch-statement) .</span><span class="sxs-lookup"><span data-stu-id="ca4ac-142">For information on the `switch` statement and pattern matching, see the [Pattern matching with the `switch` statement](#pattern-matching-with-the-switch-statement) section.</span></span>

<span data-ttu-id="ca4ac-143">Ponieważ C# 6 obsługuje tylko wzorce stałe i nie zezwala na powtarzanie wartości stałych, etykiety przypadków definiują wzajemnie wykluczające się wartości, a tylko jeden wzorzec może być zgodny z wyrażeniem Match.</span><span class="sxs-lookup"><span data-stu-id="ca4ac-143">Because C# 6 supports only the constant pattern and doesn't allow the repetition of constant values, case labels define mutually exclusive values, and only one pattern can match the match expression.</span></span> <span data-ttu-id="ca4ac-144">W związku z tym kolejność, w której `case` wyświetlane są instrukcje, jest nieważna.</span><span class="sxs-lookup"><span data-stu-id="ca4ac-144">As a result, the order in which `case` statements appear is unimportant.</span></span>

<span data-ttu-id="ca4ac-145">W języku C# 7,0, jednak ponieważ inne wzorce są obsługiwane, etykiety przypadków nie muszą definiować wzajemnie wykluczających się wartości, a wiele wzorców może pasować do wyrażenia Match.</span><span class="sxs-lookup"><span data-stu-id="ca4ac-145">In C# 7.0, however, because other patterns are supported, case labels need not define mutually exclusive values, and multiple patterns can match the match expression.</span></span> <span data-ttu-id="ca4ac-146">Ponieważ są wykonywane tylko instrukcje w pierwszej sekcji przełącznika, które zawiera pasujący wzorzec, kolejność, w której są `case` wyświetlane instrukcje, jest teraz ważna.</span><span class="sxs-lookup"><span data-stu-id="ca4ac-146">Because only the statements in the first switch section that contains the matching pattern are executed, the order in which `case` statements appear is now important.</span></span> <span data-ttu-id="ca4ac-147">Jeśli w języku C# wykryje sekcja Switch, której instrukcja "Case" lub instrukcje są równoważne lub są podzbiorami poprzednich instrukcji, generuje błąd kompilatora, CS8120 "przypadek przełączania został już obsłużony w poprzednim przypadku".</span><span class="sxs-lookup"><span data-stu-id="ca4ac-147">If C# detects a switch section whose case statement or statements are equivalent to or are subsets of previous statements, it generates a compiler error, CS8120, "The switch case has already been handled by a previous case."</span></span>

<span data-ttu-id="ca4ac-148">Poniższy przykład ilustruje `switch` instrukcję, która używa różnych niewzajemnie wyłącznych wzorców.</span><span class="sxs-lookup"><span data-stu-id="ca4ac-148">The following example illustrates a `switch` statement that uses a variety of non-mutually exclusive patterns.</span></span> <span data-ttu-id="ca4ac-149">Jeśli przesuniesz `case 0:` sekcję Switch tak, aby nie była już pierwszą sekcją w `switch` instrukcji, w języku C# zostanie wygenerowany błąd kompilatora, ponieważ liczba całkowita, której wartością jest zero, jest podzbiorem wszystkich liczb całkowitych, które jest wzorcem zdefiniowanym przez `case int val` instrukcję.</span><span class="sxs-lookup"><span data-stu-id="ca4ac-149">If you move the `case 0:` switch section so that it's no longer the first section in the `switch` statement, C# generates a compiler error because an integer whose value is zero is a subset of all integers, which is the pattern defined by the `case int val` statement.</span></span>

[!code-csharp[switch#5](~/samples/snippets/csharp/language-reference/keywords/switch/switch5.cs#1)]

<span data-ttu-id="ca4ac-150">Możesz rozwiązać ten problem i wyeliminować Ostrzeżenie kompilatora na jeden z dwóch sposobów:</span><span class="sxs-lookup"><span data-stu-id="ca4ac-150">You can correct this issue and eliminate the compiler warning in one of two ways:</span></span>

- <span data-ttu-id="ca4ac-151">Zmieniając kolejność sekcji Switch.</span><span class="sxs-lookup"><span data-stu-id="ca4ac-151">By changing the order of the switch sections.</span></span>

- <span data-ttu-id="ca4ac-152">Za pomocą [klauzuli when](#the-case-statement-and-the-when-clause) w `case` etykiecie.</span><span class="sxs-lookup"><span data-stu-id="ca4ac-152">By using a [when clause](#the-case-statement-and-the-when-clause) in the `case` label.</span></span>

## <a name="the-default-case"></a><span data-ttu-id="ca4ac-153">`default`Wielkość liter</span><span class="sxs-lookup"><span data-stu-id="ca4ac-153">The `default` case</span></span>

<span data-ttu-id="ca4ac-154">`default`Przypadek określa sekcję Switch, która ma zostać wykonana, jeśli wyrażenie Match nie jest zgodne z żadną inną `case` etykietą.</span><span class="sxs-lookup"><span data-stu-id="ca4ac-154">The `default` case specifies the switch section to execute if the match expression doesn't match any other `case` label.</span></span> <span data-ttu-id="ca4ac-155">Jeśli `default` przypadek nie istnieje i wyrażenie Match nie pasuje do żadnej innej `case` etykiety, przepływ programu przechodzą przez `switch` instrukcję.</span><span class="sxs-lookup"><span data-stu-id="ca4ac-155">If a `default` case is not present and the match expression doesn't match any other `case` label, program flow falls through the `switch` statement.</span></span>

<span data-ttu-id="ca4ac-156">`default`Przypadek może pojawić się w dowolnej kolejności w `switch` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="ca4ac-156">The `default` case can appear in any order in the `switch` statement.</span></span> <span data-ttu-id="ca4ac-157">Bez względu na jego kolejność w kodzie źródłowym jest zawsze Szacowana jako Ostatnia, po `case` ocenie wszystkich etykiet.</span><span class="sxs-lookup"><span data-stu-id="ca4ac-157">Regardless of its order in the source code, it's always evaluated last, after all `case` labels have been evaluated.</span></span>

## <a name="pattern-matching-with-the-switch-statement"></a><span data-ttu-id="ca4ac-158">Dopasowanie wzorca do `switch` instrukcji</span><span class="sxs-lookup"><span data-stu-id="ca4ac-158">Pattern matching with the `switch` statement</span></span>

<span data-ttu-id="ca4ac-159">Każda `case` instrukcja definiuje wzorzec, który jest zgodny z wyrażeniem Match, powoduje, że jego sekcja Switch zostanie wykonana.</span><span class="sxs-lookup"><span data-stu-id="ca4ac-159">Each `case` statement defines a pattern that, if it matches the match expression, causes its  containing switch section to be executed.</span></span> <span data-ttu-id="ca4ac-160">Wszystkie wersje języka C# obsługują stałe wzorce.</span><span class="sxs-lookup"><span data-stu-id="ca4ac-160">All versions of C# support the constant pattern.</span></span> <span data-ttu-id="ca4ac-161">Pozostałe wzorce są obsługiwane począwszy od języka C# 7,0.</span><span class="sxs-lookup"><span data-stu-id="ca4ac-161">The remaining patterns are supported beginning with C# 7.0.</span></span>

### <a name="constant-pattern"></a><span data-ttu-id="ca4ac-162">Wzorzec stałej</span><span class="sxs-lookup"><span data-stu-id="ca4ac-162">Constant pattern</span></span>

<span data-ttu-id="ca4ac-163">Wzorzec stałej testuje, czy wyrażenie dopasowania jest równe określonej stałej.</span><span class="sxs-lookup"><span data-stu-id="ca4ac-163">The constant pattern tests whether the match expression equals a specified constant.</span></span> <span data-ttu-id="ca4ac-164">Jego składnia to:</span><span class="sxs-lookup"><span data-stu-id="ca4ac-164">Its syntax is:</span></span>

```csharp
   case constant:
```

<span data-ttu-id="ca4ac-165">gdzie *stała* jest wartością do przetestowania.</span><span class="sxs-lookup"><span data-stu-id="ca4ac-165">where *constant* is the value to test for.</span></span> <span data-ttu-id="ca4ac-166">*stała* może być dowolnym z następujących wyrażeń stałych:</span><span class="sxs-lookup"><span data-stu-id="ca4ac-166">*constant* can be any of the following constant expressions:</span></span>

- <span data-ttu-id="ca4ac-167">Literał [bool](../builtin-types/bool.md) : `true` lub `false` .</span><span class="sxs-lookup"><span data-stu-id="ca4ac-167">A [bool](../builtin-types/bool.md) literal: either `true` or `false`.</span></span>
- <span data-ttu-id="ca4ac-168">Dowolna stała [całkowita](../builtin-types/integral-numeric-types.md) , taka jak `int` , a `long` lub `byte` .</span><span class="sxs-lookup"><span data-stu-id="ca4ac-168">Any [integral](../builtin-types/integral-numeric-types.md) constant, such as an `int`, a `long`, or a `byte`.</span></span>
- <span data-ttu-id="ca4ac-169">Nazwa zadeklarowanej `const` zmiennej.</span><span class="sxs-lookup"><span data-stu-id="ca4ac-169">The name of a declared `const` variable.</span></span>
- <span data-ttu-id="ca4ac-170">Stała wyliczenia.</span><span class="sxs-lookup"><span data-stu-id="ca4ac-170">An enumeration constant.</span></span>
- <span data-ttu-id="ca4ac-171">Literał [znakowy](../builtin-types/char.md) .</span><span class="sxs-lookup"><span data-stu-id="ca4ac-171">A [char](../builtin-types/char.md) literal.</span></span>
- <span data-ttu-id="ca4ac-172">Literał [ciągu](../builtin-types/reference-types.md) .</span><span class="sxs-lookup"><span data-stu-id="ca4ac-172">A [string](../builtin-types/reference-types.md) literal.</span></span>

<span data-ttu-id="ca4ac-173">Wyrażenie stałe jest oceniane w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="ca4ac-173">The constant expression is evaluated as follows:</span></span>

- <span data-ttu-id="ca4ac-174">Jeśli *wyrażenie* i *stała* są typami całkowitymi, operator równości języka C# określa, czy wyrażenie zwróci wartość `true` (to znaczy czy `expr == constant` ).</span><span class="sxs-lookup"><span data-stu-id="ca4ac-174">If *expr* and *constant* are integral types, the C# equality operator determines whether the expression returns `true` (that is, whether `expr == constant`).</span></span>

- <span data-ttu-id="ca4ac-175">W przeciwnym razie wartość wyrażenia jest określana przez wywołanie metody static [obiektu. Equals (wyrażenie, stała)](xref:System.Object.Equals(System.Object,System.Object)) .</span><span class="sxs-lookup"><span data-stu-id="ca4ac-175">Otherwise, the value of the expression is determined by a call to the static [Object.Equals(expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) method.</span></span>

<span data-ttu-id="ca4ac-176">W poniższym przykładzie za pomocą wzorca stałego można określić, czy konkretna data to weekend, pierwszy dzień tygodnia pracy, ostatni dzień tygodnia pracy lub środek tygodnia pracy.</span><span class="sxs-lookup"><span data-stu-id="ca4ac-176">The following example uses the constant pattern to determine whether a particular date is a weekend, the first day of the work week, the last day of the work week, or the middle of the work week.</span></span> <span data-ttu-id="ca4ac-177">Oblicza <xref:System.DateTime.DayOfWeek?displayProperty=nameWithType> Właściwość bieżącego dnia względem elementów członkowskich <xref:System.DayOfWeek> wyliczenia.</span><span class="sxs-lookup"><span data-stu-id="ca4ac-177">It evaluates the <xref:System.DateTime.DayOfWeek?displayProperty=nameWithType> property of the current day against the members of the <xref:System.DayOfWeek> enumeration.</span></span>

[!code-csharp[switch#7](~/samples/snippets/csharp/language-reference/keywords/switch/const-pattern.cs#1)]

<span data-ttu-id="ca4ac-178">Poniższy przykład używa wzorca stałego do obsługi danych wejściowych użytkownika w aplikacji konsolowej, która symuluje automatyczną maszynę Kawową.</span><span class="sxs-lookup"><span data-stu-id="ca4ac-178">The following example uses the constant pattern to handle user input in a console application that simulates an automatic coffee machine.</span></span>

[!code-csharp[switch#6](~/samples/snippets/csharp/language-reference/keywords/switch/switch6.cs)]

### <a name="type-pattern"></a><span data-ttu-id="ca4ac-179">Wzorzec typu</span><span class="sxs-lookup"><span data-stu-id="ca4ac-179">Type pattern</span></span>

<span data-ttu-id="ca4ac-180">Wzorzec typu umożliwia obliczanie i konwersję zwięzłego typu.</span><span class="sxs-lookup"><span data-stu-id="ca4ac-180">The type pattern enables concise type evaluation and conversion.</span></span> <span data-ttu-id="ca4ac-181">Gdy jest używany z `switch` instrukcją do wykonywania dopasowania do wzorca, sprawdza, czy wyrażenie może być konwertowane do określonego typu i, jeśli to możliwe, rzutuje go na zmienną tego typu.</span><span class="sxs-lookup"><span data-stu-id="ca4ac-181">When used with the `switch` statement to perform pattern matching, it tests whether an expression can be converted to a specified type and, if it can be, casts it to a variable of that type.</span></span> <span data-ttu-id="ca4ac-182">Jego składnia to:</span><span class="sxs-lookup"><span data-stu-id="ca4ac-182">Its syntax is:</span></span>

```csharp
   case type varname
```

<span data-ttu-id="ca4ac-183">Where *Type* jest nazwą typu, do którego zostanie przekonwertowany wynik *wyrażenia* , a *nazwa_zmiennej* jest obiektem, do którego zostanie przekonwertowany wynik *wyrażenia* , jeśli dopasowanie się powiedzie.</span><span class="sxs-lookup"><span data-stu-id="ca4ac-183">where *type* is the name of the type to which the result of *expr* is to be converted, and *varname* is the object to which the result of *expr* is converted if the match succeeds.</span></span> <span data-ttu-id="ca4ac-184">Typ "czas kompilacji" *wyrażenia* może być parametrem typu ogólnego, rozpoczynając od języka C# 7,1.</span><span class="sxs-lookup"><span data-stu-id="ca4ac-184">The compile-time type of *expr* may be a generic type parameter, starting with C# 7.1.</span></span>

<span data-ttu-id="ca4ac-185">`case`Wyrażenie ma `true` wartość PRAWDA:</span><span class="sxs-lookup"><span data-stu-id="ca4ac-185">The `case` expression is `true` if any of the following is true:</span></span>

- <span data-ttu-id="ca4ac-186">*wyrażenie* jest wystąpieniem tego samego typu co *Typ*.</span><span class="sxs-lookup"><span data-stu-id="ca4ac-186">*expr* is an instance of the same type as *type*.</span></span>

- <span data-ttu-id="ca4ac-187">*wyrażenie* jest wystąpieniem typu, który pochodzi od *typu*.</span><span class="sxs-lookup"><span data-stu-id="ca4ac-187">*expr* is an instance of a type that derives from *type*.</span></span> <span data-ttu-id="ca4ac-188">Innymi słowy, wynik *wyrażenia* może być rzutowany na wystąpienie *typu*.</span><span class="sxs-lookup"><span data-stu-id="ca4ac-188">In other words, the result of *expr* can be upcast to an instance of *type*.</span></span>

- <span data-ttu-id="ca4ac-189">*wyrażenie* ma typ czasu kompilacji, który jest klasą bazową *typu*, a *wyrażenie* ma typ środowiska uruchomieniowego, który jest *typem* lub pochodzi od *typu*.</span><span class="sxs-lookup"><span data-stu-id="ca4ac-189">*expr* has a compile-time type that is a base class of *type*, and *expr* has a runtime type that is *type* or is derived from *type*.</span></span> <span data-ttu-id="ca4ac-190">*Typ czasu kompilacji* zmiennej to typ zmiennej, zgodnie z definicją w deklaracji typu.</span><span class="sxs-lookup"><span data-stu-id="ca4ac-190">The *compile-time type* of a variable is the variable's type as defined in its type declaration.</span></span> <span data-ttu-id="ca4ac-191">*Typ środowiska uruchomieniowego* zmiennej to typ wystąpienia, które jest przypisane do tej zmiennej.</span><span class="sxs-lookup"><span data-stu-id="ca4ac-191">The *runtime type* of a variable is the type of the instance that is assigned to that variable.</span></span>

- <span data-ttu-id="ca4ac-192">*wyrażenie* jest wystąpieniem typu, który implementuje interfejs *typu* .</span><span class="sxs-lookup"><span data-stu-id="ca4ac-192">*expr* is an instance of a type that implements the *type* interface.</span></span>

<span data-ttu-id="ca4ac-193">Jeśli wyrażenie CASE ma wartość true, właściwość *nazwa_zmiennej* jest ostatecznie przypisana i ma zakres lokalny tylko w sekcji Switch.</span><span class="sxs-lookup"><span data-stu-id="ca4ac-193">If the case expression is true, *varname* is definitely assigned and has local scope within the switch section only.</span></span>

<span data-ttu-id="ca4ac-194">Zwróć uwagę, że `null` nie pasuje do typu.</span><span class="sxs-lookup"><span data-stu-id="ca4ac-194">Note that `null` doesn't match a type.</span></span> <span data-ttu-id="ca4ac-195">Aby dopasować do `null` , należy użyć następującej `case` etykiety:</span><span class="sxs-lookup"><span data-stu-id="ca4ac-195">To match a `null`, you use the following `case` label:</span></span>

```csharp
case null:
```

<span data-ttu-id="ca4ac-196">Poniższy przykład używa wzorca typu, aby podać informacje dotyczące różnych rodzajów typów kolekcji.</span><span class="sxs-lookup"><span data-stu-id="ca4ac-196">The following example uses the type pattern to provide information about various kinds of collection types.</span></span>

[!code-csharp[type-pattern#1](~/samples/snippets/csharp/language-reference/keywords/switch/type-pattern.cs#1)]

<span data-ttu-id="ca4ac-197">Zamiast `object` , można utworzyć metodę rodzajową przy użyciu typu kolekcji jako parametru typu, jak pokazano w poniższym kodzie:</span><span class="sxs-lookup"><span data-stu-id="ca4ac-197">Instead of `object`, you could make a generic method, using the type of the collection as the type parameter, as shown in the following code:</span></span>

[!code-csharp[type-pattern#3](~/samples/snippets/csharp/language-reference/keywords/switch/type-pattern3.cs#1)]

<span data-ttu-id="ca4ac-198">Wersja ogólna różni się od pierwszej próbki na dwa sposoby.</span><span class="sxs-lookup"><span data-stu-id="ca4ac-198">The generic version is different than the first sample in two ways.</span></span> <span data-ttu-id="ca4ac-199">Po pierwsze nie można użyć `null` przypadku.</span><span class="sxs-lookup"><span data-stu-id="ca4ac-199">First, you can't use the `null` case.</span></span> <span data-ttu-id="ca4ac-200">Nie można użyć żadnego ze stałych przypadków, ponieważ kompilator nie może konwertować dowolnego dowolnego typu `T` do dowolnego typu innego niż `object` .</span><span class="sxs-lookup"><span data-stu-id="ca4ac-200">You can't use any constant case because the compiler can't convert any arbitrary type `T` to any type other than `object`.</span></span> <span data-ttu-id="ca4ac-201">Co było miało `default` teraz testy o wartości innej niż null `object` .</span><span class="sxs-lookup"><span data-stu-id="ca4ac-201">What had been the `default` case now tests for a non-null `object`.</span></span> <span data-ttu-id="ca4ac-202">Oznacza to, że `default` testy przypadku tylko dla `null` .</span><span class="sxs-lookup"><span data-stu-id="ca4ac-202">That means the `default` case tests only for `null`.</span></span>

<span data-ttu-id="ca4ac-203">Bez dopasowania do wzorca ten kod może być zapisany w następujący sposób.</span><span class="sxs-lookup"><span data-stu-id="ca4ac-203">Without pattern matching, this code might be written as follows.</span></span> <span data-ttu-id="ca4ac-204">Użycie dopasowania wzorca typu daje bardziej zwarty, czytelny kod, eliminując konieczność sprawdzenia, czy wynik konwersji jest `null` lub aby wykonać powtarzające się rzutowania.</span><span class="sxs-lookup"><span data-stu-id="ca4ac-204">The use of type pattern matching produces more compact, readable code by eliminating the need to test whether the result of a conversion is a `null` or to perform repeated casts.</span></span>

[!code-csharp[type-pattern2#1](~/samples/snippets/csharp/language-reference/keywords/switch/type-pattern2.cs#1)]

## <a name="the-case-statement-and-the-when-clause"></a><span data-ttu-id="ca4ac-205">`case`Instrukcja i `when` klauzula</span><span class="sxs-lookup"><span data-stu-id="ca4ac-205">The `case` statement and the `when` clause</span></span>

<span data-ttu-id="ca4ac-206">Począwszy od języka C# 7,0, ponieważ instrukcje Case nie muszą się wzajemnie wykluczać, można dodać `when` klauzulę, aby określić dodatkowy warunek, który musi być spełniony dla instrukcji case, aby obliczyć wartość true.</span><span class="sxs-lookup"><span data-stu-id="ca4ac-206">Starting with C# 7.0, because case statements need not be mutually exclusive, you can add a `when` clause to specify an additional condition that must be satisfied for the case statement to evaluate to true.</span></span> <span data-ttu-id="ca4ac-207">`when`Klauzula może być dowolnym wyrażeniem zwracającym wartość logiczną.</span><span class="sxs-lookup"><span data-stu-id="ca4ac-207">The `when` clause can be any expression that returns a Boolean value.</span></span>

<span data-ttu-id="ca4ac-208">W poniższym przykładzie zdefiniowano klasę bazową `Shape` , `Rectangle` Klasa, która pochodzi od `Shape` klasy, i `Square` Klasa, która pochodzi od `Rectangle` .</span><span class="sxs-lookup"><span data-stu-id="ca4ac-208">The following example defines a base `Shape` class, a `Rectangle` class that derives from `Shape`, and a `Square` class that derives from `Rectangle`.</span></span> <span data-ttu-id="ca4ac-209">Używa klauzuli, `when` Aby zapewnić, że `ShowShapeInfo` traktuje `Rectangle` obiekt, który ma przypisaną taką samą długość i szerokość, `Square` nawet jeśli nie został skonkretyzowany jako `Square` obiekt.</span><span class="sxs-lookup"><span data-stu-id="ca4ac-209">It uses the `when` clause to ensure that the `ShowShapeInfo` treats a `Rectangle` object that has been assigned equal lengths and widths as a `Square` even if it hasn't been instantiated as a `Square` object.</span></span> <span data-ttu-id="ca4ac-210">Metoda nie próbuje wyświetlić informacji o obiekcie `null` lub kształcie, którego obszar jest równy zero.</span><span class="sxs-lookup"><span data-stu-id="ca4ac-210">The method doesn't attempt to display information either about an object that is `null` or a shape whose area is zero.</span></span>

[!code-csharp[when-clause#1](~/samples/snippets/csharp/language-reference/keywords/switch/when-clause.cs#1)]

<span data-ttu-id="ca4ac-211">Należy zauważyć, że `when` klauzula w przykładzie, która próbuje sprawdzić, czy `Shape` obiekt `null` nie jest wykonywany.</span><span class="sxs-lookup"><span data-stu-id="ca4ac-211">Note that the `when` clause in the example that attempts to test whether a `Shape` object is `null` doesn't execute.</span></span> <span data-ttu-id="ca4ac-212">Poprawny wzorzec typu do przetestowania dla elementu `null` is `case null:` .</span><span class="sxs-lookup"><span data-stu-id="ca4ac-212">The correct type pattern to test for a `null` is `case null:`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="ca4ac-213">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="ca4ac-213">C# language specification</span></span>

<span data-ttu-id="ca4ac-214">Aby uzyskać więcej informacji, zobacz [instrukcja SWITCH](~/_csharplang/spec/statements.md#the-switch-statement) w [specyfikacji języka C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="ca4ac-214">For more information, see [The switch statement](~/_csharplang/spec/statements.md#the-switch-statement) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="ca4ac-215">Specyfikacja języka jest ostatecznym źródłem informacji o składni i użyciu języka C#.</span><span class="sxs-lookup"><span data-stu-id="ca4ac-215">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="ca4ac-216">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ca4ac-216">See also</span></span>

- [<span data-ttu-id="ca4ac-217">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="ca4ac-217">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="ca4ac-218">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="ca4ac-218">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="ca4ac-219">Słowa kluczowe języka C#</span><span class="sxs-lookup"><span data-stu-id="ca4ac-219">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="ca4ac-220">if-else</span><span class="sxs-lookup"><span data-stu-id="ca4ac-220">if-else</span></span>](if-else.md)
- [<span data-ttu-id="ca4ac-221">Dopasowanie wzorca</span><span class="sxs-lookup"><span data-stu-id="ca4ac-221">Pattern Matching</span></span>](../../pattern-matching.md)
