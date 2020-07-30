---
title: Relacje typu w operacjach kwerend LINQ (C#)
description: Dowiedz się, jak typy zmiennych w zapytaniu LINQ odnoszą się do siebie nawzajem. Operacje zapytań LINQ są silnie wpisywane w źródle danych, w zapytaniu i w wykonaniu.
ms.date: 07/20/2015
helpviewer_keywords:
- inferring type information [LINQ in C#]
- data sources [LINQ in C#], type relationships
- queries [LINQ in C#], type relationships
- relationships [LINQ in C#]
- type relationships [LINQ in C#]
- variable relationships [LINQ in C#]
- type information inferred [LINQ in C#]
- data transformations [LINQ in C#]
- LINQ [C#], type relationships
ms.assetid: 99118938-d47c-4d7e-bb22-2657a9f95268
ms.openlocfilehash: 20f0b37a156e3b3f9c63f14cb83d678d26f685ee
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302285"
---
# <a name="type-relationships-in-linq-query-operations-c"></a>Relacje typu w operacjach kwerend LINQ (C#)
Aby efektywnie pisać zapytania, należy zrozumieć, jak typy zmiennych w kompletnej operacji zapytania wszystkie odnoszą się do siebie. Jeśli rozumiesz te relacje, łatwiej będzie comprehend przykłady LINQ i przykłady kodu w dokumentacji. Ponadto dowiesz się, co się dzieje w tle, gdy zmienne są wpisywane niejawnie przy użyciu `var` .  
  
 Operacje zapytań LINQ są jednoznacznie wpisywane w źródle danych, w samej kwerendzie i w wykonaniu zapytania. Typ zmiennych w zapytaniu musi być zgodny z typem elementów w źródle danych i typem zmiennej iteracji w `foreach` instrukcji. Takie silne wpisywanie gwarantuje, że błędy typu są przechwytywane w czasie kompilacji, gdy można je poprawić przed ich wystąpieniem przez użytkowników.  
  
 Aby przedstawić te relacje typu, większość przykładów, które są zgodne z użyciem jawnego wpisywania dla wszystkich zmiennych. W ostatnim przykładzie pokazano, jak te same zasady mają zastosowanie nawet w przypadku użycia niejawnego wpisywania przy użyciu funkcji [var](../../../language-reference/keywords/var.md).  
  
## <a name="queries-that-do-not-transform-the-source-data"></a>Zapytania, które nie przekształcają danych źródłowych  
 Na poniższej ilustracji przedstawiono LINQ to Objects operacji zapytania, która nie wykonuje transformacji danych. Źródło zawiera sekwencję ciągów, a dane wyjściowe zapytania są również sekwencją ciągów.  
  
 ![Diagram przedstawiający relację typów danych w zapytaniu LINQ.](./media/type-relationships-in-linq-query-operations/linq-query-data-type-relation.png)  
  
1. Argument typu źródła danych określa typ zmiennej zakresu.  
  
2. Typ wybranego obiektu określa typ zmiennej zapytania. Oto `name` ciąg. W związku z tym zmienna zapytania jest `IEnumerable<string>` .  
  
3. Zmienna zapytania jest powtarzana w `foreach` instrukcji. Ponieważ zmienna zapytania jest sekwencją ciągów, Zmienna iteracji jest również ciągiem.  
  
## <a name="queries-that-transform-the-source-data"></a>Zapytania, które przekształcają dane źródłowe  
 Na poniższej ilustracji przedstawiono [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] operację zapytania, która wykonuje prostą transformację danych. Zapytanie pobiera sekwencję `Customer` obiektów jako dane wejściowe i wybiera tylko `Name` Właściwość w wyniku. Ponieważ `Name` jest ciągiem, zapytanie tworzy sekwencję ciągów jako dane wyjściowe.  
  
 ![Diagram przedstawiający zapytanie, które przekształca typ danych.](./media/type-relationships-in-linq-query-operations/linq-query-transform-data-type.png)  
  
1. Argument typu źródła danych określa typ zmiennej zakresu.  
  
2. `select`Instrukcja zwraca `Name` właściwość zamiast kompletnego `Customer` obiektu. Ponieważ `Name` jest ciągiem, argument typu `custNameQuery` ma wartość, a `string` nie `Customer` .  
  
3. Ponieważ `custNameQuery` jest sekwencją ciągów, `foreach` Zmienna iteracji pętli musi być również `string` .  
  
 Na poniższej ilustracji przedstawiono nieco bardziej skomplikowaną transformację. `select`Instrukcja zwraca typ anonimowy, który przechwytuje tylko dwa elementy członkowskie oryginalnego `Customer` obiektu.  
  
 ![Diagram przedstawiający bardziej złożone zapytania, które przekształcają typ danych.](./media/type-relationships-in-linq-query-operations/linq-complex-query-transform-data-type.png)  
  
1. Argument typu źródła danych jest zawsze typem zmiennej zakresu w zapytaniu.  
  
2. Ponieważ `select` instrukcja generuje typ anonimowy, zmienna zapytania musi być wpisana niejawnie przy użyciu `var` .  
  
3. Ponieważ typ zmiennej zapytania jest niejawny, Zmienna iteracji w `foreach` pętli musi być również niejawna.  
  
## <a name="letting-the-compiler-infer-type-information"></a>Zezwalanie na informacje o typie wnioskowania kompilatora  
 Chociaż należy zrozumieć relacje typu w operacji zapytania, masz możliwość zezwalania kompilatorowi na wykonywanie wszystkich zadań. [Var](../../../language-reference/keywords/var.md) słowa kluczowego może być używana dla każdej zmiennej lokalnej w operacji zapytania. Poniższa ilustracja jest podobna do przykładu numer 2, który został omówiony wcześniej. Jednak kompilator dostarcza mocny typ dla każdej zmiennej w operacji zapytania.  
  
 ![Diagram przedstawiający przepływ typu z niejawnym wpisywaniem.](./media/type-relationships-in-linq-query-operations/linq-type-flow-implicit-typing.png)  
  
 Aby uzyskać więcej informacji na temat `var` , zobacz [niejawnie wpisane zmienne lokalne](../../classes-and-structs/implicitly-typed-local-variables.md).  
