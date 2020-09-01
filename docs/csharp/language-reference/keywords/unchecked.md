---
description: unchecked — odwołanie w C#
title: unchecked — odwołanie w C#
ms.date: 07/20/2015
f1_keywords:
- unchecked_CSharpKeyword
- unchecked
helpviewer_keywords:
- unchecked keyword [C#]
ms.assetid: 0c021f7c-923f-4b3d-a58f-55336f5ac27e
ms.openlocfilehash: bb66639e3657b247b9ebcad1594daf1f57a5c76b
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89141988"
---
# <a name="unchecked-c-reference"></a>unchecked (odwołanie w C#)

`unchecked`Słowo kluczowe jest używane do pomijania sprawdzania przepełnienia dla operacji arytmetycznych i konwersji typu całkowitego.

W niesprawdzonym kontekście, jeśli wyrażenie generuje wartość spoza zakresu typu docelowego, przepełnienie nie jest oflagowane. Na przykład, ponieważ obliczenia w poniższym przykładzie są wykonywane w `unchecked` bloku lub wyrażeniu, fakt, że wynik jest za duży dla liczby całkowitej, jest ignorowany i `int1` ma przypisaną wartość-2 147 483 639.

[!code-csharp[csrefKeywordsChecked#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsChecked/CS/csrefKeywordsChecked.cs#5)]

Jeśli `unchecked` środowisko zostanie usunięte, wystąpi błąd kompilacji. Przepełnienie można wykryć w czasie kompilacji, ponieważ wszystkie warunki wyrażenia są stałymi.

Wyrażenia zawierające warunki niestałe są domyślnie niezaznaczone w czasie kompilacji i w czasie wykonywania. Zobacz [zaewidencjonowano](checked.md) , aby uzyskać informacje na temat włączania sprawdzonego środowiska.

Ze względu na to, że sprawdzanie przepełnienia jest czasochłonne, użycie niesprawdzonego kodu w sytuacjach, gdy nie ma żadnych niebezpieczeństwa przepełnienia może zwiększyć wydajność. Jeśli jednak przepełnienie jest możliwe, należy użyć zaznaczonego środowiska.

## <a name="example"></a>Przykład

Ten przykład pokazuje, jak używać `unchecked` słowa kluczowego.

[!code-csharp[csrefKeywordsChecked#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsChecked/CS/csrefKeywordsChecked.cs#2)]

## <a name="c-language-specification"></a>specyfikacja języka C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Zobacz też

- [Odwołanie w C#](../index.md)
- [Przewodnik programowania w języku C#](../../programming-guide/index.md)
- [Słowa kluczowe języka C#](index.md)
- [checked i unchecked](checked-and-unchecked.md)
- [dane](checked.md)
