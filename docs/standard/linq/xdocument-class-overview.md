---
title: Klasa XDocument — Omówienie
description: Klasa LINQ to XML XDocument zawiera informacje niezbędne do prawidłowego dokumentu XML. W wielu przypadkach nie potrzebujesz funkcji obiektu XDocument i zamiast tego można użyć obiektu XElement.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 63305603-ab54-49fc-84e4-f76eecc59549
ms.openlocfilehash: c26b7ac42733aad24d831f4a0a181e0fd8275eaf
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89552924"
---
# <a name="xdocument-class-overview"></a>Klasa XDocument — Omówienie

<xref:System.Xml.Linq.XDocument>Klasa zawiera informacje niezbędne do prawidłowego dokumentu XML, który zawiera deklarację XML, instrukcje przetwarzania i komentarze.

Tylko wtedy, <xref:System.Xml.Linq.XDocument> gdy wymagane są konkretne funkcje dostarczone przez klasę, należy utworzyć obiekty <xref:System.Xml.Linq.XDocument> . W wielu przypadkach można bezpośrednio korzystać z programu <xref:System.Xml.Linq.XElement> . Praca bezpośrednio z programem <xref:System.Xml.Linq.XElement> to prostszy model programowania.

<xref:System.Xml.Linq.XDocument> pochodzi z <xref:System.Xml.Linq.XContainer> , więc może zawierać węzły podrzędne. Jednak <xref:System.Xml.Linq.XDocument> obiekty mogą mieć tylko jeden węzeł podrzędny <xref:System.Xml.Linq.XElement> . Odzwierciedla to standard XML, że w dokumencie XML może istnieć tylko jeden element główny.

## <a name="components-of-xdocument"></a>Składniki klasy XDocument

<xref:System.Xml.Linq.XDocument>Może zawierać następujące elementy:

- Jeden <xref:System.Xml.Linq.XDeclaration> obiekt. <xref:System.Xml.Linq.XDeclaration> umożliwia określenie odpowiednich części deklaracji XML: wersji XML, kodowania dokumentu oraz tego, czy dokument XML jest autonomiczny.
- Jeden <xref:System.Xml.Linq.XElement> obiekt. Ten obiekt jest węzłem głównym dokumentu XML.
- Dowolna liczba <xref:System.Xml.Linq.XProcessingInstruction> obiektów. Instrukcja przetwarzania komunikuje informacje z aplikacją, która przetwarza kod XML.
- Dowolna liczba <xref:System.Xml.Linq.XComment> obiektów. Komentarze będą elementy równorzędne z elementem głównym. <xref:System.Xml.Linq.XComment>Obiekt nie może być pierwszym argumentem na liście, ponieważ nie jest on prawidłowy dla dokumentu XML, aby można było zacząć od komentarza.
- Jeden <xref:System.Xml.Linq.XDocumentType> dla DTD.

W przypadku serializacji elementu <xref:System.Xml.Linq.XDocument> , nawet jeśli `XDocument.Declaration` jest `null` , wynik będzie miał deklarację XML, jeśli moduł zapisujący ma `Writer.Settings.OmitXmlDeclaration` ustawioną wartość `false` (wartość domyślna).

Domyślnie program LINQ to XML ustawia wersję na "1,0" i ustawia kodowanie na "UTF-8".

## <a name="use-xelement-without-xdocument"></a>Użyj XElement bez metody XDocument

Jak wspomniano wcześniej, <xref:System.Xml.Linq.XElement> Klasa jest klasą główną w interfejsie programowania LINQ to XML. W wielu przypadkach aplikacja nie będzie wymagać tworzenia dokumentu. Korzystając z <xref:System.Xml.Linq.XElement> klasy, można:

- Utwórz drzewo XML.
- Dodaj do niego inne drzewa XML.
- Zmodyfikuj drzewo XML.
- Zapisz go.

## <a name="use-xdocument"></a>Użyj metody XDocument

Aby utworzyć obiekt <xref:System.Xml.Linq.XDocument> , użyj konstrukcji funkcjonalnej, tak jak w przypadku konstruowania <xref:System.Xml.Linq.XElement> obiektów.

Poniższy przykład tworzy <xref:System.Xml.Linq.XDocument> obiekt i powiązane z nim obiekty zawarte.

```csharp
XDocument d = new XDocument(
    new XComment("This is a comment."),
    new XProcessingInstruction("xml-stylesheet",
        "href='mystyle.css' title='Compact' type='text/css'"),
    new XElement("Pubs",
        new XElement("Book",
            new XElement("Title", "Artifacts of Roman Civilization"),
            new XElement("Author", "Moreno, Jordao")
        ),
        new XElement("Book",
            new XElement("Title", "Midieval Tools and Implements"),
            new XElement("Author", "Gazit, Inbar")
        )
    ),
    new XComment("This is another comment.")
);
d.Declaration = new XDeclaration("1.0", "utf-8", "true");
Console.WriteLine(d);

d.Save("test.xml");
```

```vb
Dim doc As XDocument = <?xml version="1.0" encoding="utf-8"?>
                       <!--This is a comment.-->
                       <?xml-stylesheet href='mystyle.css' title='Compact' type='text/css'?>
                       <Pubs>
                           <Book>
                               <Title>Artifacts of Roman Civilization</Title>
                               <Author>Moreno, Jordao</Author>
                           </Book>
                           <Book>
                               <Title>Midieval Tools and Implements</Title>
                               <Author>Gazit, Inbar</Author>
                           </Book>
                       </Pubs>
                       <!--This is another comment.-->
doc.Save("test.xml")
```

Przykład generuje dane wyjściowe w test.xml:

```xml
<?xml version="1.0" encoding="utf-8"?>
<!--This is a comment.-->
<?xml-stylesheet href='mystyle.css' title='Compact' type='text/css'?>
<Pubs>
  <Book>
    <Title>Artifacts of Roman Civilization</Title>
    <Author>Moreno, Jordao</Author>
  </Book>
  <Book>
    <Title>Midieval Tools and Implements</Title>
    <Author>Gazit, Inbar</Author>
  </Book>
</Pubs>
<!--This is another comment.-->
```

## <a name="see-also"></a>Zobacz też

- [Przegląd LINQ to XML](linq-xml-overview.md)
