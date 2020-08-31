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
# <a name="if-else-c-reference"></a>if-else (odwołanie w C#)

`if`Instrukcja określa, która instrukcja ma być uruchamiana na podstawie wartości wyrażenia logicznego. W poniższym przykładzie `bool` zmienna `condition` jest ustawiona na, `true` a następnie zaewidencjonowana w `if` instrukcji. Wynik to `The variable is set to true.`.

[!code-csharp[csrefKeywordsSelection#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsSelection/CS/csrefKeywordsSelection.cs#1)]

Przykłady w tym temacie można uruchomić, umieszczając je w `Main` metodzie aplikacji konsolowej.

`if`Instrukcja w języku C# może przyjmować dwie formy, jak pokazano w poniższym przykładzie.

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

W `if-else` instrukcji, jeśli ma `condition` wartość true, są `then-statement` uruchamiane. Jeśli `condition` ma wartość false, `else-statement` uruchomienia. Ponieważ `condition` nie może mieć jednocześnie wartości true i false, `then-statement` a `else-statement` `if-else` instrukcja nie może być jednocześnie uruchomiona. Po wykonaniu `then-statement` `else-statement` instrukcji lub, formant jest przenoszony do następnej instrukcji za `if` instrukcją.

W `if` instrukcji, która nie zawiera `else` instrukcji, jeśli `condition` ma wartość true, są `then-statement` uruchamiane. Jeśli `condition` ma wartość false, sterowanie jest przekazywane do następnej instrukcji po `if` instrukcji.

Zarówno, `then-statement` jak i `else-statement` może składać się z pojedynczej instrukcji lub wielu instrukcji, które są ujęte w nawiasy klamrowe ( `{}` ). W przypadku pojedynczej instrukcji nawiasy klamrowe są opcjonalne, ale zalecane.

Instrukcja lub instrukcje w `then-statement` i `else-statement` może być dowolnego rodzaju, łącznie z inną `if` instrukcją zagnieżdżoną w oryginalnej `if` instrukcji. W zagnieżdżonych `if` instrukcjach każda `else` klauzula należy do ostatniej `if` , która nie ma odpowiedniego elementu `else` . W poniższym przykładzie `Result1` pojawia się, jeśli obie `m > 10` i `n > 20` szacują wartość true. Jeśli `m > 10` ma wartość true `n > 20` , ale ma wartość false, `Result2` pojawia się.

[!code-csharp[csrefKeywordsSelection#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsSelection/CS/csrefKeywordsSelection.cs#2)]

Jeśli zamiast tego chcesz, `Result2` aby był wyświetlany, gdy ma `(m > 10)` wartość false, możesz określić to skojarzenie przy użyciu nawiasów klamrowych, aby ustalić początkową i końcową instrukcję zagnieżdżoną `if` , jak pokazano w poniższym przykładzie.

[!code-csharp[csrefKeywordsSelection#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsSelection/CS/csrefKeywordsSelection.cs#3)]

`Result2` występuje, gdy warunek `(m > 10)` zwróci wartość false.

## <a name="example"></a>Przykład

W poniższym przykładzie wprowadzasz znak z klawiatury, a program używa zagnieżdżonej `if` instrukcji, aby określić, czy znak wejściowy jest znakiem alfabetycznym. Jeśli znak wejściowy jest znakiem alfabetycznym, program sprawdza, czy znak wejściowy jest pisany małymi lub wielką literą. W każdym przypadku pojawia się komunikat.

[!code-csharp[csrefKeywordsSelection#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsSelection/CS/csrefKeywordsSelection.cs#4)]

## <a name="example"></a>Przykład

Możesz również zagnieżdżać `if` instrukcję wewnątrz bloku else, jak pokazano w poniższym kodzie częściowym. Przykład zagnieżdża `if` instrukcje wewnątrz dwóch bloków else i jeden blok then. Komentarze określają, które warunki mają wartość PRAWDA lub FAŁSZ w każdym bloku.

[!code-csharp[csrefKeywordsSelection#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsSelection/CS/csrefKeywordsSelection.cs#5)]

## <a name="example"></a>Przykład

Poniższy przykład określa, czy znak wejściowy jest małą literą, wielką literą lub cyfrą. Jeśli wszystkie trzy warunki mają wartość FAŁSZ, znak nie jest znakiem alfanumerycznym. Przykład wyświetla komunikat dla każdego przypadku.

[!code-csharp[csrefKeywordsSelection#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsSelection/CS/csrefKeywordsSelection.cs#6)]

Podobnie jak instrukcja w bloku else lub blok then może być dowolną prawidłową instrukcją, można użyć dowolnego prawidłowego wyrażenia logicznego dla warunku. Można użyć [operatorów logicznych](../operators/boolean-logical-operators.md) , takich jak `!` , `&&` , `||` , `&` , `|` i, `^` Aby wprowadzić warunki złożone. Poniższy kod przedstawia przykłady.

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

## <a name="c-language-specification"></a>specyfikacja języka C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Zobacz też

- [Odwołanie w C#](../index.md)
- [Przewodnik programowania w języku C#](../../programming-guide/index.md)
- [Słowa kluczowe języka C#](index.md)
- [?: — Operator](../operators/conditional-operator.md)
- [if-else — instrukcja (C++)](/cpp/cpp/if-else-statement-cpp)
- [przełącznika](switch.md)
