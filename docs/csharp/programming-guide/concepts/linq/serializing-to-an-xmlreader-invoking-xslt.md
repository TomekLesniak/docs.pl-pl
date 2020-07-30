---
title: Serializowanie do elementu XmlReader (wywoływanie XSLT) (C#)
description: Dowiedz się, w jaki sposób używać metody do tworzenia elementu XmlReader w języku C#. Moduł odczytywany z tego elementu XmlReader odczytuje węzły z drzewa XML i przetwarza je.
ms.date: 07/20/2015
ms.assetid: 4cc3ee03-ef4c-429b-a408-fedd10b728cd
ms.openlocfilehash: aa5a232c74c5314cb7f1cf03c2a8875ca1cd04df
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302415"
---
# <a name="serializing-to-an-xmlreader-invoking-xslt-c"></a>Serializowanie do elementu XmlReader (wywoływanie XSLT) (C#)
W przypadku korzystania z <xref:System.Xml?displayProperty=nameWithType> funkcji współdziałania programu [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] można użyć programu <xref:System.Xml.Linq.XNode.CreateReader%2A> do utworzenia <xref:System.Xml.XmlReader> . Moduł odczytujący z tego <xref:System.Xml.XmlReader> odczytuje węzły z drzewa XML i przetwarza je odpowiednio.  
  
## <a name="invoking-an-xslt-transformation"></a>Wywoływanie transformacji XSLT  
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
  
 Ten przykład generuje następujące wyniki:  
  
```xml  
<Root>  
  <C1>Child1 data</C1>  
  <C2>Child2 data</C2>  
</Root>  
```  
  
## <a name="see-also"></a>Zobacz też

- [Serializowanie drzew XML (C#)](serializing-to-files-textwriters-and-xmlwriters.md)
