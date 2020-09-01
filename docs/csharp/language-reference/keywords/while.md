---
description: Informacje o czasie wykonywania w języku C#
title: Informacje o czasie wykonywania w języku C#
ms.date: 05/28/2018
f1_keywords:
- while_CSharpKeyword
- while
helpviewer_keywords:
- while keyword [C#]
ms.assetid: 72a0765c-6852-4aca-b327-4a11cb7f5c59
ms.openlocfilehash: 97299f9ac6f2cdd6bbddf831b3ee2ad711935fbe
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89141871"
---
# <a name="while-c-reference"></a>while (odwołanie w C#)

`while`Instrukcja wykonuje instrukcję lub blok instrukcji, gdy określone wyrażenie logiczne zwraca wartość `true` . Ponieważ to wyrażenie jest oceniane przed każdym wykonaniem pętli, `while` Pętla wykonuje zero lub więcej razy. Różni się to od [pętli do](do.md) , która wykonuje jeden lub więcej razy.

W dowolnym momencie w `while` bloku instrukcji można przerwać pętlę przy użyciu instrukcji [Break](break.md) .

Możesz przejść bezpośrednio do oceny `while` wyrażenia przy użyciu instrukcji [Continue](continue.md) . Jeśli wyrażenie zwróci wartość `true` , wykonywanie jest kontynuowane na pierwszej instrukcji w pętli. W przeciwnym razie wykonywanie jest kontynuowane po pierwszej instrukcji po pętli.

Możesz również wyjść z `while` pętli przez instrukcje [goto](goto.md), [Return](return.md)lub [throw](throw.md) .

## <a name="example"></a>Przykład

W poniższym przykładzie pokazano sposób użycia `while` instrukcji. Wybierz pozycję **Uruchom** , aby uruchomić przykładowy kod. Następnie można zmodyfikować kod i uruchomić go ponownie.

[!code-csharp-interactive[while loop example](snippets/IterationKeywordsExamples.cs#3)]

## <a name="c-language-specification"></a>specyfikacja języka C#

Aby uzyskać więcej informacji, zobacz sekcję [While instrukcji](~/_csharplang/spec/statements.md#the-while-statement) w [specyfikacji języka C#](/dotnet/csharp/language-reference/language-specification/introduction).

## <a name="see-also"></a>Zobacz też

- [Odwołanie w C#](../index.md)
- [Przewodnik programowania w języku C#](../../programming-guide/index.md)
- [Słowa kluczowe języka C#](index.md)
- [do — instrukcja](do.md)
