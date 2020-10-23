---
description: override — modyfikator — odwołanie w C#
title: override — modyfikator — odwołanie w C#
ms.date: 10/22/2020
f1_keywords:
- override
- override_CSharpKeyword
helpviewer_keywords:
- override keyword [C#]
ms.assetid: dd1907a8-acf8-46d3-80b9-c2ca4febada8
ms.openlocfilehash: 618200183348e68a4600adb9592a635f61f6a875
ms.sourcegitcommit: 98d20cb038669dca4a195eb39af37d22ea9d008e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/22/2020
ms.locfileid: "92434876"
---
# <a name="override-c-reference"></a>override (odwołanie w C#)

`override`Modyfikator jest wymagany, aby zwiększyć lub zmodyfikować abstrakcyjną lub wirtualną implementację dziedziczonej metody, właściwości, indeksatora lub zdarzenia.

W poniższym przykładzie `Square` Klasa musi udostępniać zastąpioną implementację, `GetArea` ponieważ `GetArea` jest dziedziczona z klasy abstrakcyjnej `Shape` :

[!code-csharp[csrefKeywordsModifiers#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#1)]

`override`Metoda zapewnia nową implementację metody dziedziczonej z klasy bazowej. Metoda zastępowana przez `override` deklarację jest znana jako zastąpiona metoda podstawowa. `override`Metoda musi mieć taką samą sygnaturę jak zastąpiona metoda podstawowa. Począwszy od języka C# 9,0, `override` metody obsługują typy zwrotne typu współvariant. W szczególności zwracany typ `override` metody może pochodzić od typu zwracanego odpowiadającej metody podstawowej. W języku C# 8,0 i starszych, zwracane typy `override` metody i zastąpiona metoda bazowa muszą być takie same.

Nie można zastąpić metody niewirtualnej lub statycznej. Zastąpiona metoda bazowa musi mieć wartość `virtual` , `abstract` , lub `override` .

`override`Deklaracja nie może zmienić dostępności `virtual` metody. Obie `override` metody i `virtual` metody muszą mieć ten sam [modyfikator poziomu dostępu](access-modifiers.md).

Nie można użyć `new` `static` modyfikatora, lub, `virtual` Aby zmodyfikować `override` metodę.

Zastępowanie deklaracji właściwości musi określać dokładnie ten sam modyfikator dostępu, typ i nazwę, co Właściwość dziedziczona. Począwszy od języka C# 9,0, zastępowanie właściwości tylko do odczytu obsługuje typy zwrotne typu współvariant. Zastąpiona właściwość musi mieć wartość `virtual` , `abstract` lub `override` .

Aby uzyskać więcej informacji na temat sposobu używania `override` słowa kluczowego, zobacz [przechowywanie wersji z przesłonięciami i nowymi słowami kluczowymi](../../programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) i [wiedzą, kiedy używać przesłonięć i nowych słów kluczowych](../../programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md). Aby uzyskać informacje na temat dziedziczenia, zobacz [dziedziczenie](../../programming-guide/classes-and-structs/inheritance.md).

## <a name="example"></a>Przykład

W tym przykładzie zdefiniowano klasę bazową o nazwie `Employee` i klasę pochodną o nazwie `SalesEmployee` . `SalesEmployee`Klasa zawiera dodatkowe pole, `salesbonus` i zastępuje metodę, `CalculatePay` Aby można było ją uwzględnić.

[!code-csharp[csrefKeywordsModifiers#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#9)]

## <a name="c-language-specification"></a>specyfikacja języka C#

Aby uzyskać więcej informacji, zobacz sekcję [zastępowanie metod](~/_csharplang/spec/classes.md#override-methods) w [specyfikacji języka C#](~/_csharplang/spec/introduction.md).

Aby uzyskać więcej informacji na temat typów zwracanych z niezmiennymi, zobacz [Uwaga dotycząca oferty funkcji](~/_csharplang/proposals/csharp-9.0/covariant-returns.md).

## <a name="see-also"></a>Zobacz też

- [Dokumentacja języka C#](../index.md)
- [Dziedziczenie](../../programming-guide/classes-and-structs/inheritance.md)
- [Słowa kluczowe języka C#](index.md)
- [Modyfikatory](index.md)
- [streszczeń](abstract.md)
- [virtual](virtual.md)
- [New (modyfikator)](new-modifier.md)
- [Polimorfizm](../../programming-guide/classes-and-structs/polymorphism.md)
