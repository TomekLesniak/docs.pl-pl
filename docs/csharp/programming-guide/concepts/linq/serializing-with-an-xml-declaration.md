---
title: Serializacja przy użyciu deklaracji XML (C#)
description: Informacje o konfiguracjach, w których Serializacja w języku C# generuje deklarację XML, łącznie z serializowaniem do pliku, TextWriter i XmlWriter.
ms.date: 07/20/2015
ms.assetid: c237fa4a-a042-40fd-886f-17b54c66bb75
ms.openlocfilehash: 7e91b61f037d28149f7c2355f4233dc319b54627
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302363"
---
# <a name="serializing-with-an-xml-declaration-c"></a>Serializacja przy użyciu deklaracji XML (C#)
W tym temacie opisano sposób kontrolowania, czy Serializacja generuje deklarację XML.  
  
## <a name="xml-declaration-generation"></a>Generowanie deklaracji XML  
 Serializacja do metody lub metody, <xref:System.IO.File> <xref:System.IO.TextWriter> <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType> lub <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType> Metoda generuje deklarację XML. Podczas serializacji do <xref:System.Xml.XmlWriter> , ustawienia składnika zapisywania (określone w <xref:System.Xml.XmlWriterSettings> obiekcie) określają, czy deklaracja XML jest generowana, czy nie.  
  
 W przypadku serializacji do ciągu przy użyciu `ToString` metody, otrzymany kod XML nie będzie zawierał deklaracji XML.  
  
### <a name="serializing-with-an-xml-declaration"></a>Serializowanie przy użyciu deklaracji XML  
 Poniższy przykład tworzy <xref:System.Xml.Linq.XElement> , zapisuje dokument do pliku, a następnie drukuje plik do konsoli programu:  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("Child", "child content")  
);  
root.Save("Root.xml");  
string str = File.ReadAllText("Root.xml");  
Console.WriteLine(str);  
```  
  
 Ten przykład generuje następujące wyniki:  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<Root>  
  <Child>child content</Child>  
</Root>  
```  
  
### <a name="serializing-without-an-xml-declaration"></a>Serializacja bez deklaracji XML  
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
  
 Ten przykład generuje następujące wyniki:  
  
```xml  
<Root><Child>child content</Child></Root>  
```  
  
## <a name="see-also"></a>Zobacz też

- [Serializowanie drzew XML (C#)](serializing-to-files-textwriters-and-xmlwriters.md)
