---
description: Informacje o instrukcji try-catch-finally-C#
title: Informacje o instrukcji try-catch-finally-C#
ms.date: 07/20/2015
f1_keywords:
- catch-finally_CSharpKeyword
- catch-finally
helpviewer_keywords:
- finally blocks [C#]
- try-catch statement [C#]
ms.assetid: a1b443b0-ff7a-43ab-b835-0cc9bfbd15ca
ms.openlocfilehash: 6e85330e12c53e0728ef671530709748090ebe02
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89142014"
---
# <a name="try-catch-finally-c-reference"></a>try-catch-finally (odwołanie w C#)

Typowym zastosowaniem `catch` i `finally` razem jest uzyskanie zasobów i korzystanie z nich w `try` bloku, zaradzenie sobie z wyjątkowymi okolicznościami w `catch` bloku i zwolnienie zasobów w `finally` bloku.

 Aby uzyskać więcej informacji i przykładów dotyczących ponownego zgłaszania wyjątków, zobacz [try-catch](try-catch.md) i [wyrzucanie wyjątków](../../../standard/exceptions/index.md). Aby uzyskać więcej informacji na temat `finally` bloku, zobacz [try-finally](try-finally.md).

## <a name="example"></a>Przykład

[!code-csharp[csrefKeywordsExceptions#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsExceptions/CS/csrefKeywordsExceptions.cs#1)]  

## <a name="c-language-specification"></a>specyfikacja języka C#

Aby uzyskać więcej informacji, zobacz sekcję [try instrukcji](~/_csharplang/spec/statements.md#the-try-statement) w [specyfikacji języka C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Zobacz też

- [Odwołanie w C#](../index.md)
- [Przewodnik programowania w języku C#](../../programming-guide/index.md)
- [Słowa kluczowe języka C#](index.md)
- [Instrukcje try, throw i catch (C++)](/cpp/cpp/try-throw-and-catch-statements-cpp)
- [throw](throw.md)
- [Instrukcje: Jawne zgłaszanie wyjątków](../../../standard/exceptions/how-to-explicitly-throw-exceptions.md)
- [using, instrukcja](using-statement.md)
