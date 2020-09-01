---
description: Return — Instrukcja (odwołanie w C#)
title: Return — Instrukcja (odwołanie w C#)
ms.date: 07/20/2015
f1_keywords:
- return_CSharpKeyword
- return
helpviewer_keywords:
- return statement [C#]
- return keyword [C#]
ms.assetid: 6da6e152-5b58-4448-8f3f-470dd0617ecd
ms.openlocfilehash: 486db846304c0972942ff58f3d5b276083681abe
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89137007"
---
# <a name="return-c-reference"></a>return (odwołanie w C#)

`return`Instrukcja kończy wykonywanie metody, w której występuje i zwraca kontrolę do metody wywołującej. Może również zwrócić wartość opcjonalną. Jeśli metoda jest `void` typem, `return` instrukcja może zostać pominięta.

 Jeśli instrukcja return znajduje się wewnątrz `try` bloku, `finally` blok, jeśli taki istnieje, zostanie wykonany przed powracaniem kontroli do metody wywołującej.

## <a name="example"></a>Przykład

 W poniższym przykładzie metoda `CalculateArea()` zwraca zmienną lokalną `area` jako `double` wartość.

[!code-csharp[csrefKeywordsJump#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#6)]  

## <a name="c-language-specification"></a>specyfikacja języka C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Zobacz też

- [Odwołanie w C#](../index.md)
- [Przewodnik programowania w języku C#](../../programming-guide/index.md)
- [Słowa kluczowe języka C#](index.md)
- [Return — Instrukcja](/cpp/cpp/return-statement-cpp)
