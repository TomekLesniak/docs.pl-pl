---
description: Class — słowo kluczowe — odwołanie w C#
title: Class — słowo kluczowe — odwołanie w C#
ms.date: 07/18/2017
f1_keywords:
- class_CSharpKeyword
- class
helpviewer_keywords:
- class keyword [C#]
ms.assetid: b95d8815-de18-4c3f-a8cc-a0a53bdf8690
ms.openlocfilehash: 67c9c4be55cce25edf9ecb84b257a8523f193bec
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89142118"
---
# <a name="class-c-reference"></a>class (odwołanie w C#)

Klasy są deklarowane za pomocą słowa kluczowego `class` , jak pokazano w następującym przykładzie:

```csharp
class TestClass
{
    // Methods, properties, fields, events, delegates
    // and nested classes go here.
}
```

## <a name="remarks"></a>Uwagi

W języku C# można używać tylko jednego dziedziczenia. Innymi słowy, Klasa może dziedziczyć implementację tylko z jednej klasy bazowej. Jednak Klasa może zaimplementować więcej niż jeden interfejs. W poniższej tabeli przedstawiono przykłady dziedziczenia klas i implementacji interfejsu:

|Dziedziczenie|Przykład|
|-----------------|-------------|
|Brak|`class ClassA { }`|
|Pojedynczy|`class DerivedClass : BaseClass { }`|
|Brak, implementuje dwa interfejsy|`class ImplClass : IFace1, IFace2 { }`|
|Single, implementuje jeden interfejs|`class ImplDerivedClass : BaseClass, IFace1 { }`|

Klasy zadeklarowane bezpośrednio w przestrzeni nazw, a nie zagnieżdżone w innych klasach, mogą być [publiczne](./public.md) lub [wewnętrzne](./internal.md). Klasy są `internal` domyślnie.

Elementy członkowskie klasy, w tym klasy zagnieżdżone, mogą być [publiczne](public.md), [chronione wewnętrznie](protected-internal.md), [chronione](protected.md), [wewnętrzne](internal.md), [prywatne](private.md)i [prywatne](private-protected.md). Elementy członkowskie są `private` domyślnie.

Aby uzyskać więcej informacji, zobacz [Modyfikatory dostępu](../../programming-guide/classes-and-structs/access-modifiers.md).

Można zadeklarować klasy ogólne z parametrami typu. Aby uzyskać więcej informacji, zobacz [klasy ogólne](../../programming-guide/generics/generic-classes.md).

Klasa może zawierać deklaracje następujących elementów członkowskich:

- [Konstruktory](../../programming-guide/classes-and-structs/constructors.md)

- [Stałe](../../programming-guide/classes-and-structs/constants.md)

- [Pola](../../programming-guide/classes-and-structs/fields.md)

- [Finalizatory](../../programming-guide/classes-and-structs/destructors.md)

- [Metody](../../programming-guide/classes-and-structs/methods.md)

- [Właściwości](../../programming-guide/classes-and-structs/properties.md)

- [Indeksatory](../../programming-guide/indexers/index.md)

- [Operatory](../operators/index.md)

- [Zdarzenia](../../programming-guide/events/index.md)

- [Delegaci](../../programming-guide/delegates/index.md)

- [Klasy](../../programming-guide/classes-and-structs/classes.md)

- [Interfejsy](../../programming-guide/interfaces/index.md)

- [Typy struktur](../builtin-types/struct.md)

- [Typów wyliczeniowych](../builtin-types/enum.md)

## <a name="example"></a>Przykład

Poniższy przykład demonstruje deklarowanie pól klasy, konstruktorów i metod. Ilustruje także tworzenie wystąpień obiektów i drukowanie danych wystąpienia. W tym przykładzie zadeklarowane są dwie klasy. Pierwsza klasa, `Child` , zawiera dwa prywatne pola ( `name` i `age` ), dwa konstruktory publiczne i jedną metodę publiczną. Druga klasa, `StringTest` ,,, jest używana do przechowywania `Main` .

[!code-csharp[csrefKeywordsTypes#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#5)]

## <a name="comments"></a>Komentarze

Zwróć uwagę, że w poprzednim przykładzie pola prywatne ( `name` i `age` ) można uzyskać dostęp tylko za pomocą metody publicznej `Child` klasy. Na przykład nie można wydrukować nazwy elementu podrzędnego z `Main` metody przy użyciu instrukcji podobnej do następujących:

```csharp
Console.Write(child1.name);   // Error
```

Uzyskiwanie dostępu do prywatnych elementów członkowskich `Child` z programu `Main` byłoby możliwe tylko wtedy `Main` , gdy należały do klasy.

Typy zadeklarowane wewnątrz klasy bez modyfikatora dostępu domyślnie do `private` , dlatego elementy członkowskie danych w tym przykładzie nadal byłyby, `private` Jeśli słowo kluczowe zostało usunięte.

Na koniec należy zauważyć, że dla obiektu utworzonego przy użyciu konstruktora bez parametrów ( `child3` ) `age` pole zostało domyślnie zainicjowane do zera.

## <a name="c-language-specification"></a>specyfikacja języka C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Zobacz też

- [Odwołanie w C#](../index.md)
- [Przewodnik programowania w języku C#](../../programming-guide/index.md)
- [Słowa kluczowe języka C#](./index.md)
- [Typy odwołań](./reference-types.md)
