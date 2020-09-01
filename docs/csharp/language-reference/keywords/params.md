---
description: params — słowo kluczowe dla tablic parametrów — odwołanie w C#
title: params — słowo kluczowe dla tablic parametrów — odwołanie w C#
ms.date: 07/20/2015
f1_keywords:
- params_CSharpKeyword
- params
helpviewer_keywords:
- parameters [C#], params
- params keyword [C#]
- parameter array
ms.assetid: 1690815e-b52b-4967-8380-5780aff08012
ms.openlocfilehash: a2726c725508cd297001aaabddeff414704d1115
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89134474"
---
# <a name="params-c-reference"></a>params (odwołanie w C#)

Za pomocą `params` słowa kluczowego, można określić [parametr metody](method-parameters.md) , który przyjmuje zmienną liczbę argumentów. Typ parametru musi być tablicą jednowymiarową.

Żadne dodatkowe parametry nie są dozwolone po `params` słowie kluczowym w deklaracji metody i tylko jedno `params` słowo kluczowe jest dozwolone w deklaracji metody.

Jeśli zadeklarowany typ `params` parametru nie jest tablicą jednowymiarową, wystąpi błąd kompilatora [CS0225](../../misc/cs0225.md) .

Po wywołaniu metody z `params` parametrem można przekazać:

- Rozdzielana przecinkami lista argumentów typu elementów tablicy.
- Tablica argumentów określonego typu.
- Brak argumentów. Jeśli nie wyślesz żadnych argumentów, długość `params` listy wynosi zero.

## <a name="example"></a>Przykład

Poniższy przykład ilustruje różne sposoby wysyłania argumentów do `params` parametru.

[!code-csharp[csrefKeywordsMethodParams#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsMethodParams/CS/csrefKeywordsMethodParams.cs#5)]

## <a name="c-language-specification"></a>specyfikacja języka C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Zobacz też

- [Odwołanie w C#](../index.md)
- [Przewodnik programowania w języku C#](../../programming-guide/index.md)
- [Słowa kluczowe języka C#](index.md)
- [Parametry metody](method-parameters.md)
