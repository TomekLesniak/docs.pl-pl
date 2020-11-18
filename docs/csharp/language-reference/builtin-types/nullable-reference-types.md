---
title: Typy odwołań do wartości null — odwołanie w C#
description: Dowiedz się więcej o typach referencyjnych języka C# do dopuszczających wartość null
ms.date: 04/06/2020
ms.openlocfilehash: d961af9ba3b4776e6b4ec3eeea5392fb0d0394ce
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94822428"
---
# <a name="nullable-reference-types-c-reference"></a>Typy odwołań dopuszczających wartość null (odwołanie w C#)

> [!NOTE]
> Ten artykuł dotyczy typów referencyjnych dopuszczających wartość null. Można również zadeklarować [wartości null dla typów](nullable-value-types.md).

Typy odwołań dopuszczających wartość null są dostępne począwszy od języka C# 8,0, w kodzie, który został wybrał w *kontekście obsługującym wartość null*. Typy odwołań dopuszczających wartość null, ostrzeżenia analityczne o wartości null i [Operatory null-łagodniejszej](../operators/null-forgiving.md) są opcjonalnymi funkcjami języka. Wszystkie są domyślnie wyłączone. *Kontekst dopuszczający wartość null* jest kontrolowany na poziomie projektu przy użyciu ustawień kompilacji lub kodu przy użyciu pragm.

 W kontekście dopuszczającym wartość null:

- Zmienna typu referencyjnego `T` musi zostać zainicjowana przy użyciu wartości innej niż null i nigdy nie może zostać przypisana wartość, która może być `null` .
- Zmienna typu referencyjnego `T?` może zostać zainicjowana z `null` lub przypisana `null` , ale jest wymagana do sprawdzenia `null` przed cofnięciem odwołania.
- Zmienna `m` typu `T?` jest traktowana jako inna niż null w przypadku zastosowania operatora null-łagodniejszej, jak w `m!` .

Różnice między typem referencyjnym niedopuszczający wartości null `T` a typem referencyjnym dopuszczającym wartość null `T?` są wymuszane przez interpretację przez kompilator powyższych reguł. Zmienna typu `T` i zmienna typu `T?` są reprezentowane przez ten sam typ .NET. Poniższy przykład deklaruje ciąg niedopuszczający wartości null i ciąg dopuszczający wartość null, a następnie używa operatora null-łagodniejszej do przypisywania wartości do ciągu niedopuszczający wartości null:

:::code language="csharp" source="snippets/shared/NullableReferenceTypes.cs" id="SnippetCoreSyntax":::

Zmienne `notNull` i `nullable` są reprezentowane przez <xref:System.String> Typ. Ponieważ typy niedopuszczające wartości null i dopuszczające wartość null są przechowywane jako ten sam typ, istnieje kilka lokalizacji, w których użycie typu odwołania do wartości null jest niedozwolone. Ogólnie rzecz biorąc typ referencyjny dopuszczający wartość null nie może być używany jako klasa bazowa ani zaimplementowany interfejs. Nie można użyć typu referencyjnego dopuszczającego wartość null w żadnym wyrażeniu do tworzenia obiektów lub testowania typu. Typ referencyjny dopuszczający wartość null nie może być typem wyrażenia dostępu do składowej. Następujące przykłady przedstawiają te konstrukcje:

```csharp
public MyClass : System.Object? // not allowed
{
}

var nullEmpty = System.String?.Empty; // Not allowed
var maybeObject = new object?(); // Not allowed
try
{
    if (thing is string? nullableString) // not allowed
        Console.WriteLine(nullableString);
} catch (Exception? e) // Not Allowed
{
    Console.WriteLine("error");
}
```

## <a name="nullable-references-and-static-analysis"></a>Odwołania do wartości null i analizy statycznej

Przykłady w poprzedniej sekcji ilustrują charakter typów referencyjnych dopuszczających wartość null. Typy referencyjne dopuszczające wartość null nie są nowymi typami klas, ale zamiast adnotacji dla istniejących typów odwołań. Kompilator używa tych adnotacji, aby znaleźć potencjalne błędy odwołania o wartości null w kodzie. Nie istnieje różnica czasu wykonywania między typem referencyjnym niedopuszczanym do wartości null i typem referencyjnym dopuszczającym wartość null. Kompilator nie dodaje żadnego sprawdzenia dla typów referencyjnych, które nie dopuszcza wartości null. Korzyści są w analizie w czasie kompilacji. Kompilator generuje ostrzeżenia, które ułatwiają znajdowanie i naprawianie potencjalnych błędów o wartości null w kodzie. Zadeklarujesz swój cel, a kompilator ostrzega o tym, gdy kod narusza ten cel.

