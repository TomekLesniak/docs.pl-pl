---
title: Serializacja do elementu XmlReader (Invoke XSLT) — LINQ to XML
description: Za pomocą elementu "Reader" można utworzyć element XmlReader, który zawiera węzły drzewa XML do transformacji XSLT.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 4cc3ee03-ef4c-429b-a408-fedd10b728cd
ms.openlocfilehash: e079627b5fe114438feabaa1a49f42a65afedf43
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553065"
---
# <a name="serialize-to-an-xmlreader-invoke-xslt-linq-to-xml"></a>Serializacja do elementu XmlReader (Invoke XSLT) (LINQ to XML)

Korzystając z <xref:System.Xml?displayProperty=nameWithType> funkcji współdziałania LINQ to XML, można użyć programu <xref:System.Xml.Linq.XNode.CreateReader%2A> do utworzenia <xref:System.Xml.XmlReader> . Moduł odczytujący z tego <xref:System.Xml.XmlReader> odczytuje węzły z drzewa XML i przetwarza je odpowiednio.

## <a name="example-invoke-an-xslt-transformation"></a>Przykład: Wywołaj transformację XSLT

Jedynym możliwym zastosowaniem tej metody jest wywoływanie transformacji XSLT. Można utworzyć drzewo XML, utworzyć obiekt <xref:System.Xml.XmlReader> z drzewa XML, utworzyć nowy dokument, a następnie utworzyć <xref:System.Xml.XmlWriter> do zapisu w nowym dokumencie. Następnie można wywołać transformację XSLT, przekazując <xref:System.Xml.XmlReader> i <xref:System.Xml.XmlWriter> . Po pomyślnym zakończeniu przekształcenia nowe drzewo XML zostanie wypełnione wynikami transformacji.

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
using (XmlWriter writer = newTree.CreateWriter()) {
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
