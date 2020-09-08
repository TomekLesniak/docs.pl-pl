---
title: Serializacja przy użyciu deklaracji XML — LINQ to XML
description: Można kontrolować, czy deklaracja XML jest generowana podczas serializacji XML w języku C# lub Visual Basic.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: c237fa4a-a042-40fd-886f-17b54c66bb75
ms.openlocfilehash: 8d25d199b149ac6aeb2aa37dc248523e79847220
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89552957"
---
# <a name="serialize-with-an-xml-declaration-linq-to-xml"></a>Serializacja przy użyciu deklaracji XML (LINQ to XML)

W tym artykule opisano sposób kontrolowania, czy deklaracja XML jest generowana podczas serializacji kodu XML w języku C# lub Visual Basic.

Serializacja do metody lub metody, <xref:System.IO.File> <xref:System.IO.TextWriter> <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType> lub <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType> Metoda generuje deklarację XML. Podczas serializacji do <xref:System.Xml.XmlWriter> , ustawienia składnika zapisywania (określone w <xref:System.Xml.XmlWriterSettings> obiekcie) określają, czy jest generowana deklaracja XML.

W przypadku serializacji do ciągu przy użyciu `ToString` metody, otrzymany kod XML nie będzie zawierał deklaracji XML.

## <a name="example-serialize-with-an-xml-declaration"></a>Przykład: serializacji z deklaracją XML

Poniższy przykład tworzy <xref:System.Xml.Linq.XElement> , zapisuje dokument do pliku, a następnie drukuje plik do konsoli programu:

```csharp
XElement root = new XElement("Root",
    new XElement("Child", "child content")
);
root.Save("Root.xml");
string str = File.ReadAllText("Root.xml");
Console.WriteLine(str);
```

```vb
Dim root As XElement = <Root>
                           <Child>child content</Child>
                       </Root>
root.Save("Root.xml")
Dim str As String = File.ReadAllText("Root.xml")
Console.WriteLine(str)
```

Ten przykład generuje następujące wyniki:

```xml
<?xml version="1.0" encoding="utf-8"?>
<Root>
  <Child>child content</Child>
</Root>
```

## <a name="example-serialize-without-an-xml-declaration"></a>Przykład: serializacja bez deklaracji XML

Poniższy przykład pokazuje, jak zapisać element <xref:System.Xml.Linq.XElement> w <xref:System.Xml.XmlWriter> .

```csharp
StringBuilder sb = new StringBuilder();
XmlWriterSettings xws = new XmlWriterSettings();
xws.OmitXmlDeclaration = true;

using (XmlWriter xw = XmlWriter.Create(sb, xws)) {
    XElement root = new XElement("Root",
        new XElement("Child", "child content")
    );
    root.Save(xw);
}
Console.WriteLine(sb.ToString());
```

```vb
Dim sb As StringBuilder = New StringBuilder()
Dim xws As XmlWriterSettings = New XmlWriterSettings()
xws.OmitXmlDeclaration = True

Using xw As XmlWriter = XmlWriter.Create(sb, xws)
    Dim root = <Root>
                   <Child>child content</Child>
               </Root>
    root.Save(xw)
End Using
Console.WriteLine(sb.ToString())
```

Ten przykład generuje następujące wyniki:

```xml
<Root><Child>child content</Child></Root>
```
