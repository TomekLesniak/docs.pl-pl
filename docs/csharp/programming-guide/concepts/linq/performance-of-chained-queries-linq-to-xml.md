---
title: Wydajność zapytań łańcuchowych (LINQ to XML) (C#)
description: Dowiedz się więcej o wydajności zapytań łańcucha. Zapytanie łańcuchowe jest kwerendą, która używa innego zapytania jako źródła.
ms.date: 07/20/2015
ms.assetid: b2f1d715-8946-4dc0-8d56-fb3d1bba54a6
ms.openlocfilehash: 1e9173e85845dd085f4d7bf6deec7eb498acd7f3
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302857"
---
# <a name="performance-of-chained-queries-linq-to-xml-c"></a>Wydajność zapytań łańcuchowych (LINQ to XML) (C#)

Jedną z najważniejszych zalet LINQ (i LINQ to XML) jest to, że kwerendy łańcuchowe mogą wykonywać, a także pojedyncze, bardziej skomplikowane zapytania.

Zapytanie łańcuchowe jest kwerendą, która używa innego zapytania jako źródła. Na przykład, w poniższym prostym kodzie, `query2` ma `query1` jako Źródło:

```csharp
XElement root = new XElement("Root",
    new XElement("Child", 1),
    new XElement("Child", 2),
    new XElement("Child", 3),
    new XElement("Child", 4)
);

var query1 = from x in root.Elements("Child")
             where (int)x >= 3
             select x;

var query2 = from e in query1
             where (int)e % 2 == 0
             select e;

foreach (var i in query2)
    Console.WriteLine("{0}", (int)i);
```

Ten przykład generuje następujące wyniki:

```output
4
```

To zapytanie łańcuchowe zapewnia ten sam profil wydajności co iteracja w połączonej liście.

- <xref:System.Xml.Linq.XContainer.Elements%2A>Oś ma zasadniczo taką samą wydajność jak iteracja w połączonej liście. <xref:System.Xml.Linq.XContainer.Elements%2A>jest zaimplementowany jako iterator z odroczonym wykonaniem. Oznacza to, że wykonuje kilka zadań oprócz iteracji przez połączoną listę, na przykład przydzielanie obiektu iteratora i śledzenie stanu wykonywania. Ta czynność może zostać podzielona na dwie kategorie: pracy, która jest wykonywana w chwili, gdy iterator jest skonfigurowany, i pracy, która jest wykonywana podczas każdej iteracji. Konfiguracja pracy jest małą, stałą ilością pracy i pracy wykonywanej podczas każdej iteracji jest proporcjonalna do liczby elementów w kolekcji źródłowej.

- W programie `query1` `where` klauzula powoduje wywołanie <xref:System.Linq.Enumerable.Where%2A> metody. Ta metoda jest również zaimplementowana jako iterator. Konfiguracja zadań składa się z tworzenia wystąpienia delegata, który będzie odwoływać się do wyrażenia lambda oraz normalnej konfiguracji iteratora. Dla każdej iteracji delegat jest wywoływany, aby wykonać predykat. Konfiguracja pracy i pracy wykonanej podczas każdej iteracji jest podobna do wykonanej pracy podczas iteracji na osi.

- W programie `query1` klauzula SELECT powoduje, że zapytanie wywołuje <xref:System.Linq.Enumerable.Select%2A> metodę. Ta metoda ma ten sam profil wydajności co <xref:System.Linq.Enumerable.Where%2A> Metoda.

- W programie `query2` obie `where` klauzule i `select` klauzula mają taki sam profil wydajności jak w `query1` .

Iteracja w programie `query2` jest w związku z tym bezpośrednio proporcjonalna do liczby elementów w źródle pierwszego zapytania, czyli czasu liniowego. Odpowiadający przykład Visual Basic będzie miał ten sam profil wydajności.

Aby uzyskać więcej informacji na temat iteratorów, zobacz [Yield](../../../language-reference/keywords/yield.md).

Aby zapoznać się z bardziej szczegółowym samouczkiem dotyczącym łączenia zapytań, zobacz [Samouczek: Łączenie łańcuchowe zapytań](./deferred-execution-and-lazy-evaluation-in-linq-to-xml.md).
