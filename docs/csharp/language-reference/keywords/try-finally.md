---
description: Informacje o instrukcji try-finally-C#
title: Informacje o instrukcji try-finally-C#
ms.date: 07/20/2015
f1_keywords:
- finally
- finally_CSharpKeyword
helpviewer_keywords:
- finally keyword [C#]
- try-finally statement [C#]
ms.assetid: c27623fb-7261-4464-862c-7a369d3c8f0a
ms.openlocfilehash: 621c5bf1607136361b72f978681607ec2aec150f
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89141975"
---
# <a name="try-finally-c-reference"></a>try-finally (odwołanie w C#)

Za pomocą `finally` bloku, można wyczyścić wszystkie zasoby, które są przydzielone w bloku [try](try-catch.md) , i można uruchomić kod nawet wtedy, gdy wystąpi wyjątek w `try` bloku. Zazwyczaj instrukcje bloku są uruchamiane, `finally` gdy kontrolka opuszcza `try` instrukcję. Transfer kontroli może wystąpić w wyniku normalnego wykonania, wykonania `break` `continue` instrukcji,, `goto` , lub `return` , lub propagacji wyjątku z `try` instrukcji.

W ramach obsłużonego wyjątku `finally` zagwarantowany jest, że skojarzony blok jest uruchamiany. Jeśli jednak wyjątek nie jest obsługiwany, wykonanie `finally` bloku jest zależne od tego, w jaki sposób wyzwalany jest wyjątek operacji unwind. To z kolei zależy od konfiguracji komputera.

Zwykle, gdy nieobsługiwany wyjątek kończący aplikację, niezależnie od tego, czy `finally` blok jest uruchomiony, nie jest ważne. Jednakże jeśli istnieją instrukcje w `finally` bloku, który musi być uruchamiany nawet w takiej sytuacji, jedno rozwiązanie ma dodać `catch` blok do `try` - `finally` instrukcji. Alternatywnie można przechwytywać wyjątek, który może zostać wygenerowany w `try` bloku `try` - `finally` instrukcji wyższej w górę stosu wywołań. Oznacza to, że można przechwytywać wyjątek w metodzie, która wywołuje metodę, która zawiera `try` - `finally` instrukcję, lub w metodzie, która wywołuje tę metodę, lub w dowolnej metodzie w stosie wywołań. Jeśli wyjątek nie zostanie przechwycony, wykonanie `finally` bloku zależy od tego, czy system operacyjny wybiera wyzwalacz operacji unwind.

## <a name="example"></a>Przykład

W poniższym przykładzie instrukcja konwersji nieprawidłowa powoduje `System.InvalidCastException` wyjątek. Wyjątek nie jest obsługiwany.

[!code-csharp[csrefKeywordsExceptions#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsExceptions/CS/csrefKeywordsExceptions.cs#4)]

W poniższym przykładzie wyjątek z `TryCast` metody jest przechwytywany w metodzie dalej w stosie wywołań.

[!code-csharp[csrefKeywordsExceptions#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsExceptions/CS/csrefKeywordsExceptions.cs#6)]

Aby uzyskać więcej informacji na temat `finally` , zobacz [try-catch-finally](try-catch-finally.md).

C# zawiera również [instrukcję using](using-statement.md), która zapewnia podobną funkcjonalność dla <xref:System.IDisposable> obiektów w wygodnej składni.

## <a name="c-language-specification"></a>specyfikacja języka C#

Aby uzyskać więcej informacji, zobacz sekcję [try instrukcji](~/_csharplang/spec/statements.md#the-try-statement) w [specyfikacji języka C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Zobacz też

- [Odwołanie w C#](../index.md)
- [Przewodnik programowania w języku C#](../../programming-guide/index.md)
- [Słowa kluczowe języka C#](index.md)
- [Instrukcje try, throw i catch (C++)](/cpp/cpp/try-throw-and-catch-statements-cpp)
- [throw](throw.md)
- [try-catch](try-catch.md)
- [Instrukcje: Jawne zgłaszanie wyjątków](../../../standard/exceptions/how-to-explicitly-throw-exceptions.md)
