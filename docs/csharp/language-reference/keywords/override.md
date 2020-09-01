---
description: override — modyfikator — odwołanie w C#
title: override — modyfikator — odwołanie w C#
ms.date: 07/20/2015
f1_keywords:
- override
- override_CSharpKeyword
helpviewer_keywords:
- override keyword [C#]
ms.assetid: dd1907a8-acf8-46d3-80b9-c2ca4febada8
ms.openlocfilehash: 51ca806310214981b7ff24a796fe078d902dca4d
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89134462"
---
# <a name="override-c-reference"></a>override (odwołanie w C#)

`override`Modyfikator jest wymagany, aby zwiększyć lub zmodyfikować abstrakcyjną lub wirtualną implementację dziedziczonej metody, właściwości, indeksatora lub zdarzenia.

## <a name="example"></a>Przykład

W tym przykładzie `Square` Klasa musi udostępniać zastąpioną implementację, `GetArea` ponieważ `GetArea` jest dziedziczona z klasy abstrakcyjnej `Shape` :

[!code-csharp[csrefKeywordsModifiers#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#1)]

`override`Metoda zapewnia nową implementację elementu członkowskiego, który jest Dziedziczony z klasy bazowej. Metoda zastępowana przez `override` deklarację jest znana jako zastąpiona metoda podstawowa. Zastąpiona metoda bazowa musi mieć taką samą sygnaturę jak `override` Metoda. Aby uzyskać informacje na temat dziedziczenia, zobacz [dziedziczenie](../../programming-guide/classes-and-structs/inheritance.md).

Nie można zastąpić metody niewirtualnej lub statycznej. Zastąpiona metoda bazowa musi mieć wartość `virtual` , `abstract` , lub `override` .

`override`Deklaracja nie może zmienić dostępności `virtual` metody. Obie `override` metody i `virtual` metody muszą mieć ten sam [modyfikator poziomu dostępu](access-modifiers.md).

Nie można użyć `new` `static` modyfikatora, lub, `virtual` Aby zmodyfikować `override` metodę.

Zastępowanie deklaracji właściwości musi określać dokładnie ten sam modyfikator dostępu, typ i nazwę, co Właściwość dziedziczona, a zastąpiona właściwość musi mieć wartość `virtual` , `abstract` lub `override` .

Aby uzyskać więcej informacji na temat sposobu używania `override` słowa kluczowego, zobacz [przechowywanie wersji z przesłonięciami i nowymi słowami kluczowymi](../../programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) i [wiedzą, kiedy używać przesłonięć i nowych słów kluczowych](../../programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).

## <a name="example"></a>Przykład

W tym przykładzie zdefiniowano klasę bazową o nazwie `Employee` i klasę pochodną o nazwie `SalesEmployee` . `SalesEmployee`Klasa zawiera dodatkowe pole, `salesbonus` i zastępuje metodę, `CalculatePay` Aby można było ją uwzględnić.

[!code-csharp[csrefKeywordsModifiers#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#9)]

## <a name="c-language-specification"></a>specyfikacja języka C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Zobacz też

- [Odwołanie w C#](../index.md)
- [Przewodnik programowania w języku C#](../../programming-guide/index.md)
- [Dziedziczenie](../../programming-guide/classes-and-structs/inheritance.md)
- [Słowa kluczowe języka C#](index.md)
- [Modyfikatory](index.md)
- [streszczeń](abstract.md)
- [virtual](virtual.md)
- [New (modyfikator)](new-modifier.md)
- [Polimorfizm](../../programming-guide/classes-and-structs/polymorphism.md)
