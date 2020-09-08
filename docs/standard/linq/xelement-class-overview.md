---
title: XElement, Klasa — Omówienie
description: Klasa XElement reprezentuje elementy XML. Można jej użyć do tworzenia i zmieniania elementów, dodawania atrybutów i elementów podrzędnych oraz do serializacji.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 2b9f0cd8-a1d1-4037-accf-0f38a410fa11
ms.openlocfilehash: 325afd09661532fe44aecf89fe9784520274638e
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553128"
---
# <a name="xelement-class-overview"></a>XElement, Klasa — Omówienie

<xref:System.Xml.Linq.XElement>Klasa jest jedną z podstawowych klas w LINQ to XML. Reprezentuje element XML. Na poniższej liście przedstawiono, co można użyć w tej klasie:

- Utwórz elementy.
- Zmień zawartość elementu.
- Dodawanie, zmienianie lub usuwanie elementów podrzędnych.
- Dodaj atrybuty do elementu.
- Serializacja zawartości elementu w postaci tekstu.

Możesz również współpracować z innymi klasami w <xref:System.Xml?displayProperty=nameWithType> , takich jak <xref:System.Xml.XmlReader> , <xref:System.Xml.XmlWriter> , i <xref:System.Xml.Xsl.XslCompiledTransform> .

W tym artykule opisano funkcje dostarczone przez <xref:System.Xml.Linq.XElement> klasę.

## <a name="construct-xml-trees"></a>Konstruowanie drzew XML

Drzewa XML można konstruować na różne sposoby, w tym następujące:

- Drzewo XML można skonstruować w kodzie. Aby uzyskać więcej informacji, zobacz [drzewa XML](functional-construction.md).
- Można analizować XML z różnych źródeł, w tym <xref:System.IO.TextReader> plików tekstowych lub adresów sieci Web (URL). Aby uzyskać więcej informacji, zobacz [Analizowanie XML](parse-string.md).
- <xref:System.Xml.XmlReader>Aby wypełnić drzewo, można użyć elementu. Aby uzyskać więcej informacji, zobacz <xref:System.Xml.Linq.XNode.ReadFrom%2A>.
- Jeśli masz moduł, który może zapisywać zawartość w <xref:System.Xml.XmlWriter> programie, możesz użyć <xref:System.Xml.Linq.XContainer.CreateWriter%2A> metody do utworzenia składnika zapisywania, przekazania składnika zapisywania do modułu, a następnie użyć zawartości zapisanej w programie w <xref:System.Xml.XmlWriter> celu wypełnienia drzewa XML.

Poniższy przykład tworzy drzewo. Wersja języka C# używa zagnieżdżonych operacji tworzenia elementów. Możesz użyć tej samej techniki w Visual Basic, ale w tym przykładzie użyto literałów XML.

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

```vb
Dim contacts As XElement = _
    <Contacts>
        <Contact>
            <Name>Patrick Hines</Name>
            <Phone>206-555-0144</Phone>
            <Address>
                <Street1>123 Main St</Street1>
                <City>Mercer Island</City>
                <State>WA</State>
                <Postal>68042</Postal>
            </Address>
        </Contact>
    </Contacts>
```

Można również użyć zapytania LINQ to XML, aby wypełnić drzewo XML, jak pokazano w następującym przykładzie:

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
            Where el.Value > 2 _
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

## <a name="serialize-xml-trees"></a>Serializowanie drzew XML

Można serializować drzewo XML do <xref:System.IO.File> , a <xref:System.IO.TextWriter> lub <xref:System.Xml.XmlWriter> .

Aby uzyskać więcej informacji, zobacz [Serializowanie drzew XML](preserve-white-space-serializing.md).

## <a name="retrieve-xml-data-via-axis-methods"></a>Pobieranie danych XML za pomocą metod osi

Możesz użyć metod osi do pobierania atrybutów, elementów podrzędnych, elementów podrzędnych i elementów nadrzędnych. LINQ to XML zapytania działają na podstawie metod osi i zapewniają kilka elastycznych i wydajnych sposobów nawigowania i przetwarzania drzewa XML.

Aby uzyskać więcej informacji, zobacz [LINQ to XML osi — Omówienie](linq-xml-axes-overview.md).

## <a name="query-xml-trees"></a>Tworzenie zapytań dotyczących drzew XML

Można pisać LINQ to XML zapytań, które wyodrębniają dane z drzewa XML.

Aby uzyskać więcej informacji, zobacz temat [Omówienie drzew XML dla zapytań](query-xml-trees-overview.md).

## <a name="modify-xml-trees"></a>Modyfikowanie drzew XML

Można modyfikować element na różne sposoby, w tym zmieniać jego zawartość lub atrybuty. Można również usunąć element z jego elementu nadrzędnego.

Aby uzyskać więcej informacji, zobacz [Modyfikowanie drzew XML](in-memory-xml-tree-modification-vs-functional-construction.md).

## <a name="see-also"></a>Zobacz też

- [Omówienie programowania LINQ to XML](functional-vs-procedural-programming.md)
