---
title: Jak utworzyć drzewo na podstawie elementu XmlReader LINQ to XML
description: Można użyć elementu XmlReader w języku C# lub Visual Basic, aby odczytać XML i utworzyć drzewo XML. Musisz prawidłowo umieścić element XmlReader w węźle elementu.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 60951c9c-7087-406c-b5bb-c60e58609b21
ms.openlocfilehash: 659135ae9930d4ba63b13e436ebd278807e4256b
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553200"
---
# <a name="how-to-create-a-tree-from-an-xmlreader-linq-to-xml"></a>Jak utworzyć drzewo na podstawie elementu XmlReader (LINQ to XML)

W tym artykule pokazano, jak utworzyć drzewo XML bezpośrednio z poziomu <xref:System.Xml.XmlReader> języka C# lub Visual Basic. Aby utworzyć obiekt <xref:System.Xml.Linq.XElement> z poziomu <xref:System.Xml.XmlReader> , należy umieścić <xref:System.Xml.XmlReader> w węźle elementu. <xref:System.Xml.XmlReader>Program pominie Komentarze i instrukcje przetwarzania, ale jeśli <xref:System.Xml.XmlReader> jest umieszczony w węźle tekstowym, zostanie wygenerowany błąd. Aby uniknąć takich błędów, umieść <xref:System.Xml.XmlReader> element na elemencie przed utworzeniem drzewa XML z <xref:System.Xml.XmlReader> .

## <a name="example-load-xelement-object-from-an-xmlreader-object"></a>Przykład: Załaduj obiekt XElement z obiektu XmlReader

Ten przykład używa przykładowego [pliku XML dokumentu XML: Books](sample-xml-file-books.md).

Poniższy kod tworzy <xref:System.Xml.XmlReader> obiekt, odczytuje węzły do momentu znalezienia pierwszego węzła elementu i ładuje <xref:System.Xml.Linq.XElement> obiekt.

```csharp
XmlReader r = XmlReader.Create("books.xml");
while (r.NodeType != XmlNodeType.Element)
    r.Read();
XElement e = XElement.Load(r);
Console.WriteLine(e);
```

```vb
Dim r As XmlReader = XmlReader.Create("books.xml")
Do While r.NodeType <> XmlNodeType.Element
    r.Read()
Loop
Dim e As XElement = XElement.Load(r)
Console.WriteLine(e)
```

Ten przykład generuje następujące wyniki:

```xml
<Catalog>
   <Book id="bk101">
      <Author>Garghentini, Davide</Author>
      <Title>XML Developer's Guide</Title>
      <Genre>Computer</Genre>
      <Price>44.95</Price>
      <PublishDate>2000-10-01</PublishDate>
      <Description>An in-depth look at creating applications
      with XML.</Description>
   </Book>
   <Book id="bk102">
      <Author>Garcia, Debra</Author>
      <Title>Midnight Rain</Title>
      <Genre>Fantasy</Genre>
      <Price>5.95</Price>
      <PublishDate>2000-12-16</PublishDate>
      <Description>A former architect battles corporate zombies,
      an evil sorceress, and her own childhood to become queen
      of the world.</Description>
   </Book>
</Catalog>
```

## <a name="see-also"></a>Zobacz też

- [Analiza kodu XML](parse-string.md)
