---
title: Funkcje C# obsługujące LINQ
description: Dowiedz się więcej na temat funkcji języka C# do użycia z kwerendami LINQ i w innych kontekstach. Te konstrukcje języka zostały wprowadzone w języku C# 3,0.
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ [C#], features supporting LINQ
ms.assetid: 524b0078-ebfd-45a7-b390-f2ceb9d84797
ms.openlocfilehash: 13254c69193e04ffcf11e3e23f1deb460063a6c1
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/11/2020
ms.locfileid: "88063695"
---
# <a name="c-features-that-support-linq"></a>Funkcje C# obsługujące LINQ

W poniższej sekcji wprowadzono nowe konstrukcje języka wprowadzone w języku C# 3,0. Chociaż te nowe funkcje są używane do stopnia z zapytania LINQ, nie są ograniczone do LINQ i mogą być używane w dowolnym kontekście, w którym są użyteczne.

## <a name="query-expressions"></a>Wyrażenia kwerend

Wyrażenia zapytań używają składni deklaracyjnej podobnej do SQL lub XQuery w celu wykonywania zapytań na kolekcjach IEnumerable. W czasie kompilacji Składnia zapytania jest konwertowana na wywołania metody do implementacji dostawcy LINQ standardowych metod rozszerzenia operatora zapytania. Aplikacje kontrolują standardowe operatory zapytań, które znajdują się w zakresie przez określenie odpowiedniej przestrzeni nazw z `using` dyrektywą. Następujące wyrażenie zapytania pobiera tablicę ciągów, grupuje je według pierwszego znaku w ciągu i porządkuje grupy.

```csharp
var query = from str in stringArray
            group str by str[0] into stringGroup
            orderby stringGroup.Key
            select stringGroup;
```

Aby uzyskać więcej informacji, zobacz [wyrażenia zapytań LINQ](../../../linq/index.md).

## <a name="implicitly-typed-variables-var"></a>Niejawnie wpisane zmienne (var)

Zamiast jawnie określić typ podczas deklarowania i inicjowania zmiennej, można użyć modyfikatora [var](../../../language-reference/keywords/var.md) , aby nakazać kompilatorowi wywnioskowanie i przypisanie typu, jak pokazano poniżej:

```csharp
var number = 5;
var name = "Virginia";
var query = from str in stringArray
            where str[0] == 'm'
            select str;
```

Zmienne zadeklarowane jako `var` są równie silnie wpisywane jako zmienne, których typ określa się jawnie. Użycie systemu `var` umożliwia tworzenie typów anonimowych, ale może być używane tylko dla zmiennych lokalnych. Tablice mogą być również deklarowane przy użyciu niejawnego wpisywania.

Aby uzyskać więcej informacji, zobacz [niejawnie wpisane zmienne lokalne](../../classes-and-structs/implicitly-typed-local-variables.md).

## <a name="object-and-collection-initializers"></a>Inicjatory obiektów i kolekcji

Inicjatory obiektów i kolekcji umożliwiają inicjowanie obiektów bez jawnego wywoływania konstruktora dla obiektu. Inicjatory są zwykle używane w wyrażeniach zapytań, gdy projektują dane źródłowe do nowego typu danych. Przy założeniu klasy o nazwie `Customer` z publiczną `Name` i `Phone` właściwością inicjatora obiektów można używać tak jak w poniższym kodzie:

```csharp
var cust = new Customer { Name = "Mike", Phone = "555-1212" };
```

Kontynuując pracę z naszą `Customer` klasą, Załóżmy, że istnieje źródło danych o nazwie `IncomingOrders` i że dla każdego zamówienia z dużą, chcemy `OrderSize` utworzyć nową wartość `Customer` na podstawie tej kolejności. Zapytanie LINQ można wykonać w tym źródle danych i użyć inicjalizacji obiektu do wypełnienia kolekcji:

```csharp
var newLargeOrderCustomers = from o in IncomingOrders
                            where o.OrderSize > 5
                            select new Customer { Name = o.Name, Phone = o.Phone };
```

Źródło danych może mieć więcej właściwości znajdujących się pod okapem niż `Customer` Klasa, taka jak `OrderSize` , ale z inicjalizacją obiektu, dane zwrócone z zapytania są Molded do żądanego typu danych. wybieramy dane, które są istotne dla naszej klasy. W związku z tym mamy teraz `IEnumerable` wypełnioną nową, `Customer` pożądaną nowością. Powyższe dane można także napisać w składni metody LINQ:

```csharp
var newLargeOrderCustomers = IncomingOrders.Where(x => x.OrderSize > 5).Select(y => new Customer { Name = y.Name, Phone = y.Phone });
```

Aby uzyskać więcej informacji, zobacz:

- [Inicjatory obiektów i kolekcji](../../classes-and-structs/object-and-collection-initializers.md)

- [Składnia wyrażeń dla standardowych operatorów zapytań](./query-expression-syntax-for-standard-query-operators.md)

## <a name="anonymous-types"></a>Typy anonimowe

Typ anonimowy jest konstruowany przez kompilator, a nazwa typu jest dostępna tylko dla kompilatora. Typy anonimowe umożliwiają wygodne grupowanie zestawu właściwości w wyniku zapytania, bez konieczności definiowania oddzielnego nazwanego typu. Typy anonimowe są inicjowane za pomocą nowego wyrażenia i inicjatora obiektów, jak pokazano poniżej:

```csharp
select new {name = cust.Name, phone = cust.Phone};
```

Aby uzyskać więcej informacji, zobacz [Typy anonimowe](../../classes-and-structs/anonymous-types.md).

## <a name="extension-methods"></a>Metody rozszerzeń

Metoda rozszerzenia to metoda statyczna, która może być skojarzona z typem, tak aby można ją było wywołać tak, jakby była metodą wystąpienia w typie. Ta funkcja umożliwia, w efekcie, "dodać" nowe metody do istniejących typów bez ich faktycznego modyfikowania. Standardowe operatory zapytań to zestaw metod rozszerzających, które udostępniają funkcje zapytań LINQ dla dowolnego typu, który implementuje <xref:System.Collections.Generic.IEnumerable%601> .

Aby uzyskać więcej informacji, zobacz [metody rozszerzenia](../../classes-and-structs/extension-methods.md).

## <a name="lambda-expressions"></a>Wyrażenia lambda

Wyrażenie lambda jest funkcją wbudowaną, która używa operatora => do oddzielania parametrów wejściowych od treści funkcji i może być konwertowana w czasie kompilacji do delegata lub drzewa wyrażenia. W programowaniu LINQ, można napotkać wyrażenia lambda podczas wykonywania wywołań metody bezpośredniej do standardowych operatorów zapytań.

Aby uzyskać więcej informacji, zobacz:

- [Funkcje anonimowe](../../statements-expressions-operators/anonymous-functions.md)

- [Wyrażenia lambda](../../../language-reference/operators/lambda-expressions.md)

- [Drzewa wyrażeń (C#)](../expression-trees/index.md)

## <a name="see-also"></a>Zobacz także

- [Language-Integrated Query (LINQ) (C#)](./index.md)
