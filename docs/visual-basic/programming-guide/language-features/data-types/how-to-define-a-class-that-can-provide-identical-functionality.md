---
title: 'Instrukcje: Definiowanie klasy, która może zapewnić identyczną funkcjonalność różnych typów danych'
ms.date: 07/20/2015
helpviewer_keywords:
- data type arguments [Visual Basic], using
- type parameters [Visual Basic], defining
- data type arguments [Visual Basic], defining
- arguments [Visual Basic], data types
- Of keyword [Visual Basic], using
- constraints, Visual Basic generic types
- generic parameters
- data type parameters
- data type parameters [Visual Basic], using
- generics [Visual Basic], defining classes with type parameters
- data types [Visual Basic], as parameters
- data types [Visual Basic], as arguments
- parameters [Visual Basic], type
- type arguments
- types [Visual Basic], generic
- parameters [Visual Basic], generic
- type parameters
- data type arguments
- parameters [Visual Basic], data type
- generics [Visual Basic], defining generic types
- data type parameters [Visual Basic], defining
- type arguments [Visual Basic], defining
- arguments [Visual Basic], type
ms.assetid: a914adf8-e68f-4819-a6b1-200d1cf1c21c
ms.openlocfilehash: 268daf333dc5463e5436304cec188a9e6d477166
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077127"
---
# <a name="how-to-define-a-class-that-can-provide-identical-functionality-on-different-data-types-visual-basic"></a>Porady: definiowanie klasy, która może zapewnić identyczną funkcjonalność różnych typów danych (Visual Basic)

Można zdefiniować klasę, z której można tworzyć obiekty, które zapewniają identyczną funkcjonalność dla różnych typów danych. W tym celu należy określić co najmniej jeden *parametr typu* w definicji. Klasa może następnie służyć jako szablon dla obiektów, które używają różnych typów danych. Klasa zdefiniowana w ten sposób jest nazywana *klasą generyczną*.  
  
 Zaletą zdefiniowania klasy generycznej jest to, że definiujesz ją tylko raz, a Twój kod może używać go do tworzenia wielu obiektów, które używają szerokiej gamy typów danych. Skutkuje to lepszą wydajnością niż Definiowanie klasy z `Object` typem.  
  
 Oprócz klas można także definiować struktury ogólne, interfejsy, procedury i Delegaty oraz korzystać z nich.  
  
### <a name="to-define-a-class-with-a-type-parameter"></a>Aby zdefiniować klasę z parametrem typu  
  
1. Zdefiniuj klasę w normalny sposób.  
  
2. Dodaj `(Of` *typeparameter* `)` natychmiast po nazwie klasy, aby określić parametr typu.  
  
3. Jeśli masz więcej niż jeden parametr typu, Utwórz listę rozdzieloną przecinkami wewnątrz nawiasów. Nie powtarzaj `Of` słowa kluczowego.  
  
4. Jeśli kod wykonuje operacje na parametrze typu innym niż proste przypisanie, należy użyć tego parametru typu z `As` klauzulą, aby dodać jedno lub więcej *ograniczeń*. Ograniczenie gwarantuje, że typ dostarczony dla tego parametru typu spełnia wymagania, takie jak następujące:  
  
    - Obsługuje operacje, takie jak `>` , czy kod wykonuje  
  
    - Obsługuje składową, taką jak metoda, do której uzyskuje dostęp kod  
  
    - Uwidacznia Konstruktor bez parametrów  
  
     Jeśli nie określisz żadnych ograniczeń, jedyną operacją i elementami członkowskimi, które mogą być używane przez dany kod, są te obsługiwane przez [Typ danych Object](../../../language-reference/data-types/object-data-type.md). Aby uzyskać więcej informacji, zobacz [Typ listy](../../../language-reference/statements/type-list.md).  
  
5. Zidentyfikuj każdy element członkowski klasy, który ma zostać zadeklarowany przy użyciu dostarczonego typu, i Zadeklaruj go `As` `typeparameter` . Dotyczy to magazynu wewnętrznego, parametrów procedury i zwracanych wartości.  
  
6. Upewnij się, że kod używa tylko operacji i metod, które są obsługiwane przez każdy typ danych, który może dostarczyć `itemType` .  
  
     W poniższym przykładzie zdefiniowano klasę, która zarządza prostą listą. Zawiera listę w tablicy wewnętrznej `items` , a kod przy użyciu może deklarować typ danych elementów listy. Konstruktor sparametryzowany umożliwia użycie kodu w celu ustawienia górnej granicy `items` , a Konstruktor bez parametrów ustawia tę wartość na 9 (łącznie 10 elementów).  
  
     [!code-vb[VbVbalrDataTypes#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#7)]  
  
     Można zadeklarować klasę z `simpleList` do przechowywania listy `Integer` wartości, innej klasy do przechowywania listy `String` wartości, a druga do przechowywania `Date` wartości. Z wyjątkiem typu danych członków listy obiekty utworzone na podstawie wszystkich tych klas zachowują się identycznie.  
  
     Argument typu, który jest używany przez kod, `itemType` może być typem wewnętrznym, takim jak `Boolean` lub `Double` , strukturą, wyliczeniem lub dowolnym typem klasy, z uwzględnieniem aplikacji zdefiniowanej przez aplikację.  
  
     Możesz przetestować klasę `simpleList` przy użyciu następującego kodu.  
  
     [!code-vb[VbVbalrDataTypes#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#8)]  
  
## <a name="see-also"></a>Zobacz także

- [Typy danych](index.md)
- [Typy ogólne w Visual Basic](generic-types.md)
- [Niezależność od języka i składniki niezależne od języka](../../../../standard/language-independence-and-language-independent-components.md)
- [Z](../../../language-reference/statements/of-clause.md)
- [Lista typów](../../../language-reference/statements/type-list.md)
- [Instrukcje: Używanie klasy ogólnej](how-to-use-a-generic-class.md)
- [Object — typ danych](../../../language-reference/data-types/object-data-type.md)
