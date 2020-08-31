---
description: Odwołanie if-else-C#
title: Odwołanie if-else-C#
ms.date: 07/20/2015
f1_keywords:
- if_CSharpKeyword
- else
- else_CSharpKeyword
- if
helpviewer_keywords:
- else keyword [C#]
- if keyword [C#]
ms.assetid: d9a1d562-8cf5-4bd4-9ba7-8ad970cd25b2
ms.openlocfilehash: e2de84807a049bd47ea277db9fb010d0c2e4857d
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89118510"
---
# <a name="if-else-c-reference"></a><span data-ttu-id="c758a-103">if-else (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="c758a-103">if-else (C# Reference)</span></span>

<span data-ttu-id="c758a-104">`if`Instrukcja określa, która instrukcja ma być uruchamiana na podstawie wartości wyrażenia logicznego.</span><span class="sxs-lookup"><span data-stu-id="c758a-104">An `if` statement identifies which statement to run based on the value of a Boolean expression.</span></span> <span data-ttu-id="c758a-105">W poniższym przykładzie `bool` zmienna `condition` jest ustawiona na, `true` a następnie zaewidencjonowana w `if` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="c758a-105">In the following example, the `bool` variable `condition` is set to `true` and then checked in the `if` statement.</span></span> <span data-ttu-id="c758a-106">Wynik to `The variable is set to true.`.</span><span class="sxs-lookup"><span data-stu-id="c758a-106">The output is `The variable is set to true.`.</span></span>

[!code-csharp[csrefKeywordsSelection#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsSelection/CS/csrefKeywordsSelection.cs#1)]

<span data-ttu-id="c758a-107">Przykłady w tym temacie można uruchomić, umieszczając je w `Main` metodzie aplikacji konsolowej.</span><span class="sxs-lookup"><span data-stu-id="c758a-107">You can run the examples in this topic by placing them in the `Main` method of a console app.</span></span>

<span data-ttu-id="c758a-108">`if`Instrukcja w języku C# może przyjmować dwie formy, jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="c758a-108">An `if` statement in C# can take two forms, as the following example shows.</span></span>

```csharp
// if-else statement
if (condition)
{
    then-statement;
}
else
{
    else-statement;
}
// Next statement in the program.

// if statement without an else
if (condition)
{
    then-statement;
}
// Next statement in the program.
```

<span data-ttu-id="c758a-109">W `if-else` instrukcji, jeśli ma `condition` wartość true, są `then-statement` uruchamiane.</span><span class="sxs-lookup"><span data-stu-id="c758a-109">In an `if-else` statement, if `condition` evaluates to true, the `then-statement` runs.</span></span> <span data-ttu-id="c758a-110">Jeśli `condition` ma wartość false, `else-statement` uruchomienia.</span><span class="sxs-lookup"><span data-stu-id="c758a-110">If `condition` is false, the `else-statement` runs.</span></span> <span data-ttu-id="c758a-111">Ponieważ `condition` nie może mieć jednocześnie wartości true i false, `then-statement` a `else-statement` `if-else` instrukcja nie może być jednocześnie uruchomiona.</span><span class="sxs-lookup"><span data-stu-id="c758a-111">Because `condition` can’t be simultaneously true and false, the `then-statement` and the `else-statement` of an `if-else` statement can never both run.</span></span> <span data-ttu-id="c758a-112">Po wykonaniu `then-statement` `else-statement` instrukcji lub, formant jest przenoszony do następnej instrukcji za `if` instrukcją.</span><span class="sxs-lookup"><span data-stu-id="c758a-112">After the `then-statement` or the `else-statement` runs, control is transferred to the next statement after the `if` statement.</span></span>

<span data-ttu-id="c758a-113">W `if` instrukcji, która nie zawiera `else` instrukcji, jeśli `condition` ma wartość true, są `then-statement` uruchamiane.</span><span class="sxs-lookup"><span data-stu-id="c758a-113">In an `if` statement that doesn’t include an `else` statement, if `condition` is true, the `then-statement` runs.</span></span> <span data-ttu-id="c758a-114">Jeśli `condition` ma wartość false, sterowanie jest przekazywane do następnej instrukcji po `if` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="c758a-114">If `condition` is false, control is transferred to the next statement after the `if` statement.</span></span>

<span data-ttu-id="c758a-115">Zarówno, `then-statement` jak i `else-statement` może składać się z pojedynczej instrukcji lub wielu instrukcji, które są ujęte w nawiasy klamrowe ( `{}` ).</span><span class="sxs-lookup"><span data-stu-id="c758a-115">Both the `then-statement` and the `else-statement` can consist of a single statement or multiple statements that are enclosed in braces (`{}`).</span></span> <span data-ttu-id="c758a-116">W przypadku pojedynczej instrukcji nawiasy klamrowe są opcjonalne, ale zalecane.</span><span class="sxs-lookup"><span data-stu-id="c758a-116">For a single statement, the braces are optional but recommended.</span></span>

<span data-ttu-id="c758a-117">Instrukcja lub instrukcje w `then-statement` i `else-statement` może być dowolnego rodzaju, łącznie z inną `if` instrukcją zagnieżdżoną w oryginalnej `if` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="c758a-117">The statement or statements in the `then-statement` and the `else-statement` can be of any kind, including another `if` statement nested inside the original `if` statement.</span></span> <span data-ttu-id="c758a-118">W zagnieżdżonych `if` instrukcjach każda `else` klauzula należy do ostatniej `if` , która nie ma odpowiedniego elementu `else` .</span><span class="sxs-lookup"><span data-stu-id="c758a-118">In nested `if` statements, each `else` clause belongs to the last `if` that doesn’t have a corresponding `else`.</span></span> <span data-ttu-id="c758a-119">W poniższym przykładzie `Result1` pojawia się, jeśli obie `m > 10` i `n > 20` szacują wartość true.</span><span class="sxs-lookup"><span data-stu-id="c758a-119">In the following example, `Result1` appears if both `m > 10` and `n > 20` evaluate to true.</span></span> <span data-ttu-id="c758a-120">Jeśli `m > 10` ma wartość true `n > 20` , ale ma wartość false, `Result2` pojawia się.</span><span class="sxs-lookup"><span data-stu-id="c758a-120">If `m > 10` is true but `n > 20` is false, `Result2` appears.</span></span>

[!code-csharp[csrefKeywordsSelection#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsSelection/CS/csrefKeywordsSelection.cs#2)]

<span data-ttu-id="c758a-121">Jeśli zamiast tego chcesz, `Result2` aby był wyświetlany, gdy ma `(m > 10)` wartość false, możesz określić to skojarzenie przy użyciu nawiasów klamrowych, aby ustalić początkową i końcową instrukcję zagnieżdżoną `if` , jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="c758a-121">If, instead, you want `Result2` to appear when `(m > 10)` is false, you can specify that association by using braces to establish the start and end of the nested `if` statement, as the following example shows.</span></span>

[!code-csharp[csrefKeywordsSelection#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsSelection/CS/csrefKeywordsSelection.cs#3)]

<span data-ttu-id="c758a-122">`Result2` występuje, gdy warunek `(m > 10)` zwróci wartość false.</span><span class="sxs-lookup"><span data-stu-id="c758a-122">`Result2` appears if the condition `(m > 10)` evaluates to false.</span></span>

## <a name="example"></a><span data-ttu-id="c758a-123">Przykład</span><span class="sxs-lookup"><span data-stu-id="c758a-123">Example</span></span>

<span data-ttu-id="c758a-124">W poniższym przykładzie wprowadzasz znak z klawiatury, a program używa zagnieżdżonej `if` instrukcji, aby określić, czy znak wejściowy jest znakiem alfabetycznym.</span><span class="sxs-lookup"><span data-stu-id="c758a-124">In the following example, you enter a character from the keyboard, and the program uses a nested `if` statement to determine whether the input character is an alphabetic character.</span></span> <span data-ttu-id="c758a-125">Jeśli znak wejściowy jest znakiem alfabetycznym, program sprawdza, czy znak wejściowy jest pisany małymi lub wielką literą.</span><span class="sxs-lookup"><span data-stu-id="c758a-125">If the input character is an alphabetic character, the program checks whether the input character is lowercase or uppercase.</span></span> <span data-ttu-id="c758a-126">W każdym przypadku pojawia się komunikat.</span><span class="sxs-lookup"><span data-stu-id="c758a-126">A message appears for each case.</span></span>

[!code-csharp[csrefKeywordsSelection#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsSelection/CS/csrefKeywordsSelection.cs#4)]

## <a name="example"></a><span data-ttu-id="c758a-127">Przykład</span><span class="sxs-lookup"><span data-stu-id="c758a-127">Example</span></span>

<span data-ttu-id="c758a-128">Możesz również zagnieżdżać `if` instrukcję wewnątrz bloku else, jak pokazano w poniższym kodzie częściowym.</span><span class="sxs-lookup"><span data-stu-id="c758a-128">You can also nest an `if` statement inside an else block, as the following partial code shows.</span></span> <span data-ttu-id="c758a-129">Przykład zagnieżdża `if` instrukcje wewnątrz dwóch bloków else i jeden blok then.</span><span class="sxs-lookup"><span data-stu-id="c758a-129">The example nests `if` statements inside two else blocks and one then block.</span></span> <span data-ttu-id="c758a-130">Komentarze określają, które warunki mają wartość PRAWDA lub FAŁSZ w każdym bloku.</span><span class="sxs-lookup"><span data-stu-id="c758a-130">The comments specify which conditions are true or false in each block.</span></span>

[!code-csharp[csrefKeywordsSelection#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsSelection/CS/csrefKeywordsSelection.cs#5)]

## <a name="example"></a><span data-ttu-id="c758a-131">Przykład</span><span class="sxs-lookup"><span data-stu-id="c758a-131">Example</span></span>

<span data-ttu-id="c758a-132">Poniższy przykład określa, czy znak wejściowy jest małą literą, wielką literą lub cyfrą.</span><span class="sxs-lookup"><span data-stu-id="c758a-132">The following example determines whether an input character is a lowercase letter, an uppercase letter, or a number.</span></span> <span data-ttu-id="c758a-133">Jeśli wszystkie trzy warunki mają wartość FAŁSZ, znak nie jest znakiem alfanumerycznym.</span><span class="sxs-lookup"><span data-stu-id="c758a-133">If all three conditions are false, the character isn’t an alphanumeric character.</span></span> <span data-ttu-id="c758a-134">Przykład wyświetla komunikat dla każdego przypadku.</span><span class="sxs-lookup"><span data-stu-id="c758a-134">The example displays a message for each case.</span></span>

[!code-csharp[csrefKeywordsSelection#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsSelection/CS/csrefKeywordsSelection.cs#6)]

<span data-ttu-id="c758a-135">Podobnie jak instrukcja w bloku else lub blok then może być dowolną prawidłową instrukcją, można użyć dowolnego prawidłowego wyrażenia logicznego dla warunku.</span><span class="sxs-lookup"><span data-stu-id="c758a-135">Just as a statement in the else block or the then block can be any valid statement, you can use any valid Boolean expression for the condition.</span></span> <span data-ttu-id="c758a-136">Można użyć [operatorów logicznych](../operators/boolean-logical-operators.md) , takich jak `!` , `&&` , `||` , `&` , `|` i, `^` Aby wprowadzić warunki złożone.</span><span class="sxs-lookup"><span data-stu-id="c758a-136">You can use [logical operators](../operators/boolean-logical-operators.md) such as `!`, `&&`, `||`, `&`, `|`, and `^` to make compound conditions.</span></span> <span data-ttu-id="c758a-137">Poniższy kod przedstawia przykłady.</span><span class="sxs-lookup"><span data-stu-id="c758a-137">The following code shows examples.</span></span>

```csharp
// NOT
bool result = true;
if (!result)
{
    Console.WriteLine("The condition is true (result is false).");
}
else
{
    Console.WriteLine("The condition is false (result is true).");
}

// Short-circuit AND
int m = 9;
int n = 7;
int p = 5;
if (m >= n && m >= p)
{
    Console.WriteLine("Nothing is larger than m.");
}

// AND and NOT
if (m >= n && !(p > m))
{
    Console.WriteLine("Nothing is larger than m.");
}

// Short-circuit OR
if (m > n || m > p)
{
    Console.WriteLine("m isn't the smallest.");
}

// NOT and OR
m = 4;
if (!(m >= n || m >= p))
{
    Console.WriteLine("Now m is the smallest.");
}
// Output:
// The condition is false (result is true).
// Nothing is larger than m.
// Nothing is larger than m.
// m isn't the smallest.
// Now m is the smallest.
```

## <a name="c-language-specification"></a><span data-ttu-id="c758a-138">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="c758a-138">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="c758a-139">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="c758a-139">See also</span></span>

- [<span data-ttu-id="c758a-140">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="c758a-140">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="c758a-141">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="c758a-141">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="c758a-142">Słowa kluczowe języka C#</span><span class="sxs-lookup"><span data-stu-id="c758a-142">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="c758a-143">?: — Operator</span><span class="sxs-lookup"><span data-stu-id="c758a-143">?: Operator</span></span>](../operators/conditional-operator.md)
- [<span data-ttu-id="c758a-144">if-else — instrukcja (C++)</span><span class="sxs-lookup"><span data-stu-id="c758a-144">if-else Statement (C++)</span></span>](/cpp/cpp/if-else-statement-cpp)
- [<span data-ttu-id="c758a-145">przełącznika</span><span class="sxs-lookup"><span data-stu-id="c758a-145">switch</span></span>](switch.md)
