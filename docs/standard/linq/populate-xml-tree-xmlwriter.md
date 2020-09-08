---
title: Jak wypełnić drzewo XML elementem XmlWriter LINQ to XML
description: Aby wypełnić drzewo XML w języku C# i Visual Basic, Utwórz element XMLWriter przy użyciu funkcji tworzenia i zapisu do elementu XmlWriter.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: cd5674d1-5c54-4efc-ba68-e23b2875295f
ms.openlocfilehash: 3f8005eca009ae5f2102444a5494336d2caa2450
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553456"
---
# <a name="how-to-populate-an-xml-tree-with-an-xmlwriter-linq-to-xml"></a>Wypełnianie drzewa XML elementem XmlWriter (LINQ to XML)

Jednym ze sposobów wypełnienia drzewa XML jest użycie <xref:System.Xml.Linq.XContainer.CreateWriter%2A> do utworzenia <xref:System.Xml.XmlWriter> , a następnie zapisanie w <xref:System.Xml.XmlWriter> . Drzewo XML jest wypełniane wszystkimi węzłami, które są zapisywane w <xref:System.Xml.XmlWriter> .

Ta metoda jest zwykle używana w przypadku używania LINQ to XML z inną klasą, która oczekuje na zapis w, na przykład <xref:System.Xml.XmlWriter> <xref:System.Xml.Xsl.XslCompiledTransform> .

## <a name="example-create-an-xmlwriter-to-accept-the-output-of-an-xslt-transformation"></a>Przykład: Tworzenie elementu XmlWriter do akceptowania danych wyjściowych transformacji XSLT

Za pomocą programu można <xref:System.Xml.Linq.XContainer.CreateWriter%2A> utworzyć element, <xref:System.Xml.XmlWriter> Aby akceptować dane wyjściowe transformacji XSLT. Jest to pokazane w poniższym przykładzie, który wykonuje następujące czynności:

- Tworzy drzewo XML i <xref:System.Xml.XmlReader> do odczytu z niego.
- Tworzy nowe drzewo i zapisuje w <xref:System.Xml.XmlWriter> nim.
- Wywołuje transformację XSLT, dostarczając ją z  <xref:System.Xml.XmlReader> i <xref:System.Xml.XmlWriter> .

Przekształcenie wypełnia następnie nowe drzewo.

```csharp
string xslMarkup = @"<?xml version='1.0'?>
<xsl:stylesheet xmlns:xsl='http://www.w3.org/1999/XSL/Transform' version='1.0'>
    <xsl:template match='/Parent'>
        <Root>
            <C1>
            <xsl:value-of select='Child1'/>
            </C1>
            <C2>
            <xsl:value-of select='Child2'/>
            </C2>
        </Root>
    </xsl:template>
</xsl:stylesheet>";

XDocument xmlTree = new XDocument(
    new XElement("Parent",
        new XElement("Child1", "Child1 data"),
        new XElement("Child2", "Child2 data")
    )
);

XDocument newTree = new XDocument();
using (XmlWriter writer = newTree.CreateWriter())
{
    // Load the style sheet.
    XslCompiledTransform xslt = new XslCompiledTransform();
    xslt.Load(XmlReader.Create(new StringReader(xslMarkup)));

    // Execute the transformation and output the results to a writer.
    xslt.Transform(xmlTree.CreateReader(), writer);
}

Console.WriteLine(newTree);
```

```vb
Dim xslMarkup As XDocument = _
    <?xml version='1.0'?>
    <xsl:stylesheet xmlns:xsl='http://www.w3.org/1999/XSL/Transform' version='1.0'>
        <xsl:template match='/Parent'>
            <Root>
                <C1>
                    <xsl:value-of select='Child1'/>
                </C1>
                <C2>
                    <xsl:value-of select='Child2'/>
                </C2>
            </Root>
        </xsl:template>
    </xsl:stylesheet>

Dim xmlTree As XDocument = _
    <?xml version='1.0'?>
    <Parent>
        <Child1>Child1 data</Child1>
        <Child2>Child2 data</Child2>
    </Parent>

Dim newTree As XDocument = New XDocument()
Using writer As XmlWriter = newTree.CreateWriter()
    ' Load the style sheet.
    Dim xslt As XslCompiledTransform = New XslCompiledTransform()
    xslt.Load(xslMarkup.CreateReader())

    ' Execute the transformation and output the results to a writer.
    xslt.Transform(xmlTree.CreateReader(), writer)
End Using

Console.WriteLine(newTree)
```

Ten przykład generuje następujące wyniki:

```xml
<Root>
  <C1>Child1 data</C1>
  <C2>Child2 data</C2>
</Root>
```

## <a name="see-also"></a>Zobacz też

- <xref:System.Xml.Linq.XContainer.CreateWriter%2A>
- <xref:System.Xml.XmlWriter>
- <xref:System.Xml.Xsl.XslCompiledTransform>
- [Drzewa XML](functional-construction.md)
