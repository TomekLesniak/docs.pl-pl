---
description: Continue — instrukcja — odwołanie w C#
title: Continue — instrukcja — odwołanie w C#
ms.date: 07/20/2015
f1_keywords:
- continue_CSharpKeyword
- continue
helpviewer_keywords:
- continue keyword [C#]
ms.assetid: 8a5ac96f-f98a-4519-b32d-345847ed7be0
ms.openlocfilehash: 6c70934c3b861e1a1433e5c0b95bb32e9d717c53
ms.sourcegitcommit: eb7e87496f42361b1da98562dd75b516c9d58bbc
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/09/2020
ms.locfileid: "91877655"
---
# <a name="continue-c-reference"></a>continue (odwołanie w C#)

`continue`Instrukcja przekazuje formant do następnej iteracji otaczającej instrukcji [while](./while.md), [do](./do.md), [for](./for.md)lub [foreach](./foreach-in.md) , w której występuje.

## <a name="example"></a>Przykład

W tym przykładzie licznik jest zainicjowany do zliczenia z 1 do 10. Używając `continue` instrukcji w połączeniu z wyrażeniem `(i < 9)` , instrukcje między `continue` i końcem `for` treści są pomijane w iteracjach, gdzie `i` jest mniejsza niż 9. W ciągu ostatnich dwóch iteracji `for` pętli (gdzie i = = 9 i i = 10) `continue` instrukcja nie jest wykonywana, a wartość `i` jest drukowana w konsoli.

[!code-csharp[csrefKeywordsJump#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#3)]

## <a name="c-language-specification"></a>specyfikacja języka C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Zobacz też

- [Odwołanie w C#](../index.md)
- [Przewodnik programowania w języku C#](../../programming-guide/index.md)
- [Słowa kluczowe języka C#](./index.md)
- [Break, instrukcja](/cpp/cpp/break-statement-cpp)