W kontekście obsługującym wartość null kompilator wykonuje statyczną analizę dla zmiennych dowolnego typu referencyjnego, zarówno wartości null, jak i niedopuszczających wartości null. Kompilator śledzi stan wartości null dla każdej zmiennej odwołania jako *nie null* lub *może mieć wartość null*. Domyślny stan odwołania niedopuszczający wartości null jest *inny niż null*. Domyślny stan odwołania do wartości null *może mieć wartość null*.

Typy odwołań niedopuszczających wartości null powinny zawsze być bezpieczne, aby można było usunąć odwołanie, ponieważ ich stan zerowy *nie ma wartości null*. Aby wymusić tę regułę, kompilator wystawia ostrzeżenia, jeśli typ referencyjny niedopuszczający wartości null nie został zainicjowany do wartości innej niż null. Zmienne lokalne muszą być przypisane, gdy są one zadeklarowane. Każdy Konstruktor musi przypisywać każde pole, w jego treści, Konstruktor wywoływany lub przy użyciu inicjatora pola. Kompilator wystawia ostrzeżenia, jeśli odwołanie niedopuszczające wartości null jest przypisane do odwołania, którego stan *może mieć wartość null*. Jednak ze względu na to, że odwołanie niedopuszczające wartości null *nie ma wartości null*, nie są wyświetlane żadne ostrzeżenia, gdy te zmienne zostały cofnięte.

Typy odwołań dopuszczających wartość null mogą być zainicjowane lub przypisane do `null` . Dlatego analiza statyczna musi określać, że zmienna *nie ma wartości null* , zanim zostanie wykorzystana. Jeśli odwołanie dopuszczające wartość null jest określone jako mające *wartość null*, nie można go przypisać do zmiennej odwołania, która nie dopuszcza wartości null. W poniższej klasie przedstawiono przykłady tych ostrzeżeń:

:::code language="csharp" source="snippets/shared/NullableReferenceTypes.cs" id="SnippetClassWithNullable":::

Poniższy fragment kodu pokazuje, gdzie kompilator emituje ostrzeżenia podczas korzystania z tej klasy:

:::code language="csharp" source="snippets/shared/NullableReferenceTypes.cs" id="SnippetLocalWarnings":::

Powyższe przykłady przedstawiają analizę statyczną kompilatora w celu określenia stanu null zmiennych odwołania. Kompilator stosuje reguły języka do sprawdzania wartości null i przypisań, aby poinformować o analizie.  Kompilator nie może wykonać założeń dotyczących semantyki metod lub właściwości. Jeśli wywołasz metody, które wykonują sprawdzenia wartości null, kompilator nie może znać tych metod wpływ na stan null zmiennej. Istnieje wiele atrybutów, które można dodać do interfejsów API, aby poinformować kompilator o semantyki argumentów i zwracanych wartości. Te atrybuty zostały zastosowane do wielu popularnych interfejsów API w bibliotekach programu .NET Core. Na przykład program <xref:System.String.IsNullOrEmpty%2A> został zaktualizowany, a kompilator prawidłowo interpretuje tę metodę jako sprawdzenie wartości null. Aby uzyskać więcej informacji o atrybutach, które mają zastosowanie do statycznej analizy stanu o wartości null, zobacz artykuł dotyczący [atrybutów dopuszczających wartość null](../attributes/nullable-analysis.md).

## <a name="setting-the-nullable-context"></a>Ustawianie kontekstu dopuszczającego wartość null

Istnieją dwa sposoby sterowania kontekstem dopuszczania wartości null. Na poziomie projektu można dodać `<Nullable>enable</Nullable>` ustawienie projektu. W jednym pliku źródłowym języka C# można dodać `#nullable enable` pragmę, aby włączyć kontekst dopuszczający wartość null. Zapoznaj się z artykułem dotyczącym [ustawiania strategii dopuszczania wartości null](../../nullable-migration-strategies.md).

## <a name="c-language-specification"></a>specyfikacja języka C#

Aby uzyskać więcej informacji, zobacz następujące propozycje dotyczące [specyfikacji języka C#](~/_csharplang/spec/introduction.md):

- [Typy referencyjne dopuszczające wartość null](~/_csharplang/proposals/csharp-8.0/nullable-reference-types.md)
- [Specyfikacja typu referencyjnego dopuszczająca wartość null](~/_csharplang/proposals/csharp-9.0/nullable-reference-types-specification.md)

## <a name="see-also"></a>Zobacz także

- [Dokumentacja języka C#](../index.md)
- [Typy wartości dopuszczające wartość null](nullable-value-types.md)
