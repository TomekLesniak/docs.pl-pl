---
title: Konstrukcja funkcjonalna — LINQ to XML
description: LINQ to XML zapewnia konstrukcję funkcjonalną, która umożliwia tworzenie drzewa XML w pojedynczej instrukcji.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 57a82bcf-de03-4f1c-a0c8-9a76e989d542
ms.openlocfilehash: bcdc153d7f60cfb165dcb741d62b6af5c07a148a
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553098"
---
# <a name="functional-construction-linq-to-xml"></a>Konstrukcja funkcjonalna (LINQ to XML)

LINQ to XML zapewnia zaawansowany sposób tworzenia elementów XML o nazwie *konstrukcja funkcjonalna*. Konstrukcja funkcjonalna umożliwia utworzenie drzewa XML w pojedynczej instrukcji.

Kilka najważniejszych funkcji interfejsu programowania LINQ to XML są używane w konstrukcji funkcjonalnej:

- <xref:System.Xml.Linq.XElement>Konstruktor ma różne typy argumentów dla zawartości. Na przykład można przekazać inny <xref:System.Xml.Linq.XElement> obiekt, który stanie się elementem podrzędnym. Można przekazać <xref:System.Xml.Linq.XAttribute> obiekt, który stanie się atrybutem elementu. Lub można przekazać każdy inny typ obiektu, który jest konwertowany na ciąg i stanie się zawartością tekstową elementu.
- <xref:System.Xml.Linq.XElement>Konstruktor pobiera `params` tablicę typu <xref:System.Object> , dzięki czemu można przekazać dowolną liczbę obiektów do konstruktora. Dzięki temu można utworzyć element, który ma złożoną zawartość.
- Jeśli obiekt implementuje <xref:System.Collections.Generic.IEnumerable%601> , kolekcja w obiekcie jest wyliczana i dodawane są wszystkie elementy w kolekcji. Jeśli kolekcja zawiera <xref:System.Xml.Linq.XElement> obiekty lub <xref:System.Xml.Linq.XAttribute> , każdy element w kolekcji zostanie dodany osobno. Jest to ważne, ponieważ umożliwia przekazywanie wyników zapytania LINQ do konstruktora.

## <a name="example-create-an-xml-tree"></a>Przykład: Tworzenie drzewa XML

Można użyć konstrukcji funkcjonalnej, aby napisać kod w celu utworzenia drzewa XML. Poniżej przedstawiono przykład:

```csharp
XElement contacts =
    new XElement("Contacts",
        new XElement("Contact",
            new XElement("Name", "Patrick Hines"),
            new XElement("Phone", "206-555-0144"),
            new XElement("Address",
                new XElement("Street1", "123 Main St"),
                new XElement("City", "Mercer Island"),
                new XElement("State", "WA"),
                new XElement("Postal", "68042")
            )
        )
    );
```

## <a name="example-create-an-xml-tree-using-linq-query-results"></a>Przykład: Tworzenie drzewa XML przy użyciu wyników zapytania LINQ

Te funkcje umożliwiają również pisanie kodu, który używa wyników zapytań LINQ podczas tworzenia drzewa XML, jak w poniższym przykładzie:

```csharp
XElement srcTree = new XElement("Root",
    new XElement("Element", 1),
    new XElement("Element", 2),
    new XElement("Element", 3),
    new XElement("Element", 4),
    new XElement("Element", 5)
);
XElement xmlTree = new XElement("Root",
    new XElement("Child", 1),
    new XElement("Child", 2),
    from el in srcTree.Elements()
    where (int)el > 2
    select el
);
Console.WriteLine(xmlTree);
```

W Visual Basic ten sam element jest realizowany za pomocą literałów XML:

```vb
Dim srcTree As XElement = _
    <Root>
        <Element>1</Element>
        <Element>2</Element>
        <Element>3</Element>
        <Element>4</Element>
        <Element>5</Element>
    </Root>
Dim xmlTree As XElement = _
    <Root>
        <Child>1</Child>
        <Child>2</Child>
        <%= From el In srcTree.Elements() _
            Where CInt(el) > 2 _
            Select el %>
    </Root>
Console.WriteLine(xmlTree)
```

Ten przykład generuje następujące wyniki:

```xml
<Root>
  <Child>1</Child>
  <Child>2</Child>
  <Element>3</Element>
  <Element>4</Element>
  <Element>5</Element>
</Root>
```

## <a name="see-also"></a>Zobacz też

- [Tworzenie drzew XML w języku C #](create-xml-trees.md)
- [Literały XML w Visual Basic](xml-literals.md)
